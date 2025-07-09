# Dynamic-Pricing-Model-For-Urban-Parking-Lots

Dynamic Pricing for Urban Parking Lots
Capstone Project | Summer Analytics 2025
Hosted by Consulting & Analytics Club, IIT Guwahati × Pathway

-----------------------------------------------------------------------
Overview
-----------------------------------------------------------------------
This project implements a real-time dynamic pricing engine for 14 urban parking lots using a simulated data stream. It predicts optimal parking prices based on occupancy, traffic, vehicle type, queue length, and competition, using three progressively advanced models. The system is built using Pathway, a Python framework for real-time data pipelines.

-----------------------------------------------------------------------
Assumptions
-----------------------------------------------------------------------
- Data is simulated from 14 parking lots using dataset.csv.
- Demand is influenced by occupancy, queue length, traffic condition, vehicle type, and special day flags.
- Price is constrained between INR 5.0 and INR 20.0.
- The pipeline uses daily tumbling windows for time aggregation.
- Data is streamed using pathway.demo.replay_csv.

-----------------------------------------------------------------------
Tech Stack
-----------------------------------------------------------------------
Language       : Python 3.11+
Streaming Tool : Pathway
Visualization  : Bokeh + Panel
Data Handling  : Pandas, NumPy

-----------------------------------------------------------------------
Project Flow
-----------------------------------------------------------------------
1. Data Loading & Preprocessing
   - Combines date and time columns into a unified timestamp.
   - Prepares parking_stream.csv for streaming.

2. Streaming Simulation with Pathway
   - Loads data using a simulated real-time stream.
   - Parses timestamps and applies daily tumbling windows.

3. Pricing Models
   - Model 1 (Baseline Linear): Based on occupancy delta.
   - Model 2 (Demand-Based): Adds queue length, vehicle type, traffic, and day type.

4. Visualization
   - Live Bokeh plots served through Panel showing pricing models over time.

5. Execution
   - The pipeline is activated via pw.run().
-----------------------------------------------------------------------
Demand Function
-----------------------------------------------------------------------
The demand function in this model is an empirical score based on the following inputs:

demand = α * occupancy_rate + β * queue_length + γ * traffic_level
         + δ * is_special_day + ε * vehicle_type_weight
         
Each component reflects real-world influence on user behavior:
1.Occupancy rate captures urgency
2.Queue length signals waiting time
3.Traffic level indicates external congestion
4.Special days tend to attract more cars
5.Vehicle type reflects space usage and urgency
--------------------------------------------------------------------------
Pricing Logic
--------------------------------------------------------------------------
Model 1 (Baseline):
Adjusts price linearly as:
price = base + 0.5 × (occupancy_rate - 0.5)

Model 2 (Demand-Based):
Computes a normalized demand score and scales price accordingly. Prices are clipped between ₹5 and ₹20.

--------------------------------------------------------------------------
Justification for Steps
--------------------------------------------------------------------------
1.Tumbling windows were used to ensure pricing stability within a day.
2.Pathway enables reactive, fault-tolerant streaming suitable for real-time deployment.
3.Using Bokeh + Panel allows continuous visual tracking of pricing evolution.

-----------------------------------------------------------------------
Installation
-----------------------------------------------------------------------
1. Clone the Repository:
   git clone https://github.com/yourusername/urban-parking-pricing.git
   cd urban-parking-pricing

2. Install Required Packages:
   pip install pathway pandas numpy panel bokeh

3. Upload the Dataset:
   Ensure dataset.csv is present in the root directory.

-----------------------------------------------------------------------
How to Run
-----------------------------------------------------------------------
- Open final_submission.ipynb using Jupyter Notebook or Google Colab.
- Upload dataset.csv to your environment.
- Run all cells (Restart & Run All).
- Visualizations and dynamic pricing logic will be displayed.

-----------------------------------------------------------------------
File Structure
-----------------------------------------------------------------------
urban-parking-pricing/
├── Final.ipynb      (Final notebook)
├── dataset.csv      (Parking data stream)
├── README.txt       (This file)

-----------------------------------------------------------------------
Contributors
-----------------------------------------------------------------------
Rahul Kumar

Project mentored and hosted by:
Consulting & Analytics Club – IIT Guwahati
Powered by Pathway
