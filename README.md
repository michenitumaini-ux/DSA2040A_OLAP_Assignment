Tumaini Micheni 933

 OLAP Assignment 

This project demonstrates how to implement **OLAP architectures** (ROLAP, MOLAP, HOLAP) and **OLAP operations** (slice, dice, roll-up, drill-down) using **SQLite, Pandas, and Matplotlib** in Python.  

The goal is to show how a **data warehouse star schema** can be analyzed with different OLAP approaches.

---

 📂 Project Structure

| File | Description |
|------|-------------|
| `olap_assignment.ipynb` | Jupyter Notebook with OLAP architecture implementations and operations. |
| `olap_assignment.db` | SQLite database created dynamically in the notebook. |

---

🗄️ Database Schema

This project uses a simple **Star Schema**:

 Dimension: Products
| Column       | Type    | Description |
|--------------|---------|-------------|
| product_id   | INTEGER | Unique product identifier |
| category     | TEXT    | Product category (e.g., Electronics, Clothing, Furniture) |
| name         | TEXT    | Product name |
| price        | INTEGER | Price of product |

Dimension: Dates
| Column  | Type    | Description |
|---------|---------|-------------|
| date    | DATE    | Transaction date |
| year    | INTEGER | Year of transaction |
| quarter | INTEGER | Quarter (1–4) |
| month   | INTEGER | Month (1–12) |

Fact: Sales
| Column     | Type    | Description |
|------------|---------|-------------|
| sale_id    | INTEGER | Unique sale identifier |
| date       | DATE    | Transaction date (FK to Dates) |
| product_id | INTEGER | Product ID (FK to Products) |
| quantity   | INTEGER | Units sold |
| revenue    | INTEGER | Computed = quantity × price |

---

📊 OLAP Architectures Implemented

🔹 ROLAP (Relational OLAP)
- Implemented with **SQL queries on SQLite**.
- Examples:
  - Average revenue by product category.
  - Total sales revenue by year.
  - Best-selling product in each category.
- Visualized using bar plots.

🔹 MOLAP (Multidimensional OLAP)
- Implemented with **Pandas pivot tables** (in-memory cube).
- Example:
  - Revenue cube by category × year.
- Visualized with line plots.

🔹 HOLAP (Hybrid OLAP)
- Combines **SQL for data extraction** and **Pandas for analysis**.
- Example:
  - Revenue by category and year (hybrid summary).
- Visualized with grouped bar plots.

---

🧮 OLAP Operations Demonstrated

| Operation   | Implementation |
|-------------|----------------|
| **Slice**   | Filtered sales for the year 2024. |
| **Dice**    | Filtered Q1 2024 sales for *Electronics*. |
| **Roll-up** | Aggregated revenue from product → category → year. |
| **Drill-down** | Expanded revenue from year → quarter → month. |

Each operation is shown both in **tabular form** and with **Matplotlib/Seaborn visualizations**.

---

🚀 Getting Started

1. Clone the repository
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
2. Install dependencies
bash
Copy code
pip install pandas numpy sqlite3 matplotlib seaborn jupyter
3. Run the notebook
bash
Copy code
jupyter notebook "olap_assignment.ipynb"

📌 Notes
The schema is simplified for demonstration.

Can be extended with more dimensions (customers, regions, etc.).

Demonstrates both SQL-based and in-memory cube OLAP approaches.

📄 License
This project is licensed under the MIT License.
