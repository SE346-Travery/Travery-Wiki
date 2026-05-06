# OTP Management

The system employs One-Time Passwords (OTP) for critical actions like registration verification and password resets.

## Mechanism
- **Generation**: `OtpService` generates a random 6-digit numeric code.
- **Storage**: OTPs are stored in **Redis** with a defined TTL (Time-To-Live), ensuring they expire automatically.
- **Verification**:
    - The system uses a **Lua script** in Redis for atomic verification.
    - This script checks the OTP, increments attempt counters, and deletes the OTP upon success or too many failed attempts to prevent brute-force attacks.
- **Rate Limiting**:
    - `OtpService` enforces a resend cooldown period.
    - A separate rate limit window (e.g., 1 hour) restricts the total number of OTP requests per user to prevent spam.

## Redis Keys
- `otp:register:{email}`: Stores hashed OTP for registration.
- `otp:password-reset:{email}`: Stores hashed OTP for password reset.
- `otp:attempt:{email}`: Tracks failed verification attempts.
- `otp:resend:{email}`: Enforces resend cooldown.
