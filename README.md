# 🚗 Dynamic Pricing for Urban Parking Lots

**Summer Analytics 2025 – Capstone Project**
**By:** Titus Yankson
**Hosted by:** Consulting & Analytics Club × Pathway

---

## 🧾 Overview

This project addresses inefficiencies in static parking pricing by implementing a real-time dynamic pricing engine for urban lots. Using data from 14 parking spaces over 73 days, we simulate intelligent price adjustments based on occupancy, traffic, vehicle type, and proximity to competitors — all in real time using the Pathway platform.

We developed three models of increasing intelligence:

1. **Model 1:** Linear pricing based on occupancy
2. **Model 2:** Weighted demand-based pricing
3. **Model 3:** Competitive pricing with rerouting logic based on nearby lot conditions

---

## ⚙️ Tech Stack

| Component     | Tool                          |
| ------------- | ----------------------------- |
| Language      | Python (3.11+)                |
| Libraries     | pandas, numpy, pathway, bokeh |
| Platform      | Google Colab                  |
| Visualization | Bokeh                         |
| Data Format   | CSV, JSONL                    |

---

## 🏗 Architecture Diagram

You may add a diagram using Mermaid (optional), or upload a `.png` version.
Example (in Mermaid syntax if using markdown viewer):

```
flowchart TD
    A[CSV: dataset.csv] --> B[Pathway Ingestion]
    B --> C[Model 1: Baseline]
    B --> D[Model 2: Demand-Based]
    B --> E[Model 3: Competitive Pricing]
    C --> F[Final Output (JSONL)]
    D --> F
    E --> F --> G[Bokeh Real-Time Visualization]
```

---

## 📂 Repository Contents

| File/Folder             | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| `final_notebook.ipynb`  | Single notebook implementing Models 1–3 and visualization |
| `data/dataset.csv`      | Raw dataset of 14 parking lots                            |
| `output/bokeh_plot.png` | Screenshot of real-time Bokeh chart                       |
| `requirements.txt`      | Python dependencies                                       |
| `capstone_report.pdf`   | (Optional) Final project report                           |
| `README.md`             | Project overview (this file)                              |

---

## 🔁 Project Workflow

1. Load and explore the dataset
2. Build models:

   * Model 1: Linear price based on occupancy ratio
   * Model 2: Weighted demand score (traffic, queue, vehicle type) → normalized
   * Model 3: Add Haversine distance logic for competitor influence and rerouting
3. Simulate real-time data with Pathway
4. Output results to JSONL
5. Visualize with Bokeh

---

## 🧠 Demand Function

The demand score is calculated as:

Demand = α · (Occupancy / Capacity) + β · QueueLength + γ · TrafficLevel + δ · SpecialDay + ε · VehicleTypeWeight

Prices are then computed as:

Price = BasePrice · (1 + λ · NormalizedDemand)

Prices are bounded between `$5.00` and `$20.00` to avoid erratic jumps.

---

## 🔍 Rerouting Logic (Model 3)

* Compute distances between parking lots using the Haversine formula
* If a lot is 95% full and nearby lots are cheaper and available → set `reroute = 1` and lower the price
* Otherwise, adjust price up or down based on competitor pricing

---

## 📊 Bokeh Visualization

We plotted `final_price` vs `time` for top 5 lots using interactive Bokeh plots.
The chart includes:

* Hover tool showing lot ID, timestamp, final price, reroute flag
* Toggleable legend
* Real-time trends that show the system's responsiveness

You can find the screenshot in:
`output/bokeh_plot.png`

---

## 📄 Report (Optional)

See `capstone_report.pdf` for:

* Project motivation
* Dataset structure
* Full demand function explanation
* Screenshots & analysis
* Summary of rerouting impact and pricing stability

---

## 🛠 Setup Instructions

To install dependencies:

```
pip install pandas numpy bokeh pathway
```

Run the notebook:

* Open `final_notebook.ipynb` in Google Colab
* Upload `dataset.csv` in the `/data` folder
* Run all cells in order

---

## ✅ Submission Summary

| Item                         | Status                            |
| ---------------------------- | --------------------------------- |
| Model 1: Linear pricing      | ✅ Implemented                     |
| Model 2: Demand-based        | ✅ Normalized demand score         |
| Model 3: Competitive pricing | ✅ With rerouting                  |
| Real-time simulation         | ✅ Done via Pathway                |
| Visualization                | ✅ Bokeh + PNG output              |
| Documentation                | ✅ This README + Report (optional) |
| Repo Access                  | ✅ Public                          |

---

## 🙌 Acknowledgements

* Consulting & Analytics Club, IIT Guwahati
* Pathway AI – for real-time infrastructure
* Summer Analytics Mentors & Peers – for support and review

---

**Made with 🧠, ☕, and 🕓 by Titus Yankson – Summer Analytics 2025**

---

