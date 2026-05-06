---
title: "ERD Summary"
category: sources
tags: [database, erd, relationships]
updated: 2026-05-06
---

# Source: ERD_Summary.md

## Summary
A high-level synthesis of the Travery database design, focusing on the relationships between key modules: User & Auth, Fleet Management, Fixed Routes, Hotel & Add-ons, and Package Tours.

### Key Relationship Clusters
- **User & Roles**: Table-per-Type inheritance model for users.
- **Fleet Management**: Shared resources (Coaches, Drivers) used by both Bus and Tour modules.
- **Fixed Routes**: Hub-and-spoke model connecting [[Station]]s via [[Route]]s.
- **Hotel & Add-ons**: Hierarchical management of room inventory and supplemental services.
- **Package Tours**: Integration of Hotel and Coach resources into a single booking flow.

## Identified Entities
- **Clusters**: [[User]], [[Fleet]], [[Fixed-Route]], [[Hotel]], [[Package-Tour]], [[Auxiliary]]
