# Airtable CRM Schema

Suggested **Appointments / Customers** fields:

| Field | Type | Purpose |
|---|---|---|
| Customer Name | Text | Display |
| Email Address | Email | Contact / lookup |
| Phone Number | Phone | Contact / lookup |
| Appointment Type | Text | Service requested |
| Appointment Date | Date/time | Current appointment |
| Status | Single select | Scheduled / Rescheduled / Cancelled |
| Booking UID | Text, unique | Cal.com canonical identifier |
| Created At | Date/time | Audit |
| Updated At | Date/time | Audit |

## Important

Do not use **Customer Name** as the unique booking key.

For production healthcare use, verify privacy, retention and regulatory obligations before storing patient information. This portfolio schema intentionally excludes clinical data.
