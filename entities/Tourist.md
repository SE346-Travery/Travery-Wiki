---
title: "Tourist"
category: entities
tags: [user, role]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Tourist

Specialized user entity for customers who book services.

## Database Table: `tourists`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `user_id` | UUID | PK, FK(users.id) | Link to base user |
| `passport_number` | VARCHAR(50) | UNIQUE, NULL | National ID or Passport |
| `date_of_birth` | DATE | NULL | Birth date for insurance/age verification |
| `gender` | VARCHAR(10) | NULL | MALE, FEMALE, OTHER |

## Relationships
- **Base**: Inherits from [[User]].
- **Activity**: Creates [[TourBooking]], [[HotelBooking]], and [[CoachBooking]].

## References
- [[database-schema]]
- [[khach-hang]]
