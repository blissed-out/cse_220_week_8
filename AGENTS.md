# AGENTS.md

## Project Overview

School Management System — CSE 220 (Software Engineering) team project.

- Web-based admin portal + public website + Flutter mobile app for Nepali schools
- Multi-school SaaS model (Super Admin creates schools; each school only sees its own data)
- Roles: Admin, Principal, Accountant, Teacher, Student
- Key features: attendance, NEB-based grading, certificates/marksheets/ID cards (PDF), Khalti/eSewa fee payments, BS (Bikram Sambat) academic calendar, admissions, AI quizzes, IEMIS government reporting
- Current phase: requirements/design only — no application code yet

## Team Members

| Name            | Role |
| --------------- | ---- |
| Aadarsh Banjade |      |
| Sijan Budha     |      |
| Nihal Zapaliya  |      |

## Project Structure

```
├── requirements/   Functional & non-functional requirements, stakeholder analysis
├── design/         UML diagrams (use case, class, sequence, activity) — drawio + svg
└── testing/        Test plans & results (not yet created)
```

## Stakeholders

| Stakeholder          | Role |
| -------------------- | ---- |
| School Administrator | Manages day-to-day school operations (admission, attendance, fees, results, certificates, reports) |
| Principal            | Oversees academic/admin activities (dashboard overview, analytics, approval workflows) |
| Accountant           | Handles financial transactions (fee collection, receipts, payment tracking, reports) |
| Teacher              | Teaches and manages students (mark attendance, enter results, view class info) |
| Student              | Views results, attendance, notices; downloads certificates |
| Parent / Guardian    | Monitors child's results, attendance; pays fees online |
| Super Admin          | Manages system across all schools (create schools, manage accounts, system configuration) |

## Scope

### In Scope

- Public school website with information and contact features
- Web-based admin portal for managing students, teachers, attendance, results, fees, certificates
- Mobile app (Flutter) for students, parents, teachers (view data, mark attendance)
- Online fee payment through Khalti and eSewa
- AI-generated quizzes and exam papers
- Government reporting (IEMIS export)

### Out of Scope

- Mobile app development details (only the requirement is included)
- Payroll and salary management
- Library management system
- Real-time chat or messaging between users

## Functional Requirements (Summary)

1. **User Roles & Authentication** — Email/password login; 5 roles (Admin, Principal, Accountant, Teacher, Student); role-based access; persistent sessions
2. **Public Website** — Homepage with school info/features/contact, Google Reviews, contact form
3. **Attendance Management** — Mark present/absent/leave; teacher attendance; edit records; live attendance board; reports & yearly summaries
4. **Results & Grading** — Enter exam results; NEB GPA rules; 4 result stages (draft → submitted → verified → published); bulk publish/verify; repeat-class marking
5. **Certificates, Marksheets & ID Cards** — Character/Transfer Certificates, marksheets (PDF); ID cards with photos & QR codes
6. **Fee & Payment Management** — Fee categories & assignment; online payment via Khalti/eSewa; receipts
7. **Academic Year Management** — BS (Bikram Sambat) calendar; year statuses (upcoming, active, closed, archived); student promotion at year-end
8. **Admission Management** — Online admission applications; admin review/processing
9. **Notice Board** — Publish notices; display on public site and dashboards
10. **AI Features** — Generate quizzes and exam papers using AI
11. **Reporting & Data Export** — Export attendance/academic data; IEMIS export (Nepal CEHRD)
12. **Mobile App** — Flutter for students, parents, teachers; shared database with web
13. **Dashboard** — Role-specific overviews (attendance, results, fees, classes, schedules)

## Non-Functional Requirements (Summary)

1. **Performance** — Pages ≤ 3s; 100 concurrent users; saves ≤ 2s
2. **Security** — Secure password storage; strict school data isolation; auth required; login brute-force protection
3. **Reliability** — 99% availability during school hours; no data loss on crash; desktop + mobile browsers
4. **Mobile App** — Android + iOS; shared database with website
5. **Usability** — Clean interface; common tasks ≤ 3 clicks
6. **Maintainability** — Modular code; DB changes via migration files
7. **Language Support** — English + Nepali dashboards; public site may be English only
8. **Backup & Data Safety** — Regular DB backups; deleted data recoverable ≥ 30 days

## Design Artifacts

| Diagram | File(s) |
| ------- | ------- |
| Use Case | `design/use-case-diagram.drawio` + `.drawio.svg` |
| Class | `design/class-diagram.drawio` + `class-diagram.drawio.svg` + `class-diagram.svg` |
| Sequence | `design/sequence-diagram.drawio` + `.svg` |
| Activity (main) | `design/activity-diagram.drawio` |
| Activity — Login | `design/activity-diagrams/login-activity.drawio` + `.svg` |
| Activity — Admission | `design/activity-diagrams/admission-activity.drawio` + `.svg` |
| Activity — Fee Payment | `design/activity-diagrams/fee-payment-activity.drawio` + `.svg` |
| Activity — Academic Year | `design/activity-diagrams/academic-year-activity.drawio` + `.svg` |
| Activity — Certificate | `design/activity-diagrams/certificate-activity.drawio` + `.svg` |
| Activity — Result Publication | `design/activity-diagrams/result-publication-activity.drawio` + `.svg` |

## Guidelines

- Requirements docs live in `requirements/` (functional, non-functional, stakeholders)
- Diagrams are authored as `.drawio` files; keep the paired `.svg` exports in sync
- Activity diagrams go under `design/activity-diagrams/` with `-activity` suffix
- Testing artifacts belong in `testing/` (create if missing)
- Keep `README.md`, `AGENTS.md`, and requirement docs consistent when the project evolves
- This repo is currently in the requirements/design phase — no application code yet
