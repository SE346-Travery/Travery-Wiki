---
title: "Database Schema"
category: sources
tags: [database, postgres, schema]
updated: 2026-05-06
---

# Source: Database_Schema.md

## Summary
A detailed definition of the Travery system's database schema, including columns, data types (PostgreSQL), and constraints across five development phases.

### Key Phases
- **Phase 1: Core Base & Auth**: Identity and role-based access control ([[User]], [[Tourist]], [[Receptionist]], etc.).
- **Phase 2: Configuration & Rule Engines**: Fleet management ([[Coach]], [[Driver]]), Amenities, and Refund Policies.
- **Phase 3: Bookable Assets**: The core services: [[Hotel]], [[Route]], and [[Tour]].
- **Phase 4: Operational Instances**: Real-world executions like [[CoachTrip]] and [[TourInstance]].
- **Phase 5: Transactional Data**: Bookings, Payments, Reviews, and Refunds.

## Identified Entities
- **Core Base**: [[User]], [[Tourist]], [[Receptionist]], [[Coordinator]], [[Guide]], [[Admin]], [[Station]], [[Image]]
- **Fleet**: [[Coach]], [[CoachSeat]], [[Driver]]
- **Services**: [[Hotel]], [[RoomType]], [[Room]], [[Amenity]], [[HotelService]], [[Route]], [[Tour]], [[TourItinerary]]
- **Operations**: [[CoachTrip]], [[TourInstance]]
- **Transactions**: [[CoachBooking]], [[HotelBooking]], [[TourBooking]], [[CoachTicket]], [[HotelBookingDetail]], [[RoomAssignment]], [[AddOnOrder]], [[BookingMember]], [[PaymentTransaction]], [[RefundRequest]], [[Review]]
