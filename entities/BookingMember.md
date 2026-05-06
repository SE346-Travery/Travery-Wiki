---
title: "BookingMember"
category: entities
tags: [transaction, detail]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: BookingMember

Polymorphic entity representing an individual passenger or guest in a booking.

## Database Table: `booking_members`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `booking_id` | UUID | NOT NULL | Parent ID (Poly) |
| `booking_type` | VARCHAR(50) | NOT NULL | TOUR_BOOKING or HOTEL_BOOKING |
| `full_name` | VARCHAR(100) | NOT NULL | Legal name |
| `passport_number` | VARCHAR(50) | NOT NULL | Identity ID |
| `date_of_birth` | DATE | NULL | Age verification |

## Relationships
- **Parent**: Links polymorphically to [[TourBooking]] or [[HotelBooking]].
- **Purpose**: Used for insurance submission (Tours) or local police reporting (Hotels).

## References
- [[database-schema]]
- [[erd-summary]]
