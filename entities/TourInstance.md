---
title: "TourInstance"
category: entities
tags: [operations, execution]
sources: [database-schema, erd-summary]
updated: 2026-05-12
---

# Entity: TourInstance

A real-world departure of a [[Tour]] on a specific date.

## Database Table: `tour_instances`

| Column                 | Data Type   | Constraints          | Description                                             |
| ---------------------- | ----------- | -------------------- | ------------------------------------------------------- |
| `id`                   | UUID        | PK                   | Unique identifier                                       |
| `tour_id`              | UUID        | FK(tours.id)         | Base template                                           |
| `coordinator_id`       | UUID        | FK(users.id)         | Operational manager                                     |
| `guide_id`             | UUID        | FK(users.id), NULL   | Field lead                                              |
| `coach_id`             | UUID        | FK(coaches.id), NULL | Assigned vehicle                                        |
| `driver_id`            | UUID        | FK(drivers.id), NULL | Assigned driver                                         |
| `hotel_booking_id`     | UUID        | NULL                 | Internal link to [[HotelBooking]]                       |
| `start_date`           | DATE        | NOT NULL             | Departure date (Indexed)                                |
| `end_date`             | DATE        | NOT NULL             | Return date                                             |
| `current_participants` | INT         | DEFAULT 0            | Paid bookings                                           |
| `status`               | VARCHAR(50) | DEFAULT 'PLANNING'   | PLANNING, OPEN, FULL, IN_PROGRESS, COMPLETED, CANCELLED |

## Search Optimization (Lucene)
- **Indexed Fields**: `start_date`, `status`.
- **Relationship**: Embedded as nested objects within [[Tour]].

## Constraints & Business Rules
- **Capacity**: Participant limits are defined at the [[Tour]] level (default 10-30).
- **Under-booking**: If the minimum requirement (typically 10 pax) is not met by **3 days** prior to departure, Travery may cancel the instance and issue a 100% refund.

## Relationships
- **Base**: Instantiated from [[Tour]].
- **Sales**: Collects multiple [[TourBooking]] entries.
- **Staffing**: Assigned [[Guide]], [[Driver]], and [[Coach]].
- **Accommodation**: Automatically generates a hidden [[HotelBooking]] for the group.

## References
- [[database-schema]]
- [[tour-tron-goi]]
