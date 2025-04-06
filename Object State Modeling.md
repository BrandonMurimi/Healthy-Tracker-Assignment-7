
The critical objects in your system
1. User Account Object
![Screenshot 2025-04-06 190346](https://github.com/user-attachments/assets/6f73e560-8aa6-4d6a-a6a4-1763bb8f0ded)
Explanation:

Key States: Unregistered, Registered, Active, Suspended, Banned

Transitions:

Registration requires email verification (FR-006)

Auto-suspension after inactivity (NFR-003)

Permanent ban for violations (FR-006)

Guards:

verifyEmail() requires valid email confirmation

reactivateAccount() requires admin approval

2. Fitness Activity Object
![Screenshot 2025-04-06 190859](https://github.com/user-attachments/assets/a9bd04ec-54d7-4f93-8325-0a9d533e0f54)
Explanation:

Key States: Draft, Recorded, Processing, Analyzed, Error

Transitions:

Manual save vs auto-sync from wearables (FR-004)

Data validation during processing (FR-001)

Guards:

submitForAnalysis() requires minimum 50 steps

completeAnalysis() depends on server availability

3. Wearable Device Connection
![Screenshot 2025-04-06 191638](https://github.com/user-attachments/assets/2e997546-6f32-4736-b96d-56f1e95643e6)

   Explanation:

Key States: Disconnected, Connecting, Connected, Syncing, Failed

Transitions:

Secure pairing flow (FR-004, FR-009)

Auto-timeout for security (NFR-002)

Guards:

authenticationSuccess() requires valid OAuth token

syncComplete() needs ≥80% battery on wearable

4. Fitness Goal Object
![Screenshot 2025-04-06 192838](https://github.com/user-attachments/assets/8839cc2f-6696-4253-a073-fa2350dc726e)

Explanation:

Key States: Setup, Active, Achieved, Failed, Paused

Transitions:

Smart start date handling (FR-003)

Auto-archiving to reduce clutter (FR-005)

Guards:

targetReached() validates against sensor data

userPause() limited to 3x/month

5. Notification Object
![Screenshot 2025-04-06 193007](https://github.com/user-attachments/assets/a6619719-777f-4f23-b959-241a53da5d26)

Explanation:

Key States: Queued, Sending, Delivered, Read, Failed

Transitions:

Retry mechanism for failures (FR-008)

Engagement tracking (FR-007)

Guards:

retry() attempts max 3 times

processNotification() checks user preferences

6. System Report Object
![Screenshot 2025-04-06 193312](https://github.com/user-attachments/assets/7f6f388c-0b17-44f4-ace4-abf7265a38b8)

Explanation:

Key States: Requested, Generating, Ready, Partial, Downloaded

Transitions:

Handles missing data gracefully (FR-005)

Auto-cleanup of old reports (NFR-001)

Guards:

dataCompiled() requires ≥90% data availability

missingDataReceived() waits max 24h

7. Payment Subscription
![Screenshot 2025-04-06 193437](https://github.com/user-attachments/assets/f8cfb61c-fa64-49d3-845d-88e306f5ddeb)

Explanation:

Key States: Trial, Active, Renewing, Expired

Transitions:

Grace period for renewals (FR-010)

Early renewal reminders (FR-008)

Guards:

paymentProcessed() validates card details

renewWithin30Days() applies late fee

8. API Request Object
![Screenshot 2025-04-06 193631](https://github.com/user-attachments/assets/f823dc7d-ce21-4ceb-9cfc-17e4e6206eff)

Explanation:

Key States: Pending, Processing, Completed, RateLimited, Failed

Transitions:

Rate limiting implementation (NFR-010)

Quick fail for invalid requests (FR-009)

Guards:

authenticate() checks JWT validity

wait() duration scales with violation count

How This Maps to Requirements

## **State Diagrams to Requirements Mapping**

| Diagram                  | Related FR  | Key Coverage                              | Non-Functional Coverage       |
|--------------------------|-------------|-------------------------------------------|-------------------------------|
| **User Account**         | FR-006      | Account lifecycle controls                | NFR-003 (Inactivity handling) |
| **Fitness Activity**     | FR-001      | Step recording validation                 | NFR-004 (Data validation)     |
| **Wearable Connection**  | FR-004      | Secure pairing workflow                   | NFR-002 (Security)            |
| **Fitness Goal**         | FR-003      | Achievement tracking logic                | NFR-005 (UX feedback)         |
| **Notification**         | FR-007/008  | Delivery reliability & user engagement    | NFR-006 (Performance)         |
| **System Report**        | FR-005      | Data completeness handling                | NFR-001 (Storage management)  |
| **Payment Subscription** | FR-010      | Billing cycle management                  | NFR-007 (Payment compliance)  |
| **API Request**          | FR-009      | Security and performance safeguards       | NFR-010 (Rate limiting)       |
