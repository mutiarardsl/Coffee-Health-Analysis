# Coffee Consumption and Health Analysis Using Random Forest

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview
This project analyzes the relationship between coffee consumption and health conditions using Random Forest machine learning algorithm on a global dataset of 4,059 observations.

## Key Results
- **Accuracy**: 98.40%
- **F1-Score (weighted)**: 0.982
- **Key Finding**: BMI and age are the strongest health predictors, not caffeine consumption

## Dataset
- **Source**: Global Coffee Health Dataset from Kaggle
- **Size**: 4,059 observations (after cleaning from 10,000)
- **Features**: 16 variables including demographics, lifestyle, biometrics
- **Target**: Health_Issues (Mild, Moderate, Severe)

## Features
- Coffee consumption: Coffee_Intake, Caffeine_mg
- Demographics: Age, Gender, Country, Occupation
- Lifestyle: Smoking, Alcohol_Consumption, Physical_Activity_Hours, Sleep_Hours, Sleep_Quality, Stress_Level
- Biometrics: BMI, Heart_Rate

## Methodology
1. **Data Exploration**: Statistical analysis, correlation matrix, class distribution
2. **Preprocessing**: 
   - Missing values handling
   - Feature encoding (Ordinal, Label, One-Hot)
   - Stratified train-test split (80-20)
3. **Modeling**: 
   - Baseline Random Forest model
   - Hyperparameter tuning with GridSearchCV (5-fold CV)
4. **Evaluation**: Accuracy, Precision, Recall, F1-Score, Confusion Matrix
5. **Feature Importance Analysis**

## Installation
```bash
git clone https://github.com/yourusername/coffee-health-analysis.git
cd coffee-health-analysis
pip install -r requirements.txt
```

## Usage
```python
# Run the analysis
python src/model.py

# Or use the Jupyter notebook
jupyter notebook notebooks/analysis.ipynb
```

## Results

### Model Performance
| Metric | Score |
|--------|-------|
| Accuracy | 98.40% |
| F1-Score (weighted) | 0.982 |
| F1-Score (macro) | 0.640 |

### Classification Report
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| Mild | 0.99 | 1.00 | 0.99 | 716 |
| Moderate | 0.95 | 0.90 | 0.93 | 93 |
| Severe | 0.00 | 0.00 | 0.00 | 3 |

### Feature Importance
1. **BMI** (0.29) - Most influential predictor
2. **Age** (0.27) - Second most important factor
3. **Sleep_Hours** (0.07)
4. **Caffeine_mg** (0.05)
5. **Physical_Activity_Hours** (0.05)

## Key Findings
- BMI and age are stronger health predictors than caffeine consumption
- Sufficient sleep (7-10 hours) correlates with milder health issues
- Extreme class imbalance (0.4% Severe cases) limits model's ability to predict severe health issues
- Lifestyle and physiological factors have greater impact on health than coffee consumption alone

## Limitations
- Cross-sectional data (cannot establish causality)
- Extreme class imbalance for Severe category
- Generalization limited to dataset characteristics

## Future Work
- Apply oversampling techniques (SMOTE, ADASYN) for class imbalance
- Collect more data for minority classes
- Compare with other algorithms (XGBoost, LightGBM, CatBoost)
- Implement longitudinal analysis for causal relationships
- Develop health monitoring application

## Technologies Used
- **Python 3.8+**
- **scikit-learn**: Machine learning modeling
- **pandas**: Data manipulation
- **matplotlib & seaborn**: Data visualization
- **NumPy**: Numerical computations

## Authors
- Hanifa Syifa Safitri
- Mutiara Rosida Sholihat
- Sylvasisca Andini Faradyan
- Lutfiah Nailil Izzah
- Acik Imtia Chana

**Informatics Engineering, Faculty of Computer Science**  
**Universitas Brawijaya**

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Global Coffee Health Dataset from Kaggle
- Faculty of Computer Science, Universitas Brawijaya
- Research references from Stevens et al. (2021), Gao et al. (2025), and others

## Citation
If you use this project in your research, please cite:
```
Safitri, H.S., Sholihat, M.R., Faradyan, S.A., Izzah, L.N., & Chana, A.I. (2025).
Analisis Pengaruh Konsumsi Kopi terhadap Kesehatan Menggunakan Pendekatan 
Machine Learning Random Forest dengan Studi Data Global. 
Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 1(1).
```
