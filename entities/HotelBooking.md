---
title: "HotelBooking"
category: entities
tags: [transaction, sale]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: HotelBooking

A reservation for lodging. Can be stand-alone or part of a [[TourInstance]].

## Database Table: `hotel_bookings`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | Guest/Buyer |
| `tour_instance_id`| UUID | FK(tour_instances.id), NULL | Associated tour |
| `total_price` | DECIMAL(12,2)| NOT NULL | Total cost |
| `payment_deadline`| TIMESTAMP | NULL | Hold period |
| `status` | VARCHAR(50) | DEFAULT 'PENDING' | PENDING, PAID, CHECKED_IN, CHECKED_OUT, CANCELLED |

## Relationships
- **Details**: Contains multiple [[HotelBookingDetail]] entries.
- **Members**: Contains [[BookingMember]] list.
- **Add-ons**: Parent for [[AddOnOrder]].
- **Finance**: Linked to [[PaymentTransaction]].

## References
- [[database-schema]]
- [[khach-san]]
