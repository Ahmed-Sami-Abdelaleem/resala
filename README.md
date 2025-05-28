# 📦 Resala Branch Management Platform (فرع العاشر من رمضان)

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)]()
[![Build Status](https://img.shields.io/travis/user/repo/master.svg)](https://travis-ci.org/user/repo)

> A volunteer & beneficiary management system for **Resala Charity** - digitizing internal operations for the 10th of Ramadan branch. Built with ❤️ in Egypt.

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
