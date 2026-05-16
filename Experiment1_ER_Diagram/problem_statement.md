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

<img width="1175" height="786" alt="Screenshot 2026-05-16 112954" src="https://github.com/user-attachments/assets/58af9f8c-a464-40dc-a0c8-503d19fe2d99" />


### Entities and Attributes

| Entity          | Attributes (PK, FK)                                                   | Notes                                                        |
| --------------- | --------------------------------------------------------------------- | ------------------------------------------------------------ |
| Member          | **Member_ID (PK)**, Name, Membership_Type, Start_Date, Phone          | Stores details of gym members                                |
| Trainer         | **Trainer_ID (PK)**, Name, Specialization, Experience, Phone          | Stores trainer information and expertise                     |
| Program         | **Program_ID (PK)**, Program_Name, Duration, Fee                      | Contains fitness program details like Yoga, Zumba            |
| Session         | **Session_ID (PK)**, Date, Time, Member_ID (FK), Trainer_ID (FK)      | Represents personal training sessions booked by members      |
| Attendance      | **Attendance_ID (PK)**, Date, Status, Member_ID (FK), Session_ID (FK) | Tracks attendance of members for sessions                    |
| Payment         | **Payment_ID (PK)**, Amount, Date, Payment_Type, Member_ID (FK)       | Stores payment records for memberships and sessions          |
| Member_Program  | **Member_ID (PK, FK)**, **Program_ID (PK, FK)**                       | Junction table for Member–Program many-to-many relationship  |
| Trainer_Program | **Trainer_ID (PK, FK)**, **Program_ID (PK, FK)**                      | Junction table for Trainer–Program many-to-many relationship |


### Relationships and Constraints

| Relationship                | Cardinality | Participation       | Notes                                                                      |
| --------------------------- | ----------- | ------------------- | -------------------------------------------------------------------------- |
| Member joins Program        | M:N         | Partial             | A member can join multiple programs; each program can have many members    |
| Trainer assigned to Program | M:N         | Partial             | Trainers may handle multiple programs; programs may have multiple trainers |
| Member books Session        | 1:N         | Total on Session    | One member can book many sessions                                          |
| Trainer conducts Session    | 1:N         | Total on Session    | One trainer can conduct many personal training sessions                    |
| Session has Attendance      | 1:N         | Total on Attendance | Attendance is recorded for every session                                   |
| Member makes Payment        | 1:N         | Partial             | Members can make multiple payments                                         |


### Assumptions
- Each personal training session involves one member and one trainer only.
- Attendance is maintained separately for each session attended by a member.
- Payments include both membership fees and personal training session fees.
- A member must register before joining any fitness program.
- Programs such as Yoga and Zumba can be handled by multiple trainers simultaneously.
---
