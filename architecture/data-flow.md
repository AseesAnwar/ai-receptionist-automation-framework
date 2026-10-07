# Call and Data Flow

## Check availability

1. Caller asks for a time.
2. Vapi sends a structured `checkAvailability` tool call.
3. Make validates required fields.
4. Make queries Cal.com for the requested window.
5. If free, Make returns an available response.
6. If unavailable, Make queries nearby slots and returns two alternatives.
7. Vapi converts the structured result into natural speech.

## Book appointment

1. Caller selects a confirmed time.
2. Vapi repeats key details before committing.
3. Make sends the booking request to Cal.com.
4. Cal.com returns a successful booking and UID.
5. Make writes the UID and booking details to Airtable.
6. Make sends a confirmation email.
7. Make returns success to Vapi only after the calendar action succeeds.

## Reschedule / cancel

1. Customer is identified using booking UID, email or phone.
2. Make resolves the exact booking.
3. State change is performed in Cal.com.
4. Airtable is updated.
5. Notification is sent.
6. Make returns the final result to Vapi.

## Data minimisation

The public framework assumes only operational appointment data:
- name
- email
- phone
- appointment type
- appointment date/time
- booking UID
- booking status

Clinical notes and sensitive medical information are out of scope.
