
# Drone Flight Time Prediction using Machine Learning

## Project Overview

This project aims to predict the **total flight time of a drone** using machine learning techniques based on real-world telemetry data. I built a baseline model using **Linear Regression**, and later improved its performance using **Principal Component Analysis (PCA)** to reduce dimensionality while retaining essential information.

---

## Dataset Description

I used a publicly available dataset from a published research paper:

> **Title**: *In-flight positional and energy use data from a quadcopter drone during 209 autonomous flights*  
> **Source**: [Carnegie Mellon University – KiltHub](https://kilthub.cmu.edu/articles/dataset/Data_Collected_with_Package_Delivery_Quadcopter_Drone/12683453)  
> **Type**: Time-series data collected from a DJI Matrice 100 quadcopter  
> **Files**:
- `flights.csv`: Telemetry readings at each time step (e.g., battery, GPS, speed, wind)
- `parameters.csv`: Metadata per flight (e.g., payload, altitude, route)

Note: The raw `.csv` files were not uploaded to GitHub due to size limits. Only the cleaned `.ipynb` notebook is provided.

---

## Project Workflow

### 1. **Exploratory Data Analysis**
- Reviewed data structure, feature types, and missing values
- Identified useful metrics: battery voltage, current, wind speed, etc.

### 2. **Baseline Model**
- Selected a few obvious features (`battery_voltage`, `current`, `payload`, etc.)
- Built a **Linear Regression** model
- Achieved **R² Score**: `-0.1030` (very poor), **MSE**: `1606.15`

### 3. **Performance Challenges**
- The model underfitted due to:
  - Weak feature relationships
  - No scaling or feature transformations
  - Ignoring rich telemetry dimensions

### 4. **Improved Model with PCA**
- Aggregated all telemetry data (mean & std per flight)
- Normalized features using `StandardScaler`
- Applied **PCA (90% variance retention)** to reduce feature count from ~40+ to 15–18
- Re-trained Linear Regression

### **Final Performance**
| Metric       | Initial Model | After PCA |
|--------------|----------------|-----------|
| R² Score     | `-0.1030` ❌    | `0.9282` ✅ |
| MSE (seconds)| `1606.15` ❌    | `104.55` ✅ |

---

## Tools & Libraries

- **Python** (Jupyter Notebook)
- **Pandas** & **NumPy**
- **Scikit-learn** (LinearRegression, PCA, StandardScaler)
- **Matplotlib** & **Seaborn** (EDA and Visualizations)

---

## Key Learnings

- **PCA** significantly improved performance without complex models
- **Data preprocessing** (scaling, aggregation) is critical in ML
- Even simple models can perform very well with strong features

---

## Author

**Jeevana Sree B**  
📧 [jeevanasree@outlook.com](mailto:jeevanasree@outlook.com)  
🌐 [github.com/Jeevana-Sree](https://github.com/Jeevana-Sree)  
🔗 [linkedin.com/in/jeevanasreeb/](https://www.linkedin.com/in/jeevanasreeb)


