# Appointment Booking

## Goal

Create one confirmed appointment and persist its unique identifier.

## Required inputs

- customer name
- email
- phone
- service type
- preferred date/time
- Cal.com event type ID

## V2 transaction order

1. Validate the request.
2. Create booking in Cal.com.
3. Capture booking UID.
4. Create/update CRM appointment record with UID.
5. Send confirmation.
6. Return success to the voice agent.

## Key design improvement

The original workflow stored customer and appointment information but did not make the booking UID the central identifier. V2 does.

That UID enables exact rescheduling and cancellation without relying on names.
