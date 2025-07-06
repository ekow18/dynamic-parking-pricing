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


    📦 Repository Contents
File/Folder	Description
final_notebook.ipynb	Contains all 3 pricing models and Pathway integration
data/dataset.csv	Main input dataset for the models
output/bokeh_plot.png	Screenshot of real-time Bokeh visualization
requirements.txt	Python dependencies
capstone_report.pdf	(Optional) Report with summary & explanation
README.md	This file

Project Workflow
Load & clean dataset (dataset.csv)
Implement:
    Model 1: Price = base + α × (occupancy / capacity).
    Model 2: Weighted demand score → normalized → dynamic price.
    Model 3: Add competitor proximity + reroute logic.
Stream pricing data in real-time with Pathway.
Plot prices dynamically using Bokeh.

Visualization
The bokeh_plot.png shows real-time dynamic pricing over time for top 5 busiest lots.
    Line charts for each lot
    Tooltip shows time, price, and reroute flag
    Interactive legend for filtering

If included, the report (Dynamic Pricing for Urban Parking Lots.pdf) covers:
    Project motivation & problem
    Data structure
    Demand formula & reasoning
    Competitive pricing logic
    Sample outputs and findings

# Install dependencies
pip install -r requirements.txt

Submission Status
     Models 1, 2, 3 implemented in one notebook.
     Real-time data simulation using Pathway.
     Bokeh dashboard included.
     Report PDF attached.
     Repository is public and well-documented.

Access:
This repository is public and ready for evaluation.
All assets are self-contained — no additional setup needed.

🙌 Acknowledgments
Consulting & Analytics Club, IITG.
Pathway Engineering Team.
All mentors & peers in Summer Analytics 2025.

Made with 💡 and 🧠 by Titus Yankson
