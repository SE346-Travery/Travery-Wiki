---
title: "Review"
category: entities
tags: [transaction, auxiliary]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: Review

Polymorphic user feedback for completed services.

## Database Table: `reviews`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | Author |
| `booking_id` | UUID | NOT NULL | Verified purchase ID |
| `booking_type` | VARCHAR(50) | NOT NULL | TOUR_BOOKING, etc. |
| `target_id` | UUID | NOT NULL | Object being rated |
| `target_type` | VARCHAR(50) | NOT NULL | TOUR, HOTEL, ROUTE |
| `average_rating`| INT | NOT NULL | 1-5 stars |
| `content` | TEXT | NULL | Text comment |

## Constraints
- `UNIQUE(booking_id, booking_type)`: One review per purchase.

## References
- [[database-schema]]
- [[erd-summary]]
