## 2. Use Case Specifications

### Use Case 1: Register Patient Account
**Actor:** Patient  
**Description:** Allows a patient to create an account.  
**Preconditions:** The patient has not registered before.  
**Postconditions:** The patient has a valid account.  
**Basic Flow:**
1. Patient enters personal details.
2. System validates information.
3. System creates an account.
4. Confirmation message is sent.

**Alternative Flow:**
- If the email already exists, an error is displayed.

### Use Case 2: Book Appointment
**Actor:** Patient  
**Description:** Allows a patient to book an appointment with a doctor.  
**Preconditions:** The patient is registered and logged in.  
**Postconditions:** An appointment is scheduled.  
**Basic Flow:**
1. Patient selects doctor, date, and time.
2. System checks availability.
3. System confirms appointment.
4. Patient receives a confirmation.

**Alternative Flow:**
- If the doctor is unavailable, the system prompts the user to select another slot.

### Use Case 3: View Doctor Schedule
**Actor:** Doctor  
**Description:** Allows doctors to view their scheduled appointments.  
**Preconditions:** The doctor is logged in.  
**Postconditions:** The doctor sees an updated schedule.  let
**Basic Flow:**
1. Doctor logs in.
2. System retrieves the doctor’s schedule.
3. Schedule is displayed.