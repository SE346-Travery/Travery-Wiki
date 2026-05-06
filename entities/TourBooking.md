---
title: "TourBooking"
category: entities
tags: [transaction, sale]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: TourBooking

A customer's reservation for a specific [[TourInstance]].

## Database Table: `tour_bookings`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | The buyer |
| `tour_instance_id` | UUID | FK(tour_instances.id) | The trip |
| `total_price` | DECIMAL(12,2) | NOT NULL | Total paid |
| `payment_deadline` | TIMESTAMP | NULL | 15-minute hold limit |
| `status` | VARCHAR(50) | DEFAULT 'PENDING' | PENDING, PAID, CANCELLED |

## Constraints & Business Rules
- **Payment**: Requires 100% upfront payment.
- **Hold Time**: The booking is held for **15 minutes** pending payment. If unpaid, it is automatically cancelled.
- **List Finalization**: The guest list must be finalized at least **5 days** before departure.

## Relationships
- **Parties**: Placed by a [[Tourist]] for a [[TourInstance]].
- **Members**: Contains multiple [[BookingMember]] entries (passengers).
- **Finance**: Linked to [[PaymentTransaction]].
- **Review**: Can generate one [[Review]] post-completion.

## References
- [[database-schema]]
- [[tour-tron-goi]]
