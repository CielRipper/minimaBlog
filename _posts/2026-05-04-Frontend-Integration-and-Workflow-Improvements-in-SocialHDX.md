---
layout: post
title: "Frontend Integration and Workflow Improvements in SocialHDX"
date: 2026-05-04
author:
 - Jaxon Treadwell
---

As the SocialHDX project moved closer to the final presentation stage, a major focus became improving the usability and visual consistency of the application.

Earlier in development, the project contained a mixture of static frontend prototype pages and scaffolded backend Razor Pages. During this phase, I worked on integrating these systems together and making the backend application feel more like a complete and connected website.

---

## Moving from prototypes to a connected application

At the start of development, many of the frontend pages existed primarily as static HTML prototypes. These pages helped establish the visual style and user workflow of the application, but they were not directly connected to the backend database.

As development progressed, I worked on migrating many of these frontend ideas into the Razor Pages backend so the application could support real database functionality.

This included integrating:

- Dashboard layouts
- Navigation structure
- Card-based UI sections
- Workflow navigation
- Search and filtering systems

The goal was to make the final application feel like one connected system instead of separate frontend and backend projects.

---

## Improving page usability and layout

One major issue during development was that the default scaffolded Razor Pages looked inconsistent and difficult to navigate.

To improve this, I worked on redesigning several backend pages using a more modern card-based layout.

Pages updated during this stage included:

- Campus Events
- Prescriptions
- Students
- Prescribers
- Student Cases
- Student Case Notes

The updated layouts made information easier to read and helped create a more polished presentation for the final prototype.

Additional interface improvements included:

- Unified navigation bars
- Improved dashboard organization
- Better button visibility
- More consistent page titles
- Easier access to common actions

---

## Improving workflows between entities

Another major focus during this phase was improving how users move throughout the system.

Instead of simply viewing isolated pages, the workflow now supports actions such as:

- Viewing campus events
- Assigning an event to a student
- Creating a prescription
- Viewing saved prescriptions
- Tracking cases and notes
- Returning to the dashboard to view updated information

This created a more realistic simulation of how a social prescribing platform might function in practice.

---

## Dashboard and data improvements

I also worked on improving the backend dashboard so it displayed meaningful database information instead of placeholder content.

The dashboard now includes:

- Student counts
- Event counts
- Prescription counts
- Open case counts
- Recent prescription activity
- Quick access actions

Adding realistic test data further improved the usability of the system and helped demonstrate the intended workflows during testing and presentation preparation.

---

## Challenges during integration

The most difficult part of this phase was connecting visual design improvements with backend functionality.

It was relatively easy to make pages look better visually, but ensuring they still worked correctly with database relationships and Razor Page routing required additional debugging.

Some of the more difficult areas included:

- Maintaining consistent navigation across pages
- Connecting frontend-inspired layouts to backend data
- Preserving CRUD functionality while redesigning pages
- Organizing workflows so the application felt cohesive

This phase required balancing technical backend functionality with presentation quality and usability.

---

## Reflection on the project progress

By the end of this phase, the application had evolved from a collection of disconnected pages into a much more unified prototype.

The project now supports:

- Connected database workflows
- Functional CRUD operations
- Event recommendation workflows
- Case and note tracking
- Unified navigation and styling
- Dashboard-driven management systems

Working on these integrations helped me better understand how frontend design and backend systems work together in larger web applications.

---

## GitHub Repository

Repository for the project:

[SocialHDX Repository](https://github.com/CielRipper/SocialHDX)