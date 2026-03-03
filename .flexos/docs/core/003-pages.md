---
id: pages-mybalidogsimport
title: Page & Screen Architecture
description: An outline of the key pages and screens that make up the user interface of MyBaliDogsImport, detailing their purpose and components.
type: doc
subtype: core
status: draft
sequence: 3
tags:
  - architecture
  - ui
  - pages
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

This document details the primary pages and screens that form the user interface of the MyBaliDogsImport platform. Each page is designed to support the core user flows and features defined in other documentation.

### Public-Facing Pages (No Authentication Required)

**1. Landing Page (`/`)**
*   **Purpose:** To serve as the digital storefront for MyBaliDogsImport. It must clearly articulate the problem, our solution, and guide different user types (rescues, adopters, volunteers) to the next step.
*   **Sections:**
    *   **Hero:** A compelling image of a Bali dog with the tagline and clear calls-to-action like "For Rescues" and "Find a Dog".
    *   **How It Works:** A simplified, 3-step visual guide explaining the process.
    *   **Key Features:** Cards highlighting features like 'Compliance Automation', 'Journey Tracking', and 'Volunteer Matching'.
    *   **Testimonials:** Quotes from partner rescue organizations or successful adopters.
    *   **Call to Action:** A final prominent section encouraging user registration.

**2. Authentication Pages (`/auth/:type`)**
*   **Purpose:** To provide secure and straightforward user registration, login, and password recovery.
*   **Sections:**
    *   **Login (`/auth/login`):** A clean form for email and password entry, a 'Forgot Password?' link, and social login options (Google).
    *   **Sign-up (`/auth/signup`):** A form to create a new account, capturing name, email, password, and requiring role selection (Rescue, Adopter, or Volunteer) to tailor the onboarding experience.
    *   **Password Recovery (`/auth/reset-password`):** A simple interface to request a password reset link via email.

### Authenticated Pages (Login Required)

**3. User Dashboard (`/dashboard`)**
*   **Purpose:** To act as a personalized home base, presenting the most relevant information and actions based on the user's role.
*   **Sections (Role-Dependent):**
    *   **Rescue Admin:** Displays key stats ('Dogs In Progress', 'Pending Documents'), a list of active cases needing attention, and a quick-add button for a new dog.
    *   **Adopter:** Shows the status of their application, and if approved, the detailed journey tracker for their specific dog.
    *   **Volunteer:** Lists their registered travel plans and any dogs they have been matched with or assigned to transport.

**4. Dog Import Cases List (`/dogs`)**
*   **Purpose:** A powerful list view for rescue admins to manage all their active and archived dog import cases efficiently.
*   **Sections:**
    *   **Search & Filter:** Robust controls to filter dogs by status (e.g., 'Awaiting Titer Test'), destination country, assigned adopter, or name.
    *   **Case List:** A table or card view showing a dog's photo, name, current status, destination, and key dates. Each entry links to the detail page.
    *   **Primary Action:** A prominent 'Add New Dog Import Case' button.

**5. Dog Import Case Detail (`/dogs/:id`)**
*   **Purpose:** The single source of truth for one specific dog's import journey. This is the most complex and information-dense page.
*   **Sections:**
    *   **Header:** Displays the dog's name, primary photo, and current high-level status (e.g., 'Flight Booked').
    *   **Tabbed Navigation:** Information is organized into logical tabs:
        *   **Profile & Health:** All core details, medical history, microchip number, etc.
        *   **Documents:** The dynamic compliance checklist. Lists all required and uploaded documents, their status (pending, approved), and provides upload functionality.
        *   **Journey Timeline:** The interactive, visual timeline of all completed and upcoming milestones.
        *   **Communication:** An integrated message board for all stakeholders (admin, adopter, volunteer) related to this specific dog.

**6. Adopter Applications (`/applications`)**
*   **Purpose:** A dedicated workspace for rescue admins to manage the flow of incoming adoption requests.
*   **Sections:**
    *   **Application Queue:** A filterable list of all applications, showing applicant name, dog applied for, and status.
    *   **Detail View:** Clicking an application reveals all the applicant's submitted information and documents for review.
    *   **Action Buttons:** Clear buttons to 'Approve', 'Reject', or 'Request More Information' for each application.

**7. Volunteer Portal (`/volunteers`)**
*   **Purpose:** A hub for volunteers to manage their availability and assignments.
*   **Sections:**
    *   **My Travel Plans:** A list of the volunteer's registered flights, with options to add new trips or edit existing ones.
    *   **Matching Dogs:** A view of dogs that need transport on routes the volunteer is flying.
    *   **My Transports:** Details and instructions for any dogs the volunteer has been confirmed to escort.

**8. Account Settings (`/settings`)**
*   **Purpose:** Allows all user types to manage their personal account details.
*   **Sections:**
    *   **Profile:** Update name, contact information, and address.
    *   **Security:** Change password.
    *   **Notifications:** Toggle preferences for in-app and email alerts.