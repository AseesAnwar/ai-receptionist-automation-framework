# Implementation Guide

## Phase 1 — Accounts

1. Obtain a test-capable Twilio number.
2. Configure a Vapi assistant.
3. Connect/import the number into Vapi according to current provider instructions.
4. Use test Cal.com, Airtable and email resources.

## Phase 2 — Voice-agent contract

Define four tools:
- checkAvailability
- bookAppointment
- rescheduleAppointment
- cancelAppointment

Point test tool calls to the V2 Make webhook and capture one real payload so mappings are based on observed data.

## Phase 3 — Make V2

Implement in this order:
1. availability
2. booking
3. manage booking
4. notifications
5. core router
6. error and audit handling

## Phase 4 — Validation

Run the test plan with synthetic customers only. Compare Make executions against actual Cal.com and Airtable state.

## Phase 5 — Portfolio evidence

Capture:
- sanitized Make scenario screenshots
- architecture diagram
- synthetic test results
- optional short demo video

Never publish API keys, account SIDs, auth tokens, real phone numbers, webhook secrets, real customer data or unredacted execution payloads.
