---
layout: post
title: "Data Modeling"
date: 2026-02-25
author: 
 - Jaxon Treadwell
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
