# Testing Strategy - School Management System

This directory contains the comprehensive test documentation for the School Management System, a college project for CSE 220. 
Our strategy ensures high quality, security, and performance across both the web-based portal and the Flutter mobile app.

## Testing Levels Covered

We follow a structured approach encompassing four levels of testing:

1. **Unit Testing**: Focuses on individual function/method-level logic. This includes core algorithms such as GPA calculation, fee computation, and date conversion (BS↔️AD).
2. **Integration Testing**: Verifies interactions between modules. This ensures data flows correctly across the system (e.g., attendance marking updating the dashboard, fee payment triggering receipt generation).
3. **System Testing**: Validates end-to-end workflows. This checks complete processes like the full admission lifecycle or the result publishing workflow.
4. **User Acceptance Testing (UAT)**: Evaluates the system from stakeholder perspectives (Super Admin, Admin, Principal, Accountant, Teacher, Student, Parent/Guardian). These tests ensure the system meets business requirements and provides a good user experience.

## Tools & Approach

- **Manual Testing**: Documented test cases will be executed manually initially to verify functionality against requirements.
- **Test Case Structure**: Each test case includes a unique ID, objective, preconditions, inputs, and expected outputs.
- **Coverage**: We ensure coverage across all major modules including Authentication, Attendance, Results, Fees, Certificates, Admission, Notices, AI Features, Dashboards, and the Public Website.
