
Activity Workflow Modeling
1. User Registration Workflow
![Screenshot 2025-04-06 202025](https://github.com/user-attachments/assets/4d711960-81a6-4a46-85c6-fd1de6c72575)

Explanation:

Stakeholder Concern: Ensures secure onboarding (FR-006)

Key Features:

Email validation prevents fake accounts

Auto-cleanup of unverified data (NFR-001)

Swimlanes:

User: Provides input

System: Validates & creates account

2. Wearable Device Sync
![Screenshot 2025-04-06 202443](https://github.com/user-attachments/assets/fd7f156d-6b1a-4aa2-930c-63d216a3e171)

Explanation:

Stakeholder Concern: Reliable fitness data collection (FR-004)

Parallel Actions:

Data sync + real-time UI update

Security logging

Swimlanes:

Wearable: Provides data

Mobile App: Handles sync

3. Fitness Goal Achievement
![Screenshot 2025-04-06 202653](https://github.com/user-attachments/assets/269827d2-b9ef-4bf7-bf03-f6a9ee04e27c)

Explanation:

Stakeholder Concern: User motivation (FR-003)

Decisions:

Dynamic progress calculation

Personalized notifications

4. Report Generation
![Screenshot 2025-04-06 202954](https://github.com/user-attachments/assets/4df0ed28-1504-471b-b28f-587b279c5fa7)

Explanation:

Stakeholder Concern: Data accuracy (FR-005)

Parallel Actions:

Data validation + visualization

Auto-retry for missing data

5. Notification System
![Screenshot 2025-04-06 203520](https://github.com/user-attachments/assets/6c088b33-249d-433c-8a18-02ddb351e06d)

Explanation:

Stakeholder Concern: Engagement (FR-008)

Error Handling:

Multi-channel fallback

Attempt limit

6. Premium Subscription
![Screenshot 2025-04-06 204113](https://github.com/user-attachments/assets/39c6cde4-a823-4379-83e9-4148951ae220)

Explanation:

Stakeholder Concern: Revenue (FR-010)

Recovery Path:

Draft saving for abandoned flows

7. Data Export
![Screenshot 2025-04-06 204242](https://github.com/user-attachments/assets/ab409a1f-7cc1-4da2-9560-87e5c82bc0fa)

Explanation:

Stakeholder Concern: System stability (NFR-010)

Protections:

Rate limiting

Input validation
