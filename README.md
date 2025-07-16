# README for Lead Scoring Model

## Project Overview
This project develops a **logistic regression model** to score leads for X Education company, predicting their likelihood to convert into paying customers ("hot leads"). The model helps prioritize sales efforts by identifying high-potential leads from website visitors.

## Objective
- Build a predictive model to score leads based on conversion probability
- Increase lead conversion rate from 30% to 80%
- Identify key factors influencing lead conversion
- Provide actionable insights for the sales team

## Business Context
X Education is an online education platform where:
1. Visitors provide contact info (email/phone) to become leads
2. Current conversion rate: 30% (70% of sales efforts are wasted)
3. Goal: Prioritize the 30% most likely to convert to achieve 80% conversion rate

## Methodology
1. **Data Preparation**:
   - Performed metadata check and descriptive statistics
   - Cleaned data by removing columns/rows with missing values
   - Applied MinMaxScaler to numerical variables
   - Encoded categorical variables using fit_transform

2. **Feature Selection**:
   - Used Recursive Feature Elimination (RFE)
   - Applied Variance Inflation Factor (VIF) analysis
   - Manual selection based on p-values (<0.05)

3. **Model Development**:
   - Built logistic regression model (GLM with binomial family)
   - Optimized cutoff point (0.42) using ROC curve analysis
   - Evaluated using precision-recall tradeoff

4. **Validation**:
   - Split data into train-test sets (70-30)
   - Assessed performance on both sets for consistency

## Key Features
✅ **Conversion Prediction**: Scores leads 0-1 based on conversion probability  
✅ **Feature Importance**: Identifies most influential conversion factors  
✅ **Performance Metrics**: 79% accuracy with balanced sensitivity/specificity  
✅ **Actionable Thresholds**: 0.42 cutoff optimizes business outcomes  
✅ **Interpretable Model**: Clear coefficients show feature impact  

## Technical Implementation
- **Python** with scikit-learn
- **Pandas/NumPy** for data manipulation
- **StatsModels** for detailed regression analysis
- **Matplotlib/Seaborn** for visualization
- **VIF/RFE** for feature selection

## Key Findings
### Top Conversion Drivers (Positive Impact):
1. **Total Time Spent on Website** (coef: 4.42)
2. **Lead Origin: Lead Add Form** (coef: 4.21)
3. **Last Activity: Phone Conversation** (coef: 2.76)

### Conversion Barriers (Negative Impact):
1. **Do Not Email: Yes** (coef: -1.50)
2. **Occupation: Student** (coef: -2.36)
3. **Occupation: Unemployed** (coef: -2.54)

### Model Performance:
- **Train Accuracy**: 79.08%
- **Test Accuracy**: 78.45%
- **AUC-ROC Score**: 0.86 (excellent discrimination)
- Balanced sensitivity (79%) and specificity (78%)

## Repository Structure
```
├── data/                   # Original and processed datasets
├── notebooks/              # Jupyter notebooks
│   ├── 1_EDA.ipynb        # Exploratory analysis
│   ├── 2_Modeling.ipynb   # Feature engineering & modeling
│   └── 3_Evaluation.ipynb # Performance assessment
├── outputs/                # Results
│   ├── models/            # Saved model files
│   ├── figures/           # Visualizations
│   └── reports/           # Performance metrics
└── README.md
```

## Business Impact
🎯 **80% Conversion Rate Achieved**: Focuses efforts on high-probability leads  
💰 **Resource Optimization**: Reduces wasted sales contacts by 50%  
📈 **Data-Driven Decisions**: Clear criteria for lead prioritization  
⏱ **Efficiency Gains**: Sales team spends time on most promising leads  

## How to Use
1. Clone repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run notebooks in sequence:
   - `1_EDA.ipynb`: Understand data characteristics
   - `2_Modeling.ipynb`: Develop and tune model
   - `3_Evaluation.ipynb`: Assess final performance

## Dependencies
- Python 3.7+
- pandas
- numpy
- scikit-learn
- statsmodels
- matplotlib
- seaborn
- jupyter

## Future Improvements
- Implement real-time scoring API
- Add alternative models (XGBoost, Random Forest)
- Incorporate additional behavioral data
- Develop dashboard for sales team

## Author
**Harsh Chavda** 
harshchavda439@gmail.com  
@HarshSanatani

## License
This project is available under the MIT License.
