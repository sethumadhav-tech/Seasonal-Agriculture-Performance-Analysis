# 🌾 Seasonal Agriculture Performance Analysis

An exploratory data analysis project focused on understanding how **agricultural performance changes across Kharif, Rabi, and Zaid seasons**.

The project examines seasonal differences in yield, production, revenue, profit, water use and efficiency, environmental conditions, disease/pest risk, crop choice, irrigation methods, and regional performance.

## 📌 Project Overview

### Objective

The analysis aims to:

* Understand the structure and quality of the agricultural dataset
* Clean and prepare the data for analysis
* Compare agricultural performance across seasons
* Identify relationships between environmental/resource variables and yield
* Analyze crop, region, and irrigation differences
* Detect unusual observations and outliers
* Test whether seasonal differences are statistically significant
* Develop evidence-based agricultural planning recommendations

## 📊 Dataset

**Dataset:** Seasonal Agriculture Performance Dataset

* **Records:** 4,000 farm records
* **Columns:** 28
* **Key dimensions:** season, geography, crop, farming practices, environmental conditions, production, resource use, and financial performance

Important variables include:

| Category           | Example variables                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------- |
| Season & geography | `Season`, `State`                                                                                 |
| Crop & farm        | `Crop`, `Farm_ID`, `Farm_Area_Hectares`                                                           |
| Production         | `Yield_Tonnes_Ha`, `Production_Tonnes`                                                            |
| Economics          | `Market_Price_INR_Tonne`, `Total_Cost_INR`, `Revenue_INR`, `Profit_INR`                           |
| Water              | `Water_Used_m3`, `Water_Efficiency_t_per_1000m3`                                                  |
| Environment        | `Rainfall_mm`, `Avg_Temperature_C`, `Humidity_pct`, `Soil_Moisture_pct`                           |
| Inputs             | `Nitrogen_kg_ha`, `Phosphorus_kg_ha`, `Potassium_kg_ha`, `Fertilizer_kg_ha`, `Pesticide_Litre_ha` |
| Risk & quality     | `Disease_Pest_Risk_pct`, `Seed_Quality_Score`                                                     |
| Irrigation         | `Irrigation_Method`                                                                               |

## 🧹 Data Preparation

The notebook performs the following preparation steps:

* Checks data types, missing values, unique values, and duplicate rows
* Finds missing values in `Rainfall_mm`, `Soil_Moisture_pct`, and `Yield_Tonnes_Ha`
* Median-imputes missing values in:

  * `Rainfall_mm`
  * `Soil_Moisture_pct`
* Keeps missing `Yield_Tonnes_Ha` values missing for yield-specific statistical analysis
* Recalculates `Profit_Margin_pct` from revenue and profit
* Validates important arithmetic relationships between production, yield, area, revenue, price, cost, and profit

There are **no duplicate rows** in the dataset.

## 🔎 Analysis Workflow

The notebook follows this workflow:

1. **Dataset Understanding**
2. **Data Cleaning and Preparation**
3. **Univariate Exploration**
4. **Seasonal Performance Comparison**
5. **Distribution and Outlier Analysis**
6. **Crop and Season Analysis**
7. **Region and Irrigation Comparisons**
8. **Environmental Conditions and Resource Use**
9. **Economic Performance**
10. **Statistical Tests for Seasonal Differences**
11. **Data Consistency Checks**
12. **Key Findings**
13. **Data-Driven Recommendations**
14. **Final Conclusion**

## 📈 Statistical Analysis

Because several financial and agricultural variables are skewed and contain outliers, the project uses both parametric and non-parametric approaches.

### Tests Used

* **One-way ANOVA** for comparing yield means across seasons
* **Kruskal–Wallis test** for comparing seasonal distributions
* **Spearman correlation** for evaluating monotonic relationships between environmental/resource variables and yield
* **IQR-based outlier detection** for selected numerical variables

The analysis emphasizes distributional differences and uses medians and stratified comparisons where means may be strongly affected by extreme observations.

