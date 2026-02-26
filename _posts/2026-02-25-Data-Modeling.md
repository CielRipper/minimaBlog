---
layout: post
title: "Data Modeling"
date: 2026-02-25
author: 
 - Jaxon Treadwell
---

In this lab, I converted a written scenario for an online grocery ordering system into a structured data model. I started by writing user stories, then built an Entity-Relationship Diagram (ERD) to represent the conceptual model, and finally sketched the relational schema (tables, primary keys, and foreign keys) using Redgate.

This was my first time doing full data modeling from a scenario, and building the ERD + schema helped me understand how entities, attributes, and relationships fit together (especially how many-to-many relationships are handled).

---

## Assumptions I made

To translate the scenario into a model, I made these assumptions:

- A customer must register before placing an order.
- One customer can place many orders, but each order belongs to exactly one customer.
- An order can contain many items, and each item can appear in many different orders.
- Because Orders and Items form a many-to-many relationship, I used an associative entity (**OrderItem**) to store item-specific details for each order.
- Each item has exactly one manufacturer, and each manufacturer can produce many items.
- Once an order is finalized, it can no longer be modified. I represent this using a `status` field (ex: `open` vs `finalized`).

---

## User stories

Below are five user stories based on the scenario. I estimated sizes using a simple 1–8 scale (bigger number = more work/complexity) and noted dependencies between stories.

### 1) Customer registration
**As a customer, I want to create an account using my name, address, and phone number so that I can place grocery orders.**  
**Size:** 3  
**Connections:** Required before creating an order.

### 2) Store owner manages inventory items
**As the store owner, I want to add and update grocery items with a name, price, description, quantity available, and manufacturer so customers can shop online.**  
**Size:** 5  
**Connections:** Needed before customers can add items to orders.

### 3) Customer starts an order
**As a customer, I want to start an order for pickup or delivery so that I can choose how I receive my groceries.**  
**Size:** 5  
**Connections:** Depends on registration (Story 1).

### 4) Customer adds items to an order (line items)
**As a customer, I want to select items and specify quantity, special instructions, and whether substitutions are allowed so that my order is accurate.**  
**Size:** 8  
**Connections:** Depends on having an order (Story 3) and having items available (Story 2). This is where the OrderItem entity matters.

### 5) Customer finalizes order with a fulfillment time
**As a customer, I want to choose a date and time for fulfillment when I finalize my order so that I know when to pick it up or receive delivery.**  
**Size:** 3  
**Connections:** Depends on order creation (Story 3) and adding items (Story 4). Finalizing also locks the order from edits.

---

## Entity-Relationship Diagram (LucidChart)

Here is the ER diagram I created in LucidChart:

![Lab 6 ER Diagram]({{ '/assets/images/lab6-erd.png' | relative_url }})

### How the ER diagram is structured

The core entities are:

- **Customer**
- **Orders**
- **Item**
- **Manufacturer**
- **OrderItem** (associative entity / line items)

The key relationships are:

- **Customer (1) -> Orders (many)**  
  One customer can place many orders.

- **Orders (1) -> OrderItem (many)**  
  One order can contain many line items.

- **Item (1) -> OrderItem (many)**  
  An item can appear in many line items across many orders.

- **Manufacturer (1) -> Item (many)**  
  One manufacturer can produce many items.

The biggest design decision was resolving the many-to-many relationship between Orders and Items. The **OrderItem** entity stores the item-specific order details (quantity, instructions, substitution) that would not make sense as attributes of Orders or Items alone.

---

## Relational Schema (Redgate)

Here is the relational schema exported from Redgate:

![Lab 6 Schema]({{ '/assets/images/lab6-schema.png' | relative_url }})

### Primary keys and foreign keys

Each table has a primary key, and foreign key columns represent the relationships:

- `Orders.customer_id` -> `Customer.customer_id`
- `OrderItems.order_id` -> `Orders.order_id`
- `OrderItems.item_id` -> `Item.item_id`
- `Item.manufacturer_id` -> `Manufacturer.manufacturer_id`

These FK columns directly match the relationships shown in the ER diagram.

---

## Are you satisfied with the representation?

Yes. The model is clean, normalized, and scalable. Separating **Orders** from **OrderItem** allows the schema to represent item-level details (quantity, substitutions, instructions) without duplicating data or forcing awkward columns into the wrong entity.

This structure would also support realistic queries like:

- all orders for a customer
- all items inside an order
- checking item inventory levels
- listing all items by manufacturer

---

## Complications I could run into implementing this

Some real-world complications that could show up in implementation include:

- **Inventory race conditions:** multiple users ordering the last units of an item at the same time.
- **Substitutions:** the system needs business logic to decide what “substitution allowed” means (similar items? same brand? same category?).
- **Finalization locking:** preventing edits after finalization needs to be enforced both in the UI and in backend logic.
- **Pickup vs delivery differences:** delivery might eventually require extra attributes (delivery instructions, driver assignment, etc.).

---

## What I learned

This lab helped me understand how to identify entities vs attributes and how to correctly model relationships. The biggest takeaway was learning how many-to-many relationships are handled using an associative entity (OrderItem), and how to decide whether a piece of data belongs to the order as a whole or to a specific item within the order.