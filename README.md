# Medical Transportation Optimization - Capstone Project
### Authors: Esther Cusnir, Cage LeBlanc, Diego Jimenez
This capstone project, conducted with the CareMax transportation department, focuses on optimizing **non-emergency patient transportation routing and timeliness compliance**.  
Using R in Jupyter, we created two analytical notebooks that process trip logs from **October–December 2023** to evaluate operational constraints and routing inefficiencies.

---

## Notebook Summaries

### **1. Pickup Timing Analysis (`Pickup_Time.ipynb`)**
- Calculates how early each patient was picked up before their scheduled appointment.
- Converts time difference from **seconds → minutes**, preserving NAs.
- Groups results into **10-minute intervals (0–210 min)**.
- Flags trips where pickup occurred **>60 minutes early** (constraint violation).
- Visualizes frequency with histogram bars and **Pareto cumulative trend** in `ggplot2` (R kernel).

### **2. Trip Duration Analysis (`Trip_duration.ipynb`)**
- Computes trip duration by subtracting **Pickup.Perform → Dropoff.Perform**.
- Converts total trip time into **minutes**.
- Removes invalid or NA time differences.
- Bins trip durations into **10-minute labeled intervals**.
- Plots histogram bars with secondary axis showing **cumulative percentage distribution (Pareto view)**.

---

## Overall Project Findings (from report)
- **24.14% of trips** were scheduled with pickup times **>1 hour before appointment**, violating CareMax’s constraint.  
- **15.65% of trips** exceeded the **1-hour in-vehicle limit**.
- Routing and scheduling were highly **manual and non-filtered across regions**, causing optimization challenges.
- Using **MediRoutes features** like **zip code and vehicle groups** and **batch scheduling** could significantly improve routing, system speed, and labor efficiency.

---

## Key Recommendations Supported by Notebooks
- Implement **zip-group routing and vehicle grouping** to filter regions.
- Adopt **batch scheduling with violation parameters** to automatically enforce timing constraints.
- Train dispatch staff to use new features effectively.
- Explore contract renegotiation of outsourced ride terms based on evidence-driven timeliness improvement goals.

---

## Project Goal Achievements
- Identified major bottlenecks in **routing filters**, **pickup timing compliance**, and **labor-heavy scheduling**.
- Validated conclusions using **real trip logs**, properly sectioned for reproducibility in R + Jupyter.
- Created interval-based visualizations to highlight **pickup drift and cumulative timing inefficiencies**.
- Extended problem statements when scope changed, ensuring ethical use despite accessing non-NDA-protected internal data.

---

## Final Conclusion

CareMax’s current routing system suffers from **lack of regional filtering, late optimization, and excessive early pickups** that violate appointment timing constraints.  
Through local R analysis, we demonstrated that **nearly 1 in 4 pickups occur too early, and 1 in 6 trips are too long**, creating measurable noncompliance that impacts patient satisfaction.

By enabling **zip code groups + vehicle groups + batch scheduling constraints**, the company can:

- **Reduce manual scheduling overhead**
- **Increase system responsiveness for dispatch staff**
- **Improve routing and service-constraint compliance**
- **Strengthen customer satisfaction through better timely pickups**
- **Lower operational cancellation and labor coordination costs**

> These notebooks collectively support one core truth:  
> **Route optimization software must replace a fully manual dispatching dependency if CareMax wants to meet their promised service level of picking patients up at most 1 hour before their appointment while minimizing travel time.**

---

For any questions or improvement ideas, please refer to the notebook logic or contact the capstone team for clarification.

```r
install.packages(c("ggplot2","scales"))
library(ggplot2)
library(scales)
df <- read.csv("all_data1.csv")




