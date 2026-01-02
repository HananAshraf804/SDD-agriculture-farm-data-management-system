# SDD-agriculture-farm-data-management-system
Software Design Document
<Agriculture – Farm Data Management System>



Submitted by
<Hanan Ashraf(F22BINFT1M01221)>

Submitted to
<Ms. Sara Farid  >



Department of Information Technology
Faculty of Computing
The Islamia University of Bahawalpur

Summery
The Software Design Document describes the technical design of the Agriculture Farm Data Management System, a web-based, offline-first farm management application that runs entirely in the browser without any backend server. The system is developed using HTML, CSS, and Vanilla JavaScript, with data stored locally in browser Local Storage in JSON format and support for the Urdu (RTL) language.
The architecture follows a client-side modular approach, separating the user interface, business logic, and data storage layers. The system includes key functional modules such as Field & Crop Management, Machinery Management, Worker & Operator Management, Bike/Transport Management, Stock Management, Video & Training, and Reporting. Each module handles specific farm operations and provides dedicated functions for data entry, tracking, and reporting.
The data design uses structured JSON arrays for each module, enabling easy backup and restore through JSON export/import. The user interface is mobile-friendly, dashboard-based, and supports role-based access control for Admin, Supervisor, and Operator roles.
Non-functional considerations focus on performance, reliability, and maintainability, ensuring fast load times, full offline operation, and modular, well-documented code. Security is handled locally with role-based access and no external network dependency.
The document also outlines design constraints such as local storage limits and single-device usage, along with future enhancements including IndexedDB integration, authentication, analytics, PWA support, and multimedia features.
Table of Content
1. Introduction
   1.1 Purpose
   1.2 Scope
   1.3 Intended Audience
2. System Architecture
   2.1 Architectural Overview
3. Module Design
   3.1 Field & Crop Management Module
   3.2 Machinery Management Module
   3.3 Worker & Operator Module
   3.4 Bike / Transport Module
   3.5 Stock Management Module
   3.6 Video & Training Module
   3.7 Reporting Module
4. Data Design
   4.1 Data Storage Strategy
   4.2 Sample Data Structure
5. Interface Design
   5.1 User Interface
   5.2 Navigation
6. Security Design
7. Error Handling & Validation
8. Non-Functional Design Considerations
  8.1 Performance
   8.2 Reliability
   8.3 Maintainability
9. Design Constraints
10. Future Design Enhancements
11. Conclusion

                             1. Introduction
1.1 Purpose
This Software Design Document (SDD) describes the design and architecture of the Agriculture Farm Data Management System. It explains how the system will be built, including modules, data structures, interfaces, and design decisions, based on the approved SRS.
1.2 Scope
The system is a web-based, offline farm management application that runs entirely in the browser. It digitizes farm operations such as crop management, machinery tracking, worker activities, stock handling, and reporting, with Urdu language support and JSON-based backup.
1.3 Intended Audience
    • Software developers
    • Project supervisor
    • Evaluators / examiners
    • Maintenance team

2. System Architecture
2.1 Architectural Overview
The system follows a Client-Side Modular Architecture.
Architecture Type:
    • Standalone
    • Browser-based
    • Offline-first
Key Characteristics:
    • No backend server
    • Data stored in Browser Local Storage
    • Developed using HTML, CSS, JavaScript (Vanilla)
User Interface (HTML/CSS)
        ↓
Business Logic (JavaScript)
        ↓
Local Storage (JSON Data)

3. Module Design
3.1 Field & Crop Management Module
Responsibilities:
    • Manage fields and crops
    • Store sowing, harvesting, fertilizer, and pesticide data
Main Functions:
    • addField()
    • updateField()
    • deleteField()
    • getFieldReport()
Data Stored:
    • Field ID
    • Crop name
    • Seed quantity
    • Fertilizer usage
    • Dates

3.2 Machinery Management Module
Responsibilities:
    • Track tractors, machinery, and fuel usage
    • Assign operators
Main Functions:
    • addMachinery()
    • updateMachineryStatus()
    • assignOperator()
    • logFuelUsage()
Status Types:
    • Working
    • Under Repair

3.3 Worker & Operator Module
Responsibilities:
    • Store worker details
    • Track daily tasks and working hours
Main Functions:
    • addWorker()
    • logWorkerTask()
    • calculateDailyHours()

3.4 Bike / Transport Module
Responsibilities:
    • Manage bikes
    • Assign bikes to supervisors
Main Functions:
    • addBike()
    • assignBike()
    • updateBikeCondition()

3.5 Stock Management Module
Responsibilities:
    • Maintain seeds, sprays, fertilizers stock
    • Track daily usage
Main Functions:
    • addStockItem()
    • updateStockUsage()
    • checkLowStock()

3.6 Video & Training Module
Responsibilities:
    • Store training videos
    • Categorize by purpose
Main Functions:
    • addVideo()
    • assignVideoToSupervisor()
    • filterVideos()

3.7 Reporting Module
Responsibilities:
    • Generate daily and weekly reports
    • Export and import JSON data
Main Functions:
    • generateDailyReport()
    • generateWeeklyReport()
    • exportJSON()
    • importJSON()

4. Data Design
4.1 Data Storage Strategy
    • Uses Browser Local Storage
    • Data stored in JSON format
    • Each module has a separate JSON array
4.2 Sample Data Structure
{
  "fields": [],
  "machinery": [],
  "workers": [],
  "bikes": [],
  "videos": [],
  "stock": [],
  "reports": []
}

5. Interface Design
5.1 User Interface
    • Mobile-friendly responsive design
    • Simple forms and tables
    • Urdu (RTL) language support
5.2 Navigation
    • Dashboard-based layout
    • Separate tabs/modules
    • Role-based visible options

6. Security Design
    • Local-only data storage
    • No external network access
    • Role-based access:
        ◦ Admin (full access)
        ◦ Supervisor (limited control)
        ◦ Operator (data entry only)

7. Error Handling & Validation
    • Required field validation
    • Numeric input checks
    • Confirmation dialogs before delete
    • Local Storage capacity warning

8. Non-Functional Design Considerations
8.1 Performance
    • Fast load (<3 seconds)
    • Lightweight JavaScript functions
8.2 Reliability
    • Works fully offline
    • JSON export/import for backup
8.3 Maintainability
    • Modular JavaScript files
    • Well-commented code
    • Easy future upgrades

9. Design Constraints
    • Browser Local Storage size limit
    • Single-device usage
    • No multi-user real-time access

10. Future Design Enhancements
    • IndexedDB integration
    • User authentication
    • Charts and analytics
    • Image uploads
    • Progressive Web App (PWA)

11. Conclusion
This SDD provides a complete technical design blueprint for implementing the Agriculture Farm Data Management System. It ensures that the system meets all requirements defined in the SRS while remaining scalable, maintainable, and user-friendly.
