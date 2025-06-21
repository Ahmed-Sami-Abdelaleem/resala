# 📦 Resala Branch Management Platform (فرع العاشر من رمضان)

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)]()
[![Build Status](https://img.shields.io/travis/user/repo/master.svg)](https://travis-ci.org/user/repo)

> A volunteer & beneficiary management system for **Resala Charity** - digitizing internal operations for the 10th of Ramadan branch. Built with ❤️ in Egypt.
<img src="https://yt3.ggpht.com/-qKEv-sRWRZI/AAAAAAAAAAI/AAAAAAAAAAA/UlZRyaBRaZY/s900-c-k-no-mo-rj-c0xffffff/photo.jpg" alt="resala logo" width="800" height="400">
---

## 📚 Table of Contents

- [🎯 Project Objective](#-project-objective)
- [🧠 Scope & Deliverables](#-scope--deliverables)
- [🧱 Technology Stack](#-technology-stack)
- [📊 Estimated Load & Usage](#-estimated-load--usage)
- [🔐 Security & KPIs](#-security--kpis)
- [⚙️ Functional Requirements](#-functional-requirements)
- [🚀 Non-Functional Requirements](#-non-functional-requirements)
- [🧪 Testing](#-testing)
- [⚙️ Installation](#️-installation)
- [🚀 Deployment](#-deployment)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [🙏 Acknowledgments](#-acknowledgments)

---

## 🎯 Project Objective

To digitize and streamline the management of volunteer activities, beneficiaries, and task assignments for **Resala فرع العاشر من رمضان**. The platform will serve internal users (admins and volunteers) with features such as:

- User management include (managers, employee, volunteers, external organization)
- Task assignments with image proof
- Beneficiary documentation

---

## 🧠 Scope & Deliverables

### ✅ In Scope
- **User Management**: Create/edit/deactivate volunteer accounts.
- **Task Management**: Assign, track, and verify volunteer tasks.
- **Beneficiary Management**: Store data and images for beneficiaries.

### ❌ Out of Scope (MVP)
- Public-facing features
- Donation system
- Notifications (SMS/email)
- Mobile app
- Multi-branch support

### 📄 Deliverables
- MVP in 7–8 months => 2 for build team & data gatharing & Analysis ---- 3~ for design System & database & UI&UX ---- 3~ implementation & tesing --- finaly we are expecting the deploment in  november 2025
- Full admin panel, volunteer portal, and backend API
- Arabic RTL responsive UI

---

## 🧱 Technology Stack

| Layer        | Technology            | Notes                                  |
|--------------|------------------------|----------------------------------------|
| UI & UX      | Figma                  | Responsive, mobile-first design        |
| Frontend     | React + Tailwind CSS   | Responsive, mobile-first design        |
| Backend      | NestJS (TypeScript)    | REST API, modular architecture         |
| Database     | PostgreSQL (via Railway)| Hosted DB                             |
| Authentication | JWT / Clerk / Auth.js | Role-based (Admin / Volunteer)         |
| Image Storage| Cloudinary (Free Tier) | Profile, task, and beneficiary images |
| Hosting      | Railway                | Backend + frontend                     |
| Version Control | Git + GitHub         | CI/CD Ready                            |

---

## 📊 Estimated Load & Usage

| Entity        | Count    | Images per Item | Total Images | Notes                                |
|---------------|----------|------------------|--------------|--------------------------------------|
| Volunteers    | ~2000    | 1                | 2000         | Profile photos                       |
| Tasks (Year)  | ~20,000  | 1                | 20,000       | Weekly tasks per user (avg)          |
| Beneficiaries | ~400     | 2–5              | ~1600        | Case documentation                   |
| **Total**     | -        | -                | ~23,600      | Within Cloudinary 25GB free tier     |

---

## 🔐 Security & KPIs

### 🔐 Security Measures
- JWT authentication
- Role-based authorization
- Secure Cloudinary signed uploads
- Backend validation and rate limiting

### 📈 KPIs (Success Metrics)
- ✅ 300+ concurrent users without crashing
- ✅ Real-time task updates and tracking
- ✅ Volunteers upload images smoothly
- ✅ Admin dashboards with accurate KPIs
- ✅ Stay within Cloudinary & Railway free limits

---

## 📋 Functional Requirements

### 👤 Manager of Resala (فرع العاشر من رمضان)

The branch manager has full administrative control over users, data, and system oversight.

#### 🔧 Employee Management
- Create and manage employees:
  - Receptionist
  - Pharmacist
  - Public Relations
  - Activity Officer
- Update employee details.
- Monitor:
  - Work performance
  - Financial contributions
  - General system activity

#### 🤝 Inter-Charity Collaboration
- View, add, and update **shared beneficiary data** from other charities.
- Monitor performance of other charities within the ecosystem.

#### 👥 Beneficiary Oversight
- Add, edit, and deactivate beneficiaries.
- Track which charity the beneficiary belongs to.
- View an overview of:
  - Needs of own and shared beneficiaries
  - Deficits in food, materials, and medicine

#### 💰 Income & Inventory
- Add and manage incoming donations:
  - Food
  - Materials

#### 📊 System Monitoring
- Dashboards for:
  - Project traffic and progress
  - Number of employees and volunteers

#### 💬 Feedback & Polling
- Monitor feedback between employees and volunteers.
- Review user suggestions.
- Create polls to gather public opinion.

---

### 🧑‍💼 Receptionist

- Works on-site at the branch.
- Manages Beneficiaries:
  - Add / update / deactivate
  - Check if they belong to another charity
- Manages Volunteers:
  - Add new volunteers
  - Deactivate or monitor them
- Handles Distress Call Reports:
  - Add with image, address, phone number, and description
- Linked to Excel system: **تارجيت العاشر** *(details provided later)*

---

### 💊 Pharmacist

- Maintains **medical inventory**.
- Distributes medication to beneficiaries as needed.
- Search for beneficiaries using mobile numbers.

---

### 📢 Activity Officer

- Sees and validates **distress call reports**.
- Prioritizes and converts them into tasks.
- Assigns tasks to volunteers according to activity and skill.
- Evaluates task results and assigns **custom points** based on:

  - **الالتزام** (Commitment): Attendance & participation
  - **الإنجاز** (Achievement): Number & quality of completed tasks
  - **روح الفريق** (Team Spirit): Teamwork and cooperation
  - **المبادرة** (Initiative): New ideas and improvement suggestions

- Participates in managing the **Volunteer Reward System**.

---

### 🧑‍🤝‍🧑 Volunteers

- Apply through a submission form.
- Receptionist approves or contacts them.
- Once enrolled in an activity:
  - Activity Officer sees volunteer data and skills.
  - Tasks assigned based on role and capacity.
- Gain points for completed tasks and engagement.
- Participate in a gamified **Reward System**.

---



## 🛠️ Non-Functional Requirements (NFRs)

### 1. 🔒 Security
- Role-based access control for managers, receptionists, pharmacists, public relations, and activity officers.
- Charities can only view or modify data shared with them.
- All operations should be logged (add, update, deactivate).
- Sensitive information (e.g., phone numbers, addresses, health info) must be encrypted.

### 2. 🧩 Scalability
- Support for multiple charities, hundreds of beneficiaries, employees, and volunteers.
- Should handle high volumes of distress reports and task assignments efficiently.

### 3. 💾 Availability & Reliability
- Ensure 99.9% system uptime.
- Reliable data access and availability for real-time work.
- Daily backups of all important data.

### 4. 📱 Usability
- Clean and intuitive UI for employees and volunteers.
- Arabic language support.
- Responsive design for mobile and tablet access.

### 5. ⚡ Performance
- Instant search results for beneficiaries and volunteers.
- Dashboards and reports should load in under 2 seconds.

### 6. 📊 Maintainability
- Modular codebase for easy updates and future enhancements.
- Admin can easily update Excel target structure (تارجيت العاشر).

### 7. 🔄 Interoperability
- Support for Excel imports/exports.
- Integration with third-party tools (e.g., Google Maps, WhatsApp).

### 8. 🧪 Testability
- Automated testing for core features (e.g., distress calls, beneficiary updates, task assignments).
- Manual QA before production deployments.

### 9. ⏱️ Response Time & Real-Time Operations
- Dashboard updates, distress calls, and task statuses should reflect changes in real time or near real time.

### 10. 🧾 Auditability
- Track and log all key operations including:
  - Who performed the action
  - When it was performed
  - What was changed



---
## UML drigrams 


## use cese digram 
![Image](https://github.com/user-attachments/assets/621e2d05-510f-4469-875f-4900a4d8f16a)

## Use Case Descriptions Table
| Use Case ID | Use Case Name                        | Actor(s)                          | Description                                                                                         | Main Flow                                                                                                                                                                                                                                                       | Alternate/Exception Flows                                                                                                                                                                                                                                                                                                                                                           |
|-------------|--------------------------------------|-----------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| UC1         | Add Beneficiary             | Receptionist        | Register a new beneficiary into the system                                 | 1. Receptionist selects "Add Beneficiary".<br>2. System displays form (name, phone, ID, address, household info).<br>3. Receptionist fills and submits the form.<br>4. System validates data and checks for duplicates.<br>5. Upon success, system saves the record and generates Beneficiary ID. | A1: Duplicate Detected → System shows existing profile, asks whether to merge or update.<br>A2: Missing Required Fields → System highlights missing fields, blocks submission.<br>A3: Invalid National ID → System prompts correction.                                                        |
| UC2         | Update Beneficiary Profile  | Receptionist        | Modify existing beneficiary information                                    | 1. Receptionist searches for the beneficiary.<br>2. System displays profile.<br>3. Receptionist clicks "Edit", updates fields (e.g., address, family size, phone).<br>4. System validates changes and saves.                                               | A1: No Access Rights → System blocks and logs attempt.<br>A2: Change Conflicts with Audit Trail → Requires approval or comment.<br>A3: Invalid Format → System rejects and highlights errors.                                                                                                  |
| UC3         | Assign Aid to Beneficiary   | Receptionist        | Assign aid (financial, food, medicine, etc.) to a beneficiary              | 1. Receptionist searches and opens beneficiary profile.<br>2. Clicks "Assign Aid".<br>3. Selects aid type, description, quantity, duration.<br>4. Submits request.<br>5. System validates availability and logs assignment.                              | A1: Aid Out of Stock → System alerts and suggests waitlist.<br>A2: Aid Already Assigned Recently → System warns and requires justification.<br>A3: Invalid Quantity → Blocks submission.                                                                                                     |
| UC4         | Record Aid Delivery         | Aid Officer         | Confirm that aid was delivered to the correct beneficiary                   | 1. Aid Officer selects "Deliveries".<br>2. Views scheduled deliveries list.<br>3. Selects aid package and confirms delivery.<br>4. Enters recipient signature or code.<br>5. System updates delivery status.                                               | A1: Recipient Not Present → Officer marks as failed, system reschedules.<br>A2: Wrong Address → Officer logs issue, system notifies admin.<br>A3: Aid Refused → Requires reason before proceeding.                                                                                             |
| UC5         | Track Beneficiary History   | Receptionist        | View a beneficiary’s full aid and update history                           | 1. Receptionist searches for beneficiary.<br>2. System shows timeline of aid received, profile edits, contact history.<br>3. User can filter by type/date.<br>4. User prints report or exports as PDF.                                                  | A1: No Record Found → Suggests broader search or creation.<br>A2: Data Corruption → System logs error and alerts IT.<br>A3: Restricted Access (e.g., flagged case) → Requires supervisor override.                                                                                             |
| UC6         | View Shared Beneficiaries            | Branch Manager, External Charity | View beneficiaries shared with partnered charities to coordinate aid                                | 1. External Charity logs in (after UC17 verification).<br>2. System displays shared beneficiaries (read-only).<br>3. Charity filters by location/needs.                                                                                                           | A1: Unauthorized Access<br>- If charity is unverified, system blocks access and logs the attempt.                                                                                                                                                                                                                                                                                   |
| UC7         | Handle Feedback & Polls              | Branch Manager                    | Create polls and analyze responses                                                                  | 1. Manager creates a poll with questions/options.<br>2. System distributes it to volunteers/beneficiaries.<br>3. Responses are aggregated into charts.                                                                                                            | A1: Low Participation<br>- System sends reminder emails after 24 hours.                                                                                                                                                                                                                                                                                                              |
| UC8         | Add Distress Reports                 | Receptionist                      | Log urgent cases requiring immediate attention                                                      | 1. Receptionist selects "Add Distress Report".<br>2. System displays form (beneficiary ID, distress type, urgency level).<br>3. Receptionist fills form and uploads documents.<br>4. System validates ID.<br>5. Receptionist submits.<br>6. System generates case, alerts staff, and queues it. | A1: Beneficiary Not Found → Suggests search or temp record.<br>A2: Missing Info → Blocks submission and highlights required fields.<br>A3: Duplicate Emergency → Shows warning and merge option.                                                                                                                                            |
| UC9         | Approve New Volunteers               | Receptionist                      | Review and approve/reject volunteer applications                                                    | 1. Receptionist goes to "Pending Applications".<br>2. System shows list with details.<br>3. Receptionist reviews and chooses approve/reject.<br>4. System processes application, sends emails, and moves to "Processed".                                           | A1: Missing Documents → Flags missing docs, allows request.<br>A2: Background Check Failed → Manual review suggested.<br>A3: Overqualified Applicant → Suggest specialist role.                                                                                                                                                                                                    |
| UC10        | Search Beneficiary by Phone          | Pharmacist                        | Locate beneficiary using phone number for medication dispensing                                     | 1. Pharmacist enters phone number.<br>2. System searches:<br>&nbsp;&nbsp;- Exact: Show record<br>&nbsp;&nbsp;- Multiple: Show list<br>3. Pharmacist selects and views full record.                                                                               | A1: Number Not Registered → Prompt to create new.<br>A2: Number Changed → Show new number.<br>A3: Privacy Restriction → Requires override with reason.                                                                                                                                                                                                                              |
| UC11        | Distribute Medication                | Pharmacist                        | Record dispensed medication and update inventory                                                    | 1. Pharmacist selects "Dispense Medication" after search.<br>2. System shows prescriptions, inventory, and allergy warnings.<br>3. Pharmacist selects meds, adds usage.<br>4. System logs transaction, deducts stock, prints receipt.                             | A1: Insufficient Stock → Suggest alternatives or reorder.<br>A2: Expired Medication → Blocks and alerts inventory manager.<br>A3: Dosage Error → Requires second verification.                                                                                                                                                                                                      |
| UC12        | Evaluate Tasks & Reward System       | Activity Officer                  | Assess completed volunteer tasks and assign ratings                                                 | 1. Officer opens "Completed Tasks".<br>2. System shows task details and evidence.<br>3. Officer rates and comments.<br>4. System updates score and triggers UC15.                                                                                                | A1: Disputed Evaluation → Flags for manager review.<br>A2: Exceptional Performance → Suggests bonus and recognition.<br>A3: Missing Evidence → Auto 2-star pending clarification.                                                                                                                                                                                                   |
| UC13        | Submit Tasks with Images             | Volunteer                         | Upload proof of completed tasks for verification                                                    | 1. Volunteer selects "Submit Task Completion".<br>2. System shows assigned tasks.<br>3. Volunteer uploads 1–3 photos and notes.<br>4. System compresses, timestamps, and notifies officer.                                                                      | A1: Late Submission → Marked late but allowed.<br>A2: Poor Photo Quality → Prompts retake.<br>A3: Task Modification → Creates sub-task.                                                                                                                                                                                                                                            |
| UC14        | Apply to Volunteer                   | Volunteer Applicant               | Submit application to join as a volunteer                                                           | 1. Applicant opens "Join Us" portal.<br>2. Fills personal info, skills, availability, uploads docs.<br>3. Submits form.<br>4. System sends confirmation, queues for UC9, gives temp ref.                                   | A1: Underage → Redirects to Junior form with guardian consent.<br>A2: AI Screening Fail → Flags for review.<br>A3: Duplicate → Offers resume option.                                                                                                                                                                                                                                |
| UC15        | Assign Points to Volunteers          | Activity Officer                  | Award points to volunteers based on evaluated tasks                                                 | 1. System pulls ratings from UC12.<br>2. Officer adjusts (+/-5) with reason.<br>3. Submits batch.<br>4. System updates profiles, checks thresholds, triggers rewards.                                                       | A1: Point Discrepancy → Volunteer can view audit trail.<br>A2: Reward Threshold → Prompts officer to plan award.<br>A3: Negative Points → Needs manager approval.                                                                                                                                                                                                                   |
| UC16        | Excel Integration – Target العاشر    | Branch Manager                    | Import/export data via Excel for bulk operations                                                    | 1. Manager chooses Excel import/export.<br>2. System offers templates.<br>3. For import:<br>&nbsp;&nbsp;- Upload Excel<br>&nbsp;&nbsp;- Validate data<br>&nbsp;&nbsp;- Preview<br>&nbsp;&nbsp;- Confirm import<br>4. For export: Generate file | A1: Template Mismatch → System provides correct template.                                                                                                                                                                                                                                                                                                                           |
| UC17        | Approve External Charity (linked)    | Branch Manager                    | Verify and approve third-party charities requesting shared access                                   | *Not fully described in original*, but referenced in UC6                                                                                                                            | A1: Fraud Suspected → Flags for manual review.                                                                                                                                                                                                                                                                                                                                      | UC18        | Generate Aid Statistics      | Admin, Receptionist   | Generate statistical reports on aid distribution, types, and frequency     | 1. Actor logs into dashboard.<br>2. Selects "Statistics" section.<br>3. Chooses time range, aid type, or beneficiary group.<br>4. System generates charts/tables summarizing data.<br>5. Actor can export or print report.             | A1: No Data for Selected Range → System notifies "No records found".<br>A2: Permission Denied (non-admins) → System restricts access to some statistics.<br>A3: System Error → Displays error and logs for admin review.                                     |
| UC19        | Generate Donor Report        | Admin                 | Generate a report summarizing donations made by a specific donor           | 1. Admin logs in.<br>2. Opens "Donor Reports".<br>3. Searches for donor by name or ID.<br>4. Selects donor and time range.<br>5. System displays donations, aid impact, and remaining balance (if any).<br>6. Admin exports report. | A1: Donor Not Found → System suggests similar names or asks to recheck input.<br>A2: No Donations in Selected Period → System displays message.<br>A3: Export Failed → System suggests retry or alternate format (e.g., CSV if PDF fails).                     |

## class digram 
![Image](https://github.com/user-attachments/assets/458e7455-77dc-4169-a779-d8c4281145dd)
---
## ERD 

---
erDiagram
    %% User Management Entities
    User {
        uuid user_id PK
        string email UK
        string password_hash
        string phone UK
        string national_id UK
        string first_name
        string last_name
        date date_of_birth
        enum gender
        text address
        string profile_image_url
        enum status
        timestamp created_at
        timestamp updated_at
        uuid created_by FK
        uuid updated_by FK
    }

    Role {
        uuid role_id PK
        string role_name UK
        text description
        json permissions
        boolean is_active
        timestamp created_at
    }

    UserRole {
        uuid user_role_id PK
        uuid user_id FK
        uuid role_id FK
        uuid branch_id FK
        date assigned_date
        date end_date
        boolean is_active
        uuid assigned_by FK
    }

    Branch {
        uuid branch_id PK
        string branch_name
        text address
        string phone
        string email
        uuid manager_id FK
        boolean is_active
        timestamp created_at
    }

    %% Volunteer Management
    Volunteer {
        uuid volunteer_id PK
        uuid user_id FK
        text skills
        text availability
        enum experience_level
        text emergency_contact
        string emergency_phone
        date join_date
        enum status
        int total_points
        timestamp last_active
        uuid approved_by FK
        timestamp approved_at
    }

    VolunteerApplication {
        uuid application_id PK
        uuid user_id FK
        text motivation_letter
        text previous_experience
        json documents_urls
        enum status
        text rejection_reason
        uuid reviewed_by FK
        timestamp reviewed_at
        timestamp submitted_at
    }

    Activity {
        uuid activity_id PK
        string activity_name
        text description
        enum category
        boolean is_active
        uuid created_by FK
        timestamp created_at
    }

    VolunteerActivity {
        uuid volunteer_activity_id PK
        uuid volunteer_id FK
        uuid activity_id FK
        date joined_date
        boolean is_active
        uuid assigned_by FK
    }

    %% Task Management
    Task {
        uuid task_id PK
        string title
        text description
        uuid activity_id FK
        uuid assigned_to FK
        uuid assigned_by FK
        enum priority
        enum status
        date due_date
        timestamp assigned_at
        timestamp started_at
        timestamp completed_at
        text completion_notes
        json images_urls
        int points_awarded
        uuid evaluated_by FK
        timestamp evaluated_at
    }

    TaskEvaluation {
        uuid evaluation_id PK
        uuid task_id FK
        int commitment_score
        int achievement_score
        int team_spirit_score
        int initiative_score
        int total_points
        text feedback
        uuid evaluated_by FK
        timestamp evaluated_at
    }

    %% Beneficiary Management
    Beneficiary {
        uuid beneficiary_id PK
        string first_name
        string last_name
        string phone UK
        string national_id UK
        text address
        int household_size
        int children_count
        enum income_level
        text special_needs
        text health_conditions
        json documents_urls
        enum status
        uuid charity_id FK
        boolean is_shared
        uuid created_by FK
        timestamp created_at
        uuid updated_by FK
        timestamp updated_at
    }

    Charity {
        uuid charity_id PK
        string charity_name UK
        text description
        text address
        string phone
        string email
        string license_number UK
        enum status
        uuid approved_by FK
        timestamp approved_at
        timestamp created_at
    }

    SharedBeneficiary {
        uuid shared_id PK
        uuid beneficiary_id FK
        uuid charity_id FK
        enum permission_level
        timestamp shared_at
        uuid shared_by FK
        boolean is_active
    }

    %% Aid Management
    AidType {
        uuid aid_type_id PK
        string type_name UK
        text description
        enum category
        string unit_of_measure
        boolean is_active
    }

    Aid {
        uuid aid_id PK
        uuid beneficiary_id FK
        uuid aid_type_id FK
        decimal quantity
        text description
        date assigned_date
        enum status
        uuid assigned_by FK
        uuid delivered_by FK
        timestamp delivered_at
        text delivery_notes
        json images_urls
    }

    Inventory {
        uuid inventory_id PK
        uuid aid_type_id FK
        uuid branch_id FK
        decimal current_stock
        decimal minimum_threshold
        decimal unit_cost
        date expiry_date
        string batch_number
        uuid updated_by FK
        timestamp updated_at
    }

    Donation {
        uuid donation_id PK
        uuid donor_id FK
        uuid aid_type_id FK
        decimal quantity
        decimal monetary_value
        date donation_date
        text notes
        uuid received_by FK
        timestamp received_at
    }

    Donor {
        uuid donor_id PK
        string donor_name
        string phone
        string email
        text address
        enum donor_type
        boolean is_anonymous
        timestamp created_at
    }

    %% Distress Management
    DistressReport {
        uuid report_id PK
        uuid beneficiary_id FK
        string title
        text description
        enum urgency_level
        enum category
        text location
        json images_urls
        enum status
        uuid reported_by FK
        timestamp reported_at
        uuid assigned_to FK
        timestamp assigned_at
        uuid resolved_by FK
        timestamp resolved_at
        text resolution_notes
    }

    %% Medical Management
    MedicalRecord {
        uuid medical_record_id PK
        uuid beneficiary_id FK
        text medical_conditions
        text allergies
        text current_medications
        date last_checkup
        uuid doctor_id FK
        timestamp created_at
        uuid created_by FK
    }

    Medication {
        uuid medication_id PK
        string medication_name UK
        text description
        string dosage_form
        string strength
        date expiry_date
        string batch_number
        decimal current_stock
        decimal unit_cost
        uuid updated_by FK
        timestamp updated_at
    }

    MedicationDispensing {
        uuid dispensing_id PK
        uuid beneficiary_id FK
        uuid medication_id FK
        decimal quantity_dispensed
        text instructions
        date dispensed_date
        uuid dispensed_by FK
        timestamp created_at
    }

    %% Feedback and Communication
    Feedback {
        uuid feedback_id PK
        uuid from_user_id FK
        uuid to_user_id FK
        enum feedback_type
        int rating
        text message
        enum status
        timestamp created_at
        timestamp responded_at
        text response
    }

    Poll {
        uuid poll_id PK
        string title
        text description
        json options
        date start_date
        date end_date
        enum target_audience
        uuid created_by FK
        timestamp created_at
        boolean is_active
    }

    PollResponse {
        uuid response_id PK
        uuid poll_id FK
        uuid user_id FK
        json selected_options
        text additional_comments
        timestamp responded_at
    }

    %% Audit and Logging
    AuditLog {
        uuid log_id PK
        uuid user_id FK
        string table_name
        string operation_type
        uuid record_id
        json old_values
        json new_values
        string ip_address
        string user_agent
        timestamp created_at
    }

    %% Rewards System
    RewardTier {
        uuid tier_id PK
        string tier_name UK
        int min_points
        int max_points
        text benefits
        string badge_image_url
        boolean is_active
    }

    VolunteerReward {
        uuid reward_id PK
        uuid volunteer_id FK
        uuid tier_id FK
        int points_earned
        date earned_date
        text description
        uuid awarded_by FK
        timestamp created_at
    }

    %% Excel Integration
    ExcelImport {
        uuid import_id PK
        string file_name
        string file_path
        enum import_type
        json mapping_config
        int total_records
        int successful_records
        int failed_records
        json error_log
        enum status
        uuid imported_by FK
        timestamp imported_at
    }

    %% Relationships
    User ||--o{ UserRole : "has"
    Role ||--o{ UserRole : "assigned to"
    Branch ||--o{ UserRole : "works at"
    User ||--o{ Volunteer : "is"
    User ||--o{ VolunteerApplication : "submits"
    Volunteer ||--o{ VolunteerActivity : "participates in"
    Activity ||--o{ VolunteerActivity : "includes"
    Activity ||--o{ Task : "contains"
    Volunteer ||--o{ Task : "assigned to"
    User ||--o{ Task : "assigns"
    Task ||--|| TaskEvaluation : "evaluated by"
    User ||--o{ TaskEvaluation : "evaluates"
    
    Charity ||--o{ Beneficiary : "manages"
    Beneficiary ||--o{ SharedBeneficiary : "shared as"
    Charity ||--o{ SharedBeneficiary : "shares with"
    Beneficiary ||--o{ Aid : "receives"
    AidType ||--o{ Aid : "type of"
    User ||--o{ Aid : "assigns"
    AidType ||--o{ Inventory : "stored as"
    Branch ||--o{ Inventory : "stores"
    
    Donor ||--o{ Donation : "makes"
    AidType ||--o{ Donation : "donated as"
    User ||--o{ Donation : "receives"
    
    Beneficiary ||--o{ DistressReport : "reports"
    User ||--o{ DistressReport : "handles"
    
    Beneficiary ||--o{ MedicalRecord : "has"
    User ||--o{ MedicalRecord : "maintains"
    Beneficiary ||--o{ MedicationDispensing : "receives"
    Medication ||--o{ MedicationDispensing : "dispensed as"
    User ||--o{ MedicationDispensing : "dispenses"
    
    User ||--o{ Feedback : "gives"
    User ||--o{ Feedback : "receives"
    User ||--o{ Poll : "creates"
    Poll ||--o{ PollResponse : "receives"
    User ||--o{ PollResponse : "responds to"
    
    User ||--o{ AuditLog : "performs action"
    
    Volunteer ||--o{ VolunteerReward : "earns"
    RewardTier ||--o{ VolunteerReward : "awarded as"
    User ||--o{ VolunteerReward : "awards"
    
    User ||--o{ ExcelImport : "imports"
    
    Branch ||--o{ User : "managed by"
    User ||--o{ User : "created by"
    User ||--o{ User : "updated by"
---
---

## 🧪 Testing

- Unit and integration tests for NestJS backend
- Manual user flow tests for admin and volunteer interfaces
- Load testing for API and image uploads

---
## ⚙️ Installation

```bash
# Clone the repo
git clone https://github.com/yourusername/resala.git
cd resala

# Install frontend and backend
cd client && npm install
cd ../server && npm install

---

Let me know if you'd like to also include API routes, database schema diagrams, or code scaffolding suggestions in the README!
