# TourBookingMember

Represents an individual person (adult or child) included in a [[TourBooking]].

## Key Fields
- `fullName`: Full name of the member.
- `identityNumber`: Passport or ID card number.
- `identityType`: Type of identification (IdentityType).
- `isChild`: Flag indicating if the member is a child.
- `status`: Individual status (TourBookingMemberStatus).

## Relationships
- `tourBooking`: The parent [[TourBooking]] this member belongs to.
