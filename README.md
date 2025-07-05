# 🅿️ Dynamic Parking Pricing Engine

A real-time intelligent pricing system designed to optimize urban parking revenue and availability. This system dynamically adjusts parking fees based on occupancy, demand, traffic, vehicle types, and competitive pressure—built from scratch using **Python**, **Pathway**, and **Bokeh** with no external machine learning libraries.

---

## 📌 Table of Contents

- [🚀 Overview](#-overview)
- [📂 Dataset Description](#-dataset-description)
- [🧠 Pricing Models](#-pricing-models)
- [⚙️ Architecture](#️-architecture)
- [📦 Tech Stack](#-tech-stack)
- [🔧 Setup Instructions](#-setup-instructions)
- [📊 Visualization](#-visualization)
- [📉 Anomaly Detection](#-anomaly-detection)
- [📈 Optimization Strategy](#-optimization-strategy)
- [🧪 Testing & Simulation](#-testing--simulation)
- [📚 Future Extensions](#-future-extensions)
- [🤝 Author](#-author)

---

## 🚀 Overview

This project simulates a **real-time dynamic pricing engine** for 14 parking lots in a city. It operates using three progressive models:
- **Model 1**: Linear pricing based on occupancy
- **Model 2**: Demand-responsive pricing using engineered features
- **Model 3**: Competitive pricing adjustment based on nearby lot prices

The system is real-time-capable via [Pathway](https://pathway.com), and prices are visualized with an interactive dashboard using **Bokeh**.

---

## 📂 Dataset Description

The engine reads from a CSV that simulates real-time updates from parking sensors.

### Key Fields:
| Column | Description |
|--------|-------------|
| `Occupancy` | Vehicles parked |
| `Capacity` | Total parking capacity (static) |
| `QueueLength` | Waiting vehicles |
| `TrafficConditionNearby` | Categorical: `low`, `average`, `high` |
| `VehicleType` | `car`, `bike`, `truck`, `cycle` |
| `IsSpecialDay` | Binary: 1 if holiday or special event |
| `LastUpdatedDate`, `LastUpdatedTime` | Timestamp of observation |

---

## 🧠 Pricing Models

### 🔹 Model 1: Baseline Linear
price = base_price * (1 + occupancy / capacity)


###🔹 Model 2: Demand-Based

Uses normalized features:
Occupancy rate
Queue length
Traffic intensity
Vehicle type weight
Event flag
Price is scaled linearly between $5 and $20 based on a composite demand score.

###🔹 Model 3: Competitor-Aware

Computes Haversine distance to competing lots
Adjusts price if competitors are cheaper

             ARCHITECTURE
                
                +------------------+
                | Parking Data CSV |
                +--------+---------+
                         |
                         ▼
          +----------------------------+
          | Data Preprocessing & Merge |
          +----------------------------+
                         |
                         ▼
          +-----------------------------+
          |  Feature Engineering & Logic|
          | (Occupancy, Queue, Events…) |
          +-----------------------------+
             |     |     |
             ▼     ▼     ▼
         Model 1  Model 2  Model 3
             |     |     |
             +-----+-----+
                   ▼
         +------------------+
         | Price Dashboard  |
         +------------------+
