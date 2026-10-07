# Notifications

Notifications are separated from calendar actions so delivery problems do not corrupt appointment state.

## Types

- booking confirmation
- reschedule confirmation
- cancellation confirmation

## Requirements

- use the actual confirmed appointment time from Cal.com
- use the rescheduled time after a reschedule, not the previous requested time
- include only necessary customer information
- notification failure should be logged and retried independently
