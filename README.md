# CoreFlow-ERP
A full-stack Enterprise Resource Planning system simulating SAP S/4HANA architecture, integrating Finance, Sales, and Inventory modules with real-time analytics.

#  SAP-Inspired Enterprise Resource Planning (ERP) System

![Django](https://img.shields.io/badge/Django-4.2-green?logo=django)
![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-purple?logo=bootstrap)
![License](https://img.shields.io/badge/License-MIT-yellow)



A comprehensive, full-stack ERP simulation inspired by the architecture of **SAP S/4HANA**. This project demonstrates the integration of core business modules—Finance (FI), Sales & Distribution (SD), Material Management (MM), and Human Capital (HCM)—into a unified platform using Django and Bootstrap 5.

---

##  Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Architecture & Design](#architecture--design)
- [SAP S/4HANA Simulation Concepts](#sap-s4hana-simulation-concepts)
- [Technology Stack](#technology-stack)
- [Installation & Setup](#installation--setup)
- [Quick Start (Simulation Mode)](#quick-start-simulation-mode)
- [Future Enhancements](#future-enhancements)
- [License](#license)

---

## 🌟 Project Overview

This project is designed to replicate the modular nature of enterprise ERP systems. It allows businesses to manage financial transactions, track inventory, process sales orders, and manage employee records in a centralized database. 

Unlike simple CRUD apps, this system implements business logic where actions in one module affect others (e.g., creating a Sales Order automatically updates Inventory levels and generates a Finance Journal Entry).

### Screenshots
*(Placeholder for screenshots)*
> ![Dashboard](screenshots/dashboard.png)
> *Executive Dashboard with KPIs and Charts*
>
> ![Sales](screenshots/sales.png)
> *Sales & Distribution Order Management*

---



##  Key Features

### 1. **Executive Dashboard**
- Real-time KPI cards (Total Revenue, Net Profit, Pending Orders).
- Interactive charts powered by **Chart.js** (Financial P&L, Sales Distribution).
- Recent activity feed tracking cross-module transactions.



### 2. **Finance Module (FI)**
- **General Ledger:** Record Income and Expenses.
- **P&L Reporting:** Automated calculation of Net Profit.
- Transaction history with categorization (Rent, Payroll, Services).




### 3. **Sales & Distribution (SD)**
- **Order Management:** Create and track customer sales orders.
- **Status Workflow:** Draft ➔ Confirmed ➔ Shipped.
- **Auto-Invoicing:** Sales orders automatically generate financial records.

- 
### 4. **Inventory Management (MM)**
- **Material Master:** Track products, SKUs, and Suppliers.
- **Stock Valuation:** Real-time stock levels and total asset value.
- **Low Stock Alerts:** Visual indicators for inventory below threshold




### 5. **Human Capital (HCM)**
- **Employee Database:** Manage staff details, positions, and departments.
- **Payroll Planning:** Record annual salary data for expense forecasting.

---


##  Architecture & Design

This project follows a **Monolithic Modular Architecture**, similar to traditional on-premise ERP systems.

```

erp_system/
│
├── apps/
│   ├── finance/          # Handles General Ledger (GL) logic
│   ├── sales/            # Handles Order Processing
│   ├── inventory/        # Handles Material Master Data
│   └── hr/               # Handles Employee Master Data
│
├── templates/            # SAP Fiori-inspired UI
├── static/               # CSS (Bootstrap) & JS (Logic)
└── db.sqlite3            # Centralized Relational Database
```

### Design Principles
- **DRY (Don't Repeat Yourself):** Base templates for layout consistency.
- **Separation of Concerns:** Business logic resides in `views.py` and `models.py`.
- **Responsive UI:** Built with Bootstrap 5 to ensure usability across devices.

---


##  SAP S/4HANA Simulation Concepts

This project mimics specific architectural concepts found in SAP:

1.  **Integration:** In SAP, an SD (Sales) order creates a FI (Finance) document. This project replicates this by linking the `SalesOrder` model to the `Transaction` model.
2.  **Master Data:** We maintain "Master Data" (Materials, Customers, Employees) separately from "Transactional Data" (Orders, Journal Entries) to ensure data integrity.
3.  **Modularity:** Each app (`finance`, `sales`, etc.) represents a distinct module that can theoretically be plugged or unplugged, mirroring SAP's module structure.

---


##  Technology Stack

| Component | Technology |
| :--- | :--- |
| **Backend** | Python 3.9+, Django 4.2 |
| **Frontend** | HTML5, CSS3, Bootstrap 5, JavaScript (ES6+) |
| **Database** | SQLite3 (Default Django DB) |
| **Data Viz** | Chart.js |
| **Icons** | FontAwesome 6 |
| **IDE** | VS Code |

---


##  Installation & Setup

### Prerequisites
- Python 3.9 or higher installed.
- pip (Python package manager).

- 


### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate
### Step 1: Clone the Repository
```bash
git clone https://github.com/rohitpawar-tech/CoreFlow-ERP/blob/main/README.md
cd sap-erp-simulation
```


# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```


### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Database Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 5: Create Superuser
```bash
python manage.py createsuperuser
# Follow prompts to create admin credentials
```



### Step 6: Run Server
```bash
python manage.py runserver
```
Visit `http://127.0.0.1:8000/` in your browser.

---


## ⚡ Quick Start (Simulation Mode)

If you want to demo the UI and logic immediately without setting up the Python backend, you can use the standalone simulation file included in this repository.

1.  Navigate to the project folder.
2.  Open `erp_simulation.html` in your web browser.
3.  **Note:** This version uses `localStorage` to simulate the database. Data will persist in your browser but will not be shared with other users.

---

##  Future Enhancements

- **Authentication:** Implement Django Auth for Role-Based Access Control (RBAC).
- **Reporting:** Export PDF invoices and Excel reports for Finance.
- **REST API:** Build a Django REST Framework (DRF) backend for mobile app connectivity.
- **Advanced Analytics:** Integrate Pandas for deeper financial forecasting.
- **Multi-tenancy:** Allow the system to handle multiple companies in a single DB instance.

---


##  Author

**Rohit Pawar **  
*Full Stack Developer & Technical Architect*

- [LinkedIn](https://www.linkedin.com/in/rohit-pawar-54132a246/)
- [GitHub](https://github.com/rohitpawar-tech/CoreFlow-ERP/edit/main/README.md)

---

