---
id: database-mybalidogsimport
title: Database Schema & Collections
description: Detailed specification of the Firebase Firestore collections, fields, and relationships for the MyBaliDogsImport platform.
type: doc
subtype: core
status: draft
sequence: 4
tags:
  - database
  - firestore
  - architecture
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

This document outlines the data architecture for MyBaliDogsImport, which will be implemented using Firebase Firestore. The schema is designed to be scalable, secure, and efficient for the platform's core functionalities.

### Core Collections

**1. `users`**
This collection stores all user accounts, regardless of their role. It is the central point for authentication and user-specific data.
*   **Description:** Contains authentication details and profile information for rescue admins, adopters, and volunteers.
*   **Fields:**
    *   `id` (string, doc ID): Firebase Auth UID.
    *   `email` (string): User's primary email.
    *   `role` (enum: 'rescue_admin', 'adopter', 'volunteer'): Defines user permissions.
    *   `profile_data` (object): Contains role-specific data such as `displayName`, `phoneNumber`, and a reference `organization_id` for `rescue_admin` users.
    *   `created_at` / `updated_at` (timestamp): Standard timestamps.

**2. `organizations`**
Stores information about the rescue organizations using the platform.
*   **Description:** Each rescue organization gets a single document in this collection.
*   **Fields:**
    *   `id` (string, doc ID): Unique identifier.
    *   `name` (string): The official name of the rescue.
    *   `contact_email` (email): Primary contact email.
    *   `logo_url` (string): URL for the organization's logo.
    *   `description` (string): Mission statement or brief description.

**3. `dogs`**
This collection is the master record for every dog entered into the system.
*   **Description:** Contains all static information about a dog, from its physical description to its medical history.
*   **Fields:**
    *   `id` (string, doc ID): Unique identifier.
    *   `name` (string): Dog's name.
    *   `main_image_url` (string): URL for the primary photo.
    *   `microchip_number` (string): Unique microchip ID.
    *   `rabies_vac_date` (date): Date of the last rabies vaccination (critical for compliance).
    *   `health_status_notes` (string): General health and temperament notes.
    *   `organization_id` (reference to `organizations`): The managing rescue.
    *   `adopter_id` (reference to `users`): The assigned adopter (if any).
    *   `flight_volunteer_id` (reference to `users`): The assigned volunteer (if any).

**4. `import_cases`**
This collection tracks the dynamic journey of a dog's import process. It is the heart of the operational workflow.
*   **Description:** Each dog has one active import case, which tracks its progress, status, and destination-specific details.
*   **Fields:**
    *   `id` (string, doc ID): Unique identifier.
    *   `dog_id` (reference to `dogs`): The dog associated with this case.
    *   `organization_id` (reference to `organizations`): The managing rescue.
    *   `destination_country` (string, e.g., 'USA', 'DEU'): The target country.
    *   `current_status` (enum: 'pending', 'in_progress', 'flight_booked', 'completed'): The current high-level status.
    *   `status_history` (array of objects): A log of all status changes, each with `status`, `timestamp`, and `notes`. This builds the Journey Timeline.
    *   `flight_details` (object): Contains flight number, departure/arrival dates and times.

**5. `documents`**
This collection stores metadata for all uploaded files, linking them to the relevant dog or import case.
*   **Description:** Manages all compliance-related files like vet certificates, permits, and adopter IDs. The actual files are stored in Firebase Storage.
*   **Fields:**
    *   `id` (string, doc ID): Unique identifier.
    *   `file_url` (string): Secure URL to the file in Firebase Storage.
    *   `document_type` (string, e.g., 'Rabies Certificate', 'Import Permit'): Categorizes the document.
    *   `uploaded_by_user_id` (reference to `users`): Who uploaded the file.
    *   `import_case_id` (reference to `import_cases`): Links the document to a specific journey.
    *   `status` (enum: 'pending_review', 'approved', 'rejected'): Tracks the review status.

**6. `applications`**
Stores adoption applications submitted by users.
*   **Description:** Manages the adopter vetting process.
*   **Fields:**
    *   `id` (string, doc ID): Unique identifier.
    *   `applicant_user_id` (reference to `users`): The prospective adopter.
    *   `dog_id` (reference to `dogs`): The dog being applied for.
    *   `application_status` (enum: 'submitted', 'under_review', 'approved', 'rejected'): The current status of the application.
    *   `application_data` (object): A JSON object containing all the user's answers to the application questions.
    *   `reviewed_by_user_id` (reference to `users`): The admin who reviewed it.

### Relationships and Data Integrity
*   **User-Organization:** A `rescue_admin` in the `users` collection is linked to an `organizations` document via an `organization_id` field.
*   **Dog-Case:** A dog's static data is in `dogs`, while its journey is in `import_cases`. They are linked via `dog_id`. This separation prevents the `dogs` document from becoming bloated with status updates.
*   **Case-Documents:** All documents are linked to an `import_case_id`, keeping all compliance files for a single journey neatly organized.
*   **Security Rules:** Firestore Security Rules will be heavily utilized to enforce role-based access. For example, an 'adopter' role can only read data from the `import_cases` where their `user.uid` matches the `adopter_id` field. Admins can only access documents belonging to their own `organization_id`.