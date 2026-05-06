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
| `payment_deadline`| TIMESTAMP | NULL | Hold period |
| `status` | VARCHAR(50) | DEFAULT 'PENDING' | PENDING, PAID, CANCELLED |

## Relationships
- **Inventory**: Spawns multiple [[CoachTicket]] records.
- **Finance**: Linked to [[PaymentTransaction]].

## References
- [[database-schema]]
- [[xe-khach-tuyen-co-dinh]]
