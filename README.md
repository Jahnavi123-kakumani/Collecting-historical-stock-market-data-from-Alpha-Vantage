
# Collecting Historical Stock Market Data from Alpha Vantage

## Overview

This repository contains a Jupyter Notebook for collecting historical stock market data using the **Alpha Vantage API**. It demonstrates how to fetch and process stock data for analysis and visualization.

---

## Features

- Fetch stock market data using the **Alpha Vantage API**.
- Download historical data for various stocks.
- Save data in CSV format for further analysis.
- Perform basic data exploration and visualization.

---

## Prerequisites

Before running the notebook, ensure you have the following:

1. **Alpha Vantage API Key**: 
   - Sign up for a free account at [Alpha Vantage](https://www.alphavantage.co/).
   - Obtain your API key.
2. **Python Environment**: 
   - Python 3.x installed.
   - Required libraries (listed below).

---

## Installation

 Install dependencies:
   ```bash
   pip install pandas matplotlib requests
   ```

---

## How to Use

1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook "Collecting historical stock market data from Alpha Vantage.ipynb"
   ```
2. Replace `<YOUR_API_KEY>` with your Alpha Vantage API key in the notebook.
3. Specify the stock symbol and time interval for the data:
   - Example: `MSFT` for Microsoft, `daily` for daily data.
4. Run the notebook to fetch and save the data.
5. Use the saved CSV file for further analysis or visualization.

---

## Example Code Snippet

The following snippet demonstrates how to fetch data using the Alpha Vantage API:

```python
import requests
import pandas as pd

# Set your API key
api_key = "<YOUR_API_KEY>"

# Define parameters
symbol = "AAPL"  # Apple Inc.
function = "TIME_SERIES_DAILY"
url = f"https://www.alphavantage.co/query?function={function}&symbol={symbol}&apikey={api_key}&datatype=csv"

# Fetch data
response = requests.get(url)

# Save to CSV
with open(f"{symbol}_daily.csv", "w") as file:
    file.write(response.text)

# Load and preview data
data = pd.read_csv(f"{symbol}_daily.csv")
print(data.head())
```

---

## Output

The notebook will:
- Download the historical stock data.
- Save it as a CSV file (e.g., `AAPL_daily.csv`).
- Display the data and plot graphs (if implemented).
