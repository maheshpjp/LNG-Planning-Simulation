<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:38bdf8,100:0ea5e9&height=200&section=header&text=LNG%20Planner&fontSize=70&fontColor=white&fontAlignY=38&desc=Annual%20LNG%20Planning%20and%20Simulation%20System&descAlignY=60&descSize=18" width="100%" />

<br/>

[![IOCL Summer Training](https://img.shields.io/badge/🏭%20IOCL%20Summer%20Training%202026-1C74A1?style=for-the-badge)](#)

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript%20(AJAX)-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white)
![SAP](https://img.shields.io/badge/SAP%20Read%20APIs-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![Excel](https://img.shields.io/badge/openpyxl%20%2F%20xlsxwriter-217346?style=flat-square&logo=microsoftexcel&logoColor=white)

</div>

---

## 🔍 What is the LNG Planning System?

The LNG Annual Planning & Simulation System is an **enterprise-oriented Django web application** that replaces spreadsheet-based annual LNG planning with a **structured, role-based, database-driven workflow**.

Planners manage **suppliers, customers, refineries, LNG cargoes and plant inventory** in one place. The system keeps a **read-only Master planning dataset**, while planners clone it into **private simulations** for what-if analysis. Approved simulations can be **promoted to a new Master Version** by authorized Planning Admins.

At its core, a **Daily Inventory Engine** automatically projects supply, allocations, shortfalls, cargo deliveries and closing inventory — day by day — and flags problems before they happen.

> 🏢 Developed during Summer Training at **Indian Oil Corporation Limited (IOCL)**, CBTC, IIPM Gurgaon &nbsp;·&nbsp; 👨‍💻 Full Stack Developer Intern &nbsp;·&nbsp; 📅 May – July 2026

---

## 🎯 Why was it built?

Traditional annual LNG planning relies on spreadsheets, which leads to:

| Challenge | How this project solves it |
|---|---|
| 🧮 Manual inventory calculations | Automated Daily Inventory Engine |
| ⚠️ High probability of calculation errors | Centralized business logic with validation |
| 🗂️ Difficult version management | Immutable, versioned Master datasets |
| 🔍 Limited auditability | Comments, version history & traceability |
| 🔀 Hard to handle alternative scenarios | Isolated, private simulations |
| 🔁 Manual propagation of supply changes | Bulk Supply Adjustment with auto-recalculation |
| 👥 Limited collaboration & governance | Role-based access control & publish workflow |

---

## ✨ What can you do with it?

| Feature | What it does |
|---|---|
| 🔐 **Role-Based Access** | Superuser, Planner & Planning Admin roles with server-side permission checks |
| 📊 **Master Versioning** | Single authoritative Master — every change creates a new immutable version |
| 🧪 **Simulations** | Clone the Master into private simulations for what-if analysis |
| 🚢 **Supplier Management** | Plant mapping, multiple non-contiguous supply date ranges, daily quantities & priority |
| 🏭 **Customer & Refinery Management** | Demand date ranges, many-to-many supplier links, allocation % & priorities |
| ⛴️ **Cargo Management** | Cargo reference, destination plant, delivery date & quantity |
| 📈 **Bulk Supply Adjustment** | Increase / decrease a supplier's supply by % — with preview before applying |
| 📅 **Daily Inventory Projection** | Plant, cargo & closing inventory, projected balance, shortfalls & alerts |
| 🔎 **Search & Filtering** | AJAX server-side search + custom date-range filtering |
| 📥 **Excel Export** | Downloadable `.xlsx` reports matching the selected date range |
| 💬 **Comments & Audit Trail** | Document planning decisions — included in Excel exports |
| 🔄 **SAP Integration** | Refresh Master data from SAP Read APIs |

---

## 👥 User Roles

| Role | Responsibilities |
|---|---|
| 🛡️ **Superuser** | Manage employees and assign roles through Django Admin |
| 🧑‍💼 **Planner** | Create & manage private simulations, perform planning and export reports |
| 👑 **Planning Admin** | All Planner capabilities **+** SAP Refresh and Publish-to-Master |

> 🔒 Planners can only modify simulations **they created**. Planning Admin privileges for SAP Refresh and Publish **do not** grant access to other users' simulations.

<details>
<summary><b>📋 Detailed role capabilities</b></summary>

<br/>

**Superuser** — system administration

```
Django Admin
   ├── Create Employees
   ├── Assign Planner Role
   ├── Assign Planning Admin Role
   └── Activate / Deactivate Employees
```

**Planner** can:
View Master · Create simulations · Edit own simulations · Manage suppliers · Manage customers · Manage refineries · Manage cargo · Run planning calculations · Add comments · Export Excel

**Planning Admin** has all Planner capabilities plus:
Refresh Master from SAP · Publish Simulation as Master · Create Master Versions

The project deliberately separates **system administration** from **planning responsibilities**.

</details>

---

## 🛠️ Built With

| Part | Tools Used |
|---|---|
| **Backend** | Python, Django |
| **Frontend** | HTML5, CSS3, JavaScript, AJAX |
| **UI** | Bootstrap |
| **Database (Dev)** | SQLite |
| **Database (Prod)** | PostgreSQL / Oracle |
| **ORM** | Django ORM |
| **Excel Reporting** | openpyxl / xlsxwriter |
| **Enterprise Integration** | SAP Read APIs |
| **Auth** | Django Authentication |
| **Browsers** | Chrome / Edge / Firefox |
| **OS** | Windows / Linux |

---

## 📊 Master Version Management

The system maintains a **single authoritative Master dataset**. Every change creates a new immutable version, preserving history and traceability.

```
SAP Refresh
     ↓
 Master V5
     ↓
Create Simulation
     ↓
Planner modifies scenario
     ↓
Planning Admin reviews
     ↓
  Publish
     ↓
 Master V6
```

## 🧪 Simulation-Based Planning

Clone the current Master into private simulations — experiment freely without touching the approved Master.

```
Master V14
   ├── Simulation A  →  Increased Supply
   ├── Simulation B  →  Reduced Supply
   └── Simulation C  →  Additional Cargo
```

Each simulation is owned by its creator and remains **isolated** from other users' simulations.

---

## 📈 Bulk Supply Adjustment

```
Select Supplier
      ↓
Increase / Decrease
      ↓
Enter Percentage
      ↓
Preview Impact      ← inspect before committing
      ↓
Apply Change
      ↓
Update Customers
      ↓
Update Refineries
      ↓
Recalculate Inventory
```

---

## 📅 Daily Inventory Engine

The core business-logic component. For **each day**, the system processes:

```
Supplier Supply
      ↓
Customer Allocation
      ↓
Refinery Allocation
      ↓
Remaining Supply → Plant Inventory
      ↓
Customer Shortfall
      ↓
Refinery Shortfall
      ↓
Cargo Delivery
      ↓
Closing Inventory
      ↓
Projected Balance
```

It calculates **Plant Inventory, Cargo Inventory, Closing Inventory, Projected Balance, Customer Shortfall, Refinery Shortfall** and **Inventory Alerts**.

> 🚨 Negative inventory and projected shortfalls are **highlighted** so planners can take corrective action.

---

## 📥 Excel Export

Downloadable `.xlsx` reports include:

| Sheet Content | |
|---|---|
| 🚢 Suppliers | 📦 Plant Inventory |
| 🏭 Customers | ⛴️ Cargo Inventory |
| 🛢️ Refineries | 📉 Closing Inventory |
| 🚚 Cargo | 📊 Projected Balance |
| 💬 Comments | 📅 Selected date range |

> The Excel report reflects the **same date-range filter** currently selected in the application.

---

## 🏗️ System Architecture

```
┌──────────────────────────────┐
│         Web Browser          │
│       HTML / CSS / JS        │
└──────────────┬───────────────┘
               ▼
┌──────────────────────────────┐
│      Django Application      │
│   Views / URLs / Templates   │
│ Authentication / Validation  │
└──────────────┬───────────────┘
               ▼
┌──────────────────────────────┐
│        Business Logic        │
│       Inventory Engine       │
│      Simulation Engine       │
│       Bulk Adjustment        │
│       Role Permissions       │
└──────────────┬───────────────┘
               ▼
┌──────────────────────────────┐
│          Django ORM          │
│     Relational Database      │
└──────────────┬───────────────┘
               ▼
┌──────────────────────────────┐
│       SAP Integration        │
│          Read APIs           │
└──────────────────────────────┘
```

The architecture separates the **presentation, Django application, business logic, database, SAP integration, inventory engine** and **reporting** layers.

---

## 🗃️ Data Model

| Group | Models |
|---|---|
| **Core** | `Employee`, `Plant`, `MasterVersion`, `PlantInventory`, `Simulation` |
| **Supply** | `Supplier`, `SupplierDate` |
| **Customers** | `Customer`, `CustomerDate`, `CustomerSupplierRelationship` |
| **Refineries** | `Refinery`, `RefineryDate`, `RefinerySupplierRelationship` |
| **Logistics** | `Cargo` |
| **Other** | `SimulationComment`, `APIConfiguration` |

**Core relationships**

```
MasterVersion
     └── Simulation
            │
   ┌────────┼─────────┬─────────┐
   ▼        ▼         ▼         ▼
Supplier Customer  Refinery   Cargo
   │        │         │
   └────────┼─────────┘
            ▼
      Relationships
            ▼
     Inventory Engine
```

> Master versions remain **immutable** after creation.

---

## 🚀 How it works, end to end

```
Employee Login
      ↓
Dashboard
      ↓
View Current Master
      ↓
Create Simulation
      ↓
Edit Suppliers → Customers → Refineries → Cargo
      ↓
Bulk Supply Adjustment
      ↓
Daily Inventory Projection
      ↓
Review Inventory Alerts
      ↓
Add Comments
      ↓
Export Excel
      ↓
Planning Admin Review
      ↓
Publish to Master
      ↓
New Master Version
```

> 🔄 SAP Refresh can independently update the Master through the authorized Planning Admin workflow.

---

## ⚡ Performance Optimizations

| Optimization | Purpose |
|---|---|
| `select_related()` | Efficient foreign-key lookups |
| `prefetch_related()` | Reverse & many-to-many relationships |
| Pagination | Large entity lists |
| AJAX search & filtering | Fast, server-side lookups without page reloads |
| Query-level date filtering | Fetch only the needed date range |
| Indexed search fields | Faster searches |
| Reduced DB round trips | Lower latency |

> Built to handle potentially **hundreds** of Suppliers, Customers, Refineries and Cargo records.

---

## 🔐 Security

- ✅ Authentication-protected planning screens
- ✅ Role-based authorization with server-side permission checks
- ✅ Protected URLs & session management
- ✅ Simulation ownership restrictions
- ✅ Restricted SAP Refresh & Master publishing
- ✅ Centralized employee role management

> Permissions are enforced at the **view / business-logic layer** — not just hidden in the frontend UI.

---

## 💻 Local Setup

**1. Clone the repository**

```bash
git clone <repository-url>
cd LNG
```

**2. Create & activate a virtual environment**

```bash
# Windows
python -m venv venv
.\venv\Scripts\Activate.ps1

# Linux / macOS
python3 -m venv venv
source venv/bin/activate
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
# or, if there's no requirements.txt:
pip install django requests openpyxl
```

**4. Apply migrations**

```bash
python manage.py migrate
```

**5. Create an admin user**

```bash
python manage.py createsuperuser
```

**6. Start the development server**

```bash
python manage.py runserver
```

| | URL |
|---|---|
| 🌐 App | http://127.0.0.1:8000/ |
| 🛠️ Django Admin | http://127.0.0.1:8000/admin/ |

---

## 📸 Screenshots

| Login Page | Dashboard |
|---|---|
| ![Login](screenshots/login.png) | ![Dashboard](screenshots/dashboard.png) |

| Master Data | Supplier Module |
|---|---|
| ![Master Data](screenshots/master-data.png) | ![Supplier](screenshots/supplier.png) |

| Customer Module | Refinery & Cargo Modules |
|---|---|
| ![Customer](screenshots/customer.png) | ![Refinery & Cargo](screenshots/refinery-cargo.png) |

| Bulk Supply Adjustment | Daily Inventory Projection |
|---|---|
| ![Bulk Adjustment](screenshots/bulk-adjustment.png) | ![Inventory Projection](screenshots/inventory-projection.png) |

---

## 🧠 Notes on the SAP Integration

- **SAP Read APIs** are consumed for: Plants, Opening Inventory, Suppliers, Supplier date ranges, Customers, Customer date ranges, Refineries, Refinery date ranges, Cargo and Supplier relationships.
- The current implementation uses **manually triggered** SAP Read APIs configured through the `APIConfiguration` model.
- 🔮 **Future scope:** automated / scheduled SAP synchronization.

---

## 🙋‍♂️ Made by

<div align="center">

**Your Name😉**

*Full Stack Developer Intern · Indian Oil Corporation Limited (IOCL)*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/your-profile/)
[![Email](https://img.shields.io/badge/Email-Say%20Hi-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)

</div>

---

<div align="center">

If this project helped you or you liked it, drop a ⭐ — it means a lot!

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:38bdf8,100:0ea5e9&height=100&section=footer"/>

</div>
