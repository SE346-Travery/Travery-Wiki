---
title: "Coordinator"
category: entities
tags: [user, role, staff]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Coordinator

Office-based staff responsible for operational management and customer care.

## Database Table: `coordinators`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK, FK(users.id) | Link to base user |
| `employee_code` | VARCHAR(50) | UNIQUE, NOT NULL | Internal staff ID |
| `department` | VARCHAR(50) | NULL | TOUR, HOTEL, COACH |

## Relationships
- **Base**: Inherits from [[User]].
- **Operations**: Creates and manages [[TourInstance]]s and [[CoachTrip]]s.
- **Support**: Handles [[ChatSession]]s and [[RefundRequest]]s.

## References
- [[database-schema]]
- [[dieu-phoi-vien]]
