---
id: page-dashboard
title: User Dashboard Page Specification
description: Specification for the personalized user dashboard, serving as the main entry point after login.
type: spec
subtype: page
status: draft
sequence: 200
tags: [ui, dashboard, main-page]
relatesTo: [secure-authentication-user-management, dog-import-case-management, journey-status-tracking]
createdAt: 2023-10-27T10:00:00Z
updatedAt: 2023-10-27T10:00:00Z
---
# User Dashboard Page Specification

The User Dashboard (`/dashboard`) is the central, personalized hub for all authenticated users of MyBaliDogsImport. It provides an immediate overview of relevant information and quick access to key functionalities based on the user's role (rescue admin, adopter, or flight volunteer). This page is designed to be highly efficient, reducing navigation time and ensuring users can quickly grasp their current status and upcoming tasks.

For **Rescue Administrators**, the dashboard displays critical metrics such as the number of dogs in transit, pending documents, and new adoption applications. It offers quick links to add a new dog, view all import cases, or manage applications. An activity feed keeps admins informed of recent status changes across all their managed cases. This ensures they have a bird's-eye view of their rescue operations.

**Adopters** will see a clear, visual representation of their adopted dog's journey progress, including completed milestones and estimated arrival dates. They can access their application status and any specific documents required from them. The dashboard serves as a transparent window into their dog's journey, fostering trust and excitement.

**Flight Volunteers** are presented with their registered travel plans, a list of dogs needing transport that match their route, and details for any assigned transport tasks. This allows them to manage their contributions effectively and stay informed about their upcoming volunteer commitments.

The dashboard integrates notifications, providing in-app alerts for critical updates, ensuring users are always aware of important changes or actions required. Its role-based design ensures that each user type receives the most pertinent information without being overwhelmed by irrelevant data, making it the primary gateway to the platform's powerful features.