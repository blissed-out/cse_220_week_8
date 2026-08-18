# Functional Requirements — School Management System

## Scope

### In Scope

- Public school website with information and contact features
- Web-based school administration portal for managing students, teachers, attendance, results, fees, and certificates
- Mobile app (Flutter) for students, parents, and teachers to view data and mark attendance
- Online fee payment through Khalti and eSewa
- AI-generated quizzes and exam papers
- Government reporting (IEMIS export)

### Out of Scope

- Mobile app development details (only the requirement for it is included)
- Payroll and salary management
- Library management system
- Real-time chat or messaging between users

## Requirements Gathering Techniques

- **Online Survey** — A Google Form was sent to teachers, parents, and school staff to collect feedback on what features they need most.
- **One-on-One Interviews** — We interviewed school administrators, teachers, and an accountant to understand their daily workflow and pain points.

## Functional Requirements

| ID | Category | Requirement |
|----|----------|-------------|
| FR-01 | User Roles & Authentication | The system shall allow users to log in with email and password. |
| FR-02 | User Roles & Authentication | The system shall support five roles: Admin, Principal, Accountant, Teacher, and Student. |
| FR-03 | User Roles & Authentication | Each role shall have access to a different set of features and pages. |
| FR-04 | User Roles & Authentication | The system shall keep the user logged in until they sign out. |
| FR-05 | Public Website | The system shall show a public homepage with school information, features, and contact details. |
| FR-06 | Public Website | The system shall display a Google Reviews section where visitors can read and write reviews. |
| FR-07 | Public Website | The system shall include a contact form for visitors to reach the school. |
| FR-08 | Attendance Management | The system shall allow teachers and admins to mark student attendance as present, absent, or leave. |
| FR-09 | Attendance Management | The system shall allow admins to mark teacher attendance. |
| FR-10 | Attendance Management | The system shall allow editing already-submitted attendance records. |
| FR-11 | Attendance Management | The system shall show a live attendance board for real-time tracking. |
| FR-12 | Attendance Management | The system shall generate attendance reports and yearly summaries. |
| FR-13 | Results & Grading | The system shall allow teachers to enter student exam results. |
| FR-14 | Results & Grading | The system shall calculate GPA based on NEB grading rules. |
| FR-15 | Results & Grading | Results shall have four stages: draft, submitted, verified, and published. |
| FR-16 | Results & Grading | The system shall allow bulk publishing and verification of results. |
| FR-17 | Results & Grading | The system shall allow marking students as repeating a class. |
| FR-18 | Certificates, Marksheets & ID Cards | The system shall generate Character and Transfer Certificates as PDFs. |
| FR-19 | Certificates, Marksheets & ID Cards | The system shall generate student marksheets as PDFs. |
| FR-20 | Certificates, Marksheets & ID Cards | The system shall generate student ID cards with photos and QR codes. |
| FR-21 | Fee & Payment Management | The system shall allow the admin to create fee categories and assign fees to students. |
| FR-22 | Fee & Payment Management | The system shall allow students or parents to pay fees online through Khalti or eSewa. |
| FR-23 | Fee & Payment Management | The system shall generate fee receipts after successful payment. |
| FR-24 | Academic Year Management | The system shall support the Bikram Sambat (BS) calendar. |
| FR-25 | Academic Year Management | The system shall allow creating and managing academic years. |
| FR-26 | Academic Year Management | The system shall support year statuses: upcoming, active, closed, and archived. |
| FR-27 | Academic Year Management | The system shall allow promoting students to the next class at year-end. |
| FR-28 | Admission Management | The system shall allow parents or students to submit admission applications online. |
| FR-29 | Admission Management | The system shall allow admins to review and process applications. |
| FR-30 | Notice Board | The system shall allow admins to publish notices and announcements. |
| FR-31 | Notice Board | The system shall display notices on the public website and within dashboards. |
| FR-32 | AI Features | The system shall allow generating quizzes and exam papers using AI. |
| FR-33 | Reporting & Data Export | The system shall allow exporting attendance and academic data. |
| FR-34 | Reporting & Data Export | The system shall support IEMIS report export for Nepal CEHRD government reporting. |
| FR-35 | Mobile App | The system shall include a mobile app (Flutter) for students, parents, and teachers. |
| FR-36 | Mobile App | The mobile app shall allow students and parents to view results, attendance, fees, and notices. |
| FR-37 | Mobile App | The mobile app shall allow teachers to mark attendance on their phones. |
| FR-38 | Dashboard | Admin and Principal shall see an overview of attendance, results, and fee data. |
| FR-39 | Dashboard | Teachers shall see their classes, schedules, and attendance tasks. |
| FR-40 | Dashboard | Students shall see their own results, attendance records, and notices. |
| FR-41 | Results & Grading | The system shall send a push/app notification to students and parents when results are published. |
| FR-42 | Admission Management | The system shall automatically create a student account with generated login credentials upon admission approval and send them by email. |
| FR-43 | Data Management | The system shall soft-delete records and allow restoring them from trash for at least 30 days. |
| FR-44 | Dashboard | The system shall show admins a consolidated student profile with personal details, marksheet, certificates, attendance, and fees. |
| FR-45 | Dashboard | The system shall provide a global search for students and records from the dashboard. |
