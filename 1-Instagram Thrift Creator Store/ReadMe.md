## Explaination

This system manages:

- Customers
- Products (limited stock items)
- Orders
- Payments
- Shipping

---

# 1. Customer & Address

### customer

This is the **base table** which stores basic user info

- Name
- Created date

---

### address

Stores delivery addresses

- Street, city, state, pincode

One customer → multiple addresses

---

# 2. Product

What we sell:

- Type (shirt, jeans)
- Color, size
- Quantity (stock)
- Condition:
    - new
    - good
    - decent (important for thrift stores)

---

# 3. Orders

Represents purchase:

- customer name
- Total amount
- Shipping status

---

# 4. Order Items

Breaks order into items:

- Which product
- Quantity
- Price

---

# 5. Payment

Tracks payment:
- Online or Cash on Delivery (COD)
- Status (paid, pending)

---

# 6. Shipping

Tracks delivery:

- Which address
- Tracking ID
- Shipping date

---

# Relationships

## Step-by-Step Flow

## Step 1: Customer signs up

- Stored in `customer`
- Adds address

---

## Step 2: Customer selects product

- Product from `product`

---

## Step 3: Order created

- Entry in `orders`
- Items stored in `order_item`

---

## Step 4: Payment done

- Entry in `payment`

---

## Step 5: Shipping

- Entry in `shipping`
- Tracking ID assigned

---
