# mlb-player-valuation
MLB Player WAR Projection & Valuation System
A full predictive modeling pipeline for predicting player WAR and estimating dollar value for roster construction and contract evaluation.

Overview:
This project builds a complete MLB player valuation system using multi-year Statcast and Fangraphs data. It predicts future WAR using a non-linear machine learning model, applies aging curve adjustments, and converts projected WAR into estimated dollar value and surplus value. The system also includes an interactive player lookup tool for quick valuation queries.
This project demonstrates skills in predictive modeling, feature engineering, baseball analytics, and practical decision-support tool design.

Key Features
  Multi-Year Data Pipeline
    Automated ingestion of MLB batting data (2018-2025)
    Cleaning, merging, and feature alignment
    Construction of an aging curve based on year-to-year WAR deltas
  Advanced Feature Engineering
    Includes both traditional and Statcast-driven metrics:
      ISO
      HR_rate
      wRC+
      wOBA
      BABIP
      HardHit%
      Barrel%
      Aging_Adjustment
    Non-Linear WAR Projection Model
      Gradient Boosting Regressor for realistic, non-extrapolated predictions
      Train/test split with performance reporting
      Avoids linear over-projection for elite players
    Player Valuation Engine
      Converts projected WAR to dollar value using customizable dollar per WAR
      Computes surplus value when salary is provided 
      Supports interactive user input
    Interactive Player Lookup
      Users can enter a player name (and optional salary) to receive:
        Projected WAR
        Estimated dollar value
        Surplus value
        Clean, readable output
        
Visualizations
  Aging Curve Visualization (WAR Delta by Age)
  This plot illustrates the average year-to-year change in WAR by player age, derived from multi-season MLB data (2018-2023).  The curve captures the typical
  developmental arc of hitters: modest gains in the early 20s, peak performance around ages 26-28, and gradual decline into the 30’s.  This aging adjustment is 
  incorporated directly into the projection model to improve realism and prevent over-estimation of late-career performance. 
  
  Actual v. Predicted WAR (Test Set Calibration)
  This scatterplot compares predicted WAR values to actual WAR outcomes on the test set.  The close clustering around the diagonal reference line indicates strong
  model calibration and generalization.  This validation step confirms that the model captures meaningful performance patterns without overfitting, providing    
  confidence in its use for forward-looking player valuation.

