# Non-Functional Requirements — School Management System

## 1. Performance

- Pages should load within 3 seconds on a standard internet connection.
- The system should handle at least 100 users using it at the same time without slowing down.
- Attendance and result data should be saved within 2 seconds of submitting.

## 2. Security

- **Authentication and Security**: The system uses Supabase Auth for login and session management. Supabase handles secure password hashing (using bcrypt), while role-based access is enforced using application roles and Supabase Row Level Security (RLS).
- Each school can only see its own data through Supabase Row Level Security (RLS) policies. A school must never see another school's data.
- Only logged-in users with valid JWT session tokens can access dashboards and authorized features.
- The login page and auth endpoints must be protected from repeated failed login attempts via rate limiting.

## 3. Reliability

- The system should be available at least 99% of the time during school hours.
- If the system crashes, no data should be lost.
- The system should work on both desktop and mobile browsers.

## 4. Mobile App

- The mobile app (Flutter) should work on both Android and iOS devices.
- The mobile app and the website should share the same database, so data is always up to date on both.

## 5. Usability

- The interface should be clean and easy to navigate.
- Teachers and admins should be able to complete common tasks (like marking attendance) with 3 or fewer clicks.

## 6. Maintainability

- The code should be organized so that new features can be added without breaking existing ones.
- Database changes should be tracked through migration files.

## 7. Language Support

- The system should support English and Nepali languages for dashboard pages.
- The public website may be in English only.

## 8. Backup & Data Safety

- The database should be backed up regularly.
- Deleted data should be recoverable for at least 30 days.
