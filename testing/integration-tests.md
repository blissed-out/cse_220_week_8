# Integration Tests

| Test ID | Test Level | Module | Test Objective | Test Description | Preconditions | Test Input | Expected Output | Actual Output | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| IT-001 | Integration | Attendance & Dashboard | Verify attendance updates dashboard | Mark attendance and check if dashboard stats update | Teacher logged in, class assigned | Mark 'Present' for 30 students in Class 10A | Admin dashboard shows '30 Present' for 10A | | |
| IT-002 | Integration | Fees & Notification | Verify fee payment triggers receipt | Pay fee via Khalti and check receipt generation | Student has pending fee, Khalti API mocked | Payment Success payload | Receipt PDF generated and saved to DB | | |
| IT-003 | Integration | Results & Notification | Verify result publishing notifies students | Change result status to published | Result is in 'verified' state | Admin clicks 'Publish Results' | App notification sent to respective students | | |
| IT-004 | Integration | AI Features & Results | Verify AI quiz generation stores results | Generate quiz and save to database | AI service connected | Admin enters topic 'Science' | Quiz JSON generated and successfully saved | | |
| IT-005 | Integration | Auth & Session | Verify brute-force login protection | Lock account after multiple failed attempts | User exists in DB | 5 incorrect login attempts consecutively | Account locked for 15 mins, API returns 429 | | |
