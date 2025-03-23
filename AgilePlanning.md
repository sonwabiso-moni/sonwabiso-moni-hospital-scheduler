
# Agile Planning Document for Hospital Appointment Scheduler

## 1. User Stories

| Story ID | User Story                                                                 | Acceptance Criteria                                                                 | Priority |
|----------|----------------------------------------------------------------------------|-------------------------------------------------------------------------------------|----------|
| US-001   | As a patient, I want to register an account so that I can book appointments. | Registration form must validate input, store data securely, and send confirmation email. | High     |
| US-002   | As a patient, I want to log in securely so that I can access my appointments. | Login should support encryption (e.g., AES-256) and multi-factor authentication (e.g., SMS). | High     |
| US-003   | As a patient, I want to book an appointment with a doctor so that I can receive medical consultation. | System should check availability, prevent double bookings, and send booking confirmation. | High     |
| US-004   | As a patient, I want to cancel my appointment so that I can reschedule if needed. | System should allow cancellation up to 24 hours before the appointment. | Medium   |
| US-005   | As a doctor, I want to view my schedule so that I can manage my appointments. | System should fetch and display an updated schedule.                              | High     |
| US-006   | As an admin, I want to manage users so that I can control system access. | Admins can add, modify, or remove users with role-based access control.            | High     |
| US-007   | As a system, I want to send automated reminders so that patients don’t miss appointments. | Notifications must be sent 24 hours before the appointment.                         | High     |
| US-008   | As a hospital IT staff, I want secure encryption of patient data so that we meet compliance standards. | System must use AES-256 encryption for data storage and comply with HIPAA standards. | High     |
| US-009   | As a patient, I want to recover my password if I forget it.                 | The system must provide an option for password recovery via email or SMS.          | Medium   |
| US-010   | As a patient, I want to see available doctors by specialty so I can choose the right one. | System should display doctors by specialty and their availability.                | Medium   |

## 2. Product Backlog

| Story ID | User Story                                      | Priority (MoSCoW) | Effort Estimate | Dependencies                | Risk         |
|----------|-------------------------------------------------|-------------------|-----------------|-----------------------------|--------------|
| US-001   | Register patient account                        | Must-have         | 3               | None                        | Low          |
| US-002   | Secure patient login                            | Must-have         | 3               | US-001                      | Low          |
| US-003   | Book an appointment                             | Must-have         | 5               | US-001, US-002               | Low          |
| US-004   | Cancel appointment                              | Should-have       | 2               | US-003                      | Medium       |
| US-005   | View doctor schedule                            | Must-have         | 3               | US-003                      | Low          |
| US-006   | Manage users                                    | Must-have         | 4               | US-001, US-002               | Low          |
| US-007   | Send automated reminders                        | Should-have       | 4               | US-003                       | Medium       |
| US-008   | Encrypt patient data                            | Must-have         | 5               | None                        | High         |
| US-009   | Password recovery                               | Should-have       | 3               | US-002                      | Medium       |
| US-010   | View available doctors by specialty             | Should-have       | 3               | US-003                      | Medium       |

## 3. Sprint Planning

### Sprint Goal: Implement core functionalities for patient registration, login, and appointment booking.

### Sprint Backlog

| Task ID | Task Description                                  | Assigned To   | Estimated Hours | Status   |
|---------|---------------------------------------------------|---------------|-----------------|----------|
| T-001   | Develop registration form                         | Dev Team      | 8               | To Do    |
| T-002   | Implement secure login system                      | Dev Team      | 10              | To Do    |
| T-003   | Design appointment booking UI                     | UI Team       | 6               | To Do    |
| T-004   | Develop backend logic for booking appointments    | Backend Team  | 10              | To Do    |
| T-005   | Set up appointment database schema                | DevOps Team   | 5               | To Do    |
| T-006   | Implement password recovery system                | Dev Team      | 4               | To Do    |
| T-007   | Configure encryption for patient data storage     | DevOps Team   | 8               | To Do    |

### Sprint Duration: 2-week sprint

### Team Capacity: 4 developers (80 hours total)

### Definition of Done:
- Code reviewed and approved.
- Unit tests written and passed.
- Deployed to staging environment.
- Documentation updated.

## 4. Reflection

The biggest challenge in prioritization was balancing usability and security. While encryption is critical, ensuring a smooth user experience (e.g., login and booking) remains a priority. Effort estimation was difficult due to varying task complexities, but using the Fibonacci sequence helped provide clearer guidance.

Stakeholder alignment was initially challenging, as certain features like reminders (US-007) were considered more urgent. However, by emphasizing compliance requirements (US-008), we were able to shift focus toward encryption.

In the next sprint, we’ll involve hospital staff earlier to gather feedback and ensure the system meets their real-world needs. Additionally, we'll focus on scalability and load testing to ensure the system can handle a large number of concurrent users.

### Scalability Considerations:
As the system will eventually need to scale to handle thousands of patients, we will add a user story in a future sprint for load testing. This will help ensure that the system can support peak times (e.g., 1,000 concurrent users).


