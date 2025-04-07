# Hospital Scheduler System – Activity Diagrams

This document contains activity diagrams for 8 key workflows in the Hospital Scheduler System. Each activity diagram follows UML standards using Mermaid and maps to relevant functional requirements from Assignment 4.

---

## 1. Book Appointment Workflow

```mermaid
%%{init: {'theme': 'default'}}%%
flowchart TD
    Start([Start]) --> EnterDetails[User enters appointment details]
    EnterDetails --> SelectDoctor[Select doctor and date]
    SelectDoctor --> Validate[System validates availability]
    Validate -->|Available| Confirm[User confirms booking]
    Validate -->|Not Available| Retry[User reselects doctor/date]
    Confirm --> Save[System saves appointment]
    Save --> SendNotification[Send confirmation email]
    SendNotification --> End([End])
```

**Explanation**:
- Aligns with FR-001: Allow users to book appointments.
- Ensures availability check and real-time confirmation to meet patient expectations.

---

## 2. Register New Patient Workflow

```mermaid
flowchart TD
    Start([Start]) --> EnterInfo[User enters personal info]
    EnterInfo --> UploadDocs[Upload ID and medical aid]
    UploadDocs --> Validate[System validates documents]
    Validate -->|Valid| CreateAccount[Create patient account]
    Validate -->|Invalid| Notify[Notify user of issues]
    CreateAccount --> SendWelcome[Send welcome email]
    SendWelcome --> End([End])
```

**Explanation**:
- Supports FR-002: New patient onboarding with proper verification.
- Branching ensures only valid users are registered.

---

## 3. Doctor Login and Availability Setup

```mermaid
flowchart TD
    Start([Start]) --> Login[Doctor logs in]
    Login --> VerifyCredentials[System verifies credentials]
    VerifyCredentials -->|Valid| SetupAvailability[Set weekly availability]
    VerifyCredentials -->|Invalid| Error[Show login error]
    SetupAvailability --> Confirm[Save to system]
    Confirm --> End([End])
```

**Explanation**:
- FR-004: Doctors should manage their availability.
- Login ensures only authorized users can modify slots.

---

## 4. Cancel Appointment Workflow

```mermaid
flowchart TD
    Start([Start]) --> Login[User logs in]
    Login --> ViewAppointments[View upcoming appointments]
    ViewAppointments --> SelectCancel[Select an appointment to cancel]
    SelectCancel --> ConfirmCancel[User confirms cancellation]
    ConfirmCancel --> UpdateStatus[Update appointment status]
    UpdateStatus --> NotifyDoctor[Notify doctor]
    NotifyDoctor --> End([End])
```

**Explanation**:
- FR-005: Enable users to cancel appointments.
- Keeps all parties notified and updates system data integrity.

---

## 5. Check-in Patient Workflow

```mermaid
flowchart TD
    Start([Start]) --> Arrive[Patient arrives]
    Arrive --> VerifyID[Reception verifies ID]
    VerifyID --> UpdateStatus[Update appointment to "Checked In"]
    UpdateStatus --> NotifyDoctor[Notify doctor]
    NotifyDoctor --> End([End])
```

**Explanation**:
- FR-006: Patients must check in before consultation.
- Keeps real-time appointment status updated for doctors.

---

## 6. Complete Consultation Workflow

```mermaid
flowchart TD
    Start([Start]) --> DoctorReview[Doctor opens patient file]
    DoctorReview --> AddNotes[Add consultation notes]
    AddNotes --> PrescribeMedication[Optionally prescribe meds]
    PrescribeMedication --> MarkComplete[Mark appointment complete]
    MarkComplete --> UpdateSystem[System updates status]
    UpdateSystem --> End([End])
```

**Explanation**:
- FR-007: Document consultations and prescribe.
- Ensures a clean wrap-up of the appointment lifecycle.

---

## 7. Generate and Send Notification

```mermaid
flowchart TD
    Start([Start]) --> TriggerEvent[Trigger: booking/cancellation/reminder]
    TriggerEvent --> CreateNotification[Generate notification message]
    CreateNotification --> DetermineChannel[Email/SMS/Push]
    DetermineChannel --> Send[Dispatch notification]
    Send --> Log[Log in user communication history]
    Log --> End([End])
```

**Explanation**:
- FR-009: Automatic notifications.
- Parallel-ready for multiple channels, addresses scalability.

---

## 8. Process Payment Workflow

```mermaid
flowchart TD
    Start([Start]) --> ChooseMethod[Patient selects payment method]
    ChooseMethod --> ValidatePayment[System processes payment]
    ValidatePayment -->|Success| ConfirmPayment[Send receipt + update]
    ValidatePayment -->|Failure| NotifyFailure[Notify and retry option]
    ConfirmPayment --> End([End])
    NotifyFailure --> End([End])
```

**Explanation**:
- FR-008: Payment system with success/failure handling.
- Improves UX by offering retry logic for failed payments.