# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
<img width="858" height="873" alt="image" src="https://github.com/user-attachments/assets/91342699-8f0c-43aa-9b2c-025c1cb00ea3" />


### Entities and Attributes
| Entity     | Attributes (PK, FK)                                                             | Notes              |
| ---------- | ------------------------------------------------------------------------------- | ------------------ |
| USER       | USER\_ID (PK), USER\_NAME, USER\_EMAIL, USER\_ADD, USER\_MOBILE, LOGIN\_ID (FK) | User information   |
| LOGIN      | LOGIN\_ID (PK), LOGIN\_PASS, LOGIN\_ROLLPASS                                    | Login details      |
| ROLES      | ROLL\_ID (PK), ROLL\_NAME, ROLL\_DESC                                           | Role details       |
| BOOKING    | BOOK\_ID (PK), BOOK\_TYPE, BOOK\_DESC, ITEM\_ID (FK)                            | Booking details    |
| ITEMS      | ITEM\_ID (PK), ITEM\_TYPE, ITEM\_DESC, RES\_ID (FK)                             | Items offered      |
| RESTAURANT | RES\_ID (PK), RES\_NAME, RES\_TYPE                                              | Restaurant details |


### Relationships and Constraints
| Relationship               | Cardinality | Participation  | Notes                                                                       |
| -------------------------- | ----------- | -------------- | --------------------------------------------------------------------------- |
| USER – LOGIN               | 1:1         | Total on USER  | Each user must have one login                                               |
| USER – ROLES (HAS)         | M\:N        | Partial        | A user can have many roles, a role can be assigned to many users            |
| USER – RESTAURANT (MANAGE) | 1\:M        | Partial        | A user can manage multiple restaurants, each restaurant managed by one user |
| BOOKING – ITEMS (HAS)      | M\:N        | Partial        | A booking can contain many items, an item can be part of many bookings      |
| ITEMS – RESTAURANT         | M:1         | Total on ITEMS | Each item belongs to one restaurant, a restaurant can have many items       |


### Assumptions
- Each User must have exactly one Login – no user exists without login credentials.

- A Restaurant is managed by a single User, but a User can manage multiple Restaurants.

- Each Item belongs to exactly one Restaurant, but a Restaurant can have many Items.

- A Booking can include multiple Items, and an Item can appear in multiple Bookings (many-to-many relationship).
 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
