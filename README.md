🅿️ Dynamic Pricing for Urban Parking Lots
A real-time simulation project that implements intelligent pricing strategies for 14 urban parking lots using Python, Numpy, Pandas, and Bokeh — with Pathway support for streaming.

Capstone project for Summer Analytics 2025 hosted by the Consulting & Analytics Club × Pathway.

📁 Files
bash
Copy code
├── dataset.csv                  # Parking data (upload manually in Colab)
├── dynamic_pricing_notebook.ipynb  # Main Colab notebook
├── README.md                    # Project documentation
🚀 Setup & Installation
✅ Google Colab
Open the notebook in Google Colab

Install required packages:

python
Copy code
!pip install geopy bokeh --quiet
Upload the dataset:

python
Copy code
from google.colab import files
uploaded = files.upload()  # Choose dataset.csv
🔍 Dataset Description
Collected over 73 days from 14 urban parking spaces, sampled every 30 minutes (18 time points/day).

Feature	Description
Occupancy	Number of parked vehicles
Capacity	Maximum lot capacity
QueueLength	Waiting vehicles
VehicleType	car, bike, truck
TrafficConditionNearby	low, medium, high
IsSpecialDay	1 for event/holiday, 0 otherwise
Latitude, Longitude	Geolocation
LastUpdatedTime	Timestamp for simulation

🧠 Models Implemented
📘 Model 1: Baseline Linear Pricing
Price increases linearly with occupancy:

Copy code
Price_t+1 = Price_t + α * (Occupancy / Capacity)
Starts from $10

Smooth increase

Acts as a reference model

📗 Model 2: Demand-Based Dynamic Pricing
Pricing based on multiple real-world features:

ini
Copy code
Demand = α·(Occ/Cap) + β·Queue − γ·Traffic + δ·IsSpecialDay + ε·VehicleType
Price = BasePrice * (1 + λ * NormalizedDemand)
Demand is normalized

Price bounded between $5 and $20

📙 Model 3: Competitive Pricing
Includes nearby lots (within 1km):

If a lot is full and neighbors are cheaper, reduce price

If neighbors are expensive, increase price

Uses Haversine distance with geopy

📊 Visualization
Interactive Bokeh plots for each lot:

Linear vs Demand vs Competitive Prices

Real-time line plots

Enable visual comparison of model behavior

python
Copy code
show(plot_prices('BHMBCCMKT01'))  # Example plot for one parking lot
🔄 Real-Time (Optional)
You can extend the notebook with:

Pathway integration to simulate streaming

Pricing engine reacting to real-time events

Suggest rerouting to nearby lots when full

Resources:

Pathway Docs – First Realtime App

✍️ Report Checklist (For Submission)
✅ Dataset summary
✅ Model explanations (with formulas)
✅ Well-commented notebook
✅ Visualizations using Bokeh
✅ Justification of assumptions and pricing logic

👨‍💻 Author
Pranjal Tiwari
Capstone Project · Summer Analytics 2025
Consulting & Analytics Club, IITG

