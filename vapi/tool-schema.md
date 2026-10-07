# Vapi Tool Interface

This file documents the intended contract. Exact Vapi schemas should be validated against the account configuration before deployment.

## checkAvailability

Expected arguments:
```json
{
  "preferredDateTime": "2026-10-20T15:00:00+11:00",
  "eventTypeId": 123456
}
```

## bookAppointment

```json
{
  "name": "Synthetic Customer",
  "email": "demo@example.com",
  "phone": "+61000000000",
  "serviceType": "Initial consultation",
  "preferredDateTime": "2026-10-20T15:00:00+11:00",
  "eventTypeId": 123456
}
```

## rescheduleAppointment

```json
{
  "booking_uid": "example-booking-uid",
  "rescheduledDateTime": "2026-10-21T11:30:00+11:00"
}
```

## cancelAppointment

```json
{
  "booking_uid": "example-booking-uid"
}
```

## Response contract

The Make webhook should return the result associated with the same Vapi tool-call identifier.

Example conceptual response:
```json
{
  "results": [
    {
      "toolCallId": "tool-call-id",
      "result": "Appointment booked for Tuesday at 3:00 PM."
    }
  ]
}
```

Never expose credentials or raw provider error payloads.
