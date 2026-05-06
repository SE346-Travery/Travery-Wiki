---
title: "CoachTicket"
category: entities
tags: [transaction, detail]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: CoachTicket

Specific ticket for an individual seat on a [[CoachTrip]].

## Database Table: `coach_tickets`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `coach_booking_id`| UUID | FK(coach_bookings.id) | Parent booking |
| `coach_seat_id`| UUID | FK(coach_seats.id) | Assigned seat |
| `passenger_name`| VARCHAR(100) | NULL | Name on ticket |
| `passenger_phone`| VARCHAR(20) | NULL | Contact for ticket |
| `price_at_booking`| DECIMAL(12,2)| NOT NULL | Historical price |

## References
- [[database-schema]]
