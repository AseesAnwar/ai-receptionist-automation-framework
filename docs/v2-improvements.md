# V2 Improvements

| Legacy risk | V2 approach |
|---|---|
| One large scenario | Small modular scenario set |
| Tool route mapping bug | Validate and route on explicit tool/function name |
| Hard-coded availability date | Dynamic requested date/time |
| CRM used in availability decision | Cal.com only for scheduling truth |
| Customer name lookup | Booking UID first |
| Mixed timezones | Australia/Melbourne consistently |
| Mixed/deprecated API calls | Revalidate current Cal.com API endpoints |
| LLM used for deterministic time logic | Deterministic date/API logic where possible |
| Weak error handling | Explicit failure outcomes + reconciliation |
| False-success risk | Return success only after calendar mutation succeeds |
| No clear audit identifier | Persist booking UID and outcome timestamps |

## Additional V2 principle

Use AI for conversation and language understanding; use deterministic APIs and rules for calendar state.
