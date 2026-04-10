## Explaination

This ER diagram manages:

- Buildings with multiple floors
- Multiple elevators inside shafts
- People requesting elevators
- Assigning the best elevator
- Tracking rides
- Handling maintenance

---

# 1. Building & Floors

### building

This is the **main entity**

- Name, address, type (office, mall, airport)
- Total floors

---

### floor

Each building has multiple floors:

- Floor 1, Floor 2, etc.

Relationship:

- One building → Many floors

---

# 2. Elevator Infrastructure

### elevator_shaft

- Physical vertical space where elevators move

---

### elevator

Actual elevator cabins:

- Capacity (kg & people)
- Manufacturer
- Installed date

Relationship:

- One shaft → can have one or more elevators (depending on design)
- One building → many elevators

---

# 3. Elevator Status

### elevator_status

Tracks live info:

- Current floor
- Working / under maintenance
- Overloaded or normal

This is like:
“Where is the elevator right now?”

---

# 4. Floor Request

### floor_request

When someone presses a button:

- Request is created which contains:
  - Which floor user wants to go
  - Time of request
  - Status (pending, completed)

Example:
You press button on 5th floor → request created

---

# 5. Ride Assignment

### ride_assignment

System decides:

- Which elevator should handle the request

This is where **smart logic happens**

- Nearest elevator
- Least busy elevator
- Direction-based optimization

---

# 6. Ride

### ride

Tracks the actual trip:

- Which elevator
- From which floor
- Start & end time
- Duration

Example:
Elevator goes from 2 → 5 → takes 20 seconds

---

# 7. Maintenance System

### maintenance_log

Tracks:

- Issues (not working, inspection)
- Progress (scheduled → in progress → completed)

Important for:

- Safety
- Downtime tracking

---

# Relationships

- Building → Floors
- Building → Elevators
- Elevator → Status
- Floor → Requests
- Request → Assignment → Ride

---
