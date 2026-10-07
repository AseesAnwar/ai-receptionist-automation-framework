# Interview Walkthrough

## 30-second version

> I built an AI receptionist automation concept for appointment-based businesses using Vapi and Twilio for voice, Make.com for orchestration, Cal.com for scheduling, Airtable as a lightweight CRM, and Outlook for notifications. I later audited the original workflow and found reliability issues such as weak booking identification, hard-coded availability handling and limited error paths. I redesigned it into a modular V2 framework centred on booking UIDs, deterministic calendar logic and safer failure handling.

## What I would show

1. Architecture diagram in the README.
2. Legacy audit and the concrete problems found.
3. Make V2 scenario structure.
4. Booking UID model.
5. Testing and error-handling plan.

## Business value

- reduces repetitive reception work
- provides 24/7 appointment handling
- standardises booking workflows
- automatically updates operational systems
- gives a clear audit trail

## Engineering discussion points

- Why Cal.com is the source of truth
- Why names are unsafe appointment identifiers
- Why the AI agent should not invent calendar state
- Why CRM/email failure is different from booking failure
- How tool-call confirmation reduces accidental state changes
