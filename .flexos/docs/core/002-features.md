---
id: features-mybalidogsimport
title: Core Features & User Stories
description: A detailed breakdown of the primary features of the MyBaliDogsImport platform, including priorities and associated user stories.
type: doc
subtype: core
status: draft
sequence: 2
tags:
  - features
  - user-stories
  - product
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

This document outlines the core features that will be developed for the MyBaliDogsImport platform. Each feature is prioritized and accompanied by user stories that illustrate its value from the perspective of our target users.

### P0 - Must-Have Features

These features form the essential backbone of the platform and are required for the initial launch.

#### 1. Dog Import Case Management (P0)
This is the foundational component of the system, acting as the central record for each dog undergoing the import process. It goes beyond a simple profile, serving as a comprehensive case file.
*   **Description:** Create and manage detailed profiles for each dog, including health records (vaccination history, deworming, rabies titer test results), microchip details, high-resolution photos, and personality/background notes. It will link a dog to its destination country, assigned adopter, and flight volunteer, creating a complete picture of the import case.
*   **User Stories:**
    *   As a rescue admin, I want to create a new import case for a rescued dog, detailing its background, medical history, and personality traits.
    *   As a rescue admin, I want to easily update a dog's vaccination status, attach scanned veterinary certificates, and log all medical treatments.
    *   As a volunteer, I want to view a dog's profile and its current import status to assist with coordination tasks like vet appointments or photo updates.

#### 2. Document & Compliance Automation (P0)
This feature is a key differentiator, actively guiding users through complex legal and health requirements to prevent costly errors.
*   **Description:** The system will automatically generate a dynamic, interactive checklist based on the dog's destination country. It will flag missing documents and upcoming deadlines (e.g., 'Rabies titer test must be drawn at least 30 days after vaccination'). It will also generate pre-filled international animal health certificates, import permits, and customs forms using data from the dog's profile, ready for official review and signature.
*   **User Stories:**
    *   As a rescue admin, I want the system to automatically flag missing documents and upcoming deadlines based on the dog's destination country's regulations.
    *   As a rescue admin, I want to generate a pre-filled Animal Health Certificate (AHC) for a dog going to Europe, ready for vet signature.
    *   As an adopter, I want to see a clear, personalized list of documents required from me (e.g., proof of address) and easily upload them securely.

#### 3. Secure Authentication & User Management (P0)
This ensures the security and integrity of the platform by controlling access to sensitive information.
*   **Description:** Provides secure login via email/password and social providers (Google). Implements robust role-based access control for three primary roles: `rescue_admin`, `adopter`, and `volunteer`. Admins can manage their organization's users, while adopters and volunteers can only see information pertinent to their specific cases.
*   **User Stories:**
    *   As a new user, I want to sign up securely with my email and a strong password.
    *   As a rescue admin, I want to manage user roles and permissions for my staff, granting or revoking access as needed.

### P1 - High-Priority Features

These features add significant value and are planned for the initial or a very near-subsequent release.

#### 4. Journey & Status Tracking (P1)
This feature provides crucial transparency and peace of mind for all stakeholders, especially adopters.
*   **Description:** A visual timeline on each Dog Import Case Detail page displays real-time status updates for the entire import journey. Milestones include 'Awaiting Titer Test', 'Permit Approved', 'Flight Booked', 'Departed Bali', and 'Arrived Safely'. Updates are pushed automatically and can also be manually triggered by admins.
*   **User Stories:**
    *   As an adopter, I want to see the real-time, visual progress of my adopted dog's import journey.
    *   As a rescue admin, I want to update a dog's journey status with a single click and add specific notes for internal or external viewing.

#### 5. Adopter & Flight Volunteer Matching (P1)
This feature streamlines the critical process of connecting dogs with homes and transport.
*   **Description:** Adopters can browse available dogs and submit detailed applications. Rescue admins can review these applications in a dedicated portal. Separately, volunteers can register their upcoming travel plans (e.g., Denpasar to Amsterdam, June 10-24), and the system will show them dogs needing transport along that route.
*   **User Stories:**
    *   As an adopter, I want to browse dogs available for international adoption and submit a comprehensive application.
    *   As a rescue admin, I want to easily match a dog needing transport to Berlin with a registered volunteer flying there next month.
    *   As a potential volunteer, I want to register my upcoming travel plans from Bali and see dogs that match my route.

#### 6. Notifications & Communication Hub (P1)
This centralizes communication, replacing fragmented email and messaging threads.
*   **Description:** Delivers automated in-app and email notifications for critical events (e.g., flight confirmation, document rejection). An integrated messaging system within each dog's case file allows for direct, context-aware communication between rescue staff, the adopter, and the volunteer.
*   **User Stories:**
    *   As an adopter, I want to receive an email notification when my dog's flight details are confirmed.
    *   As a rescue admin, I want to send a broadcast message to all stakeholders involved in a specific dog's import case directly from the platform.

#### 7. Account Settings & Preferences (P1)
Provides users with control over their personal information and platform experience.
*   **Description:** A standard settings page where users can manage their profile information (name, contact details), update security settings (password), and customize their notification preferences (e.g., opt-out of certain email alerts).
*   **User Stories:**
    *   As a user, I want to update my contact information easily within my account settings.
    *   As a user, I want to adjust which types of notifications I receive and whether they are in-app or email.