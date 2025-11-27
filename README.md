# 🚐 Patient Pickup Timing Analysis — CareMax Capstone Project
This project analyzes patient transportation logs from the December 2023 dataset to measure **how early pickups are performed before scheduled appointments**.  
Time differences between `Required Pickup` and `Appointment Time` are calculated in minutes, grouped into **10-minute intervals (0–210 min)**, and visualized using a **histogram with Pareto cumulative trend** in R.

### 🎯 Project Focus
- Validate whether pickups occur **≤ 60 minutes before appointment**.
- Identify time intervals with the highest frequency of early pickups.
- Support route optimization using data insights to improve timeliness and service level compliance.

### 📊 Key Insight From the Report
- ~24.14% of trips violate the “1 hour before appointment” pickup constraint.
- Analysis is performed locally in R using `ggplot2` visuals.

### 🛠 How to Run Locally (R)
```r
install.packages(c("ggplot2","scales"))
library(ggplot2)
library(scales)
df <- read.csv("all_data1.csv")
source("rcodechartvans.R")