> **Important:** Correlation and statistical significance do not establish causation. Differences may also reflect crop mix, geography, farm size, irrigation, or other characteristics of the dataset.

## 💡 Key Findings

### 🌧️ Seasonal Performance

* **Kharif** has the highest average yield, revenue, and profit in the observed dataset.
* **Zaid** has the lowest average yield and average profit.
* Zaid also has the **highest proportion of loss-making farms**.
* Disease/pest risk is highest on average in Kharif.

### 🌱 Crop Effects

* Crop choice is a major contributor to observed agricultural performance.
* **Sugarcane** has substantially higher yield and profit than the other crops in the dataset.
* Because of this, yield is highly skewed and mean-only comparisons can be misleading.

### 💧 Irrigation and Water Efficiency

* Drip-irrigated farms show the highest average yield and water efficiency in the dataset.
* Water efficiency has a positive and substantial Spearman association with yield.
* These findings are descriptive associations and should not be interpreted as proof of causal effects.

### 🗺️ Regional Differences

* Seasonal performance is not uniform across states.
* Some states perform relatively better during Rabi or Zaid, indicating that regional conditions and crop mix are important.

### 📊 Statistical Evidence

* Yield shows a highly significant **distributional difference** across seasons under the Kruskal–Wallis test.
* Revenue, profit, water efficiency, and disease/pest risk also show statistically significant seasonal distributional differences in the dataset.
* The contrast between ANOVA and Kruskal–Wallis results for yield highlights the impact of skewness and extreme observations.

## 🎯 Recommendations

### For Seasonal Planning

* Prioritize **Kharif opportunities** where historical yield and profitability are favorable.
* Strengthen disease and pest management during Kharif.
* Treat **Zaid as a higher financial-risk season** and evaluate crop selection, irrigation requirements, and expected market prices before planting.
* Use **state- and crop-specific strategies** instead of applying one seasonal strategy universally.

### For Resource Management

* Investigate drip irrigation as a potentially water-efficient practice.
* Evaluate irrigation effects while controlling for crop and region before making causal claims.
* Monitor **water efficiency alongside yield**, rather than maximizing water use alone.

## 🛠️ Technologies Used

* **Python**
* **Pandas** — data manipulation and analysis
* **NumPy** — numerical operations
* **Matplotlib** — visualization
* **SciPy** — statistical testing
* **Jupyter Notebook** — analysis environment

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <your-repository-folder>
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib scipy jupyter
```

### 3. Add the Dataset

Place the CSV dataset expected by the notebook in the same working directory as the notebook:

```text
seasonal_agriculture_performance_dataset (3).csv
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Seasonal_Agriculture_Performance_Analysis(1).ipynb
```

Run the notebook cells from top to bottom.

## 📁 Repository Structure

```text
seasonal-agriculture-performance-analysis/
│
├── README.md
├── Seasonal_Agriculture_Performance_Analysis(1).ipynb
├── seasonal_agriculture_performance_dataset (3).csv
└── requirements.txt
```

## ⚠️ Limitations

* The analysis is based on the observed dataset and does not establish causal relationships.
* Yield contains substantial skewness and influential high-yield observations.
* Some differences may be explained by crop, region, farm size, irrigation, or other confounding factors.
* Missing yield values are excluded from yield-specific statistical tests.
* Recommendations should be validated with additional agronomic, regional, and economic information before operational decisions are made.

## 🏁 Conclusion

The analysis identifies meaningful **seasonal variation in agricultural outcomes**, particularly for profitability, revenue, water efficiency, and disease/pest risk.

Overall, **Kharif is the strongest season in the observed sample**, while **Zaid presents the greatest profitability risk**. However, season alone does not explain agricultural performance. Crop type, region, irrigation, and resource conditions also contribute substantially.

The most defensible planning approach is therefore **season-aware and crop/region-specific**, supported by profitability, water-efficiency, and risk indicators rather than yield alone.

## 👤 Author

**Sethu Madhav**

---

⭐ If this project was useful, consider giving the repository a star.
