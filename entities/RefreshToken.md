---
title: "RefreshToken"
category: entities
tags: [auth, security]
sources: [database-schema, travery-backend]
updated: 2026-05-06
---

# Entity: RefreshToken

Used for maintaining user sessions and issuing new access tokens without re-authentication.

## Database Table: `refresh_tokens`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | Linked user |
| `token` | VARCHAR(2048) | UNIQUE, NOT NULL | Secure token string |
| `expiry_date` | TIMESTAMP | NOT NULL | Validity limit |
| `revoked` | BOOLEAN | DEFAULT FALSE | Manual invalidation flag |

## Relationships
- **User**: Belong to one [[User]].
- **Auth**: Part of the [[JWT Authentication]] flow.

## References
- [[database-schema]]
- [[jwt-authentication]]
