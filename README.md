# 📢 ADLynk — Multi-Channel Advertising Management Platform

<div align="center">

![Version](https://img.shields.io/badge/Version-1.0-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Milestone%203%20Complete-green?style=for-the-badge)
![University](https://img.shields.io/badge/Namal%20University-Mianwali-orange?style=for-the-badge)

*A centralized database-driven platform connecting business owners, billboard/vehicle asset owners, and digital advertisers across Pakistan.*

</div>

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Objectives](#-objectives)
- [Tech Stack](#-tech-stack)
- [System Requirements](#-system-requirements)
- [Installation](#-installation)
- [Usage](#-usage)
- [Database Design](#-database-design)
  - [Entities](#entities)
  - [Key Relationships](#key-relationships)
  - [Business Rules](#business-rules)
- [Project Structure](#-project-structure)
- [ERD Diagram](#-erd-diagram)
- [Team](#-team)
- [References](#-references)

---

## 🧭 Project Overview

**ADLynk** is a Multi-Channel Advertising Management Platform designed to consolidate all advertising operations into a single digital system. The platform enables business owners to manage campaigns from one unified dashboard, allowing them to book:

- 🏙️ Billboard advertising spaces (across cities in Pakistan)
- 🚗 Vehicle branding services
- 📱 Digital / social media marketing services

Using a centralized relational database, ADLynk efficiently stores and manages information on users, advertising services, billboard locations, bookings, payments, and financials — ensuring streamlined data management, transparent pricing, and easy campaign tracking.

---

## ❗ Problem Statement

The current advertising ecosystem in Pakistan suffers from several critical gaps:

| Problem | Impact |
|---|---|
| **Lack of Integration** | Business owners must contact billboard owners, vehicle branding companies, and advertisers separately via informal channels |
| **Lack of Transparency** | No centralized system to check prices, availability, or confirm bookings |
| **Manual Processes** | Campaign tracking, payments, and bookings done via spreadsheets or phone calls |
| **No Centralized Booking** | Double-bookings, cancellations, and unresolved disputes are common |

**ADLynk directly solves all of the above** by providing a single platform that brings all advertising stakeholders together with structured booking, secure payments, and full campaign visibility.

---

## 🎯 Objectives

1. **Integrate** all advertising services (billboard, vehicle, digital) into one platform
2. **Provide transparency** in service discovery, pricing, availability, and booking confirmation
3. **Enable direct booking** and campaign management without manual effort
4. **Automate** campaign tracking, payments, and booking workflows
5. **Prevent double-bookings** and booking conflicts through a structured reservation system
6. **Free businesses** to focus on growth rather than advertising logistics
7. **Democratize access** to professional advertising for businesses of all sizes, including small e-commerce stores

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Node.js (JavaScript ES6+) |
| Frontend | React.js with TypeScript |
| API Communication | Axios |
| Styling | HTML5, CSS3, TailwindCSS |
| Data Exchange Format | JSON |
| Database Engine | MySQL |
| Data Modeling | EER / Relational Model |
| Configuration | dotenv (`.env`) |
| Version Control | Git / GitHub |

### Languages Used

| # | Language | Where It Is Used |
|---|---|---|
| 1 | **JavaScript (ES6+)** | Backend (Node.js), Axios API calls, async/await operations |
| 2 | **TypeScript** | React frontend components, type-safe API handling, state management |
| 3 | **SQL** | MySQL schema (DDL), data manipulation (DML), queries, joins, and FK constraints |
| 4 | **HTML5** | Page layouts and form structures within React components |
| 5 | **CSS3 / TailwindCSS** | Responsive UI styling, grid and flexbox layouts |
| 6 | **JSON** | Request/response format between frontend and backend |
| 7 | **.env** | Database credentials, JWT secrets, server configuration |

---

## 💻 System Requirements

### Software

- **Node.js** v18.x or later
- **npm** v9.x or later (or **yarn**)
- **MySQL** v8.0 or later
- **Git**
- A modern web browser (Chrome, Edge, or Firefox — latest version)
- Code editor (VS Code recommended)

### Hardware (minimum recommended)

- **Processor:** Dual-core 2.0 GHz or higher
- **RAM:** 4 GB minimum (8 GB recommended)
- **Storage:** 500 MB free space for project files and dependencies
- **Internet connection** for installing dependencies and accessing external APIs (if any)

### Libraries / Packages

**Backend (Node.js):**
- `express` — REST API framework
- `mysql2` — MySQL database driver
- `dotenv` — environment variable management
- `jsonwebtoken` — authentication/authorization
- `bcrypt` — password hashing
- `cors` — cross-origin request handling

**Frontend (React + TypeScript):**
- `react` / `react-dom`
- `typescript`
- `axios` — HTTP client
- `tailwindcss` — utility-first CSS framework
- `react-router-dom` — client-side routing

> Exact versions are pinned in `package.json` for both `frontend/` and `backend/`.

---

## ⚙️ Installation

Follow these steps to set up the project locally.

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/ADLynk.git
cd ADLynk
```

### 2. Set up the database

1. Start your MySQL server.
2. Create a new database:
   ```sql
   CREATE DATABASE adlynk;
   ```
3. Run the schema (DDL) script to create all tables:
   ```bash
   mysql -u <username> -p adlynk < database/schema.sql
   ```
4. (Optional) Load sample data:
   ```bash
   mysql -u <username> -p adlynk < database/sample_data.sql
   ```
5. (Optional) Load stored procedures, functions, views, and triggers:
   ```bash
   mysql -u <username> -p adlynk < database/procedures_and_functions.sql
   mysql -u <username> -p adlynk < database/views_and_triggers.sql
   ```

### 3. Configure environment variables

Create a `.env` file inside the `backend/` directory:

```env
PORT=5000
DB_HOST=localhost
DB_USER=your_mysql_username
DB_PASSWORD=your_mysql_password
DB_NAME=adlynk
JWT_SECRET=your_jwt_secret_key
```

### 4. Install backend dependencies

```bash
cd backend
npm install
```

### 5. Install frontend dependencies

```bash
cd ../frontend
npm install
```

---

## ▶️ Usage

### 1. Start the backend server

```bash
cd backend
npm run dev
```

The backend API will run on `http://localhost:5000` (or the port set in `.env`).

### 2. Start the frontend application

```bash
cd frontend
npm start
```

The frontend will run on `http://localhost:3000` and connect to the backend API.

### 3. Using the platform

Once both servers are running, open `http://localhost:3000` in your browser to:

- **Register/Login** as a Business Owner, Asset Owner, or Advertiser
- **Business Owners:** create campaigns and book billboards, vehicles, or digital services
- **Asset Owners:** list billboards/vehicles, manage availability, view earnings, request withdrawals
- **Advertisers:** list digital services, manage availability, view earnings, request withdrawals
- **All Users:** view account balance, payment history, ledger entries, and submit reviews after booking completion

---

## 🗄️ Database Design

### Entities

The database consists of **14 core entities**:

| # | Entity | Description |
|---|---|---|
| 01 | `USER` | Supertype — shared information for all registered users |
| 02 | `BUSINESS_OWNER` | Clients who create campaigns and purchase advertising services |
| 03 | `ASSET_OWNER` | Users who own physical assets (billboards, vehicles) |
| 04 | `ADVERTISER` | Users providing digital advertising services |
| 05 | `BILLBOARD` | Billboard asset listings with location and pricing |
| 06 | `VEHICLE` | Vehicle fleet listings available for branding |
| 07 | `DIGITAL_SERVICE` | Online/social media advertising service offerings |
| 08 | `CAMPAIGN` | Advertising campaigns created by business owners |
| 09 | `BOOKING` | Reservations of services or physical assets |
| 10 | `PAYMENT` | Payment transaction records for bookings |
| 11 | `WITHDRAWAL` | Withdrawal requests by service providers |
| 12 | `REVIEW` | Ratings and feedback submitted after booking completion |
| 13 | `ACCOUNT_BALANCE` | Financial balance tracking for providers |
| 14 | `LEDGER_ENTRY` | Full audit trail of all balance changes |

---

### Key Relationships

```
USER (supertype)
 ├── BUSINESS_OWNER  ──creates──▶  CAMPAIGN
 │                                      │
 │                                   contains
 │                                      │
 │                                      ▼
 │                                   BOOKING ──────▶ BILLBOARD
 │                                      │      or──▶ VEHICLE
 │                                      │      or──▶ DIGITAL_SERVICE
 │                                      │
 │                                      ▼
 │                                   PAYMENT ──▶ LEDGER_ENTRY
 │
 ├── ASSET_OWNER  ──lists──▶  BILLBOARD / VEHICLE
 │                                  │
 │                            ACCOUNT_BALANCE
 │                                  │
 │                            WITHDRAWAL
 │
 └── ADVERTISER  ──provides──▶  DIGITAL_SERVICE
                                     │
                               ACCOUNT_BALANCE
                                     │
                               WITHDRAWAL
```

---

### Business Rules

1. A `USER` must have at least one role (`BUSINESS_OWNER`, `ADVERTISER`, or `ASSET_OWNER`) and may hold multiple roles simultaneously.
2. Each `BILLBOARD` and `VEHICLE` belongs to exactly one `ASSET_OWNER`. Assets must have `available` status to be booked and cannot be double-booked on overlapping dates.
3. Each `DIGITAL_SERVICE` belongs to exactly one `ADVERTISER`. Service price is fixed per campaign.
4. Each `CAMPAIGN` maps to exactly one `BOOKING`. `CAMPAIGN.total_budget` must equal `BOOKING.total_amount`. A campaign cannot be deleted if it has an associated booking.
5. A `BOOKING` references exactly one asset/service (`billboard_id`, `vehicle_id`, or `service_id`) — the other two remain `NULL`. Vehicle bookings cannot exceed fleet size.
6. Each `BOOKING` has exactly one `PAYMENT`. `PAYMENT.amount` must equal `BOOKING.total_amount`. Payment must be completed before the provider is credited.
7. Every `ADVERTISER` and `ASSET_OWNER` has exactly one `ACCOUNT_BALANCE`. The current balance equals the sum of all related `LEDGER_ENTRY` amounts.
8. Every balance change must create a `LEDGER_ENTRY` before updating `ACCOUNT_BALANCE`. Ledger entries are **immutable** — they cannot be deleted or modified.
9. Only `ADVERTISERS` and `ASSET_OWNERS` can request `WITHDRAWALS`. Withdrawal amount cannot exceed current balance. Only one pending withdrawal is allowed at a time.
10. A `BOOKING` can have at most **two reviews** (one per party). Reviews are only allowed after booking completion. Ratings must be between **1 and 5**.
11. Platform fee is a fixed percentage of `PAYMENT.amount`. All monetary values are stored in **PKR**. Providers can withdraw only after the booking start date.

---

## 📁 Project Structure

```
ADLynk/
├── backend/
│   ├── src/
│   │   ├── config/          # Database connection, environment setup
│   │   ├── controllers/      # Request handlers (business logic)
│   │   ├── routes/           # API route definitions
│   │   ├── middleware/       # Authentication, validation, error handling
│   │   ├── models/            # Database query/model layer
│   │   └── server.js          # Application entry point
│   ├── .env                   # Environment variables (not committed)
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/        # Reusable React components
│   │   ├── pages/              # Page-level components (Dashboard, Login, etc.)
│   │   ├── services/           # Axios API service functions
│   │   ├── types/               # TypeScript type definitions/interfaces
│   │   ├── App.tsx
│   │   └── index.tsx
│   └── package.json
│
├── database/
│   ├── schema.sql              # DDL — table definitions, PKs, FKs
│   ├── sample_data.sql         # DML — sample seed data
│   ├── procedures_and_functions.sql  # Stored procedures & functions
│   └── views_and_triggers.sql        # Views & triggers
│
├── docs/
│   └── DB_Report_Final.pdf     # Full ERD and database design document
│
└── README.md
```

---

## 📊 ERD Diagram

> The full Entity Relationship Diagram is included in the [Database Design Document (PDF)](./docs/DB_Report_Final.pdf).

The ERD follows an **Enhanced Entity-Relationship (EER)** model with:
- `USER` as a supertype with overlapping subtypes (`BUSINESS_OWNER`, `ASSET_OWNER`, `ADVERTISER`)
- One-to-many and one-to-one relationships enforced via foreign key constraints
- Nullable FK pattern on `BOOKING` for polymorphic asset references

---

## 👨‍💻 Team

| Name | Roll Number | Role |
|---|---|---|
| Muhammad Hamza | NUM-BSCS-2024-48 | Database Design & Documentation |
| Bilal Ahmed Khan | NUM-BSCS-2024-21 | Database Design & Documentation |
| Hadia Yasir | NUM-BSCS-2024-23 | Database Design & Documentation |

---

## 📚 References

1. A. Batool, *Database Systems: Data Modeling and ERD*, Lecture Notes, Namal University, 2026.
2. A. Batool, *Enhanced Entity-Relationship (EER) Modeling*, Lecture Notes, Namal University, 2026.
3. P. Rob and C. Coronel, *Database Systems: Design, Implementation, and Management*, 13th ed., Cengage Learning, 2019.
4. [sql.js — SQLite compiled to WebAssembly](https://sql.js.org/)
5. [React — A JavaScript library for building user interfaces](https://react.dev/)
6. Aurora, *Digital Marketing Landscape in Pakistan*, Dawn Media Group, 2024.
