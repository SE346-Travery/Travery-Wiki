---
title: "CoachSeat"
category: entities
tags: [fleet, inventory]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: CoachSeat

Logical seat location within a physical [[Coach]].

## Database Table: `coach_seats`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `coach_id` | UUID | FK(coaches.id) | Parent vehicle |
| `seat_name` | VARCHAR(10) | NOT NULL | Label (e.g., A1, B2) |
| `tier` | VARCHAR(20) | NOT NULL | UPPER, LOWER |
| `position` | VARCHAR(20) | NOT NULL | FRONT, MIDDLE, BACK |

## Relationships
- **Parent**: Belong to one physical [[Coach]].
- **Booking**: Target for [[CoachTicket]].

## References
- [[database-schema]]
