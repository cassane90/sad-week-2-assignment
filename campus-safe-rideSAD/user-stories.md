# Campus Safe Ride System: User Stories

## User Story 1: Student Requests a Safe Ride

**As a** student,  
**I want to** request a ride between campus locations,  
**So that** I can travel without walking alone at night.

### Acceptance Criteria

```gherkin
Scenario: Student requests a safe ride
Given the student is logged in
And the Safe Ride service is available
When the student enters a pickup location and destination
And confirms the request
Then the system should create the ride request
And display a confirmation to the student
```

## User Story 2: Driver Accepts a Ride Request

**As a** driver,  
**I want to** accept an available ride request,  
**So that** I can pick up the student and take them to their destination.

### Acceptance Criteria

```gherkin
Scenario: Driver accepts a ride request
Given the driver is logged in
And an available ride request exists
When the driver accepts the request
Then the system should assign the ride to the driver
And update the ride status to Assigned
```
