# Vehicle

Represents a vehicle used for transporting passengers during a [[TourInstance]].

## Key Fields
- `licensePlate`: Unique registration plate.
- `vehicleType`: Category of the vehicle (e.g., Bus, Minivan).
- `totalSeats`: Capacity of the vehicle.
- `floorCount`: Number of floors (e.g., double-decker).
- `status`: Availability status (VehicleStatus).

## Relationships
- Assigned to [[TourInstance]] departures.
