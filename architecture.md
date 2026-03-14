# Project: ZenBudget (Zero-Based Budgeting App)

## 🎯 Product Vision
A high-performance, web-based budgeting tool inspired by YNAB. 
**The Golden Rule:** Every dollar must have a job ($Total Assets = \sum Categories + Ready To Assign$).

## 🛠️ Technical Stack
- **Frontend:** Next.js (App Router), Tailwind CSS, Lucide Icons.
- **Backend:** FastAPI (Python 3.11+).
- **Database:** PostgreSQL (ACID compliant for financial integrity).
- **ORM/Validation:** SQLModel (combines SQLAlchemy + Pydantic).
- **Authentication:** JWT (JSON Web Tokens) via FastAPI OAuth2.
- **Banking Integration:** Plaid API (for transaction syncing).

## 🗄️ Database Schema & Data Models
### Accounts
- `id`: UUID (Primary Key)
- `name`: String (e.g., "Main Checking")
- `type`: Enum (Checking, Savings, Credit Card)
- `balance`: Decimal (12, 2)
- `is_on_budget`: Boolean (Determines if funds contribute to 'Ready to Assign')

### Categories
- `id`: UUID
- `name`: String
- `group`: String (e.g., "Fixed Expenses", "Fun Money")
- `assigned`: Decimal (Amount user manually allocated this month)
- `activity`: Decimal (Automated sum of transactions this month)
- `available`: Calculated field (`assigned` + `activity`)

### Transactions
- `id`: UUID
- `date`: Date
- `payee`: String
- `amount`: Decimal (Negative for spending, Positive for income)
- `category_id`: UUID (Foreign Key)
- `account_id`: UUID (Foreign Key)
- `cleared`: Boolean

## ⚙️ Business Logic Rules (For Gemini Code Assist)
1. **Zero-Based Logic:** 'Ready to Assign' must always reflect the total liquid cash not yet placed in a category.
2. **Negative Carrying:** If a category is overspent (Available < 0), the 'Ready to Assign' for the *following* month must be reduced by that amount.
3. **Transaction Flow:** Every transaction must update the `activity` field of its linked Category and the `balance` of its linked Account simultaneously.
4. **API First:** All frontend actions must communicate via FastAPI endpoints; no direct database manipulation from the UI.

## 📂 Project Directory Structure
- `/backend`: FastAPI source code, routers, and models.
- `/frontend`: Next.js components, hooks, and state management.
- `/migrations`: Alembic database migration files.
- `/docs`: API documentation and user flow diagrams.