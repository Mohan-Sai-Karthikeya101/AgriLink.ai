# AgriLink.AI — Intelligent Agricultural Decision Support System

<div align="center">

# 🌾 AgriLink.AI

### AI-Powered Agricultural Decision Support System

**Smarter Crop Selection. Better Cultivation Planning. Informed Market Decisions.**

[GitHub Repository](https://github.com/Mohan-Sai-Karthikeya101/AgriLink.ai)

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--learn-orange)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow?logo=googlecolab)
![Data Processing](https://img.shields.io/badge/Data-Pandas%20%7C%20NumPy-green)

</div>

---

## 01. PROJECT OVERVIEW

**AgriLink.AI** is a Python-based agricultural decision-support system that combines machine learning, agricultural data analysis, and market-price forecasting to assist farmers in making informed farming decisions.

The system analyses geographical, soil, nutrient, and environmental conditions to recommend suitable crops. It extends beyond crop selection by providing cultivation guidance, yield estimates, market-price analysis, and estimated financial outcomes.

The objective is to connect different stages of agricultural decision-making through one integrated application.

## 02. PROBLEM STATEMENT

Farmers often have to make important decisions about crop selection, cultivation practices, expected production, and market opportunities using information available from different sources.

Choosing an unsuitable crop, overlooking soil requirements, or making decisions without considering market conditions can affect agricultural productivity and profitability.

AgriLink.AI addresses this challenge by bringing relevant agricultural information and predictive analysis together in a single decision-support workflow.

## 03. PROJECT OBJECTIVES

- Recommend crops based on soil, nutrient, geographical, and environmental conditions.
- Rank suitable crop alternatives using prediction probabilities and suitability scoring.
- Provide crop-specific cultivation and irrigation guidance.
- Estimate agricultural yield using a trained machine-learning model.
- Analyse historical market prices and estimate future price trends.
- Identify relevant markets and compare potential selling opportunities.
- Calculate estimated revenue, cultivation expenditure, and profit.

## 04. KEY FEATURES

### 4.1 Crop Recommendation

The application analyses farmer-provided inputs and produces a ranked list of suitable crops.

Each recommendation includes a suitability score, allowing users to compare multiple crop alternatives.

### 4.2 Cultivation Guidance

Provides relevant information for recommended crops, including:

- Cultivation requirements and practices.
- Irrigation guidance.
- Nutrient management.
- Crop calendar and growing period.
- Expected harvesting period.
- Harvesting and post-harvest information.
- Shelf-life and storage guidance, where available.

### 4.3 Yield Estimation

Uses a trained regression model to estimate crop production based on agricultural and geographical information, including crop, state, district, season, year, and cultivated area.

### 4.4 Market Analysis and Price Forecasting

Analyses available historical market-price records to identify selling opportunities and estimate price trends.

The application can use market-level, district-level, or state-level information depending on available records.

### 4.5 Financial Evaluation

Combines estimated production, expected selling price, and estimated cultivation expenditure to calculate potential financial outcomes.

- **Estimated Revenue** = Estimated Production × Expected Selling Price
- **Estimated Profit** = Estimated Revenue − Estimated Cultivation Cost
- **Profit per Acre** = Estimated Profit ÷ Cultivated Land Area

These values are estimates intended to support planning, not guaranteed financial returns.

## 05. INPUT PARAMETERS

The application uses the following farmer-provided information:

| Input | Description |
|---|---|
| State | Geographical location |
| District | District of cultivation |
| Soil Type | Type of soil available |
| Soil pH | Soil acidity or alkalinity |
| Nitrogen (N) | Nitrogen content |
| Phosphorus (P) | Phosphorus content |
| Potassium (K) | Potassium content |
| Average Temperature | Local temperature |
| Water Availability | Available water for cultivation |
| Land Area | Area available for farming |

These inputs are used in the relevant recommendation and analytical stages.

## 06. MACHINE-LEARNING MODELS AND ALGORITHMS

AgriLink.AI uses the following machine-learning algorithms:

| Model / Algorithm | Application |
|---|---|
| Random Forest Classifier | Crop recommendation and probability-based ranking |
| Random Forest Regressor | Agricultural yield estimation |
| Linear Regression | Historical market-price trend modelling and forecasting |
| One-Hot Encoding | Processing categorical inputs in the yield prediction pipeline |
| Column Transformer | Applying appropriate preprocessing to different input columns |

### Crop Recommendation — Random Forest Classifier

The pre-trained Random Forest Classifier evaluates agricultural input features and produces class probabilities through `predict_proba()`. These probabilities contribute to the crop recommendation and ranking process.

### Yield Prediction — Random Forest Regressor

The yield model is implemented as a Scikit-learn Pipeline. It uses a Column Transformer and One-Hot Encoding to process categorical information before the Random Forest Regressor estimates production.

### Market Price Forecasting — Linear Regression

Linear Regression is fitted dynamically using available historical market-price records. Date-related and seasonal features are used to estimate price trends.

## 07. TECHNOLOGY STACK

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| NumPy | Numerical computations |
| Pandas | Data processing and analysis |
| Scikit-learn | Machine-learning models and regression |
| Joblib | Loading precomputed models and data |
| RapidFuzz | Approximate text matching |
| Google Colab | Cloud-based execution environment |
| GitHub | Source-code and precomputed-resource hosting |

## 08. DATASETS AND DATA PROCESSING

AgriLink.AI uses a precomputed data bundle containing trained models, agricultural datasets, and supporting resources.

The bundle includes:

- Crop-related data used for recommendation.
- Real and synthetic crop-related records maintained separately.
- Encoded crop labels and model feature information.
- Agricultural yield data and crop mappings.
- Rainfall and crop-calendar information.
- Market and historical price records.
- Crop-specific cultivation guidelines.

The application uses Pandas for data handling and preprocessing, while Joblib loads the prepared resources.

**Data transparency:** Real and synthetic records are maintained distinctly. Where synthetic information is used as supplementary data, it should not be interpreted as an actual historical observation. Dataset-specific publishers and source URLs should be consulted in the accompanying dataset documentation.

## 09. SYSTEM WORKFLOW

1. The farmer enters geographical, soil, nutrient, environmental, and land-area information.
2. The application processes the input parameters.
3. The trained crop classification model generates crop probabilities.
4. Crop probabilities and agricultural suitability scoring contribute to the ranked recommendations.
5. Relevant cultivation information is retrieved for the recommended crops.
6. The yield prediction pipeline estimates agricultural production.
7. Historical market records are analysed and price trends are estimated using Linear Regression.
8. Estimated production, selling prices, and cultivation costs are used for financial evaluation.
9. The application presents the results to support agricultural decision-making.

## 10. EXECUTION ENVIRONMENT

AgriLink.AI is designed to run in **Google Colab** as a single-cell Python implementation.

The application retrieves its precomputed resource bundle from the project's public GitHub repository and loads the required models and datasets using Joblib.

### Running the Project

1. Open [Google Colab](https://colab.research.google.com/).
2. Create a new Python notebook.
3. Copy the complete application code into a code cell.
4. Execute the cell.
5. Provide the required agricultural inputs when prompted by the application.

The required Python libraries include:

```bash
pip install numpy pandas scikit-learn joblib rapidfuzz
```

If the application code already installs missing dependencies, a separate installation step may not be necessary.

### Precomputed Resource Bundle

The application uses:

```text
agrilink_precomputed_bundle.joblib
```

This bundle stores the prepared models and supporting datasets required for execution.

## 11. NOVELTY AND UNIQUE CONTRIBUTION

The primary innovation of AgriLink.AI is its integration of multiple agricultural decision-making stages into one system.

Instead of stopping at crop recommendation, the application connects crop selection with cultivation guidance, yield estimation, market-price analysis, and financial evaluation.

Its key contribution is providing a more connected view of the farming process: **what to grow, how to cultivate it, what production to expect, and how to evaluate its potential market return.**

## 12. FUTURE SCOPE

Potential future improvements include:

- Integration of live weather forecasts and rainfall updates.
- Soil analysis using uploaded soil-test reports.
- Satellite and remote-sensing-based crop monitoring.
- More extensive verified agricultural and market datasets.
- Improved regional and seasonal model training.
- Mobile-friendly access for farmers.
- Local-language support and voice-based interaction.
- Integration with live mandi prices and market information.
- More detailed cultivation-cost estimates based on crop and region.

## 13. LIMITATIONS AND DISCLAIMER

- Recommendations depend on the quality and coverage of the available agricultural data.
- Predictions are estimates and may differ from actual field outcomes.
- Market-price forecasts depend on historical records and may not capture sudden market changes.
- Synthetic records, where used, are supplementary and are not equivalent to verified real-world observations.
- Cultivation expenditure and financial projections should be treated as estimates.
- The system is intended to support agricultural decisions and does not replace professional agricultural advice or local field assessment.

## 14. CONCLUSION

AgriLink.AI demonstrates how machine learning, agricultural datasets, predictive analysis, and financial calculations can be combined into a unified agricultural decision-support system.

By connecting crop recommendation, cultivation guidance, yield estimation, and market analysis, the project aims to make agricultural information more accessible and help farmers evaluate their options more systematically.

---

<div align="center">

### 🌱 AgriLink.AI

**Connecting Agricultural Data with Better Farming Decisions.**

[View Source Code on GitHub](https://github.com/Mohan-Sai-Karthikeya101/AgriLink.ai)

</div>
