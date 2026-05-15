# Processing Log

Record of documents processed into the wiki.

## [2026-04-26] Ingest | Business Documentation
- **File**: `raw/Travery/Traver-Docs/Travery - Tài liệu doanh nghiệp.md`
- **Action**: Created [[travery-business-docs]], updated [[travery]], [[tour-tron-goi]], [[xe-khach-tuyen-co-dinh]], [[khach-san]].

## [2026-04-26] Ingest | System Documentation
- **File**: `raw/Travery/Traver-Docs/Travery - Tài liệu nghiệp vụ hệ thống.md`
- **Action**: Created [[travery-system-docs]], added roles and workflows.

## [2026-04-26] Ingest | Dev Rules
- **File**: `raw/Travery/github_cicd_rule.md`
- **Action**: Created [[github-cicd-rules]], extracted CI/CD concepts.

## [2026-04-26] Ingest | Architecture & Codebases
- **Files**: `raw/Travery/Travery.drawio - draw.io.md`, `raw/Travery/Travery-Backend/`, `raw/Travery/Travery-Frontend/`
- **Action**: Created [[drawio-diagrams]], [[travery-backend]], and [[travery-frontend]].
- **Concepts Added**: [[erd-diagram]], [[use-case-diagram]], [[custom-tour]], [[add-on]], [[otp]], [[chat-system]], [[ci-cd-pipeline]], [[conventional-commits]].
- **Roles Added**: [[huong-dan-vien]], [[le-tan]], [[quan-tri-vien]].

## [2026-05-01] Ingest | Technical Deep-Dive
- Created detailed entity pages in `wiki/entities/`:
    - [[User]]
    - [[Tour]]
    - [[TourInstance]]
    - [[TourBooking]]
    - [[TourBookingMember]]
    - [[Vehicle]]
    - [[Driver]]
    - [[Hotel]]
    - [[RefreshToken]]
- Created technical concept pages in `wiki/concepts/`:
    - [[jwt-authentication]]
    - [[otp-management]]
    - [[monitoring-stack]]
- Updated [[index]] with new sections and links.

## [2026-05-06] Ingest | Deployment & Database Deep-Dive
- **Files**: `raw/Travery/DEPLOYMENT_GUIDE.md`, `raw/Travery/Database_Schema.md`, `raw/Travery/ERD_Summary.md`
- **Action**: Created [[deployment-guide]], [[database-schema]], and [[erd-summary]].
- **Concepts Added/Updated**: [[deployment-architecture]], [[git-strategy]], [[branch-protection-rules]], [[docker-dns]], [[monitoring-stack]].
- **Entities Added/Updated**: Comprehensive update of 20+ entity pages including [[User]], [[Tourist]], [[Receptionist]], [[Coordinator]], [[Guide]], [[Admin]], [[Hotel]], [[RoomType]], [[Room]], [[Amenity]], [[HotelService]], [[Tour]], [[TourItinerary]], [[TourInstance]], [[TourBooking]], [[BookingMember]], [[Driver]], [[Station]], [[Route]], [[Coach]], [[CoachSeat]], [[CoachTrip]], [[CoachBooking]], [[CoachTicket]], [[HotelBooking]], [[HotelBookingDetail]], [[RoomAssignment]], [[AddOnOrder]], [[PaymentTransaction]], [[RefundRequest]], [[Review]], [[RefreshToken]], [[Image]], [[ChatSession]].
- Updated [[index]] with comprehensive entity and concept list.

## [2026-05-06] Ingest | System Requirements Specification (SRS)
- **Files**: `raw/Traver-Docs/Travery - Tài liệu nghiệp vụ hệ thống.md`
- **Action**: Formally ingested the Travery-SRS, extracting deep business rules and constraints.
- **Pages Updated**: Enriched [[travery-system-docs]], [[TourBooking]], [[CoachBooking]], [[HotelBooking]], [[TourInstance]], [[RefundPolicy]], [[custom-tour]], [[add-on]], [[ChatSession]], and [[Hotel]] with specific operational parameters (e.g., 15-minute hold times, exact pax limits, refund thresholds, and SLA response times).

