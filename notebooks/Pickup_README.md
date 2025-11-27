# 📓 Pickup Timing Analysis Notebook

This Jupyter notebook analyzes how early patients are picked up before their scheduled medical appointments.  
It computes time differences in **minutes**, groups trips into **10-minute intervals (0–210 min)**, flags **pickups >60 minutes early**, and visualizes distributions using Pareto-style histograms in R.

### 🎯 Purpose
- Evaluate **pickup-timing compliance** (no pickups more than 1 hour before appointment)
- Identify peak early-pickup intervals that affect patient timeliness
- Support route optimization using data-driven insights

### 📊 Conclusions from Report Data
From our capstone R analysis comparing required vs actual pickup times:

- **24.14% of trips** violated the constraint of being picked up **≤1 hour before appointment**
- **15.65% of trips** exceeded the travel-time limit of **≤1 hour in vehicle**
- Manual dispatching was identified as inefficient, taking ~**20 min/day per driver**
- Optimization features could reduce annual labor cost significantly when implemented with batch scheduling and zip-group routing

### ✅ Run the Notebook Locally
To execute this notebook, open it using an R-enabled Jupyter runtime:

- Local Jupyter + R kernel using `ir` (installed via **IRkernel**)  
  VE but not executable here interactively.

```r
install.packages('IRkernel')
IRkernel::installspec(name = "ir", displayname = "R")
