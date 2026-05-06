---
title: "ChatSession"
category: entities
tags: [auxiliary, interaction]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: ChatSession

Represents a real-time consultation or support session.

## Database Table: `chat_sessions`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | Client |
| `coordinator_id`| UUID | FK(users.id), NULL | Assigned staff |
| `cometchat_guid`| VARCHAR(100) | UNIQUE, NOT NULL | External group ID |
| `tour_id` | UUID | FK(tours.id), NULL | Linked [[Custom Tour]] |
| `status` | VARCHAR(20) | DEFAULT 'OPEN' | OPEN, CLOSED |

## Relationships
- **Parties**: Connects a [[Tourist]] with a [[Coordinator]].
- **Outcome**: May link to a [[Tour]] if a custom package is designed.

## Operations & SLA
- **Support Hours**: Coordinators respond during business hours (8:00–17:30, Mon-Sat).
- **SLA**: Guaranteed response within **30 minutes** during business hours. Out-of-hours messages are addressed at the start of the next business day.
- **Review Resolution**: Travery commits to resolving all negative reviews via chat or direct contact within **48 working hours**.

## References
- [[database-schema]]
- [[chat-system]]
