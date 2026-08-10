# System Tests

| Test ID | Test Level | Module | Test Objective | Test Description | Preconditions | Test Input | Expected Output | Actual Output | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ST-001 | System | Admission | Verify full admission lifecycle | End-to-end admission from public form to student account creation | System running, no existing email | Fill form -> Admin Approves -> Auto-generate login | Student account created, welcome email sent | | |
| ST-002 | System | Results | Verify end-to-end result lifecycle | Draft -> Submitted -> Verified -> Published | Teacher & Principal accounts active | Enter marks -> Submit -> Principal Verifies -> Admin Publishes | Results visible on student portal | | |
| ST-003 | System | Fees | Verify end-to-end fee payment flow | Invoice generation to online payment to receipt | Academic year active, Fee structure set | Generate invoice -> Parent pays via Khalti -> Success | Invoice marked 'Paid', receipt available | | |
| ST-004 | System | Reporting | Verify IEMIS data export | Generate compliant data export | Data exists for current year | Admin clicks 'Export IEMIS' | CSV file downloaded with correct format/headers | | |
| ST-005 | System | System Wide | Verify 30-day soft delete recovery | Delete a record and restore it | Record exists (e.g., Notice) | Delete Notice -> Go to Trash -> Restore | Notice is visible again in main list | | |
