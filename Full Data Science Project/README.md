# 📊 Google Search Trends Analysis using PyTrends

## 📌 Project Overview
This project analyzes **global Google search trends** using the unofficial Google Trends API, **PyTrends**.  
Instead of relying on a static dataset, the project dynamically fetches **real-time and historical search interest data** directly from Google Trends and performs exploratory data analysis (EDA) and visualization.

The goal of this project is to understand:
- How interest in a topic evolves over time
- Which countries show the highest search interest
- How related keywords compare in popularity
- How geographic patterns influence search behavior

---

## 🧠 Key Concepts Used
- API-based data extraction (PyTrends)
- Time-series analysis
- Geographical data analysis
- Data visualization
- Modular and reusable Python functions

---

## 🛠️ Technologies & Libraries
- **Python**
- **PyTrends** (Google Trends API)
- **Pandas & NumPy** – data handling
- **Matplotlib & Seaborn** – static visualizations
- **Plotly** – interactive geographic maps

---

## 🔍 Project Workflow

### 1️⃣ Data Collection (Live API)
Data is fetched directly from Google Trends using PyTrends.  
No CSV or static dataset is required.

```python
from pytrends.request import TrendReq
pytrends = TrendReq(hl='en-US', tz=360)
