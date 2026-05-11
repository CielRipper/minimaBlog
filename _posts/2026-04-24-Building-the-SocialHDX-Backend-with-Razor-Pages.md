---
layout: post
title: "Building the SocialHDX Backend with Razor Pages"
date: 2026-04-24
author:
 - Jaxon Treadwell
---

As development on the SocialHDX project continued, my work became more focused on implementing the backend functionality of the application using ASP.NET Razor Pages and Entity Framework Core.

During this stage of the project, I worked on connecting the database models to functional web pages, improving usability, and making the application workflow function more realistically.

---

## Expanding the backend system

Once the database schema was planned, I began working on implementing CRUD functionality for the major entities in the project.

This included backend pages for:

- Students
- Campus Events
- Prescribers
- Prescriptions
- Student Cases
- Student Case Notes

Each section needed to support creating, viewing, editing, and deleting records directly through the web application.

A major goal during this phase was making sure the entities properly connected together throughout the application.

For example:

- Prescriptions needed to connect students, prescribers, and campus events
- Student cases needed to connect to students and prescribers
- Case notes needed to connect back to specific student cases

This created a more realistic workflow where information could move throughout the system instead of existing in isolated tables.

---

## Working with Razor Pages and Entity Framework

One of the most important parts of this phase was learning how Razor Pages interact with the Entity Framework database context.

As the project became larger, I became more comfortable with:

- database contexts,
- migrations,
- model relationships,
- page models,
- and loading related data.

I also spent a large amount of time debugging issues related to missing references, incorrect context names, and relationship problems between entities.

Several backend pages originally used automatically scaffolded layouts, so another part of development involved cleaning up labels and reorganizing pages so they made more sense for the project itself.

---

## Improving dashboard usability

Another major focus during this stage was improving the usability of the backend dashboard.

Originally, many backend pages felt disconnected and difficult to navigate. I worked on reorganizing navigation and creating a dashboard that made important actions easier to access.

Some of the improvements included:

- Adding better navigation links
- Improving button visibility
- Creating easier access to CRUD pages
- Cleaning up labels and page names
- Removing unnecessary pages
- Making the backend feel more unified

This helped transition the project from a collection of scaffolded pages into a more usable application prototype.

---

## Challenges during development

The most difficult part of this stage was balancing functionality and usability at the same time.

The database itself could function correctly while still being confusing to use. Because of this, development involved both backend debugging and interface cleanup simultaneously.

Some common problems included:

- Foreign key relationship issues
- Missing database context references
- Build errors after model updates
- Null reference warnings
- Mismatched labels after schema changes
- Navigation inconsistencies between pages

As the application became larger, debugging became more difficult because changes in one area could affect multiple connected pages.

---

## Lessons learned

This phase of the project helped me better understand how larger full-stack web applications are structured.

Compared to earlier labs, this project required thinking about:

- backend architecture,
- workflow organization,
- database relationships,
- usability,
- and long-term maintainability.

I also gained more confidence working with Razor Pages as a framework for combining frontend design with backend database functionality.

---

## GitHub Repository

Repository for the project:

[SocialHDX Repository](https://github.com/CielRipper/SocialHDX)