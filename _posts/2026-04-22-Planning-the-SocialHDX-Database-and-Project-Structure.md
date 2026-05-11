---
layout: post
title: "Planning the SocialHDX Database and Project Structure"
date: 2026-04-22
author:
 - Jaxon Treadwell
---

For our semester software engineering project, my team worked on a system called **SocialHDX**, which adapts the concept of social prescribing to a college campus environment. The idea behind the project is that trained professors or staff members can recommend campus events and activities to students in order to improve social connection and campus involvement.

My primary role during the early stages of the project focused on planning the backend structure, designing the database schema, and helping establish the overall workflow of the application.

---

## Initial project planning

One of the first major tasks was understanding the needs of the project and determining how information would move throughout the system.

The project needed to support several important workflows:

- Staff members need to browse and recommend events
- Students need to receive prescriptions for events
- Prescribers need to track participation and follow-up
- Cases and notes need to be stored over time
- Events need to be searchable and filterable

Because the project involved many connected pieces of information, the database structure became one of the most important parts of development.

---

## Designing the schema

During the planning phase, I spent time working on schema ideas and mapping out how the entities in the system would relate to each other.

The main entities included:

- **Students**
- **Prescribers**
- **Campus Events**
- **Prescriptions**
- **Student Cases**
- **Student Case Notes**

One of the most important parts of the schema design process was determining how these entities should connect.

For example:

- A student can receive multiple prescriptions
- A prescriber can assign multiple prescriptions
- A prescription links a student, prescriber, and event together
- Student cases can contain multiple notes over time

Thinking through these relationships helped create a more realistic application structure that could support future expansion.

---

## Preparing for presentations and client meetings

Another major part of the early project phase involved preparing materials for presentations and client discussions.

This included:

- Creating schema diagrams
- Explaining workflows
- Discussing user stories
- Determining which features were highest priority
- Planning how the system would function from a usability perspective

Some of the user stories we focused on included:

- Professors quickly assigning recommendations
- Filtering events by category and time
- Tracking whether students attended events
- Managing follow-up notes and cases

These discussions helped guide later backend implementation decisions.

---

## Challenges during the planning phase

One challenge during this stage was balancing realism with scope. There were many possible features we could add, but we needed to focus on building a functional prototype within the semester timeline.

Another challenge was organizing relationships between entities in a way that would remain manageable as the project became larger.

At this stage, a lot of the work involved thinking ahead about how the database structure would support later backend and frontend development.

---

## Lessons learned

Working on the planning and schema phase helped me better understand how important database structure is in larger applications.

Compared to smaller assignments earlier in the semester, this project required more attention to:

- relationships between tables,
- data flow,
- scalability,
- and workflow organization.

It also helped me better understand how backend structure affects nearly every other part of a web application.

---

## GitHub Repository

Repository for the project:

[SocialHDX Repository](https://github.com/CielRipper/SocialHDX)