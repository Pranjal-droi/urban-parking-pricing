# 🚗 Dynamic Pricing for Urban Parking Lots

Capstone Project — Summer Analytics 2025  
Hosted by: Consulting & Analytics Club × Pathway

---

## 📌 Objective

This project implements a **real-time dynamic pricing engine** for 14 urban parking lots based on:

- 🅿️ Occupancy
- 🚗 Vehicle type (car/bike/truck)
- 🕐 Queue length
- 🚦 Traffic congestion
- 🎉 Special events
- 📍 Nearby competitor prices

The pricing logic evolves across **3 progressively intelligent models**.

---

## 📊 Models Implemented

### ✅ Model 1: Baseline Linear Model
- Price increases linearly with occupancy ratio:
  \[
  Price_{t+1} = Price_t + α \cdot \left(\frac{Occupancy}{Capacity}\right)
  \]

### ✅ Model 2: Demand-Based Pricing
- Combines multiple features into a demand score
- Normalized demand adjusts price:
  \[
  Price = BasePrice \cdot (1 + λ \cdot NormalizedDemand)
  \]

### ✅ Model 3: Competitive Pricing
- Adjusts price by comparing with nearby parking lots
- Uses geolocation (lat-long) and distance matrix

---

## 🔄 Real-Time Simulation with Pathway

- We simulate **streamed data** using Pathway's real-time engine
- Custom pricing logic is applied on-the-fly
- Output is continuously written to a JSON stream

---

## 📈 Visualizations

- Interactive line plots using **Bokeh**
- Price trends for each model across all 14 parking lots

---

## 🚀 Run This Project in Colab

Click below to open and run the notebook:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-username>/<your-repo>/blob/main/dynamic_pricing.ipynb)

Replace `<your-username>` and `<your-repo>` with your actual GitHub handle and repository name.

---

## 🛠️ Setup & Installation

### Requirements:
- Python 3.9+
- Google Colab (no local setup needed)

### For manual use:

```bash
pip install pathway pandas numpy bokeh geopy
