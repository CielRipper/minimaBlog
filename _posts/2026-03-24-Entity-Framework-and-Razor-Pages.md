---
layout: post
title: "Entity Framework and Razor Pages"
date: 2026-03-24
author: 
 - Jaxon Treadwell
---

In this lab, I expanded on my understanding of ASP.NET Razor Pages by working with Entity Framework Core to build a more complex web application. Unlike the previous lab, which used a single table, this project involved multiple related tables and more advanced data handling.

The tutorial walked through building a university-style database application with students, courses, enrollments, and instructors. This introduced how relationships between tables are handled and how data can be queried and displayed across multiple entities.

---

## Completing the tutorial

The first part of the lab followed the Razor Pages with Entity Framework Core tutorial. This involved setting up a database with multiple tables and configuring relationships between them.

The main entities included:

- **Student**
- **Course**
- **Enrollment**
- **Instructor**
- **Department**

Using Entity Framework, I learned how these tables connect using relationships such as one-to-many and many-to-many. The application was able to display related data, such as which students are enrolled in which courses and their grades.

The application also supported full CRUD operations (create, read, update, delete) across these tables, which made it possible to manage the data through the web interface.

---

## Changes I made to the project

To go beyond the tutorial, I made several modifications:

- Renamed the application from **Contoso University** to **Hendrix College**
- Added an **Age** field to the Student model
- Added **I (Incomplete)** and **W (Withdraw)** options to the Grade enum
- Updated the Students page to allow sorting by **Age** in addition to Last Name and Enrollment Date

These changes required updating multiple parts of the project, including models, pages, and sorting logic. This helped reinforce how changes to the data model affect the entire application.

---

## Easiest parts of the lab

The easiest part of the lab was working with the structure of Razor Pages once everything was set up. Since the layout is consistent across pages, it was easy to follow how data flows from the model to the UI.

Adding new fields like Age was also straightforward once I understood how models and migrations work together.

---

## Confusing parts of the lab

The most confusing part of the lab was setting up and managing the database. Errors related to migrations, database creation, and missing tables made debugging more difficult.

Understanding when to use migrations and how the database is created required some trial and error. The interaction between the database, models, and initialization code was not immediately clear at first.

---

## Working with multiple tables

Working with multiple tables was more complex than the single-table setup in the previous lab. Instead of just storing simple data, I had to understand how tables relate to each other.

For example:
- A student can have multiple enrollments
- Each enrollment connects a student to a course
- Each enrollment also includes a grade

This required using navigation properties and including related data when querying the database. It made the application more powerful, but also more complicated to manage.

---

## Confidence moving forward

After completing this lab, I feel more prepared to work on a full team project. I now understand how to structure a database with multiple tables and how to connect that data to a web application.

Compared to the previous lab, this project was more realistic and closer to how real-world applications are built. While there were challenges with setup and debugging, the overall structure now makes much more sense.

---

## GitHub Repository

Link to my repository for this project:

[Link](https://github.com/CielRipper/cielripper.github.io/tree/main/csci340lab9/ContosoUniversity)