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

- User management
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
- MVP in 2–3 months
- Full admin panel, volunteer portal, and backend API
- Arabic RTL responsive UI

---

## 🧱 Technology Stack

| Layer        | Technology            | Notes                                  |
|--------------|------------------------|----------------------------------------|
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

## ⚙️ Functional Requirements

### 👤 User Management (Admin)
- Create/edit/deactivate volunteer accounts
- Upload 1 profile image per user
- Assign roles (admin / volunteer)

### 🧾 Task Management (Admin & Volunteer)
- Admin creates tasks: title, description, start/end, image
- Volunteer marks tasks as done + uploads proof image
- Admin verifies completed tasks

### 🧍 Beneficiary Management (Admin)
- Store: full name, gender, age, case type, area
- Upload 2–5 images per beneficiary

### 🏠 Auth & Access
- JWT login (secure)
- Volunteers see only their tasks
- Admins see and control everything

### 📊 Admin Dashboard
- KPIs: active users, task statuses, beneficiaries
- Visuals: charts, filters, search by name/date/status

---

## 🚀 Non-Functional Requirements

| Requirement        | Description                                                 |
|--------------------|-------------------------------------------------------------|
| 💨 Performance      | 300 concurrent users, lazy loading, optimized DB queries    |
| 🔐 Security         | JWT, upload tokens, input validation                        |
| 💾 Storage          | Compressed Cloudinary uploads                               |
| 🛠️ Maintainability  | Modular clean code with NestJS and React                    |
| 🔄 Scalability      | Ready for multi-branch expansion                            |
| 📱 Mobile Ready     | Responsive RTL Arabic interface                             |

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
