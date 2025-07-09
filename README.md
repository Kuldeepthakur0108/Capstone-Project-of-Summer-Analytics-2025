
# 🚗 Dynamic Pricing for Urban Parking Lots

**Capstone Project - Summer Analytics 2025**  
Hosted by: Consulting & Analytics Club × Pathway

GitHub Repository: [Capstone-Project-of-Summer-Analytics-2025](https://github.com/Kuldeepthakur0108/Capstone-Project-of-Summer-Analytics-2025)

---

## 📌 Overview

This project aims to optimize urban parking by implementing a **real-time dynamic pricing engine** for 14 parking lots. The goal is to prevent underutilization and overutilization of parking spaces using ML-based models developed **from scratch using only NumPy and Pandas**.

---

## 🧾 Problem Statement

Static pricing of urban parking leads to inefficiencies. The objective is to dynamically adjust prices based on:

- Occupancy levels
- Queue length
- Traffic congestion
- Vehicle type (car, bike, truck)
- Special events or holidays
- Nearby competitor prices

---

## 📊 Dataset

Collected over **73 days**, sampled every 30 minutes (18 slots per day) across **14 locations**.

Each row includes:

- **Location**: Latitude, Longitude
- **Parking Features**: Capacity, Occupancy, Queue Length
- **Vehicle Type**: Car, Bike, Truck
- **Environment**: Traffic Level, Special Day

---

## 🏗️ Models Implemented

### 🔹 Model 1: Baseline Linear Model
```
Price_{t+1} = Price_t + α * (Occupancy / Capacity)
```
A simple occupancy-based price change model.

---

### 🔹 Model 2: Demand-Based Dynamic Model
Constructs a demand score using:
```
Demand = α*(Occupancy/Capacity) + β*QueueLength − γ*Traffic + δ*IsSpecialDay + ε*VehicleTypeWeight  
Price_t = BasePrice * (1 + λ * NormalizedDemand)
```
Ensures smooth price fluctuations within a range (0.5x to 2x base price).

---

### 🔹 Model 3: Competitive Pricing Model
Optional but advanced model using geolocation:
- Computes nearby lot distances
- Adjusts prices relative to competitors
- Suggests rerouting if nearby lots are cheaper

---

## ⚙️ Tech Stack

- **Python**, using only: `pandas`, `numpy`, `pathway`
- **Google Colab**
- **Bokeh** for visualizations
- **Pathway** for real-time data streaming

---

## 📈 Visualizations

Real-time updates via Bokeh:
- Pricing trends over time
- Competitor comparisons
- Heatmaps of demand (optional)

---

## 🚀 How to Use

1. Clone the repository
2. Open the `Dynamic_Pricing_for_Urban_Parking_Lots.ipynb` on [Google Colab](https://colab.research.google.com/)
3. Run the cells in order:
   - Load data
   - Feature engineering
   - Pricing model
   - Real-time streaming & visualization

---

## 📘 Assumptions

- Base price starts at **$10**
- Vehicle types influence demand weights
- Traffic reduces willingness to pay
- Prices must change smoothly (no sudden spikes)

---

## 📚 References

- [Pathway Docs](https://pathway.com/developers/user-guide/introduction/first_realtime_app_with_pathway/)
- [Summer Analytics 2025](https://www.caciitg.com/sa/course25/)


