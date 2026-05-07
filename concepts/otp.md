# Concept: OTP (One-Time Password)

## Definition
A security mechanism used by [[travery]] to verify user identity during account registration and password resets.

## Technical Details
- **Length**: Typically 6 digits.
- **TTL (Time To Live)**: 5 minutes.
- **Rate Limiting**: Includes cooldowns between resend requests and maximum attempts to prevent brute force attacks.
- **Implementation**: Managed using Redis for fast access and temporary storage.

## Workflow
1. **Trigger**: User signs up or requests a password reset.
2. **Generation**: Backend generates a random 6-digit code.
3. **Delivery**: Sent via Email Service.
4. **Verification**: User enters the code; backend verifies against the hashed version stored in Redis.

## References
- [[travery-system-docs]]
- [[travery-backend]]
