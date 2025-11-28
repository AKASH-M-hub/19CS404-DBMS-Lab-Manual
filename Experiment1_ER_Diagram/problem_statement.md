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
<img width="1029" height="973" alt="image" src="https://github.com/user-attachments/assets/fec3bd55-e649-4b19-bdd9-d582c3d55965" />


### Entities and Attributes

| Entity             | Attributes (PK, FK)                                            | Notes                               |
|--------------------|----------------------------------------------------------------|-------------------------------------|
|Member              |MemberID (PK), Name, MembershipType, StartDate	                |Gym member details                   |
|Program             |ProgramID (PK), ProgramName	                                    | Fitness program details             |
|Trainer             |TrainerID (PK), Name, Specialization	                          |Fitness trainer info                 |
|Session             |SessionID (PK), SessionDate, SessionTime, Status	              |Personal training session details    |
|Payment             |PaymentID (PK), MemberID (FK), Amount, PaymentDate, PaymentType |Financial transaction tracking       |
|Enrollment          |MemberID (FK, PK), ProgramID (FK, PK)	                          |Links members to programs            |
|ProgramAssignment	 |TrainerID (FK, PK), ProgramID (FK, PK)	                        |Links trainers to programs           |
|Booking             |MemberID (FK, PK), TrainerID (FK, PK), SessionID (FK, PK)	      |Links members, trainers, sessions    |

### Relationships and Constraints

| Relationship                       | Cardinality | Participation                                | Notes                                                               |
|------------------------------------|-------------|----------------------------------------------|---------------------------------------------------------------------|
|Member ENROLLS IN Program	         |M:N	         |Total (Enrollment), Partial (Member, Program)	|Members can join multiple programs; programs have multiple members.  |
|Trainer LEADS Program	             |M:N	         |Partial (Trainer), Total (Program)	          |Trainers lead multiple programs; programs have multiple trainers.    |
|Member BOOKS Session WITH Trainer	 |M:N	         |Partial (Member, Trainer), Total (Session)	  |Members book sessions with trainers; trainers conduct sessions.      |
|Member MAKES Payment		             |1:N	         |Total (Payment), Partial (Member)	            |Payments by a member; a member makes many payments.                  |

### Assumptions
- IDs are primary keys and unique.
- Junction tables resolve all M:N relationships.
- Session status covers attendance.

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
<img width="834" height="768" alt="image" src="https://github.com/user-attachments/assets/215e74fc-8bc9-4a6f-9a17-9d1352e2cada" />


### Entities and Attributes

| Entity        | Attributes (PK, FK)                                                    | Notes                          |
|--------       |------------------------------------------------------------------------|--------------------------------|
|Member	        |MemberID (PK), Name, Address, ContactInfo	                             |Library patron details          |
|Book           |BookID (PK), Title, Author, Category	                                   |Cataloged book details          |
|Loan	          |LoanID (PK), BookID (FK), MemberID (FK), LoanDate, ReturnDate, DueDate	 |Records book borrowing       |
|Fine	          |FineID (PK), LoanID (FK), Amount, PaymentDate, Status	                 |Tracks overdue penalties       |
|Event	        |EventID (PK), EventName, EventDate, EventTime	                         |Library cultural event info       |
|Speaker		    |SpeakerID (PK), Name, Bio	                                             |Details of event speakers/authors       |
|Room		        |RoomID (PK), RoomNumber, Capacity, Type	                               |Library room details (e.g., study)       |
|Registration   |MemberID (FK, PK), EventID (FK, PK), RegistrationDate	                 |Links members to events       |
|EventSpeaker   |EventID (FK, PK), SpeakerID (FK, PK)	                                   |Links events to speakers       |
|EventRoom		  |EventID (FK, PK), RoomID (FK, PK), BookingDate	                         |Links events to rooms used       |


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
