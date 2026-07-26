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
|Member	 |MemberID (PK), Name, MembershipType,Age, PhoneNumber	|Stores member information.
|Program |ProgramID (PK), ProgramName, Duration, Schedule	|Stores fitness program details.
|Trainer |TrainerID (PK), TrainerName, Specialization, PhoneNumber	|Stores trainer information.
|Personal_Session|	SessionID (PK), SessionDate, SessionTime	|Stores personal training session details.
|Attendance|	AttendanceID (PK), AttendanceDate, Status	|Stores attendance for each personal session.
|Payment	|PaymentID (PK), PaymentDate, Amount, PaymentType	|Stores session payment details.

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Member — Joins — Program|	M : N|	Member (mandatory), Program (mandatory)	|A member can join multiple programs, and each program can have multiple members.
|Program — Assigned To — Trainer|	M : N|	Program (mandatory), Trainer (mandatory)	|A program can have multiple trainers, and a trainer can be assigned to multiple programs.
|Trainer — Conducts — Personal Session|	1 : M|	Trainer (mandatory), Personal Session (mandatory)|	Each personal training session is conducted by one trainer, and a trainer can conduct many sessions.
|Member — Books — Personal Session|	1 : M|	Member (optional), Personal Session (mandatory)|	A member may book multiple personal training sessions, and each session is booked by one member.
|Personal Session — Has — Attendance|	1 : M|	Personal Session (mandatory), Attendance (mandatory)|	Each personal training session has one or more attendance records.
|Member — Makes — Payment|	1 : M|	Member (mandatory), Payment (mandatory)|	A member can make multiple payments for memberships and personal training sessions, and each payment belongs to one member.
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
<img width="1342" height="972" alt="City Library Event   Book Lending System drawio" src="https://github.com/user-attachments/assets/cb27f277-2052-4dfa-9981-e43a4ce8c88f" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Member|	MemberId(PK),	MemberName, Address, PhoneNo	|Stores library member details.
|Book	|BookId(PK),	Title, Author, Category	|Stores information about books available in the library.
|Loan|	LoanId(PK),	LoanDate, BookID, MemberID	|Stores loan information.
|Event|	EventId(PK),	EventName, EventDate	|Stores information about library events.
|Speaker|	SpeakerId(PK),	Name, Expertise	|Stores details of speakers or authors participating in events.
|Room|	RoomId(PK),	RoomName, Capacity	|Stores details of rooms used for events and study.
|Fine	|FineId(PK),	Amount, FineDate	|Stores overdue fine details for late book returns.

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Member — Borrows — Loan|	1 : M|	Member (mandatory), Loan (mandatory)	|A member can borrow multiple books over time, resulting in multiple loan records. Each loan belongs to one member.
|Loan — Includes — Book|	M : 1|	Loan (mandatory), Book (mandatory)	|Each loan record is for one book, while a book can appear in multiple loan records over time.
|Loan — Generates — Fine	|1 : 1|	Loan (optional), Fine (mandatory)	|A loan generates one fine only if the book is returned after the due date.
|Member — Registers — Event|	M : N|	Member (optional), Event (mandatory)	|Members can register for multiple events, and each event can have many registered members.
|Event — Has — Speaker	|1 : M|	Event (mandatory), Speaker (mandatory)	|Each event has one or more speakers, and each speaker is associated with one event.
|Room — Booked In — Event	|1 : M|	Room (optional), Event (mandatory)	|One room can be booked for multiple events at different times, but each event is held in one room.

### Assumptions
- Each member, book, loan, event, speaker, room, and fine has a unique ID.
- A member can borrow multiple books through different loan records.
- A fine is generated only for overdue loans.
- Each event is conducted in one room.
- A room can host multiple events at different times.
- Members can register for multiple events. 

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
