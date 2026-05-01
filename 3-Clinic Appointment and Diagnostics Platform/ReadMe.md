## Explaination

This system manages:

- Users (patients + doctors)
- Booking appointments
- Doctor consultations
- Lab tests & reports
- Payments

---

# 1. Users, Doctors, Patients

### User

This is the **base table**

- Everyone is first a user (login system)
- Stores common info (name, email, phone)
- Stores Role (doctor / patient)

---

### Doctor

Extra details for **doctors**

- Specialization
- Experience
- Consultation fee

---

### Patient

Extra details for **patients**

- Blood group
- Allergies/medical condition
- Emergency contact

---

### Relationship

- One User → either Doctor or Patient

This is **role-based design**

---

# 2. Specialization

Defines doctor expertise:

- Cardiologist/Dermatologist/Neurologist/etc.
- One specialization → many doctors

---

# 3. Appointment (Booking System)

When a patient books a slot:

- Patient ID
- Doctor ID
- Date & time
- Status (booked, cancelled, completed)

---

# 4. Consultation

Happens after appointment:

- Diagnosis
- Doctor notes
- Consultation time

***One appointment → one consultation***

---

# 5. Tests

### Tests

List of available tests:

- Blood test
- X-ray
- MRI

---

### Consultation_Test

Doctor may prescribe tests:

- Links consultation → tests
- Tracks status (pending, completed)

---

# 6. Report

Generated after test:

- Report URL (PDF)
- Summary of result

*** One test → one report ***

---

# 7. Payment

Tracks money:

- Linked to appointment or consultation
- Payment method (UPI, card, etc.)
- Status (paid, pending)

---

# Relationships

## Step-by-Step Flow

## Step 1: User signs up

- Stored in `User`
- Becomes a `Patient`

---

## Step 2: Appointment booked

- Entry in `Appointment`

---

## Step 3: Consultation happens

- Doctor examines patient
- Entry in `Consultation`

---

## Step 4: Tests prescribed

- Entries in `Consultation_Test`

---

## Step 5: Reports generated

- Stored in `Report`

---

## Step 6: Payment done

- Entry in `Payment`

---
