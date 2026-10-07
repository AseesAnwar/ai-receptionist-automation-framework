# Testing Plan

Use only synthetic customers and test accounts.

## Unit / scenario tests

### Availability
- free slot
- occupied slot
- no nearby slots
- daylight-saving transition
- malformed datetime
- invalid event type

### Booking
- successful booking
- slot becomes unavailable before booking
- missing email
- Cal.com timeout
- CRM failure after successful booking
- notification failure after successful booking

### Reschedule
- correct booking UID
- invalid booking UID
- target slot unavailable
- successful reschedule updates CRM and email

### Cancellation
- correct UID
- already-cancelled booking
- explicit confirmation required
- CRM mirrors final state

## End-to-end voice tests

1. Call Twilio number.
2. Ask for availability.
3. Select one returned slot.
4. Confirm booking.
5. Verify Cal.com.
6. Verify Airtable UID and status.
7. Verify email.
8. Call again and reschedule.
9. Verify all systems.
10. Call and cancel.
11. Verify all systems.

## Acceptance criteria

No workflow is considered production-ready until:
- calendar action and spoken result always agree
- wrong-customer booking mutation cannot be reproduced
- error paths return safe responses
- synthetic end-to-end tests pass repeatedly
