# Non-Functional Requirements — School Management System

| ID | Category | Requirement |
|----|----------|-------------|
| NFR-01 | Performance | Pages shall load within 3 seconds on a standard internet connection. |
| NFR-02 | Performance | The system shall support at least 100 concurrent users without response time exceeding 3 seconds. |
| NFR-03 | Performance | Attendance and result data shall be saved within 2 seconds of submitting. |
| NFR-04 | Security | User passwords shall be stored using a secure, industry-standard hashing algorithm (e.g., bcrypt). |
| NFR-05 | Security | Each school shall only be able to view and modify its own data, and never another school's data. |
| NFR-06 | Security | Only logged-in users with valid session tokens shall be able to access dashboards and authorized features. |
| NFR-07 | Security | The login page and authentication endpoints shall be protected from repeated failed login attempts via rate limiting. |
| NFR-08 | Reliability | The system shall be available at least 99% of the time during school hours. |
| NFR-09 | Reliability | If the system crashes, no committed data shall be lost. |
| NFR-10 | Reliability | The system shall work on both desktop and mobile browsers. |
| NFR-11 | Mobile App | The mobile app (Flutter) shall work on both Android and iOS devices. |
| NFR-12 | Mobile App | The mobile app and the website shall share the same database, so data is always up to date on both. |
| NFR-13 | Usability | At least 90% of users in usability testing shall complete common tasks (e.g., marking attendance) without assistance. |
| NFR-14 | Usability | Teachers and admins shall be able to complete common tasks (like marking attendance) with 3 or fewer clicks. |
| NFR-15 | Maintainability | New features shall not break existing functionality; all existing automated tests shall pass after each change. |
| NFR-16 | Maintainability | Database changes shall be tracked through migration files. |
| NFR-17 | Language Support | The system shall support English and Nepali languages for dashboard pages. |
| NFR-18 | Language Support | The public website shall support English. |
| NFR-19 | Backup & Data Safety | The database shall be backed up automatically at least once per day. |
| NFR-20 | Backup & Data Safety | Deleted data shall be recoverable from backup for at least 30 days. |
