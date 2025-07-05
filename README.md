
Dynamic Pricing for Urban Parking Lots**

### 🚀 Overview
This project implements a real-time dynamic pricing engine for urban parking lots using:
- 📈 Historical and real-time features
- 🧠 Three progressively complex models
- 📊 Interactive Bokeh dashboard for live visualization

Built as part of **Summer Analytics 2025** organized by the Consulting & Analytics Club.

### 📁 Contents
- `Dynamic_Pricing_Models.ipynb` — Main notebook with code, explanations, and dashboard
- `dataset.csv` — Provided dataset with 14 parking lots over 73 days
- `README.md` — Project summary and usage

### 📊 Models Implemented
1. **Model 1: Baseline Linear Pricing**
   - Price increases linearly with occupancy rate

2. **Model 2: Demand-Based Pricing**
   - Uses occupancy, queue length, traffic, special days, and vehicle type
   - Applies a normalized demand score

3. **Model 3: Competitive Pricing**
   - Adjusts price based on competitor proximity and price
   - Uses geographic distance (within 1km) between lots

### 💻 How to Run
#### ➤ Option 1: Jupyter Notebook
```bash
jupyter notebook Dynamic_Pricing_Models.ipynb
```

#### ➤ Option 2: Run the Bokeh Dashboard
```bash
bokeh serve --show Dynamic_Pricing_Models.ipynb
```
This opens an interactive dashboard where you can select parking lots and compare pricing across models.

### 📦 Dependencies
```bash
pip install pandas numpy geopy bokeh
```

### 📌 Dataset Features
- `SystemCodeNumber`, `Latitude`, `Longitude`
- `Capacity`, `Occupancy`, `QueueLength`
- `VehicleType`, `TrafficConditionNearby`, `IsSpecialDay`
- Timestamps every 30 minutes from 8:00 AM to 4:30 PM

### 🔍 Visualizations
- Real-time line plots for each pricing model
- Dropdown to switch between parking lots

### 🧠 Team
- Participant: _Your Name_
- Event: Summer Analytics 2025
- Hosted by: Consulting & Analytics Club × Pathway
