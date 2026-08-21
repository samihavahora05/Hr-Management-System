# Enterprise HR Management System (HRMS)

An enterprise-grade, role-aware **Human Resource Management System** designed for modern organizations. Built with **Laravel 11 (PHP 8+)** on the backend and **Next.js 15 (TypeScript + TailwindCSS)** on the frontend, featuring real-time attendance tracking, leave management, recruitment ATS, performance analytics, and administrative overrides.

---

## 🌟 Key Features & Role Portals

### 🛡️ Admin Portal (`/admin`)
- **System-wide Attendance Register**: Track organization-wide check-in & check-out logs, punctuality metrics, and perform manual clock-in/out edits & corrections.
- **Master User Management**: Manage organization employees, designations, roles, department assignments, and permissions.
- **RBAC & Security**: Define custom roles, fine-grained access control permissions, and view audit trail logs.
- **Organization Settings**: Configure shifts, work schedules, grace periods, and organizational structure.

### 💼 HR Portal (`/hr`)
- **Recruitment & ATS**: Manage job openings, applicant pipelines, schedule interviews, and generate digital job offer letters.
- **Onboarding Checklists**: Assign and track new employee tasks and compliance documentation.
- **Statutory Payroll**: Configure salary structures, tax deductions, allowances, and generate monthly payslips.

### 👔 Manager & Team Leader Portals (`/manager` & `/team-leader`)
- **Direct Team Monitoring**: View team check-in status, attendance logs, and punctuality stats.
- **Task Management**: Assign tasks, monitor completion status, and review deliverables.
- **Performance Reviews**: Conduct periodic performance evaluations and track team goals.

### 👤 Employee Portal (`/employee`)
- **Personal Attendance & Clock-In/Out**: One-click check-in and check-out with automatic late calculation.
- **Leave Applications**: Request leave, view real-time balances, and track approval statuses.
- **Expense Claims & Loans**: Submit expense reimbursement claims with receipt uploads and apply for salary loans.
- **My Vault & Documents**: Secure storage for employment contracts, IDs, and tax documents.

---

## 🛠️ Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Backend Framework** | Laravel 11.x (PHP 8.2+) |
| **Frontend Framework** | Next.js 15 (React 19, TypeScript) |
| **Styling** | Vanilla CSS + TailwindCSS v4 |
| **Database** | MySQL / MariaDB |
| **Authentication** | Custom Token-Based Auth with Role Guard Middleware |
| **Containerization** | Docker & Docker Compose |

---

## 🚀 Getting Started

### Prerequisites
- **PHP** >= 8.2 with PDO, OpenSSL, Mbstring, and Tokenizer extensions
- **Composer** >= 2.0
- **Node.js** >= 18.x & **npm**
- **MySQL** >= 8.0

---

### Backend Setup (Laravel)

1. **Navigate to the backend directory**:
   ```bash
   cd backend
   ```

2. **Install PHP dependencies**:
   ```bash
   composer install
   ```

3. **Configure Environment Variables**:
   Copy `.env.example` to `.env` and configure your database credentials:
   ```bash
   cp .env.example .env
   ```
   Set your MySQL connection in `.env`:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=hr_management_system
   DB_USERNAME=root
   DB_PASSWORD=
   ```

4. **Generate Application Key**:
   ```bash
   php artisan key:generate
   ```

5. **Run Database Migrations and Seeders**:
   ```bash
   php artisan migrate --seed
   ```

6. **Start Backend Development Server**:
   ```bash
   php artisan serve
   ```
   *The API server will run at `http://localhost:8000`.*

---

### Frontend Setup (Next.js)

1. **Navigate to the frontend directory**:
   ```bash
   cd frontend
   ```

2. **Install Node dependencies**:
   ```bash
   npm install
   ```

3. **Start Frontend Development Server**:
   ```bash
   npm run dev
   ```
   *The web application will run at `http://localhost:3000`.*

---

## 🐳 Docker Deployment

To spin up the entire system (Frontend, Backend, and Database) using Docker Compose:

```bash
docker-compose up --build -d
```

---

## 📂 Project Structure

```text
hr-management-system/
├── backend/                  # Laravel API Application
│   ├── app/
│   │   ├── Http/Controllers/ # Attendance, Employee, Leave, Task, Payroll Controllers
│   │   ├── Models/           # Eloquent Models (User, Attendance, LeaveRequest, etc.)
│   │   └── Services/         # Statutory Payroll & Notification Services
│   ├── database/             # Migrations & Seeders
│   └── routes/api.php        # API Endpoints
├── frontend/                 # Next.js Application
│   ├── app/                  # Next.js App Router (Admin, HR, Manager, Employee portals)
│   ├── components/           # UI Components, Portals Layouts, Modals, Tables
│   └── lib/                  # API fetcher, Auth context, CSV export utilities
├── docker-compose.yml        # Docker Multi-container Configuration
└── README.md                 # Full Project Documentation
```

---

## 📜 License

Distributed under the MIT License.
