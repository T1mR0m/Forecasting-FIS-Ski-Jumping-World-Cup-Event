# Forecasting-FIS-Ski-Jumping-World-Cup-Event

## Overview

This project forecasts **Top 5 placements** in a **FIS Ski Jumping World Cup** event held in Engelberg on December 21, 2025, using historical competition data and a **logistic 
regression model**.
The goal is to estimate the probability that an athlete finishes within the Top 5 of a given competition.

## Data
* **Source**: Official FIS Ski Jumping World Cup results (seasons 2022–2025)
* **Format**: Original data published as PDFs
* **Processing**:
  * PDFs converted to CSV
  * Manual cleaning performed to ensure consistency across seasons
  * All feature engineering strictly avoids data leakage

## Feature Engineering
### Model Features
* **Prev_Elo**
  
  A lagged Elo-like rating capturing the jumper's competitive strength, updated after each competition and shifted by one event.
* **Top5_Rate_3**
  
  The rolling average share of Top-5 finishes over the previous three competitions.
* **Std_Rank_3**
  
  The rolling standard deviation of finishing positions over the previous three competitions, measuring performance volatility.
* **Rank_Trend_3**
  
  A short-term performance trend computed from changes in finishing positions over the previous three competitions.
### Target Variable
* **Top5**
  
  Binary variables which indicates whether competitor's finish rank is between 1 and 5.

## Feature Selection
Features were selected based on:
* **Variance Inflation Facor (IVF)** to address multicollinearity.
* **Correlation** with the target variable.
* **Mutual information** (classification).

## Forecasted Top 5 (Engelberg, Dec 21, 2025)
1) PREVC Domen
2) NIKAIDO Ren
3) KOBAYASHI Ryoyu
4) RAIMUND Philipp
5) FOUBERT Valentin 

## Actual Results
1) KOBAYASHI Ryoyu
2) PREVC Domen
3) HOFFMAN Felix
4) RAIMUND Philipp
5) TOMASIAK Kacper

## Performance Summary
* **3 out of 5 athletes** were correctly classified to Top 5 placements.
* **1 athlete’s exact placement** within the Top 5 was correctly predicted.

## Notes and Limitations
* Small sample sizes per event limit predictive certainty.
* External factors (weather, wind conditions, equipment) are not modeled.
* Only 1 model (Logistic Regression) used in forecasting.




