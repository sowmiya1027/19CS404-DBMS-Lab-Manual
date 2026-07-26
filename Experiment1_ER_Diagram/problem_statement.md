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
<img width="942" height="1302" alt="City Fitness Club Management drawio" src="https://github.com/user-attachments/assets/f0c278f5-f76d-486b-b172-ef6cb8947adb" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Member	 |MemberID (PK), Name, MembershipType, StartDate, PhoneNumber, Email	|Stores member information.
|Program |ProgramID (PK), ProgramName, Duration, Schedule	|Stores fitness program details.
|Trainer |TrainerID (PK), TrainerName, Specialization, PhoneNumber, Experience	|Stores trainer information.
|Personal_Session|	SessionID (PK), SessionDate, SessionTime	|Stores personal training session details.
|Attendance|	AttendanceID (PK), AttendanceDate, Status	|Stores attendance for each personal session.
|Payment	|PaymentID (PK), PaymentDate, Amount, PaymentMethod	|Stores membership and session payment details.

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Member RegistersJoins Program|	M : N |Tota|l	A member can join multiple programs, and each program can have multiple members.
|Trainer AssignedTo Program|	M : N	|Total|	A trainer can teach multiple programs, and a program can have multiple trainers.
|Member Books PersonalSession|	1 : M	|Partial|	A member may book multiple personal training sessions.
|Trainer Conducts PersonalSession|	1 : M	|Total|	A trainer can conduct many personal training sessions.
|PersonalSession Has Attendance|	1 : M	|Total|	Each session has attendance records.
|Member Makes Payment|	1 : M	|Total|	A member can make multiple payments for memberships and personal training sessions.
### Assumptions
- Each member, trainer, program, session, attendance, and payment has a unique ID.
- A member can join multiple fitness programs.
- A trainer can be assigned to multiple programs.
- A member can book multiple personal training sessions.
- Attendance is recorded for every personal training session.
- A member can make multiple payments for memberships and training sessions.

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
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

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
