
# 📈 Stock Market Forecasting & Portfolio Optimization

This project uses deep learning models (LSTM and CNN+LSTM) to forecast short-term stock price changes and optimize investment decisions through Integer Linear Programming (ILP).

---

## 🔍 Project Overview

The system predicts the **next-day price delta** (`Close - Open`) for selected stocks and generates a **10-day forecast**. Using these predictions, it identifies optimal **buy/sell windows** and applies an ILP-based optimizer to recommend a **profit-maximizing investment portfolio** under a fixed budget.

---

## 🧠 Core Features

- LSTM model for sequence prediction  
- Hybrid CNN+LSTM model for enhanced feature extraction  
- 10-day price delta forecasting  
- Technical indicator engineering (RSI, EMA, MACD, etc.)  
- Buy/sell window selection per stock  
- Integer Linear Programming (ILP) for capital allocation  
- Model evaluation with MAE, RMSE, R²  
- Visual comparison of predicted vs. actual prices  

---

## 📊 Technologies Used

- Python 🐍
- TensorFlow / Keras
- NumPy / Pandas / Matplotlib / Seaborn
- Yahoo Finance API (`yfinance`)
- `pandas-ta` for technical indicators
- `pulp` for ILP optimization
- `sklearn` for evaluation metrics

---

## 🚀 Getting Started

### Clone the repo:
```bash
git clone https://github.com/your-username/stock-forecast-ilp.git
cd stock-forecast-ilp
```

### Install requirements:
```bash
pip install -r requirements.txt
```

### Run the training + forecasting:
```python
from model import LSTMTrader

model = LSTMTrader(ticker='AAPL', backcandles=60, days=10)
model.run_full_pipeline()
```

### Compare models:
```python
model.compare_models()
```

### Optimize your portfolio:
```python
from ilp_optimizer import optimize_trades_with_ilp

preds = {
    'AAPL': [...],
    'NVDA': [...],
    ...
}

plan, invested, profit = optimize_trades_with_ilp(preds, budget=1000)
```

---

## 📁 Folder Structure

```
├── model.py               # LSTM, CNN+LSTM, forecasting, evaluation
├── ilp_optimizer.py       # ILP formulation for stock allocation
├── utils/                 # Helper utilities
├── plots/                 # Generated evaluation graphs
├── ref.bib                # BibTeX references
├── README.md
└── requirements.txt
```

---

## 📸 Visuals

> ![LSTM vs CNN+LSTM comparison](plots/metrics_comparison.png)  
> _Figure: Model evaluation comparing LSTM and CNN+LSTM (Test Set)_

---

## 🧪 Experimental Highlights

| Metric | LSTM (Test) | CNN+LSTM (Test) |
|--------|-------------|-----------------|
| MAE    | 1.4327      | 1.2656          |
| RMSE   | 2.2049      | 2.1962          |
| R²     | 0.4141      | 0.4187          |

---

## 📌 Future Enhancements

- Integrate real-time price feeds for live trading  
- Add hyperparameter tuning (e.g., using Optuna)  
- Explore transformer-based architectures  
- Support multi-asset and multi-day decision chains

---

## 🙏 Acknowledgments

Special thanks to **Dr. Gamal A. Ebrahim** for his supervision and guidance throughout this project.

---

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
