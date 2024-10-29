# Stock Price Prediction using LSTM

This project is a stock price prediction model built using Python, Keras, and Long Short-Term Memory (LSTM) neural networks. The program fetches historical stock price data and predicts future prices based on past trends. This can be a useful tool for analyzing stock trends and making informed predictions about future stock performance.

## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [License](#license)

## Features
- Fetches historical stock data using the `yfinance` library.
- Visualizes adjusted close prices and moving averages.
- Processes and scales data to prepare it for the LSTM model.
- Builds and trains an LSTM model to predict stock prices.
- Evaluates model performance using Root Mean Squared Error (RMSE).
- Plots the actual vs. predicted prices for easy comparison.

## Requirements
- Python 3.7+
- Libraries: 
  - `yfinance` for fetching stock data
  - `pandas` and `numpy` for data manipulation
  - `matplotlib` for data visualization
  - `sklearn` for scaling data
  - `keras` for building and training the LSTM model

Install the libraries using:
```bash
pip install -r requirements.txt
```

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/shreyvarshney1/stock-predictor.git
   cd stock-predictor
   ```
2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Run the program to start the stock data download, training, and predictions:
   ```bash
   python stock_price.py
   ```
2. The program will:
   - Download 20 years of historical stock data for Google (or any stock you specify).
   - Visualize the adjusted close price, moving averages, and percentage change in price.
   - Train an LSTM model on the historical data.
   - Predict and display future prices alongside actual values for comparison.

## Project Structure
```plaintext
StockPricePrediction/
│
├── stock_price.py   # Main script with data preprocessing, model training, and prediction
├── README.md             # Project documentation
└── requirements.txt      # List of required libraries
```

## Model Architecture
The model is built using an LSTM neural network with the following structure:
- **128 LSTM units** with `return_sequences=True`
- **Dropout layer** with a rate of 0.2 for regularization
- **64 LSTM units** without `return_sequences`
- Additional **Dropout layer**
- Fully connected **Dense layer** with 25 units
- Output layer with 1 unit for the final price prediction

The model uses `adam` optimizer and `mean_squared_error` as the loss function.

## Results
- **Evaluation Metric**: Root Mean Squared Error (RMSE) is used to assess model accuracy. A lower RMSE indicates better model performance.
- **Visualization**: The program generates plots of:
  - Adjusted Close Price over time
  - Adjusted Close Price with 100 and 250-day moving averages
  - Predicted vs. Actual stock prices

## License
This project is open-source and available under the [MIT License](LICENSE).