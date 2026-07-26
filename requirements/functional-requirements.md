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

## 1. User Roles & Authentication

- The system shall allow users to log in with email and password.
- The system shall support five roles: Admin, Principal, Accountant, Teacher, and Student.
- Each role shall have access to a different set of features and pages.
- The system shall keep the user logged in until they sign out.

## 2. Public Website

- The system shall show a public homepage with school information, features, and contact details.
- The system shall display a Google Reviews section where visitors can read and write reviews.
- The system shall include a contact form for visitors to reach the school.

## 3. Attendance Management

- The system shall allow teachers and admins to mark student attendance as present, absent, or leave.
- The system shall allow admins to mark teacher attendance.
- The system shall allow editing already-submitted attendance records.
- The system shall show a live attendance board for real-time tracking.
- The system shall generate attendance reports and yearly summaries.

## 4. Results & Grading

- The system shall allow teachers to enter student exam results.
- The system shall calculate GPA based on NEB grading rules.
- Results shall have four stages: draft, submitted, verified, and published.
- The system shall allow bulk publishing and verification of results.
- The system shall allow marking students as repeating a class.

## 5. Certificates, Marksheets & ID Cards

- The system shall generate Character and Transfer Certificates as PDFs.
- The system shall generate student marksheets as PDFs.
- The system shall generate student ID cards with photos and QR codes.

## 6. Fee & Payment Management

- The system shall allow the admin to create fee categories and assign fees to students.
- The system shall allow students or parents to pay fees online through Khalti or eSewa.
- The system shall generate fee receipts after successful payment.

## 7. Academic Year Management

- The system shall support the Bikram Sambat (BS) calendar.
- The system shall allow creating and managing academic years.
- The system shall support year statuses: upcoming, active, closed, and archived.
- The system shall allow promoting students to the next class at year-end.

## 8. Admission Management

- The system shall allow parents or students to submit admission applications online.
- The system shall allow admins to review and process applications.

## 9. Notice Board

- The system shall allow admins to publish notices and announcements.
- The system shall display notices on the public website and within dashboards.

## 10. AI Features

- The system shall allow generating quizzes and exam papers using AI.

## 11. Reporting & Data Export

- The system shall allow exporting attendance and academic data.
- The system shall support IEMIS report export for Nepal CEHRD government reporting.

## 12. Mobile App

- The system shall include a mobile app (Flutter) for students, parents, and teachers.
- The mobile app shall allow students and parents to view results, attendance, fees, and notices.
- The mobile app shall allow teachers to mark attendance on their phones.

## 13. Dashboard

- Admin and Principal shall see an overview of attendance, results, and fee data.
- Teachers shall see their classes, schedules, and attendance tasks.
- Students shall see their own results, attendance records, and notices.
