---
title: "HotelBookingDetail"
category: entities
tags: [transaction, detail]
sources: [database-schema]
updated: 2026-05-06
---
	
# Entity: HotelBookingDetail

Specific room type requirements within a [[HotelBooking]].

## Database Table: `hotel_booking_details`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `hotel_booking_id`| UUID | FK(hotel_bookings.id) | Parent booking |
| `room_type_id` | UUID | FK(room_types.id) | Selected category |
| `quantity` | INT | NOT NULL | Number of rooms |
| `price_at_booking`| DECIMAL(12,2)| NOT NULL | Historical rate |
| `start_date` | DATE | NOT NULL | Check-in date |
| `end_date` | DATE | NOT NULL | Check-out date |

## Relationships
- **Allocation**: Satisfied by [[RoomAssignment]] to physical rooms.

## References
- [[database-schema]]
