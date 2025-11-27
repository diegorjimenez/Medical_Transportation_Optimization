# 📓 Trip Duration Analysis Notebook

This notebook computes the **trip duration (Pickup → Dropoff)** for patient transportation records and visualizes the distribution using a histogram with a secondary **cumulative Pareto percentage axis**, using R’s `ggplot2` plotting system.

### 🎯 Purpose
- Measure time spent in vehicle per patient trip
- Identify duration clusters that exceed the 1-hour travel limit
- Support conclusions about fleet optimization quality of service

### 📊 Key Report Findings Reflected in This Analysis
- **15.65% of trips** lasted **>60 minutes in vehicle**, violating CareMax’s service constraint
- **24.14% of pickups** occurred **>60 minutes before appointment**, showing major drift from intended pickup deadlines
- The combination of **zip code groups + vehicle groups + batch scheduling** is expected to improve routing filters, system responsiveness, and reduce timeliness violations

### ✅ Run the Notebook Locally
To execute the notebook, load the required R visualization packages:

```r
install.packages(c("ggplot2","scales"))
library(ggplot2)
library(scales)
source("Capstone_Pickup_Time.ipynb")
```

The notebook is designed to run in:
- A Jupyter environment with `ir` kernel (**IRKernel / IRkernel**)
- Google Colab with R runtime support

---

### 📈 Cumulative % Insight
The Pareto axis visually confirms that **early pickups and long trip durations accumulate into significant service-level noncompliance**, reinforcing the need for software-based route optimization rather than fully manual dispatching.

---
