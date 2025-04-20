# Predicting Market States Using LSTM on Macroeconomic Indicators

This repository contains a project that uses macroeconomic indicators to predict market regimes (bear vs. bull) and applies various trading strategies based on these predictions. It leverages an LSTM (Long Short-Term Memory) neural network for classification and includes different back-tested strategies with risk management rules.

---

## Table of Contents
1. [Project Overview](#project-overview)  
2. [Key Features](#key-features)  
3. [Data Preprocessing](#data-preprocessing)  
4. [Model Architecture](#model-architecture)  
5. [Trading Strategies](#trading-strategies)  
6. [Risk Management](#risk-management)  
7. [Getting Started](#getting-started)  
8. [Usage](#usage)  
9. [Results & Performance](#results--performance)  
10. [Contributing](#contributing)  
11. [License](#license)

---

## Project Overview
This project aims to classify stock market regimes (bear vs. bull) using a dataset of macroeconomic indicators. The classification is used to inform dynamic trading strategies that adapt their positions depending on whether the market is expected to be in a bullish or bearish trend.

### Goals
- Explore the predictive power of macroeconomic variables on future market regimes.  
- Build a robust deep learning model (LSTM) to classify market conditions.  
- Develop and back-test multiple trading strategies that respond to predicted market regimes.  
- Implement risk management techniques via stop losses.

---

## Key Features
- **Feature Engineering**: Automates the removal of highly correlated features to reduce multicollinearity.  
- **Target Creation**: Labels each data point as `0` (bear market) or `1` (bull market).  
- **Deep Learning Approach**: Utilizes an LSTM network for sequence modeling.  
- **Multiple Trading Strategies**: Dynamically allocates capital to different asset classes based on predicted market regime.  
- **Risk Management**: Employs a 2% stop-loss rule informed by historical back-tests.

---

## Data Preprocessing
1. **Macroeconomic Indicators**: A comprehensive dataset of macro indicators (e.g., interest rates, inflation, GDP growth, etc.) is collected.  
2. **Correlation Check**: Highly correlated features are removed to reduce redundancy and avoid model overfitting.  
3. **Feature Scaling**: Normalization or standardization is applied as needed for LSTM training.  
4. **Target Variable**:  
   - **0** for Bear Market  
   - **1** for Bull Market  

---

## Model Architecture
- **Bi-Directional LSTM Layers**: The model includes two LSTM layers, which are particularly useful for time-series data.
- **Dropout Layers**: Dropout layers help the model deal with overfitting issues. 
- **Dense Layers**: After these layers, a dense layer is used to output a binary classification.  
- **Compilation**: The model is compiled with a binary crossentropy loss function and Adam optimizer.

---

## Trading Strategies
After training the LSTM to predict future market regimes, the following strategies are employed:

1. **Strategy 1**:  
   - **Bull Market (1)**: Buy and hold the S&P 500 (SPY).  
   - **Bear Market (0)**: Hold cash earning interest.

2. **Strategy 2**:  
   - **Bull Market (1)**: Buy and hold the S&P 500 (SPY).  
   - **Bear Market (0)**: Short or buy an inverse S&P 500 ETF (e.g., SH).

3. **Strategy 3**:  
   - **Bull Market (1)**: Buy and hold the Technology sector SPDR (XLK).  
   - **Bear Market (0)**: Rotate into the Consumer Staples sector SPDR (XLP).

---

## Risk Management
Each strategy incorporates risk management via:
- **2% Stop-Loss**: Positions are exited if they incur a 2% loss from the entry price, as determined by back-test results.  
- **Periodic Rebalancing**: Positions are reevaluated at each prediction interval.


---

## Results & Performance
- **Classification Metrics**: You can find accuracy, precision, recall, and F1 scores for predicting the market regime.  
- **Strategy Returns**: Each strategy’s performance is benchmarked against a simple buy-and-hold strategy of the S&P 500.  
- **Risk Adjusted Metrics**: Sharpe ratio, maximum drawdown, and return volatility are included to help compare each strategy's risk profile.

---

## Contributing
Contributions are welcome! If you have suggestions for improvements or want to add more trading strategies, please open an issue or submit a pull request.

---

## License
This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute this code for educational or commercial purposes with proper attribution.

---

*Thank you for checking out this repository! If you have questions or feedback, please [open an issue](https://github.com/farhanbham/Market-State-Classifier/issues)
