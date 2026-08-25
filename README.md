# household-consumption-elasticity-causalml
Estimating heterogeneous price elasticities of demand and welfare impacts using TURKSTAT HBA data via DML-IV (EconML)

# Household Consumption Elasticity: Causal Machine Learning with DML-IV

[![Status](https://img.shields.io/badge/Status-Work%20in%20Progress-yellow)](#)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](#)
[![Methodology](https://img.shields.io/badge/Method-DML--IV%20%7C%20Nonparametric%20IV-green)](#)

## Overview
This project estimates the heterogeneous price elasticities of demand and welfare impacts of energy and food price shocks across Turkish households using the **TURKSTAT Household Budget Survey (HBA)** microdata.

To address price endogeneity in micro-level consumption decisions (e.g., quality sorting and local demand shocks), we implement **Double Machine Learning for Instrumental Variables (DML-IV)** via `EconML`, nonparametrically conditioning on high-dimensional household characteristics.

## Identification Strategy
* **Outcome ($Y$):** Budget share ($w_i$) or log expenditure on targeted consumption items.
* **Treatment ($T$):** Household-level unit values / local price index ($P_i$).
* **Instrument ($Z$):** Regional wholesale price shocks and spatial leave-out price instruments.
* **Controls ($X$):** Household demographics, income deciles, dwelling characteristics, and NUTS regional fixed effects.

## Project Structure
```text
├── data/                # Data directory (raw microdata untracked per license)
├── sql/                 # DuckDB/SQL queries for unit value calculation
├── notebooks/           # Exploratory analysis, DAG design & visual outputs
├── src/                 # Estimation scripts (DML-IV, refutation routines)
├── tests/               # Sensitivity checks and placebo tests
└── README.md
