---
id: flow-admin-onboarding-first-dog
title: New Rescue Admin Onboarding & First Dog Case Setup Flow
description: Specification for the onboarding process for new rescue administrators, culminating in the creation of their first dog import case.
type: spec
subtype: flow
status: draft
sequence: 300
tags: [onboarding, admin, first-use]
relatesTo: [secure-authentication-user-management, dog-import-case-management, organizations]
createdAt: 2023-10-27T10:00:00Z
updatedAt: 2023-10-27T10:00:00Z
---
# New Rescue Admin Onboarding & First Dog Case Setup Flow

This flow outlines the critical initial experience for a new rescue organization administrator joining MyBaliDogsImport. The primary goal is to efficiently onboard the admin, gather essential organization details, and immediately guide them to create their first dog import case, thereby demonstrating the platform's core value proposition from the outset.

**Trigger:** A new rescue organization administrator successfully signs up for the platform.

**Steps:**

1.  **Create Account (Actor: User):** The user navigates to the signup page and inputs their email address, a secure password, and the initial name of their rescue organization. This establishes their user account and initial role as a 'rescue_admin'.

2.  **Complete Organization Profile (Actor: System):** Upon successful account creation, the system immediately prompts the user to complete essential details for their organization. This includes fields such as the organization's full legal name, primary contact information (email, phone), physical address, and a brief mission statement or description. This data is crucial for official documentation and platform functionality.

3.  **First Dog Prompt & Guidance (Actor: System):** After the organization profile is saved, the system displays a welcoming and encouraging message. This message highlights the next logical step: creating their first dog import case. A clear call to action, such as a prominent button labeled 