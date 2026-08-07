# User Acceptance Tests (UAT)

| Test ID | Test Level | Module | Test Objective | Test Description | Preconditions | Test Input | Expected Output | Actual Output | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| UAT-001 | UAT | Attendance | Verify teacher can mark attendance easily | "As a teacher, I can mark attendance for my class in under 3 clicks" | Teacher logged into mobile app | Open app -> Select Class -> Click 'Submit Attendance' | Attendance saved successfully | | |
| UAT-002 | UAT | Dashboard | Verify parent view data isolation | "As a parent, I only see my own child's data" | Parent has 1 child registered | Login as Parent | Dashboard displays only data for specific child | | |
| UAT-003 | UAT | Public Website | Verify public homepage load time | "As a visitor, the homepage loads in under 3 seconds" | Standard network connection | Navigate to homepage URL | Page fully renders in < 3 seconds | | |
| UAT-004 | UAT | Certificates | Verify principal can bulk generate IDs | "As a principal, I can generate ID cards for a whole class at once" | Class has 40 students enrolled | Select Class 10 -> Click 'Generate IDs' | Single PDF with 40 ID cards generated | | |
| UAT-005 | UAT | Authentication | Verify cross-platform login | "As a student, I can use the same credentials on web and mobile app" | Student account exists | Login on Web, then Login on Mobile | Both logins succeed and show consistent data | | |
