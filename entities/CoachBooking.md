---
title: "CoachBooking"
category: entities
tags: [transaction, sale]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: CoachBooking

A reservation for tickets on a [[CoachTrip]].

## Database Table: `coach_bookings`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | Buyer |
| `coach_trip_id`| UUID | FK(coach_trips.id) | Selected trip |
| `total_price` | DECIMAL(12,2)| NOT NULL | Payment amount |
| `payment_deadline`| TIMESTAMP | NULL | 15-minute hold period |
| `status` | VARCHAR(50) | DEFAULT 'PENDING' | PENDING, PAID, CANCELLED |

## Constraints & Business Rules
- **Payment**: Requires 100% upfront payment in a single transaction.
- **Hold Time**: The selected seats are temporarily locked for **15 minutes**.
- **Luggage Limit**: Customers are allowed up to **20 kg** of free luggage.
- **Boarding**: Customers must be at the pickup point 15-30 minutes prior to departure. The bus does not wait for late passengers (see No Show-up).

## Relationships
- **Inventory**: Spawns multiple [[CoachTicket]] records.
- **Finance**: Linked to [[PaymentTransaction]].

## References
- [[database-schema]]
- [[xe-khach-tuyen-co-dinh]]
