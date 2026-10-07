# Check Availability

## Goal

Determine whether a requested appointment time is actually available in Cal.com and, if not, return nearby alternatives.

## V2 design

Inputs:
- `preferredDateTime`
- `eventTypeId`

Outputs:
- `available`
- `option_1`
- `option_2`
- `message`
- `status`

## Rules

- Do not use Airtable customer records as a proxy for calendar availability.
- Do not hard-code date keys when reading availability results.
- Prefer deterministic date arithmetic and Cal.com responses over LLM reasoning.
- Normalize all timestamps to the chosen clinic timezone.
- Alternatives should be valid slots returned by the scheduling provider, not generated times.
