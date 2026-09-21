# Smart Electricity Meter Anomaly Detection

A machine learning framework designed to detect non-technical losses, revenue fraud, and meter malfunctions in smart power grids using high-frequency time-series data.

---

## Executive Summary

Power utilities face substantial financial losses due to Unaccounted-for Energy (UFE), driven by non-technical issues such as physical meter tampering, illegal line connections, stuck meters, and sensor calibration drift.

Standard unsupervised methods like generic Isolation Forests often fail on subtle physical failures and structured time-series patterns. This project implements a Combined System Architecture that dramatically increases detection sensitivity across critical failure modes:

* **Meter Tampering:** Achieves ~98% recall (up from ~85% with standard methods).
* **Stuck Meters:** Solves a major baseline blind spot, raising recall from <1% to ~80%.
* **Calibration Drift:** Doubles detection efficacy on degrading hardware (~32% vs. ~16%).
* **Illegal Connections:** Maintains reliable high-baseline detection (80% recall).

---

## Key Features

* **Advanced Feature Engineering:** Computes rolling statistics (`rolling_mean_48`, `rolling_std_24`), hourly/day-of-week seasonality metrics, baseline deviations, and weather interactions (`Temperature_C`, `Humidity_pct`).
* **Multi-Class Anomaly Taxonomy:** Categorizes readings into explicit fault categories rather than simple binary flags:
  * Normal Baseline (`None`)
  * Meter Tampering
  * Calibration Drift
  * Illegal Connection
  * Stuck Meter
* **Operational Triage Dashboard:** Direct integration mapping flags to specific Meter IDs (`SB01`, `RH03`, `SB02`) to auto-prioritize physical field audits and hardware maintenance.

---
