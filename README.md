# dynamic-parking-pricing
# Dynamic Pricing for Urban Parking Lots  
**Summer Analytics 2025 – Capstone Project**  
**By:** Titus Yankson  
**Hosted by:** Consulting & Analytics Club × Pathway

---

## 🧾 Overview

This project tackles inefficiencies in urban parking systems by implementing a real-time dynamic pricing engine. Using a simulated data stream of parking lot metrics (occupancy, queue, traffic, etc.), three intelligent pricing models were built:

1. **Model 1:** Baseline linear pricing  
2. **Model 2:** Demand-based pricing using multiple real-time signals  
3. **Model 3:** Competitive pricing using geo-proximity and rerouting logic

---

## ⚙️ Tech Stack

| Component     | Tool |
|---------------|------|
| Language      | Python (3.11+)  
| Libraries     | `pandas`, `numpy`, `pathway`, `bokeh`  
| Platform      | Google Colab  
| Visualization | Bokeh  
| Data Format   | CSV, JSONL  

---

## 🏗 Architecture Diagram

flowchart TD
    A[Input Dataset (CSV)]
    B[Pathway Stream]
    C[Model 1: Baseline Pricing]
    D[Model 2: Demand-Based Pricing]
    E[Model 3: Competitive Pricing + Rerouting]
    F[Pathway JSONL Output]
    G[Bokeh Dashboard]

    A --> B --> C --> F --> G
    B --> D --> F
    B --> E --> F
