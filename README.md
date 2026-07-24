# Operational Diagnostics: Regional Depot Throughput & Root Cause Analysis

An operational diagnostic project investigating a sudden throughput drop across regional distribution depots in 2026. This analysis verifies data quality, quantifies the volume drop, and isolates the root cause to deliver data-backed recommendations for the Operations Director.

---

## Workspace File Structure

* **[Mystery_Ops.csv](file:///c:/Users/USER/Desktop/Inuka_PLP_Projects/Week5_Assignment/Mystery_Ops.csv):** The raw dataset containing 2,920 records of shift-depot operational metrics (record ID, date, depot, shift, operator, machine, throughput, temperature, maintenance status, voltage, and incident type).
* **[week5_diagnostics_analysis.ipynb](file:///c:/Users/USER/Desktop/Inuka_PLP_Projects/Week5_Assignment/week5_diagnostics_analysis.ipynb):** The complete exploratory data analysis (EDA) and root cause analysis Jupyter Notebook. Fully commented, refactored, and executed with embedded visualizations.
* **[Week5_Diagnostics_Report.pdf](file:///c:/Users/USER/Desktop/Inuka_PLP_Projects/Week5_Assignment/Week5_Diagnostics_Report_Antigravity.pdf):** An executive-level PDF report summarizing the operational context, root cause insights, and actionable recommendations for the Operations Director.
* **[README.md](file:///c:/Users/USER/Desktop/Inuka_PLP_Projects/Week5_Assignment/README.md):** This readme index file.

---

## Executive Summary of Findings

### 1. The Operational Problem (Context)

* Starting **February 1, 2026**, corporate throughput experienced a severe drop.
* Data profiling shows the problem is strictly localized: Eldoret (-0.63%), Kisumu (-0.17%), and Mombasa (-0.98%) remained stable, while the **Nairobi depot** saw a **34.4% drop** (from 1,052.52 to 690.56 barrels per shift).
* **Pareto analysis** confirms **Nairobi explains 95.33% of all lost corporate throughput** (241,789 barrels out of 253,632 lost globally).

### 2. The Identified Root Cause (Insight)

* **Rotation Shift:** Nairobi abandoned its balanced machine rotation policy after Feb 1st, running machine **NBI-P03 on 81.6% of all shifts** (545 shifts).
* **Deferred Maintenance:** Machine `NBI-P03` was run continuously under deferred maintenance (`maintenance_flag = 1`), causing its average output to drop from **1,027.69 to 617.91 barrels per shift** (a loss of **409.78 barrels per shift**).
* **Statistical Proof:** The correlation between throughput and the maintenance flag in Nairobi is **-0.917** (explaining 84.1% of throughput variance). Other potential drivers (weather, voltage drops, shift times, operator performance) were statistically ruled out.
* This single maintenance failure explains **88.0% of the entire company's throughput loss**.

### 3. Actionable Recommendations (Action)

1. **Immediate Maintenance Intervention:** Take machine `NBI-P03` offline immediately for a full maintenance cycle to recover **~410 barrels per shift** (+66% increase).
2. **Restore Balanced Machine Rotation:** Rotate shifts evenly across NBI-P01, NBI-P02, and NBI-P04 while NBI-P03 is serviced to immediately restore Nairobi's throughput to **>1,020 barrels per shift**.
3. **Implement Automated Maintenance Interlocks:** Update the operational software to restrict any machine from running more than 10 consecutive shifts with a pending maintenance flag.

---

## How to Run the Analysis

### Requirements

Ensure you have Python installed with the following packages:

```bash
pip install pandas numpy matplotlib seaborn scipy reportlab
```

### Steps

1. **Jupyter Notebook:** Open `week5_diagnostics_analysis.ipynb` in VS Code or Jupyter Lab. All cells have been pre-run, showing the text summaries, data tables, and five custom plots.
2. **Executive Report:** Open `Week5_Diagnostics_Report_Antigravity.pdf` to read the concise executive summary with embedded charts.
