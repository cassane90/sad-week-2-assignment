# Healthcare Portal: Patient Care User Stories

## User Story 1: Patient Reschedules an Appointment

**As a** patient,  
**I want to** reschedule my appointment to another available time,  
**So that** I can change my appointment without calling the hospital.

### Acceptance Criteria

```gherkin
Scenario: Patient reschedules an appointment
Given the patient has a scheduled appointment
When the patient selects another available time and confirms the change
Then the system should update the appointment
And display a confirmation with the new appointment details
```

## User Story 2: Receptionist Checks In a Patient

**As a** receptionist,  
**I want to** mark an arriving patient as checked in,  
**So that** staff can see that the patient is waiting.

### Acceptance Criteria

```gherkin
Scenario: Receptionist checks in a patient
Given the patient has an appointment for today
When the receptionist selects Check In
Then the system should mark the patient as checked in
And record the arrival time
```
