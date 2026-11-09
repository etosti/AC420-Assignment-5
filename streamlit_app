  import yfinance as yf
  import pandas as pd
  import streamlit as st

  st.title("MSFT 5-Year Monthly Sharpe Ratio by Your Name")

  ticker = "MSFT"
  rf_monthly = 0.0025  # 0.25% per month

  data = yf.Ticker(ticker).history(period="5y", interval="1mo")

  if not data.empty:
      monthly_returns = data["Close"].pct_change().dropna()
      excess_returns = monthly_returns - rf_monthly
      sharpe = excess_returns.mean() / monthly_returns.std()
      st.metric(label=f"{ticker} Monthly Sharpe Ratio", value=f"{sharpe:.3f}")
  else:
      st.error("No data found for MSFT.")
