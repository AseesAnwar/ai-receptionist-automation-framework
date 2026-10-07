# Cal.com Booking Model

## Source of truth

Cal.com is treated as the authoritative booking calendar.

## Required booking fields

- event type
- start datetime
- attendee name
- attendee email
- timezone
- booking UID returned by Cal.com

## UID strategy

Store the provider booking UID in Airtable immediately after successful creation.

All future state-changing operations should target that UID.

## API policy

The V2 implementation should use currently supported Cal.com API endpoints and versions. Do not copy deprecated v1 calls from the legacy prototype without revalidating them against current Cal.com documentation.
