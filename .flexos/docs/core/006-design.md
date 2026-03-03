---
id: design-mybalidogsimport
title: Design System & Vibe
description: Defines the visual identity, color palette, typography, and overall user experience principles for the MyBaliDogsImport platform.
type: doc
subtype: core
status: draft
sequence: 6
tags:
  - design
  - ui
  - ux
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

This document outlines the design principles and visual identity for MyBaliDogsImport. The goal is to create a user interface that is not only aesthetically pleasing but also builds trust, reduces user anxiety, and facilitates efficient task completion.

### 1. Vibe & Experience Principles

The overall vibe of the platform should be **Efficient, Trustworthy, and Hopeful**.

*   **Efficient:** The primary users (rescue admins) are busy and often stressed. The UI must be clean, uncluttered, and task-oriented. Workflows should be intuitive, minimizing clicks and cognitive load. Forms should be well-structured, and data should be easy to find and parse.
*   **Trustworthy:** The process of international adoption involves significant emotional and financial investment. The design must project professionalism, security, and reliability. This means consistent branding, clear language, predictable interface patterns, and transparent status indicators. Users must feel confident that their data and the dog's critical journey are in safe hands.
*   **Hopeful:** While the platform deals with serious logistics, its ultimate purpose is joyful: uniting a rescued dog with a loving family. The design should reflect this hope. This can be achieved through high-quality photography of the dogs, celebratory animations for completed milestones, and a bright, optimistic color palette.

### 2. Color Palette

The color scheme is designed to be modern, clean, and accessible, using a primary color that evokes both the tropical setting of Bali and a sense of calm competence.

*   **Primary Color (`#06b6d4` - Cyan):** This will be used for primary calls-to-action, active navigation elements, links, and key highlights. It's a vibrant yet professional color that inspires confidence.
*   **Accent Color (`#fcd34d` - Amber):** This warm, friendly color will be used for secondary actions, highlights, and informational alerts. It provides a hopeful contrast to the primary cyan.
*   **Neutral Dark (`#1f2937` - Slate):** Used for all primary text, headings, and dark UI elements. It provides excellent readability and a modern, grounded feel.
*   **Neutral Light (`#f9fafb` - Gray):** The primary background color for most of the application. It's a soft, off-white that is easy on the eyes and provides a clean canvas for content.
*   **Feedback Colors:**
    *   **Success (Green):** For success messages, 'Approved' statuses, and completed milestones.
    *   **Warning (Orange/Amber):** For pending items, upcoming deadlines, or non-critical alerts.
    *   **Error (Red):** For error messages, 'Rejected' statuses, and critical, attention-required items.

### 3. Typography

Typography will be clean, modern, and highly legible to ensure clarity across all devices.

*   **Font Family: Inter:** This sans-serif typeface is chosen for its excellent readability at all sizes, making it perfect for UI design. Its clean, neutral aesthetic aligns with our 'Efficient' and 'Trustworthy' principles.
*   **Hierarchy:**
    *   **Headings (h1, h2, h3):** Will use a heavier weight (e.g., Bold, Semi-Bold) to establish clear visual hierarchy on pages like the Dashboard and Case Detail.
    *   **Body Text:** Will use a regular weight for maximum readability in paragraphs and form labels.
    *   **UI Elements:** Buttons, tabs, and labels will use a medium or semi-bold weight to ensure they are distinct and easy to read.

### 4. Navigation & Layout

The application will utilize a persistent sidebar navigation pattern for authenticated users, providing consistent access to key areas of the platform.

*   **Layout:** A main content area with a maximum width will ensure readability on larger screens, while being fully responsive for mobile and tablet use. The layout will be based on a consistent grid system to maintain alignment and visual harmony.
*   **Navigation Pattern:** After login, a left-hand sidebar will contain links to 'Dashboard', 'Dog Cases', 'Applications', 'Volunteers', and 'Settings'. The currently active section will be highlighted using the primary color (`#06b6d4`). This pattern provides clear context and allows for easy movement between core tasks.
*   **Key Components:**
    *   **Cards:** Used extensively on the Dashboard and Dog List pages to present digestible chunks of information with a photo, status, and key details.
    *   **Tables:** Used for dense data displays like the Adopter Applications list, with robust sorting and filtering controls.
    *   **Forms:** Will feature clear labels, helpful placeholder text, and real-time validation to guide users and prevent errors.
    *   **Visual Timeline:** The Journey Tracker will be a prominent, graphical component on the Case Detail page, using icons and colors to clearly communicate progress.