---
title: "AddOnOrder"
category: entities
tags: [transaction, add-on]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: AddOnOrder

A request for a [[HotelService]] during a stay.

## Database Table: `add_on_orders`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `hotel_booking_id`| UUID | FK(hotel_bookings.id) | Linked stay |
| `hotel_service_id`| UUID | FK(hotel_services.id) | Target service |
| `quantity` | INT | NOT NULL | Count |
| `total_price` | DECIMAL(12,2)| NOT NULL | Subtotal |
| `status` | VARCHAR(50) | DEFAULT 'PENDING' | PENDING, DELIVERED, CANCELLED |

## References
- [[database-schema]]
- [[add-on]]
