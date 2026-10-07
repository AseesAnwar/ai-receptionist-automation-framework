# Make.com Scenario Overview

The V2 project is grouped in the Make folder **02 - AI Receptionist**.

## V2 scenario scaffolds

| Scenario | Purpose | Current state |
|---|---|---|
| AI Receptionist V2 - Core Tool Router | Webhook entry point and intent/tool routing | Scaffold only; inactive |
| AI Receptionist V2 - Check Availability | Deterministic availability + alternatives | Scaffold only; inactive |
| AI Receptionist V2 - Appointment Booking | Create booking + persist UID | Scaffold only; inactive |
| AI Receptionist V2 - Manage Booking | Reschedule/cancel by booking UID | Scaffold only; inactive |
| AI Receptionist V2 - Notifications | Customer confirmations | Scaffold only; inactive |

The legacy **AI Receptionist** scenario remains unchanged as a reference implementation while V2 is developed.

## Why split the project

The original scenario contained multiple business processes in one large router. V2 separates stable responsibilities so each path can be tested independently and reused.

The split is deliberately small; the objective is maintainability, not creating unnecessary scenarios.
