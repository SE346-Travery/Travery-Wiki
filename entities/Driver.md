---
title: "Driver"
category: entities
tags: [fleet, staff]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Driver

Represents a driver operating vehicles for Travery.

## Database Table: `drivers`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `full_name` | VARCHAR(100) | NOT NULL | Driver's name |
| `phone_number` | VARCHAR(20) | UNIQUE, NOT NULL | Contact |
| `license_number` | VARCHAR(50) | UNIQUE, NOT NULL | License ID |
| `status` | VARCHAR(20) | DEFAULT 'AVAILABLE' | AVAILABLE, ON_TRIP, ON_LEAVE |

## Relationships
- **Fleet**: Assigned to either a [[CoachTrip]] (Bus service) or a [[TourInstance]] (Tour service).

## References
- [[database-schema]]
- [[erd-summary]]
