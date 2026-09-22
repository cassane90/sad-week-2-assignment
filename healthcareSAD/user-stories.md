# Healthcare Portal: Patient Care User Stories

## User Story 1: Patient Reschedules an Appointment

**As a** patient,  
**I want to** move my appointment to another available time,  
**So that** I can change my booking without calling the hospital.

### Acceptance Criteria

#### Scenario: Rescheduling an appointment

```gherkin
Given I have a scheduled appointment
When I select another available time and confirm the change
Then the system should reserve the new slot
And release the original slot
And send an "AppointmentRescheduled" event to the Notification Service
And display a confirmation with the updated appointment details
```

#### Scenario: Rescheduling shortly before the appointment

```gherkin
Given I have a scheduled appointment
And the appointment is 12 hours away
When I successfully reschedule the appointment
Then the system should apply a late-change flag
And send an "AppointmentRescheduled" event to the Notification Service
And display a confirmation with the updated appointment details
```

## User Story 2: Receptionist Records a Patient's Arrival

**As a** receptionist,  
**I want to** mark an arriving patient as checked in,  
**So that** staff can see who is waiting without me calling each nurse.

### Acceptance Criteria

#### Scenario: Checking in a patient

```gherkin
Given I am logged in as a receptionist
And the patient has an appointment today
When I find the appointment and select Check In
Then the system should mark the appointment as Checked In
And record the arrival time
And display the patient on the waiting list for today's appointments
```

#### Scenario: Patient has already checked in

```gherkin
Given the appointment is already marked as Checked In
When I try to check in the same appointment again
Then the system should show that the patient is already checked in
And keep the original arrival time
```

## Measuring the Benefits

- Count appointment changes completed without a phone call.
- Count calls needed to inform nurses that patients have arrived.

## Proposed Rule

Each appointment can only be checked in once.
