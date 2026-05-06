# Source: Travery - Tài liệu nghiệp vụ hệ thống.md (Travery-SRS)

## Summary
This document serves as the **System Requirements Specification (SRS)** for the Travery application. It acts as the definitive blueprint for digitizing service bookings, coordination, and customer care, mapping directly to the underlying [[database-schema]].

Key areas covered include:
- **Introduction**: Reinforces Travery's model as a direct service provider.
- **User Roles & Authentication**: Defines roles for [[Khách hàng]] (Tourist), [[Điều phối viên]], [[Hướng dẫn viên]], [[Lễ tân]], and [[Quản trị viên]]. It specifies registration via email, [[OTP]] verification, and session management.
- **Service Workflows**: Detailed step-by-step logic for booking [[Tour trọn gói]], [[Xe khách tuyến cố định]], and [[Khách sạn]]. Highlights strict system constraints (e.g., 10-30 pax limits for tours, 15-minute payment hold locks, 20kg luggage limits for buses).
- **Policies**: Digitized [[Chính sách hoàn tiền]] and [[No Show-up]] logic for automated calculations (e.g., 7-day, 3-6 day, <3 day thresholds).
- **Chat & Consultations**: Describes the real-time [[Chat System]] used for general support (30-min SLA) and the collaborative design of [[Custom Tour]]s (quotes valid for 3 days).
- **Technical Procedures**: Incident reporting, payment failure handling (e.g., callback timeouts), and automated 1-day reminders.

## Identified Entities
- **Organizations**: [[Travery]]
- **People/Roles**: [[Khách hàng]], [[Điều phối viên]], [[Hướng dẫn viên]], [[Lễ tân]], [[Quản trị viên]]
- **Concepts**: [[Tour trọn gói]], [[Xe khách tuyến cố định]], [[Khách sạn]], [[Chính sách hoàn tiền]], [[No Show-up]], [[Custom Tour]], [[Add-On]], [[OTP]], [[Chat]]
