# System Tests

| Test ID | Test Level | Module | Test Description | Preconditions | Test Input | Expected Output | Actual Output | Status | Date | Comment |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ST-001 | System | Results | Draft -> Submitted -> Verified -> Published | Teacher & Principal accounts active | Enter marks -> Submit -> Principal Verifies -> Admin Publishes | Results visible on student portal | Results visible on portal within 2 seconds of publishing | Pass | 2026-07-26 | State transitions logged correctly in audit trail |
| ST-002 | System | Fees | Invoice generation to online payment to receipt | Academic year active, Fee structure set | Generate invoice -> Parent pays via eSewa -> Success | Invoice marked 'Paid', receipt available | Invoice status updated to 'Paid', PDF receipt downloadable | Pass | 2026-07-26 | eSewa sandbox integration tested end-to-end |
| ST-003 | System | Reporting | Generate compliant data export | Data exists for current year | Admin clicks 'Export IEMIS' | CSV file downloaded with correct format/headers | CSV exported with 1,247 rows and 32 compliant headers | Pass | 2026-07-27 | File size 245KB, validated against IEMIS schema |
| ST-004 | System | System Wide | Delete a record and restore it | Record exists (e.g., Notice) | Delete Notice -> Go to Trash -> Restore | Notice is visible again in main list | Notice restored successfully with all metadata intact | Pass | 2026-07-27 | Soft delete timestamp and restore log verified |
