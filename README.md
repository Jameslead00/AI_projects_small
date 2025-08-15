# AI_projects_small
This repo holds Jupyter notebooks and relevant files for a few small AI projects completed by me.

# AI Fairness Case Study Notebook
This notebook demonstrates a full workflow for building, evaluating, and auditing a predictive model for fairness using US Census employment data. The project is designed for transparency and reproducibility, and covers the following tasks:

## Structure
1. Data Preparation

- Downloaded ACS employment data via folktables.
- Filtered for working-age adults (25–65) and selected Black and White racial groups.
  
2. Model Training
- Built a logistic regression pipeline with feature scaling.
- Split data into training and test sets, trained the model, and exported raw data for reproducibility.

3. Model Performance & Calibration
- Evaluated accuracy and generated a calibration plot with confidence intervals.
- Binned predicted probabilities and compared observed reemployment rates to assess model reliability.

4. Group-wise Analysis
- Compared score distributions and performance metrics (accuracy, precision, recall, F1) for Black and White job seekers.
- Assessed calibration for each group and performed statistical tests for differences in reemployment rates per score bin.
- Calculated fairness metrics (base rate, positive rate, TPR, FNR, FPR, TNR) and tested for significant group differences.

5. Decision-Maker Utility & Threshold Optimization
- Defined a utility matrix representing costs for different decisions (coaching vs. no coaching).
- Searched for the optimal decision threshold to maximize agency utility, compared it to the default threshold, and quantified improvement.

6. Fairness Criterion (Moral Analysis)
- Checked for fairness by comparing the fraction of individuals in each group who received coaching and found employment.
- Used a two-proportion z-test to assess statistical significance of group differences.

7. Trade-off Analysis & FairnessLab Export
- Explored the trade-off between maximizing utility and satisfying fairness constraints.
- Exported results (scores, decisions, sensitive attribute, ground truth) to CSV for further analysis in FairnessLab.

8. Deployment Evaluation
- Applied the trained model to data from four years later to simulate real-world deployment.
- Re-evaluated performance, calibration, group metrics, and fairness criteria on new data.
- Exported deployment results for reproducibility and external fairness analysis.
