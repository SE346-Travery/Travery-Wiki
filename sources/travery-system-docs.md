# Source: Travery - Tài liệu nghiệp vụ hệ thống.md

## Summary
This document outlines the technical and functional requirements for the **Travery** application. It serves as a blueprint for digitizing service bookings, coordination, and customer care.

Key areas covered include:
- **Introduction**: Reinforces Travery's model as a direct service provider.
- **User Roles & Authentication**: Defines roles for [[Khách hàng]] (Tourist), [[Điều phối viên]], [[Hướng dẫn viên]], [[Lễ tân]], and [[Quản trị viên]]. It specifies registration via email, [[OTP]] verification, and session management.
- **Service Workflows**: Detailed step-by-step logic for booking [[Tour trọn gói]], [[Xe khách tuyến cố định]], and [[Khách sạn]], including system-enforced constraints (e.g., seat capacity, 15-minute payment holds).
- **Policies**: Digitized [[Chính sách hoàn tiền]] and [[No Show-up]] logic for automated calculations.
- **Chat & Consultations**: Describes the real-time [[Chat]] system used for general support and the collaborative design of [[Custom Tour]].
- **Technical Procedures**: Incident reporting, payment failure handling, and automated reminders.

## Identified Entities
- **Organizations**: [[Travery]]
- **People/Roles**: [[Khách hàng]], [[Điều phối viên]], [[Hướng dẫn viên]], [[Lễ tân]], [[Quản trị viên]]
- **Concepts**: [[Tour trọn gói]], [[Xe khách tuyến cố định]], [[Khách sạn]], [[Chính sách hoàn tiền]], [[No Show-up]], [[Custom Tour]], [[Add-On]], [[OTP]], [[Chat]]
