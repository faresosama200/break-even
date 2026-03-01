<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Flask-3.1-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask"/>
  <img src="https://img.shields.io/badge/scikit--learn-1.6+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn"/>
  <img src="https://img.shields.io/badge/SQLite-3-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License"/>
</p>

<h1 align="center">🎯 SmartBEP</h1>
<h3 align="center">Intelligent Break-Even & Feasibility Analysis System</h3>

<p align="center">
  <strong>AI-powered web application for analyzing business project feasibility, calculating break-even points, predicting financial performance, and generating smart recommendations.</strong>
</p>

---

## 📋 Overview

**SmartBEP** is a comprehensive financial analysis platform designed to help entrepreneurs, business analysts, and decision-makers evaluate the feasibility of business projects with confidence. The system leverages machine learning alongside classical financial calculations to provide deep insights and actionable recommendations.

### ✨ Key Features

| Feature | Description |
|---------|-------------|
| 📊 **Break-Even Analysis** | Calculates BEP in units and revenue, contribution margins, and margin ratios |
| 🤖 **AI Risk Classification** | ML-based risk assessment (Low → Critical) using Random Forest & Gradient Boosting |
| 📈 **Financial Forecasting** | Month-by-month revenue, cost, and profit projections with growth modeling |
| 💡 **Smart Recommendations** | Context-aware, prioritized business recommendations based on analysis results |
| 🔍 **Project Comparison** | Side-by-side comparison of multiple projects with visual charts |
| 📑 **Detailed Reports** | Comprehensive analysis reports with charts and exportable data |
| 🔐 **User Authentication** | Secure registration, login, and profile management |
| 📱 **Responsive Design** | Clean, modern UI that works on desktop and mobile |

---

## 🏗️ Architecture

```
SmartBEP/
├── app/
│   ├── models/              # Database models (User, Project, FinancialInput, etc.)
│   ├── routes/              # Flask Blueprints (auth, dashboard, projects, reports)
│   ├── services/            # Business logic engines
│   │   ├── ai_engine.py           # ML risk classification & feasibility scoring
│   │   ├── financial_engine.py    # Core financial calculations (BEP, ROI, margins)
│   │   ├── prediction_engine.py   # Revenue/profit forecasting & clustering
│   │   └── recommendation_engine.py  # Smart recommendation generation
│   ├── static/              # CSS, JavaScript, images
│   ├── templates/           # Jinja2 HTML templates
│   └── utils/               # Logging, validators, helpers
├── data/                    # SQLite database & ML model storage
├── tests/                   # Unit tests
├── config.py                # Environment-based configuration
├── run.py                   # Application entry point
├── seed_data.py             # Sample data seeder
└── start.bat                # Quick start script (Windows)
```

---

## ⚡ Quick Start

### Prerequisites
- **Python 3.10+** installed and available in `PATH`

### Option 1 — One-Click Start (Windows)
```bash
start.bat
```
This script automatically creates a virtual environment, installs dependencies, initializes the database, and launches the server with browser auto-open.

### Option 2 — Manual Setup
```bash
# 1. Clone the repository
git clone https://github.com/faresosama200/break-even.git
cd break-even

# 2. Create and activate virtual environment
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Initialize database with sample data
python seed_data.py

# 5. Run the application
python run.py
```

🌐 Open your browser at **http://localhost:5000**

### Demo Account
| Username | Password |
|----------|----------|
| `demo` | `demo1234` |

---

## 🔧 Technology Stack

| Layer | Technologies |
|-------|-------------|
| **Backend** | Python, Flask 3.1, Flask-Login, Flask-WTF, Flask-SQLAlchemy |
| **AI/ML** | scikit-learn (Random Forest, Gradient Boosting, Linear Regression, KMeans) |
| **Database** | SQLite with SQLAlchemy ORM |
| **Frontend** | HTML5, CSS3, JavaScript, Bootstrap, Chart.js |
| **Security** | Werkzeug password hashing, CSRF protection, session management |

---

## 📊 Financial Calculations

SmartBEP performs the following core calculations:

- **Break-Even Point (Units)** = Fixed Costs ÷ (Selling Price − Variable Cost)
- **Break-Even Point (Revenue)** = Fixed Costs ÷ Contribution Margin Ratio
- **Contribution Margin** = Selling Price − Variable Cost per Unit
- **Contribution Margin Ratio** = CM ÷ Selling Price
- **Expected Profit** = Revenue − Total Costs
- **ROI** = (Net Profit ÷ Initial Investment) × 100
- **Safety Margin** = (Expected Volume − BEP Units) ÷ Expected Volume

---

## 🤖 AI & Machine Learning

The system uses a **hybrid approach**:

1. **Rule-Based Engine** — Works immediately with financial heuristics for risk assessment and feasibility scoring
2. **ML Models** — Automatically trains when ≥20 historical projects are available:
   - `RandomForestClassifier` for risk level classification
   - `GradientBoostingRegressor` for feasibility score prediction
   - `LinearRegression` for revenue/profit forecasting
   - `KMeans` for similar project clustering

Models are persisted in `data/models/` and loaded on startup.

---

## 📁 Sample Projects Included

The seed data includes diverse project types for demonstration:

| Project | Industry | Fixed Costs | Price/Unit |
|---------|----------|-------------|------------|
| Organic Soap Production | Manufacturing | $15,000 | $12.00 |
| Coffee Shop Startup | Food & Beverage | $45,000 | $5.50 |
| Mobile App Development | Technology | $60,000 | $9.99 |
| Handmade Jewelry | Handcraft | $5,000 | $55.00 |
| Urban Farming Microgreens | Agriculture | $8,000 | $4.00 |
| Risky Gadget Venture | Technology | $120,000 | $50.00 |

---

## 🧪 Running Tests

```bash
python -m pytest tests/ -v
```

---

## ⚙️ Configuration

The application supports three environments configured in `config.py`:

| Environment | Debug | Database | Usage |
|-------------|-------|----------|-------|
| `development` | ✅ | SQLite (file) | Local development |
| `production` | ❌ | SQLite (file) | Deployment |
| `testing` | ✅ | SQLite (memory) | Unit tests |

Set the environment via:
```bash
set FLASK_ENV=development    # Windows
export FLASK_ENV=development # Linux/macOS
```

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 👤 Author

**Fares Osama**

- GitHub: [@faresosama200](https://github.com/faresosama200)

---

<p align="center">
  <strong>⭐ Star this repository if you found it useful!</strong>
</p>
