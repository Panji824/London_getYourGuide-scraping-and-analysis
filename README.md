Tentu, berikut adalah format **README.md** yang profesional dan rapi, disesuaikan dengan alur proyek *Data Engineering* Anda (web scraping, cleansing, dan analisis Power BI).

---

## README: London Tourism Value Analysis (GetYourGuide Data)

### 1. Project Overview & Objective 🎯

This project implements an **End-to-End Data Pipeline** to analyze the quality and value of tourism activities in London, using data scraped from the GetYourGuide platform. The core objective is to identify **Best Value Offers** and assess **Quality Risk** by comparing key metrics.

| Key Metric | Variable | Purpose |
| :--- | :--- | :--- |
| **Quality** | `Rating` | Customer Satisfaction Level. |
| **Price Risk** | `Price (IDR) Rounded` | Financial exposure and cost segmentation. |
| **Credibility** | `Certified by GYG` | Platform's guarantee of quality assurance. |
| **Popularity** | `Reviews` | Statistical weight and market popularity. |

***

### 2. Methodology & Data Pipeline ⚙️

The pipeline was designed to handle dynamic content and ensure data integrity through structured ETL (Extract, Transform, Load) steps:

1.  **Acquisition (Python):**
    * **Selenium:** Used to simulate user actions, navigate the website, click the "Show More" button repeatedly, and overcome **anti-bot mechanisms**.
    * **BeautifulSoup:** Parses the fully loaded HTML content to extract raw data from the specific activity containers.
2.  **Transformation (Pandas/Power Query):**
    * **Data Cleansing:** Used **Python (Pandas)** for initial cleansing (e.g., converting prices to numeric, handling nulls) and **Power Query** for final transformations.
    * **Feature Engineering:** Creation of categorical segments: **`Price Segment`** (using `pd.cut()` for non-overlapping bins) and **`Duration (Hours)`** for granular efficiency analysis.
    * **Normalization:** Correcting the `Rating` scale ($\div 10$) and rounding `Price` to the nearest thousand.
3.  **Analysis & Visualization:** Strategic visualization using **Box Plots** and **Dual-Axis Combo Charts** to map quality against price segments.

***

### 3. Key Findings (Insights) 💡

| Insight Category | Key Observation | Strategic Value |
| :--- | :--- | :--- |
| **Value Sweet Spot** | The highest average ratings and volume are concentrated in the **Mid-Range Segment ($\text{Rp}\ 500\text{K} - \text{Rp}\ 2\text{M}$)**. | This segment offers the optimal balance of quality and affordability. |
| **Quality Gap** | **Certified Tours** showed significantly less variance in customer ratings (narrower Box Plot range) than non-certified tours. | The certification label effectively reduces customer risk, ensuring quality consistency. |
| **Efficiency/Fatigue** | Customer satisfaction decreases for tours exceeding **10 hours**, indicating a *customer fatigue point*. | Optimal tour design should target durations under 10 hours for maximum satisfaction. |

***

### 4. Technical Stack & Files

| Tool Category | Tools Used |
| :--- | :--- |
| **Core Languages** | Python, M (Power Query) |
| **Acquisition** | Selenium, BeautifulSoup |
| **Data Analysis** | Pandas, NumPy |
| **Visualization** | Seaborn, Matplotlib, **Power BI** |

**Files:**

* `[Nama File Notebook].ipynb`: Full Python script for scraping and initial feature engineering.
* `london_data_final.csv`: The final, cleaned dataset ready for analysis.
* `[Nama File Presentasi].pptx`: Project slides and visualization results. 
