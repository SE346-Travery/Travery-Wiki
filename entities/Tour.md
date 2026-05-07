---
title: "Tour"
category: entities
tags: [asset, travel]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: Tour

Defines a tour package template. Can be a standard offering or a [[custom-tour]].

## Database Table: `tours`

| Column                 | Data Type     | Constraints            | Description                 |
| ---------------------- | ------------- | ---------------------- | --------------------------- |
| `id`                   | UUID          | PK                     | Unique identifier           |
| `name`                 | VARCHAR(255)  | NOT NULL               | Tour title                  |
| `description`          | TEXT          | NULL                   | Detailed itinerary intro    |
| `coordinator_id`       | UUID          | FK(users.id)           | Designer of the tour        |
| `hotel_id`             | UUID          | FK(hotels.id), NULL    | Primary stay point          |
| `requested_by_user_id` | UUID          | FK(users.id), NULL     | Requester (if Custom)       |
| `destination_code`     | VARCHAR(50)   | NOT NULL               | Target region               |
| `pickup_location`      | VARCHAR(500)  | NOT NULL               | Meeting point               |
| `price_per_adult`      | DECIMAL(12,2) | NOT NULL               | Cost for adults             |
| `price_per_child`      | DECIMAL(12,2) | NOT NULL               | Cost for children           |
| `is_custom`            | BOOLEAN       | DEFAULT FALSE          | Flag for personalized tours |
| `refund_policy_id`     | UUID          | FK(refund_policies.id) | Cancellation rules          |

## Relationships
- **Structure**: Includes multiple [[TourItinerary]] days.
- **Execution**: Instantiated as many [[TourInstance]] departures.
- **Support**: Linked to [[ChatSession]] if generated from a consultation.

## References
- [[database-schema]]
- [[tour-tron-goi]]
- [[custom-tour]]
