## Explaination

This ER diagram manages:

- Vehicles entering parking
- Assigning them a parking spot
- Tracking how long they stay
- Charging them money

---

# 1. Vehicle & Vehicle Type

### Vehicle

This stores **who owns the vehicle and details**

- owner name, phone number
- license plate
- category (2-wheeler, car, etc.)

### VehicleType

This defines **types of vehicles**

- 2-wheeler
- 4-wheeler
- EV

Relationship:

- One **VehicleType** → Many **Vehicles**

Example:

- “4-wheeler” → many cars

---

# 2. Access Category

This is for **special people**

- VIP
- Exhibitor
- Staff

Some parking spots are **reserved only for specific people**

---

# 3. Parking Structure

### ParkingZone

- Big area (like Zone A, Zone B)

### ParkingLevel

- Each zone can have multiple levels (like basement floors)

### ParkingSpot

- Actual parking slot

👉 Relationship chain:

- Zone → Levels → Spots

---

# 4. ParkingSpot

Each spot has rules:

- Which vehicle type allowed (`required_category_id`)
- Reserved for whom (`reserved_for_access_id`)
- EV charging available?
- Available or not?

Example:

- Spot 101:
  - Only EV cars
  - Reserved for VIP
  - Has charging station

---

# 5. Parking Ticket

When a vehicle enters:

- A ticket is generated which Contains:
  - Vehicle ID
  - Spot assigned
  - Entry time

like: “A parking slip”

---

# 6. Parking Session

This tracks **real usage**

- When vehicle entered
- When it exited
- Total duration
- Status (active/completed)

Why separate from ticket?
Because:

- Ticket = entry record
- Session = full lifecycle (entry → exit)

---

# 7. Payment Record

After parking ends:

- Payment is calculated which Contains:
  - Base price
  - Total amount
  - Payment method (UPI, cash, card)
  - Status (paid / pending / waived)

---

# Relationships

## Step-by-Step Flow

### 1. Vehicle arrives

- Stored in **Vehicle**
- Type checked via **VehicleType**

---

### 2. Spot assigned

- System finds a **ParkingSpot**
  - Matching vehicle type
  - Matching access category (if needed)

---

### 3. Ticket generated

- Entry recorded in **ParkingTicket**

---

### 4. Session starts

- Entry time stored in **ParkingSession**

---

### 5. Vehicle exits

- Exit time updated
- Duration calculated

---

### 6. Payment done

- Stored in **PaymentRecord**

---
