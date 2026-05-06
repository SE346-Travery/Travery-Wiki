---
title: "Receptionist"
category: entities
tags: [user, role, staff]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Receptionist

Hotel-based staff responsible for check-ins and on-site service coordination.

## Database Table: `receptionists`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `user_id` | UUID | PK, FK(users.id) | Link to base user |
| `hotel_id` | UUID | FK(hotels.id) | Assigned hotel |
| `employee_code` | VARCHAR(50) | UNIQUE, NOT NULL | Internal staff ID |
| `shift_type` | VARCHAR(50) | NULL | DAY, NIGHT, etc. |

## Relationships
- **Base**: Inherits from [[User]].
- **Workplace**: Belong to one [[Hotel]].

## References
- [[database-schema]]
- [[le-tan]]
