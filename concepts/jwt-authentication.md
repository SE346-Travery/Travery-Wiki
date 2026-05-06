# JWT Authentication

Travery uses JSON Web Tokens (JWT) for secure, stateless authentication and session management.

## Flow
1. **Token Generation**: Upon successful login, the `JwtService` generates two tokens:
   - **Access Token**: Short-lived token for authorizing API requests.
   - **Refresh Token**: Long-lived token stored in the database ([[RefreshToken]]) used to obtain new access tokens.
2. **Authorization**: The `JwtAuthenticationFilter` intercepts every incoming request:
   - Extracts the Bearer token from the `Authorization` header.
   - Validates the token's signature, expiry, and type using `JwtService`.
   - Checks if the token's JTI (JWT ID) is blacklisted via `TokenBlacklistService`.
   - If valid, populates the `SecurityContextHolder` with user details.

## Components
- `JwtService`: Core logic for generating, parsing, and validating tokens.
- `JwtAuthenticationFilter`: Spring Security filter for processing JWTs on each request.
- `TokenBlacklistService`: Uses **Redis** to store invalidated JTIs (e.g., after logout) until their original expiry time.
- `RefreshTokenService`: Manages the lifecycle of [[RefreshToken]] entities, including persistence and revocation.