## [2026-05-07] Lint | Remove Assignments
- **Action**: Removed `assignments-dev-backend.md` from the wiki to match the deleted raw file (Backend API style doesn't use `/api/v1/`).
- **Pages Updated**: Removed reference from [[index]].

## [2026-05-07] Lint | Fix Dead Links
- **Action**: Scanned the entire wiki for broken `[[links]]`. Re-mapped friendly-name links to proper file slugs (e.g., `[[Custom Tour]]` -> `[[custom-tour]]`, `[[Điều phối viên]]` -> `[[dieu-phoi-vien]]`) and removed formatting for completely unresolvable dead links (e.g., `[[Nginx]]` -> `Nginx`).
- **Pages Updated**: Updated dozens of concept, entity, and organization pages to ensure complete link consistency.

## [2026-05-08] Ingest | Backend Evolution
- **Source**: `raw/Travery-Backend/`
- **Action**: Ingested updates from the backend codebase.
- **Key Changes**: 
    - Updated [[travery-backend]] with Hibernate Search (Lucene), Virtual Threads, and social login dependencies.
    - Created [[Destination]] entity.
    - Updated [[Tour]] to reflect the structural shift from `destination_code` (String) to `destination_id` (FK to Destination).
    - Updated [[index]] with the new entity.

## [2026-05-12] Ingest | Seed Data & Service SLAs
- **Sources**: `raw/Travery-Backend/docs/Seed_Accounts.md`, updated `raw/Travery-Docs/`
- **Action**: Ingested development seed data and updated system business rules.
- **New Source**: [[seed-accounts]]
- **New People**: Created 9 seed user profiles ([[nguyen-van-hung]], [[tran-thi-mai]], [[le-minh-tuan]], [[pham-quoc-bao]], [[hoang-thi-lan]], [[vo-thanh-tam]], [[dang-ngoc-han]], [[bui-minh-khoi]], [[ngo-thi-hong]]).
- **New Organizations**: Created [[travery-grand-hotel]] and [[travery-beach-resort]].
- **New Concepts**: Created [[service-level-agreement]] (SLAs) and [[payment-failure-handling]].
- **Updates**:
    - Refreshed [[travery-system-docs]] with specific SLAs and failure handling logic.
    - Fixed [[RefundPolicyRule]] to use `days_before` instead of `hours_before_departure` to align with backend code.
    - Updated [[index]] with all new pages.

## [2026-05-12] Lint | Align Participant Limits with SRS
- **Action**: Corrected tour participant limits across the wiki to match the **Travery-SRS** and backend implementation.
- **Key Change**: Updated maximum participants from 30 to **40** (default).
- **Pages Updated**: [[travery-system-docs]], [[tour-tron-goi]], and [[TourInstance]].

## [2026-05-14] Ingest | Search & Refactoring Update
- **Source**: `raw/Travery-Backend/`
- **Action**: Ingested significant refactorings and Search Engine optimizations.
- **Key Changes**: 
    - **Entity Refactoring**: Moved `min_participants` and `max_participants` from [[TourInstance]] to [[Tour]]. Added `average_rating` and `duration_days` to [[Tour]].
    - **Participant Limits**: Reverted default maximum participants to **30** (capped at 30 in code).
    - **Search Integration**: Documented Hibernate Search (Lucene) indexing on [[Tour]] and [[TourInstance]].
    - **Schema Update**: Documented change from `hours_before_departure` to `days_before` in [[RefundPolicyRule]].
    - **Seeding**: New `V3` migration identified for seeding standard refund policies.
- **Pages Updated**: [[travery-backend]], [[Tour]], [[TourInstance]], [[RefundPolicyRule]], [[travery-system-docs]], [[tour-tron-goi]].

## [2026-05-15] Ingest | Advanced Search & Coordinator APIs
- **Source**: `raw/Travery-Backend/`
- **Action**: Ingested advanced search logic and coordinator-specific functional updates.
- **Key Changes**:
    - **Search Engine**: Updated Hibernate Search to **8.2.2.Final**. Created [[full-text-search]] concept.
    - **Logic**: Documented fuzzy search, term boosting, and nested availability filtering in `TourSearchCustomRepositoryImpl`.
    - **APIs**: Documented new Coordinator endpoints for tour instance lifecycle management.
    - **Caching**: Documented hybrid caching strategy (Redis + local Spring Cache).
    - **Infrastructure**: Documented production Docker configurations.
- **New Page**: [[full-text-search]].
- **Pages Updated**: [[travery-backend]], [[monitoring-stack]], [[index]].

## [2026-05-15] Lint | Maintenance & Consolidation
- **Action**: Cleaned up redundant entities and fixed broken links identified during cross-referencing with the database schema.
- **Key Changes**:
    - **Consolidation**: Deleted `TourBookingMember` (use [[BookingMember]]) and `Vehicle` (use [[Coach]]).
    - **Dead Link Fixes**: Re-mapped `[[SLA]]` to [[service-level-agreement]].
    - **Cross-Referencing**: Linked [[full-text-search]] from [[Tour]] and [[travery-backend]]. Linked [[otp-management]] from [[otp]].
    - **Metadata**: Linked [[hoang-duc-chinh]] (Lead Developer) as the primary contact in [[travery-backend]].
- **Pages Updated**: [[index]], [[travery-system-docs]], [[otp]], [[travery-backend]], [[Tour]].
