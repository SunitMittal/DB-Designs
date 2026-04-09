## Explaination

This system manages:

- Users (clients + trainers)
- Fitness programs (workouts + diet)
- Client progress tracking
- Payments & subscriptions
- Live sessions & consultations

---

# 1. Users, Clients, Trainers

### users

This is the **base table**

- Everyone is first a user (login system)
- Stores common info (name, email, password)

---

### clients

Extra details for **clients**

- Fitness goals
- Weight, height
- Diet & health conditions
- Assigned trainer

One user → can become a client

---

### trainers

Extra details for **trainers**

- Experience
- Specializations
- Pricing
- Availability

One user → can become a trainer

---

### Relationship

- `users → clients`
- `users → trainers`

This is **role-based design**

---

# 2. Programs

### programs

Created by trainers:

- Weight loss / muscle gain / etc.
- Duration, difficulty, price

---

### program_weeks

Programs are divided into weeks:

- Week 1, Week 2...

---

### workout_plans

Each week has daily workouts:

- Monday plan
- Tuesday plan

---

### exercises

Master list:

- Push-up, squat, etc.

---

### workout_plan_exercises

This connects:

- Workout → Exercises

With details:

- Sets
- Reps
- Order

Example:
Monday workout:

- Push-ups (3x10)
- Squats (4x12)

---

# 3. Diet System

### diet_plans

Each week also has:

- Calories
- Macros (protein, carbs, fat)

---

### meal_entries

Breaks diet into meals:

- Breakfast
- Lunch
- Dinner

Example:
Breakfast:

- Oats 100g → 300 calories

---

# 4. Enrollment & Subscription

### client_enrollments

Tracks:

- Which client joined which program
- Assigned trainer
- Start & end date

---

### subscriptions

Billing system:

- Monthly / yearly
- Payment cycles

Important difference:
| Table | Purpose |
| ------------ | ----------------- |
| enrollment | access to program |
| subscription | payment plan |

---

### payments

Tracks actual payments:

- Success / failed
- Payment method
- Gateway IDs

---

# 5. Live Interaction

### consultations

1-on-1 sessions:

- Trainer ↔ Client
- Scheduled calls

---

### live_sessions

Group sessions:

- One trainer
- Many clients

---

### live_session_enrollments

Who joined the live session

---

# 6. Progress Tracking

### checkins

Weekly updates from client:

- Weight
- Energy
- Sleep
- Diet adherence

---

### body_measurements

Detailed body stats:

- Chest, waist, arms, etc.

---

### trainer_feedback

Trainer responds with:

- Feedback
- Plan changes
- Motivation

---

# Relationships

## Step-by-Step Flow

## Step 1: User joins

- Stored in `users`
- Becomes a `client`

---

## Step 2: Trainer assigns program

- Trainer creates `program`
- Client enrolls (`client_enrollments`)

---

## Step 3: Payment

- Subscription created
- Payment recorded

---

## Step 4: Client follows plan

- Weekly workouts (`workout_plans`)
- Diet (`diet_plans`)

---

## Step 5: Weekly check-in

- Client submits progress (`checkins`)
- Adds body measurements

---

## Step 6: Trainer feedback

- Trainer reviews
- Updates plan if needed

---

## Step 7: Live sessions / calls

- Client attends sessions
- Books consultations

---
