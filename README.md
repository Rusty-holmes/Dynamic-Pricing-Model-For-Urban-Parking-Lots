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
├── parking_stream.csv  (modified data frame for realtime streaming)
├── README.txt       (This file)

-----------------------------------------------------------------------
Contributors
-----------------------------------------------------------------------
Rahul Kumar

Project mentored and hosted by:
Consulting & Analytics Club – IIT Guwahati
Powered by Pathway
