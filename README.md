# 🚗 Dynamic Pricing for Urban Parking Lots

Capstone Project — Summer Analytics 2025  
Hosted by: Consulting & Analytics Club × Pathway  

---

## 📌 Project Overview

Urban parking is a limited and highly dynamic resource. Static pricing often results in either underutilization or overcrowding of parking lots.  
This project simulates and builds a **real-time dynamic pricing engine** for 14 urban parking spaces using a combination of **data-driven models**, **geospatial intelligence**, and **real-time stream processing**.

The goal is to:
- Adjust parking prices in real-time
- Improve space utilization
- Ensure fairness and responsiveness using explainable logic

---

## 🧰 Tech Stack

| Category        | Tools/Technologies                    |
|----------------|----------------------------------------|
| Language        | Python 3.9+                            |
| Data Processing | Pandas, NumPy                          |
| Real-Time Engine| [Pathway](https://pathway.com/)        |
| Geospatial Calc | geopy                                  |
| Visualization   | Bokeh                                  |
| Hosting/Version | Google Colab, GitHub                   |

---

## 🏗️ System Architecture

mermaid
flowchart TD
    A[Static Dataset (CSV)] -->|Simulated Stream| B[Pathway Engine]
    B --> C[Feature Processing & Encoding]
    C --> D1[Model 1: Linear Pricing]
    C --> D2[Model 2: Demand-Based Pricing]
    C --> D3[Model 3: Competitive Pricing]
    D1 --> E[Unified Price Output Stream]
    D2 --> E
    D3 --> E
    E --> F[JSON Output / Bokeh Visualization]

🔄 Workflow & Logic
🔸 Input
18,000+ rows of 73 days of data (18 time points/day for 14 lots)
Each row contains:
Occupancy, Capacity, QueueLength
VehicleType, TrafficConditionNearby, IsSpecialDay
Latitude, Longitude

🔸 Real-Time Processing with Pathway
Pathway reads the static CSV and simulates real-time streaming
Each row is treated as an event with a timestamp

Models Implemented
✅ Model 1: Linear Pricing
Simple baseline model using:
Price(t+1) = Price(t) + α × (Occupancy / Capacity)

✅ Model 2: Demand-Based Pricing
Weighted scoring function:
Demand = α·(Occupancy/Capacity) + β·Queue − γ·Traffic + δ·Special + ε·VehicleTypeWeight

Price:
Price = BasePrice × (1 + λ × tanh(NormalizedDemand))

✅ Model 3: Competitive Pricing
Calculates distance matrix between lots
Adjusts price up or down depending on proximity and competitor pricing

📈 Visualizations
Real-time price trends for each lot are plotted using Bokeh, comparing:
Linear pricing
Demand-based pricing
Competitive-adjusted pricing

