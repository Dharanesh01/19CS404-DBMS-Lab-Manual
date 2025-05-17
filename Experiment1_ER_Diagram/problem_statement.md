# Experiment 1: Entity-Relationship (ER) Diagram
REG NO 212222060042
## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - DHARANESH M

## Scenario Chosen:
Hospital 

## ER Diagram:
![image](https://github.com/user-attachments/assets/c953e4e0-4e92-4217-91b2-dff8cc5a5cee)


## Entities and Attributes:
Department:Department ID, Department Name

Doctors:Doctor ID, Doctor Name, Specialisation, Department

Patients:Patient ID, Patient Name, Phone No, Insurance Details

Medical Records:Medical Record ID, Doctor ID, Patient ID, Details

Billing Section:Billing ID, Patient ID, Date

Payments:Transaction ID, Amount, Payment Status

## Relationships and Constraints:
Has (Hospital–Department):One-to-Many,A hospital has multiple departments.

Manages (Hospital–Patients):One-to-Many,A hospital manages many patients.

Maintains (Hospital–Medical Records):One-to-Many,A hospital maintains multiple medical records.

Holds (Doctors–Medical Records):One-to-Many,Each doctor can hold multiple medical records.Partial Participation

Schedule (Doctors–Patients):Many-to-ManyAppointments between doctors and patients.Partial Participation

PaysFor (Patients–Billing Section–Payments):One-to-ManyPatients are billed, and each billing record may have a payment.

## Extension (Prerequisite / Billing):
Prerequisite:

Modeled as a recursive relationship on the Medical Records or Treatment entity if expanded, where a procedure or record may depend on another.

Billing:

A separate entity connected to both Patients and Payments via PaysFor relationship.

Attributes: Amount, Payment Status, Date, Transaction ID

## Design Choices:
Modularity:

Separate entities for doctors, patients, billing, and records keep the system organized and scalable.ERP-Like System Representation:

The hospital acts like a central ERP managing departments, staff, patients, and services.

Real-World Mapping:

Relationships reflect hospital workflows—appointments, medical history tracking, billing, and payments.

Security & Access (optional):

You can introduce a Login entity for doctors, patients, and admin staff for secure access to records and scheduling (like in your academic model).

## RESULT
The concepts of Entity-Relationship (ER) modeling were understood and successfully applied by creating an ER diagram for a real-world hospital management system. The diagram effectively represents core entities such as:HospitalDepartmentDoctorsPatientsMedical RecordsBilling SectionPayments.This ER model clearly demonstrates the structure, workflow, and interaction within a hospital system, making it a well-structured representation of a complex real-world application using ER modeling principles.
