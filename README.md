# Developer Analytics & Engineering Productivity Report

This project is a portfolio-ready **Developer Analytics Dashboard and Insights Report** implemented in a Jupyter Notebook. It simulates a junior data analyst's work querying a PostgreSQL database to extract engineering metrics, assess project risk, and analyze subscription tier value.

---

## 🚀 Project Overview

The objective of this analysis is to evaluate developer activity, track code contribution volumes, identify project backlog risks, and analyze developer behaviors across subscription tiers (Free vs. Pro). The project connects to a local PostgreSQL instance, extracts unified database records across 5 relational tables, and uses `pandas` and data visualization libraries (`seaborn`/`matplotlib`) to create clear, manager-facing insights.

---

## 🛠️ Tech Stack & Tools

*   **Database**: PostgreSQL 18
*   **Database Connector**: `psycopg2`
*   **Data Manipulation**: Python & `pandas`
*   **Data Visualization**: `matplotlib` and `seaborn`
*   **Environment**: Jupyter Notebook (`.ipynb`)

---

## 📊 Relational Database Schema

The database consists of five interconnected tables representing a developer environment:
1.  **`developers`**: Account credentials, country, subscription tier, and active status.
2.  **`projects`**: Project names, primary languages (Java, Python, C#, C++, Swift, etc.), and backing databases.
3.  **`daily_logs`**: Logs of developer hours worked and self-reported productivity scores (1-10).
4.  **`code_snippets`**: Volume of code (lines of code) written by developer per language.
5.  **`bug_reports`**: Tracking bug counts, severity (Critical, High, Medium, Low), and duration open.

---

## 📈 Key Findings & Insights

### 1. Developer Productivity & Contribution Metrics
*   **Top Contributor**: `sql_master` leads all developers with **1,650 lines of code** and maintains a perfect productivity score of **10.0** (based on 12.0 hours logged).
*   **Activity Gap**: A large portion of registered developers (such as `legacy_dev`, `null_pointer`, and `logic_loop`) show **0 lines of code** and zero logged hours. This highlights an opportunity to audit inactive seats or assist with developer onboarding.

### 2. Project Health & Backlog Quality Risks
*   **Triage Bottleneck**: The `Inventory API` project has **2 active bug reports**, including a **Critical** bug that has been open for an average of **16.0 days**. This indicates a critical resource bottleneck.
*   **Severity Concentrations**: High-severity bugs (Critical/High) are clustered in Python and C# backend projects (`Inventory API`, `E-commerce Backend`, `3D Render Pipeline`), while low-severity bugs are resolved much faster (e.g. `Offline DevLog` average of **2.5 days open**).

### 3. Subscription Tier Value & Engagement Analysis
*   **Pro Tier Dominance**: Developers on the **Pro tier** show significantly higher engagement, averaging **6.75 hours logged** per active day and a **7.60/10 productivity score**. They contribute an average of **541.67 lines of code** per developer.
*   **Free Tier Benchmark**: In contrast, **Free tier** developers average only **2.50 hours** daily with a **4.80/10 productivity score** and **204.50 lines of code**.
*   **Linear Productivity Correlation**: Scatter plot regression confirms a strong positive correlation between hours logged and productivity scores. Pro tier developers are tightly clustered in the high-engagement, high-productivity quadrant.

---

## 💻 How to Run the Analysis

1.  **Database Connection Config**:
    Open the first code cell of `project2_developer_analytics.ipynb` and enter your database credentials:
    ```python
    DB_HOST = "localhost"
    DB_PORT = 5433  # Set to your PostgreSQL port (e.g. 5432 or 5433)
    DB_NAME = "postgres"
    DB_USER = "postgres"
    DB_PASS = "YOUR_PASSWORD"  # Replace with your actual password
    ```
2.  **Execute the Notebook**:
    Open the notebook in Jupyter Lab or Jupyter Notebook, and select **Run All Cells** from the top menu.
