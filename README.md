# 💧 Data Analysis on Water Quality Index (WQI) of India

A data analytics project that computes a standard **Water Quality Index (WQI)** for river monitoring stations across India and analyzes state-wise water quality using Python (pandas, seaborn, matplotlib) and an interactive **Power BI** dashboard.

## 🎯 Objective

Raw water-quality monitoring data (pH, dissolved oxygen, BOD, conductivity, nitrate, coliform counts, etc.) is hard to interpret on its own. This project converts those raw physicochemical parameters into a single, interpretable **Water Quality Index** per station and state, then visualizes which Indian states have the best/worst water quality and why.

## 📊 Parameters Used

| Parameter | Symbol | What it indicates |
|---|---|---|
| pH | `pH` | Acidity/alkalinity of water |
| Dissolved Oxygen | `D.O.` | Oxygen available for aquatic life |
| Biochemical Oxygen Demand | `B.O.D.` | Organic pollution load |
| Electrical Conductivity | `EC` | Dissolved ionic/salt content |
| Nitrate + Nitrite | `N+N` | Agricultural/sewage contamination |
| Total & Fecal Coliform | `TC` / `FC` | Bacterial/fecal contamination |

## 🧮 Methodology

The notebook implements the standard **weighted arithmetic WQI method**:

1. **Clean & type-cast** the raw dataset (handle missing values, coerce numeric columns)
2. **Compute a sub-index** for each parameter based on standard permissible-limit tables (e.g. pH sub-index scores 100 for the 7–8.5 ideal range, degrading outside it)
3. **Assign relative weights** to each parameter based on its importance to overall water quality (pH: 0.165, DO: 0.281, BOD: 0.234, EC: 0.009, Nitrate: 0.028, Coliform: 0.281)
4. **Aggregate into a final WQI score** per monitoring station: `WQI = Σ (sub-index × weight)`
5. **Group by state** to get a state-wise average WQI and export it for visualization

## 📈 Key Analyses & Visualizations

- State-wise bar charts for WQI, pH, BOD, conductivity, dissolved oxygen, nitrate, and coliform levels
- Identification of states with **abnormal pH** (too acidic/alkaline for safe use)
- Identification of states exceeding safe **coliform**, **BOD**, **conductivity**, and **nitrate** thresholds
- Pairplot / correlation view across all water-quality parameters
- A final ranked view highlighting the best and worst states by WQI

**Headline finding:** Puducherry recorded the highest (best) WQI in the dataset, while Punjab recorded the lowest, indicating comparatively poorer river water quality.

## 🛠️ Tech Stack

- Python — pandas, NumPy
- scikit-learn
- Visualization — seaborn, matplotlib
- Power BI (`.pbix`) for the interactive dashboard

## 📁 Project Structure

```
Data-Analysis-on-Water-Quality-Index-of-India/
├── Mini project.ipynb   # Full data cleaning, WQI calculation & analysis
└── Mini project.pbix    # Power BI interactive dashboard
```

## 🚀 Getting Started

```bash
git clone https://github.com/yuvraj182005/Data-Analysis-on-Water-Quality-Index-of-India.git
cd Data-Analysis-on-Water-Quality-Index-of-India
pip install pandas numpy scikit-learn seaborn matplotlib openpyxl jupyter
jupyter notebook "Mini project.ipynb"
```

Open `Mini project.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) to explore the interactive dashboard.

> ⚠️ The notebook currently reads from a hardcoded local path (`C:\Users\yuvra\...`). Update this to a relative `data/` path before sharing — see suggestions below.




## 👤 Author

**K. Yuvraj Sundaram** — [@yuvraj182005](https://github.com/yuvraj182005)
