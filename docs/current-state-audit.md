# Legacy Configuration Audit

The existing Make.com **AI Receptionist** prototype was reviewed module-by-module.

## What already worked conceptually

- webhook entry point
- tool-based routing
- availability checking
- booking creation
- rescheduling
- cancellation
- Airtable CRM records
- Outlook confirmations
- webhook responses to the AI layer

## Risks found

### Incorrect availability route condition
The availability route appeared to compare a phone value with `checkAvailability`, rather than routing on the function/tool name.

### Hard-coded date key
Alternative-slot logic referenced a specific date key in a returned slots object. This would not generalise across customer requests.

### Availability mixed with CRM lookup
Airtable email existence was involved in the available/unavailable branch, although CRM presence is not proof that a calendar time is occupied.

### Mixed API versions
The prototype mixed Cal.com v1 and v2 calls. V2 should revalidate every endpoint against current provider documentation.

### Weak appointment identity
Reschedule/cancel flows relied heavily on customer lookup and iteration rather than a stored unique booking UID.

### Customer lookup by name
Airtable searches used customer name in places. Names are not unique.

### Reschedule email mapping
The reschedule notification appeared to reference the original preferred datetime instead of the new rescheduled datetime.

### Timezone inconsistency
Both Australia/Melbourne and Australia/Sydney appeared in configuration.

### Service type mapping inconsistency
The service type mapping referenced a differently named tool-call collection than other variables, which may produce empty values.

### Limited error handling
The prototype had no robust strategy for API failure, booking conflicts, notification failures or reconciliation.

### Disconnected test modules
Google Calendar / Gmail modules remained outside the main flow and one had a configuration issue.

## Audit outcome

The original scenario is retained unchanged as a historical/reference implementation. The V2 design addresses these issues without claiming completion until tested.
