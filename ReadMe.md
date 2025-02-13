# 📈 Stock Price Prediction - BBVA  

## 🔹 1️⃣ Introduction  
The goal of this project is to predict the **next day's closing price** of BBVA stock using **machine learning**.  
We use **technical indicators** (RSI, MACD, Bollinger Bands) and train a **Linear Regression model**.  

---

## 🔹 2️⃣ Data Preprocessing  

### 📌 Steps Followed:  
- **Loaded dataset (`bbva.csv`).**  
- Converted **Date** column to datetime format.  
- Checked for missing values and used **Forward Fill (`ffill`)**.  
- Sorted data by date.  

---

## 🔹 3️⃣ Feature Engineering  

### 📌 Technical Indicators Used:  
| **Feature** | **Why We Used It?** |
|------------|----------------|
| **RSI (Relative Strength Index)** | Measures momentum to detect overbought/oversold conditions. |
| **MACD (Moving Average Convergence Divergence)** | Identifies trends and potential buy/sell signals. |
| **Bollinger Bands** | Helps analyze volatility and price breakouts. |
| **SMA (50 & 200-day Moving Averages)** | Captures long-term and short-term trends. |
| **Daily Return (%)** | Tracks percentage change in price. |
| **Volatility** | Measures risk and price fluctuations. |

🔹 **Features were selected based on financial market analysis best practices.**  

---

## 🔹 4️⃣ Model Selection & Hyperparameter Tuning  

### 📌 Chosen Model: **Linear Regression**  
- Linear Regression was chosen as a **baseline model** because:  
  ✅ It is **simple & interpretable**.  
  ✅ It is **fast to train** and performs well on structured data.  
  ✅ It provides a **benchmark before trying deep learning (LSTM)**.  

### 📌 Hyperparameter Tuning  
For this project:  
- **No hyperparameter tuning was needed** since **Linear Regression** has no major tunable parameters.  
- Future improvements could include **hyperparameter tuning for LSTM**.

---

## 🔹 5️⃣ Model Evaluation  

### 📌 Why These Evaluation Metrics?  
To assess the model’s performance, we selected:  

| **Metric** | **Why We Use It?** |
|------------|----------------|
| **MAE (Mean Absolute Error)** | Measures the average absolute difference between actual & predicted prices. It's easy to interpret in currency terms. |
| **MSE (Mean Squared Error)** | Penalizes larger errors more than MAE, which helps detect big prediction mistakes. |
| **RMSE (Root Mean Squared Error)** | Same unit as stock price (€), making it easy to understand. Lower RMSE means better predictions. |
| **R² Score (Coefficient of Determination)** | Measures how well the model explains price variations. Closer to 1 means better fit. |
| **MAPE (Mean Absolute Percentage Error)** | Expresses prediction error as a percentage, allowing comparison across different stocks. |

📌 **Why RMSE & MAPE?**  
- **RMSE** is widely used in stock price forecasting because it's easy to interpret.  
- **MAPE** is useful because it shows prediction error **as a percentage**, helping compare across different stock prices.  
- **R² Score** ensures the model **explains trends well**, rather than just minimizing error.  

---

## 🔹 6️⃣ Evaluation Results  

| **Metric** | **Value** | **Interpretation** |
|------------|------------|----------------|
| **MAE (Mean Absolute Error)** | **0.0899** | Predictions are off by ~€0.0899 on average. |
| **MSE (Mean Squared Error)** | **0.0148** | Smaller squared errors mean fewer large errors. |
| **RMSE (Root Mean Squared Error)** | **0.1215** | Typical prediction error is ~€0.12. |
| **R² Score** | **0.9898** | 99% of price movement is explained by the model. |
| **MAPE (Mean Absolute Percentage Error)** | **1.3%** | Predictions are **98.7% accurate**. |

📉 **Future Improvements:**  
- Try **LSTM (Deep Learning)** for better generalization.  
- Use more features like **sentiment analysis from news articles**.  

---

## 🔹 7️⃣ How to Run the Code  

### 📌 **Run on Google Colab** (Recommended)  
1️.Open [Google Colab](https://colab.research.google.com/).  
2️.Upload `notebooks/stock_analysis.ipynb`.  
3️.Upload `bbva_featured.csv` manually.  
4️.Run all cells.  

---

### 📌 **Run Locally (GitHub)**  
1️.Clone this repository:  
   ```bash
   git clone https://github.com/Reyhanbayan/stock-price-prediction.git
   cd stock-price-prediction
2️.Install dependencies (optional, for local execution):
   pip install -r requirements.txt
3️.Run Jupyter Notebook:
jupyter notebook
4️.Open notebooks/stock_analysis.ipynb and run all cells.

📝 Author
👤 Bayan Al-Anani
📧 Email: banani2000@hotmail.com
🔗 LinkedIn: http://www.linkedin.com/in/bayan-al-anani-0514a74a