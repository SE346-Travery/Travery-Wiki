---
title: "Coach"
category: entities
tags: [fleet, vehicle]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Coach

Physical vehicle assets owned by Travery.

## Database Table: `coaches`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `license_plate` | VARCHAR(20) | UNIQUE, NOT NULL | Registry plate |
| `coach_type` | VARCHAR(50) | NOT NULL | SEAT, BED, LIMOUSINE |
| `capacity` | INT | NOT NULL | Total seats/beds |
| `status` | VARCHAR(20) | DEFAULT 'ACTIVE' | ACTIVE, MAINTENANCE |

## Relationships
- **Inventory**: Contains multiple [[CoachSeat]] definitions.
- **Ops**: Assigned to [[CoachTrip]] or [[TourInstance]].

## References
- [[database-schema]]
- [[erd-summary]]
