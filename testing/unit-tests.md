# Unit Tests

| Test ID | Test Level | Module | Test Objective | Test Description | Preconditions | Test Input | Expected Output | Actual Output | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| UT-001 | Unit | Results & Grading | Verify NEB GPA calculation for valid marks | Calculate GPA for a standard subject score | System configuration loaded | Subject Mark: 85 (out of 100) | GPA returned: 3.6, Grade: A | | |
| UT-002 | Unit | Results & Grading | Verify GPA calculation for invalid marks | Handle out-of-bound marks | None | Subject Mark: 105 | Error/Exception: Invalid mark range | | |
| UT-003 | Unit | Fee Management | Verify late fee computation | Calculate fee with penalty days | Fee rule defined (Rs 10/day late) | Due: Jan 1, Paid: Jan 10 (9 days late), Base: 1000 | Total Fee returned: 1090 | | |
| UT-004 | Unit | Academic Year | Verify BS to AD date conversion | Convert standard Nepali date to Gregorian | Date utility initialized | BS Date: 2080-01-01 | AD Date: 2023-04-14 | | |
| UT-005 | Unit | Authentication | Verify Supabase password hashing | Ensure Supabase Auth stores bcrypt hashes with unique salts | Supabase Auth project configured | Register two users with same plaintext password: "SecurePass123" | auth.users.encrypted_password values are bcrypt hashes (`$2...`) and hashes differ per user due to unique salts | | |
| UT-006 | Unit | Certificates | Verify QR Code string generation | Check if QR payload contains correct student ID | Student data loaded | Student ID: "ST-2023-001" | Payload string: "verify:ST-2023-001" | | |
