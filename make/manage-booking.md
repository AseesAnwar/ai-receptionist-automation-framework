# Manage Booking

## Supported actions

- reschedule
- cancel

## Identification

Preferred:
1. booking UID
2. verified email / phone to locate the UID
3. never customer name alone

## Reschedule

- fetch exact booking
- validate new requested time
- reschedule using current Cal.com API
- update Airtable status and appointment datetime
- notify customer
- return the new appointment details

## Cancel

- fetch exact booking
- request explicit caller confirmation
- cancel using current Cal.com API
- update Airtable status to Cancelled
- notify customer
- return cancellation result
