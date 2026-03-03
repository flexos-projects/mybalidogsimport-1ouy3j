---
id: flows-mybalidogsimport
title: Key User Flows
description: A breakdown of the critical user journeys and interaction flows within the MyBaliDogsImport platform.
type: doc
subtype: core
status: draft
sequence: 5
tags:
  - user-flow
  - product
  - ux
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

This document describes the step-by-step processes for the most critical user interactions on the MyBaliDogsImport platform. Understanding these flows is essential for designing an intuitive and efficient user experience.

### 1. New Rescue Admin Onboarding & First Dog Case Setup
This flow is crucial for user activation and demonstrating the platform's core value immediately.

*   **Trigger:** A new rescue organization administrator signs up.
*   **Goal:** To guide the admin through setting up their organization and creating their first dog import case.
*   **Steps:**
    1.  **Create Account:** User navigates to the signup page, selects the 'Rescue Organization' role, and enters their email, password, and organization name.
    2.  **Complete Profile:** Upon first login, the system presents a modal or dedicated page prompting the admin to complete their organization's profile (e.g., contact info, logo).
    3.  **Dashboard Prompt:** The User Dashboard displays a welcome message and a prominent call-to-action, 'Create Your First Dog Import Case', guiding them to the `/dogs` page and clicking 'Add New Dog'.
    4.  **Enter Dog Details:** The admin fills out the dog's core profile in a structured form: name, photos, microchip number, breed, age, and health notes.
    5.  **Initiate Import Case:** After saving the dog's profile, the admin is prompted to 'Start Import Process'. They select the **Destination Country** (e.g., 'Canada').
    6.  **Review Compliance Checklist:** The system automatically navigates to the new Dog Import Case Detail page (`/dogs/:id`). On the 'Documents' tab, a dynamic checklist specific to Canada is displayed, showing all required documents and steps, ready for the admin to begin working.

### 2. Adopter Applies for a Dog and Tracks the Journey
This flow covers the entire adopter experience from discovery to arrival.

*   **Trigger:** An interested individual wants to adopt a dog from Bali.
*   **Goal:** To allow a user to find a dog, apply, and stay informed throughout the import process.
*   **Steps:**
    1.  **Discover Dog:** User browses a public gallery of available dogs (or is sent a direct link) and clicks on a dog's profile.
    2.  **Initiate Application:** On the dog's profile, the user clicks 'Apply to Adopt'.
    3.  **Authenticate:** The system prompts the user to log in or sign up. Upon successful authentication, they are redirected back to the application form.
    4.  **Complete Application:** The user fills out a comprehensive, multi-step form detailing their living situation, experience, and references.
    5.  **Submit & Wait:** The user submits the form. They receive a confirmation email, and their User Dashboard now shows the application with a status of 'Submitted'.
    6.  **Application Approved:** A rescue admin reviews and approves the application. The system sends an email notification to the adopter.
    7.  **Track Journey:** The adopter's User Dashboard now prominently features the 'Journey & Status Tracker' for their dog, showing the visual timeline of progress. They will receive further notifications as milestones like 'Flight Booked' are completed.

### 3. Updating a Dog's Journey Status
This is a frequent and critical flow for rescue admins to keep all stakeholders informed.

*   **Trigger:** A milestone in a dog's import process has been completed (e.g., a vet check).
*   **Goal:** To quickly and easily update the dog's status, which automatically notifies relevant parties.
*   **Steps:**
    1.  **Navigate to Case:** The rescue admin logs in and navigates to the specific Dog Import Case Detail page (`/dogs/:id`) from their dashboard or the main list.
    2.  **Interact with Timeline:** The admin clicks on the next incomplete milestone in the 'Journey Timeline' component, or clicks a general 'Update Status' button.
    3.  **Select New Status:** A modal appears with a dropdown of predefined, logical next statuses (e.g., 'Vet Check Completed', 'Permit Submitted').
    4.  **Add Contextual Notes:** The admin adds optional notes, such as 'All clear from the vet, titer test sample sent to lab today.'
    5.  **Confirm Update:** The admin clicks 'Save Update'.
    6.  **System Actions:** The platform instantly updates the visual timeline, adds the new entry to the `status_history` array in the `import_cases` collection, and sends automated email/in-app notifications to the assigned adopter and flight volunteer, including the admin's notes.

### 4. Volunteer Registers Travel & is Matched
This flow connects volunteers' travel plans with the rescue's transport needs.

*   **Trigger:** A user is traveling from Bali and wants to help transport a dog.
*   **Goal:** To register travel plans and be matched with a dog needing a flight companion.
*   **Steps:**
    1.  **Register:** The user signs up with the 'Volunteer' role and navigates to the Volunteer Portal (`/volunteers`).
    2.  **Add Travel Plans:** The volunteer clicks 'Add New Travel Plan' and enters their origin (pre-filled as Bali/DPS), destination city/airport (e.g., Seattle/SEA), and travel dates.
    3.  **View Matching Dogs:** The system saves the travel plan and automatically displays a list of dogs that are approved for travel and need transport to Seattle.
    4.  **Offer Help:** The volunteer reviews the matching dogs and clicks 'Offer to be Flight Companion' for a specific dog.
    5.  **Admin Notification:** The rescue admin receives a notification: 'Jane Doe has offered to be the flight companion for Fido on her upcoming trip to Seattle'.
    6.  **Confirmation:** The admin reviews the offer and, if suitable, formally assigns the volunteer to the dog's import case. The system then notifies the volunteer that they have been confirmed, and provides them with access to the dog's journey details and communication hub.