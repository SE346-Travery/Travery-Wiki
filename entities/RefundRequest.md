---
title: "RefundRequest"
category: entities
tags: [transaction, finance]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: RefundRequest

A request to return funds for a cancelled service.

## Database Table: `refund_requests`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `payment_transaction_id`| UUID | FK(payment_transactions.id) | Source payment |
| `user_id` | UUID | FK(users.id) | Requester |
| `processed_by_id`| UUID | FK(users.id), NULL | Coordinator |
| `requested_amount`| DECIMAL(12,2)| NOT NULL | Calculated amount |
| `actual_refunded`| DECIMAL(12,2)| NULL | Settled amount |
| `customer_reason`| TEXT | NULL | Cancellation reason |
| `status` | VARCHAR(50) | DEFAULT 'PENDING' | PENDING, PROCESSING, COMPLETED, REJECTED |

## References
- [[database-schema]]
- [[chinh-sach-hoan-tien]]
