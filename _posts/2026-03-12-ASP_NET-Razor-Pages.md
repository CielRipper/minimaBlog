---
layout: post
title: "ASP.NET Razor Pages"
date: 2026-03-12
author: 
 - Jaxon Treadwell
---

In this lab, I worked through the ASP.NET Razor Pages tutorial to learn how to build a dynamic web application connected to a database. The tutorial walked through building a small movie database application where users can create, view, edit, and delete movie entries. After completing the tutorial example, I then created my own version of the application using a different topic.

The tutorial introduced the basic structure of an ASP.NET Razor Pages application, including how pages are organized, how models represent data, and how Entity Framework connects the application to a database. Once the project was set up, the application could run locally and be accessed through a browser.

---

## Completing the tutorial

The first part of the lab followed the official Razor Pages tutorial. This involved creating a Movie model, setting up the database context, and configuring the application to use SQLite. After installing the required packages and setting up Entity Framework, I used the scaffolding tools to automatically generate the pages needed to manage the movie data.

The scaffolding process created several pages automatically:

- **Index** – displays all movies in the database
- **Create** – allows adding a new movie
- **Edit** – allows updating an existing movie
- **Details** – shows information about a single movie
- **Delete** – removes a movie from the database

Once the migrations were run and the database was created, I was able to open the application locally and interact with the Movie database through the browser.

---

## Creating my own application

After finishing the tutorial version, I created my own application using a different domain. Instead of movies, I built a simple **music playlist tracker**. The model I created stores information about songs that might appear in a playlist.

The fields in my model include:

- **Title** – the name of the song
- **Album** – the album the song appears on
- **Artist / Band** – the artist or group that created the song
- **Genre** – the genre of the song
- **Song Length** – the length of the song
- **Playlist Order** – the order the song appears in the playlist

Using the same scaffolding command used in the tutorial, Razor automatically generated a full set of pages to manage songs. This allowed me to create, edit, view, and delete songs from the playlist through the web interface.

---

## Easiest parts of the tutorial

The easiest part of the tutorial was working with the scaffolding tools. Once the model and database context were set up, a single command generated all of the necessary pages for interacting with the data. This saved a lot of time and made it much easier to understand how Razor Pages organizes the application structure.

Running the application locally and interacting with the database through the browser was also very straightforward once the setup was complete.

---

## Confusing parts of the tutorial

The most confusing part of the tutorial was the initial setup and configuration. Installing the correct packages, configuring the database context, and making sure the project structure was correct took some time to figure out. Several commands produced errors until the correct dependencies were installed.

Understanding how the different pieces fit together (models, database context, migrations, and scaffolding) was also a little confusing at first, but it became clearer after the application started working.

---

## Translating the tutorial to my own application

Translating the tutorial to my own application was fairly straightforward once I understood the structure. The main change was creating a new model for songs instead of movies. After defining the fields for the Song model, I used the same scaffolding process to generate a new set of pages.

This demonstrated how the Razor Pages framework can be reused to quickly create new applications that manage different types of data.

---

## Differences between Jekyll and Razor Pages

There are several differences between Jekyll and Razor Pages. Jekyll is a static site generator that creates pages from markdown files and templates. It is ideal for blogs and simple websites because it produces static HTML files.

Razor Pages, on the other hand, is a dynamic web framework. Instead of generating static pages ahead of time, Razor Pages can interact with databases and generate content dynamically when the user requests it. This allows applications to support features like user input, database updates, and interactive forms.

---

## Confidence moving forward

After completing this lab, I feel more confident working with ASP.NET and Razor Pages. While the setup process was initially confusing, the overall structure of the framework makes sense once everything is configured correctly. The scaffolding tools and database integration make it possible to quickly build applications that interact with structured data.

This lab showed how Razor Pages can be used to build full web applications rather than static websites, which makes it a powerful tool for building interactive systems.

---

## GitHub Repository

Link to my repository for this project:

[Link](https://github.com/CielRipper/cielripper.github.io/tree/main/csci340lab8/RazorPagesMovie)