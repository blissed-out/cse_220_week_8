# Use Case Diagram

```mermaid
usecaseDiagram
    actor Visitor
    actor Student
    actor Parent
    actor Teacher
    actor Accountant
    actor Admin
    actor Principal
    actor SuperAdmin

    usecase UC1 as "View Homepage"
    usecase UC2 as "Write Review"
    usecase UC3 as "Submit Application"
    usecase UC4 as "Pay Fees Online"
    usecase UC5 as "View Results"
    usecase UC6 as "Mark Attendance"
    usecase UC7 as "Edit Attendance"
    usecase UC8 as "Enter Results"
    usecase UC9 as "Verify Results"
    usecase UC10 as "Publish Results"
    usecase UC11 as "Manage Fee Categories"
    usecase UC12 as "Assign Fees"
    usecase UC13 as "Generate Certificates"
    usecase UC14 as "Generate Marksheets"
    usecase UC15 as "Generate ID Cards"
    usecase UC16 as "Manage Academic Years"
    usecase UC17 as "Promote Students"
    usecase UC18 as "Review Applications"
    usecase UC19 as "View Dashboard"
    usecase UC20 as "Export IEMIS Reports"
    usecase UC21 as "Manage Notices"
    usecase UC22 as "Manage Users"
    usecase UC23 as "Login"

    Visitor --> UC1
    Visitor --> UC2

    Student --> UC23
    Student --> UC5

    Parent --> UC23
    Parent --> UC4
    Parent --> UC5

    Teacher --> UC23
    Teacher --> UC6
    Teacher --> UC7
    Teacher --> UC8
    Teacher --> UC5

    Accountant --> UC23
    Accountant --> UC11
    Accountant --> UC12
    Accountant --> UC4

    Admin --> UC23
    Admin --> UC6
    Admin --> UC7
    Admin --> UC8
    Admin --> UC10
    Admin --> UC11
    Admin --> UC12
    Admin --> UC13
    Admin --> UC14
    Admin --> UC15
    Admin --> UC16
    Admin --> UC17
    Admin --> UC18
    Admin --> UC19
    Admin --> UC20
    Admin --> UC21
    Admin --> UC22

    Principal --> UC23
    Principal --> UC9
    Principal --> UC10
    Principal --> UC16
    Principal --> UC17
    Principal --> UC19

    SuperAdmin --> UC23
    SuperAdmin --> UC22
```
