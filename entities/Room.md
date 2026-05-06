---
title: "Room"
category: entities
tags: [asset, inventory]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Room

A physical, uniquely numbered room within a [[Hotel]].

## Database Table: `rooms`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `hotel_id` | UUID | FK(hotels.id) | Parent hotel |
| `room_type_id` | UUID | FK(room_types.id) | Category |
| `room_number` | VARCHAR(50) | NOT NULL | Label (e.g., 101A) |
| `status` | VARCHAR(20) | DEFAULT 'AVAILABLE'| AVAILABLE, OCCUPIED, MAINTENANCE |

## Constraints
- `UNIQUE(hotel_id, room_number)`: Ensures room numbers are unique within each hotel.

## Relationships
- **Allocation**: Assigned to guests via [[RoomAssignment]].

## References
- [[database-schema]]
