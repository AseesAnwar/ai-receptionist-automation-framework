# Error-Handling Strategy

## Principle

A conversational system must never claim an action succeeded when the underlying scheduling action failed.

## Failure classes

### Validation failure
Examples: missing email, malformed timestamp, unknown tool name.

Response: return a safe tool result requesting the missing information. Do not call downstream systems.

### Scheduling conflict
The slot was available during conversation but became unavailable before booking.

Response: do not create a CRM record as booked. Query alternatives and ask the caller to choose again.

### Cal.com/API failure
Response: return a temporary-failure message, log the error, and avoid a false success response.

### CRM failure after booking success
Calendar booking remains valid. Record a reconciliation task/error so CRM can be repaired later. Do not cancel a legitimate appointment solely because the mirror failed.

### Notification failure after booking success
Booking remains valid. Retry or flag notification delivery separately.

## Recommended Make behaviour

- Use error handlers for external APIs where failure changes the customer outcome.
- Store failed bundles where a retry is useful.
- Add an audit record containing request type, outcome, timestamp and booking UID.
- Keep error responses generic; never expose API keys, internal stack traces or provider details to the caller.
