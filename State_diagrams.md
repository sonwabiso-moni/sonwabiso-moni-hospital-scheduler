# Hospital Scheduler System – State Transition Diagrams

This document includes state transition diagrams for 8 critical objects in the Hospital Scheduler System. Each diagram follows UML standards using Mermaid and is linked to specific functional requirements from Assignment 4.

---

## 1. Appointment State Diagram

```mermaid
stateDiagram-v2
    [*] --> Requested
    Requested --> Approved : Admin approves
    Requested --> Cancelled : User cancels
    Approved --> CheckedIn : Patient checks in
    CheckedIn --> Completed : Doctor marks as complete
    Approved --> Cancelled : User cancels
    CheckedIn --> Cancelled : No-show or user cancels


## 2.User Account State Diagram

```mermaid
stateDiagram-v2
    [*] --> Registered
    Registered --> Active : Email verified
    Registered --> Inactive : Verification expired
    Active --> Suspended : Admin suspends
    Suspended --> Reactivated : Admin reactivates
    Active --> Deleted : User deletes account

## 3. Doctor Profile State Diagram

```mermaid
stateDiagram-v2
    [*] --> Created
    Created --> Verified : Admin verifies credentials
    Verified --> Active : Profile published
    Active --> OnLeave : Doctor takes leave
    OnLeave --> Active : Returns from leave
    Active --> Archived : Doctor leaves hospital

## 4. Patient Record State Diagram

```mermaid
stateDiagram-v2
    [*] --> Created
    Created --> Updated : New information added
    Updated --> Archived : Patient is discharged
    Archived --> Reactivated : Patient returns

## 5. Payment State Diagram

```mermaid
stateDiagram-v2
    [*] --> Pending
    Pending --> Completed : Payment successful
    Pending --> Failed : Payment declined
    Failed --> Retried : User retries payment
    Retried --> Completed : Payment successful


## 6. Notification State Diagram

```mermaid
stateDiagram-v2
    [*] --> Generated
    Generated --> Sent : Notification dispatched
    Sent --> Read : User views it
    Sent --> Expired : User does not read within time
    Read --> Archived : For historical reference
    
 ## 7. Prescription State Diagram

```mermaid   
stateDiagram-v2
    [*] --> Draft
    Draft --> Issued : Doctor finalizes prescription
    Issued --> Fulfilled : Patient collects medication
    Issued --> Cancelled : Doctor cancels or edits prescription

 ## 8. Room Booking State Diagram

```mermaid   
stateDiagram-v2
    [*] --> Available
    Available --> Booked : Appointment scheduled
    Booked --> InUse : Occupied by patient
    InUse --> Cleaned : Post-discharge
    Cleaned --> Available : Ready for next patient
