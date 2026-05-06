---
title: "RoomAssignment"
category: entities
tags: [operations, hotel]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: RoomAssignment

Matches a physical [[Room]] to a guest's [[HotelBookingDetail]] during check-in.

## Database Table: `room_assignments`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `hotel_booking_detail_id`| UUID | FK(hotel_booking_details.id) | Requirement link |
| `room_id` | UUID | FK(rooms.id) | Physical room link |

## References
- [[database-schema]]
