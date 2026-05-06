---
title: "CoachTrip"
category: entities
tags: [operations, execution]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: CoachTrip

A real-world execution of a [[Route]] on a specific time.

## Database Table: `coach_trips`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `route_id` | UUID | FK(routes.id) | Base path |
| `coach_id` | UUID | FK(coaches.id) | Assigned vehicle |
| `driver_id` | UUID | FK(drivers.id) | Assigned driver |
| `coordinator_id` | UUID | FK(users.id) | Manager |
| `departure_time` | TIMESTAMP | NOT NULL | Exact start |
| `arrival_time` | TIMESTAMP | NULL | Actual arrival |
| `status` | VARCHAR(50) | DEFAULT 'SCHEDULED' | SCHEDULED, IN_PROGRESS, COMPLETED, CANCELLED |

## Relationships
- **Inventory**: Provides seats for [[CoachBooking]].

## References
- [[database-schema]]
- [[xe-khach-tuyen-co-dinh]]
