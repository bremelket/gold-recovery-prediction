# Gold Recovery Prediction for Ore Processing Optimization

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Latest-orange.svg)](https://scikit-learn.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Regression-green.svg)](https://scikit-learn.org/)

**Machine learning model predicting gold recovery factor from ore to enable cost-effective decision-making in industrial mining operations.**

**Author:** Ekaterina Bremel  
**Project Type:** Regression, Industrial ML  
**Status:** Completed

---

## 🎯 Project Overview

Built a predictive model to assess the efficiency of gold extraction from ore, helping mining operations optimize the purification process and make cost-effective decisions about ore processing. The model predicts recovery rates at different stages of the extraction pipeline.

### Business Impact
- **Goal:** Predict gold recovery efficiency before full processing
- **Challenge:** Avoid processing unprofitable ore batches
- **Solution:** ML model forecasting recovery factor from process parameters
- **Result:** sMAPE of 8.97 on test set, enabling reliable production planning

---

## 📊 Dataset Description

**Gold Ore Extraction Process:**
The dataset represents a multi-stage gold purification process:
1. **Flotation:** Primary concentration stage
2. **Purification:** Two-stage cleaning process
3. **Final Concentrate:** Recovered gold output

**Features Include:**
- **Process Parameters:**
  - Feed characteristics (ore composition)
  - Reagent concentrations
  - Flotation conditions
  - Air flow rates
  - Processing times

- **Chemical Composition:**
  - Gold (Au) concentration at various stages
  - Silver (Ag) content
  - Lead (Pb) levels
  - Other mineral impurities

- **Target Variables:**
  - Rougher recovery (primary stage)
  - Final recovery (complete process)
  - Recovery efficiency metrics

**Data Characteristics:**
- Multi-stage time-series measurements
- Real industrial mining data
- Missing values requiring careful handling
- Anomalies (zero concentrations, impossible values)

---

## 🛠️ Technical Approach

### 1. Data Preparation & Cleaning

**Data Validation:**
- Verified recovery calculation formulas
- Calculated rougher stage recovery rates: MAE = 1.05 (validation passed ✓)
- Identified and handled missing values
- Removed anomalies and zero concentration entries

**Feature Engineering:**
- Aggregated multi-stage measurements
- Created derived features from chemical compositions
- Calculated concentration ratios
- Time-based feature extraction

### 2. Exploratory Data Analysis

**Key Findings:**
- Analyzed concentration distributions across stages
- Identified correlation between feed characteristics and recovery
- Examined particle size impact on efficiency
- Visualized process flow and stage relationships

**Visualizations:**
- Line plots: Recovery trends across batches
- Histograms: Concentration distributions
- KDE plots: Probability density analysis
- Stacked bar charts: Stage-wise composition
- Scatter plots: Feature correlations
- Heatmaps: Correlation matrices
- Box plots: Outlier detection

### 3. Model Selection & Training

**Models Evaluated:**
1. **Linear Regression** (Baseline)
2. **Decision Tree Regressor**
3. **Random Forest Regressor** ✅ (Best Performance)

**Custom Evaluation Metric:**
Built custom sMAPE (symmetric Mean Absolute Percentage Error) function:
```
sMAPE = (1/n) * Σ |actual - predicted| / ((|actual| + |predicted|) / 2) * 100%
```

**Training Strategy:**
- Cross-validation to prevent overfitting
- Hyperparameter tuning
- Feature importance analysis
- Model comparison on validation set

### 4. Model Evaluation

**Final Model: Random Forest Regressor**

**Performance Metrics:**
- **Test Set sMAPE:** 8.97%
- **Validation Performance:** Consistent across folds
- **Interpretability:** Feature importance rankings available

**Model Advantages:**
- Robust to outliers
- Handles non-linear relationships
- Provides feature importance
- Good generalization to unseen data

---

## 🚀 Key Results

✅ **sMAPE: 8.97%** - Strong predictive accuracy for production planning  
✅ **Random Forest** - Best performing model after comparison  
✅ **Production-ready** - Can be integrated into mining operations workflow  
✅ **Cost optimization** - Enables informed decisions on ore batch processing  
✅ **Feature insights** - Identified key drivers of recovery efficiency

---

## 💻 Technologies Used

**Machine Learning:**
- Scikit-learn - Regression models
- Random Forest Regressor
- Cross-validation
- Custom metric implementation

**Data Science Stack:**
- Python 3.8+
- Pandas - Data manipulation
- NumPy - Numerical computations
- Matplotlib - Visualization
- Seaborn - Statistical plotting

**Statistical Analysis:**
- Exploratory Data Analysis
- Feature engineering
- Outlier detection
- Correlation analysis

---

## 📁 Project Structure

```
gold-recovery-prediction/
├── index.html              # Full analysis notebook (HTML export)
├── README.md              # This file
└── data/                  # (Data not included - proprietary)
    ├── train.csv          # Training dataset
    ├── test.csv           # Test dataset
    └── full.csv           # Complete dataset
```

---

## 🔍 View Full Analysis

**[👉 View Interactive Notebook (HTML)](index.html)**

The complete analysis includes:
- Comprehensive data validation
- Exploratory data analysis with visualizations
- Feature engineering process
- Model comparison (Linear, Decision Tree, Random Forest)
- Custom sMAPE metric implementation
- Performance evaluation
- Feature importance analysis

---

## 📈 Sample Visualizations

The project includes:
- Recovery rate distributions
- Stage-wise concentration changes
- Correlation heatmaps
- Feature importance charts
- Model comparison plots
- Predicted vs. Actual recovery scatter plots
- Time series of recovery trends

---

## 🎓 Skills Demonstrated

**Machine Learning:**
- Regression modeling
- Ensemble methods (Random Forest)
- Model selection and comparison
- Custom metric implementation
- Cross-validation techniques
- Hyperparameter tuning

**Data Engineering:**
- Data validation and quality checks
- Complex feature engineering
- Multi-stage process data handling
- Missing value treatment
- Anomaly detection and removal

**Statistical Analysis:**
- Exploratory Data Analysis (EDA)
- Distribution analysis
- Correlation analysis
- Statistical validation
- Performance metrics interpretation

**Domain Knowledge:**
- Industrial process understanding
- Mining operations context
- Cost-benefit analysis
- Production optimization

**Visualization:**
- Multi-dimensional data visualization
- Process flow representation
- Statistical plotting
- Business reporting

---

## 🌟 Real-World Applications

**Mining Operations:**
- Batch processing decisions (process now vs. stockpile)
- Resource allocation optimization
- Production planning and scheduling

**Cost Management:**
- Identify unprofitable ore batches early
- Optimize reagent usage
- Minimize processing of low-yield ore

**Quality Control:**
- Monitor process efficiency trends
- Early detection of process degradation
- Benchmark performance across facilities

**Strategic Planning:**
- Ore body valuation
- Mine development decisions
- Investment analysis for processing upgrades

---

## 🔮 Future Improvements

**Model Enhancements:**
- Deep learning for complex non-linear patterns
- Time series modeling for temporal dependencies
- Multi-target prediction (simultaneous stage predictions)
- Ensemble of diverse model types

**Feature Engineering:**
- Include equipment condition data
- Add environmental factors (temperature, humidity)
- Incorporate ore source geological data
- Real-time process monitoring features

**Production Deployment:**
- Real-time prediction API
- Dashboard for operators
- Alert system for low predicted recovery
- Integration with process control systems

**Business Value:**
- Calculate ROI from prediction-based decisions
- A/B testing different processing strategies
- Continuous learning from new data

---

## 🏭 Technical Implementation Notes

**Data Quality:**
- Rigorous validation of input data
- Automated anomaly detection
- Clear handling of missing values
- Documentation of data assumptions

**Model Interpretability:**
- Feature importance rankings
- Decision path analysis (for tree models)
- SHAP values for explanation (future enhancement)
- Clear communication of limitations

**Scalability:**
- Efficient data processing pipeline
- Batch prediction capability
- Model retraining workflow
- Version control for models

---

## 📧 Contact

**Ekaterina Bremel**
- LinkedIn: [https://www.linkedin.com/in/ekaterina-bremel-65b1b1238/]
- Email: bremelketl@gmail.com
- GitHub: @bremelket

---

## 📝 License

Copyright © 2026 Ekaterina Bremel. All rights reserved.

This project is available for viewing as part of my portfolio. Unauthorized copying, modification, distribution, or use of this code is prohibited.

---

**⭐ If you find this project interesting, please consider giving it a star!**
