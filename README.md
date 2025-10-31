🧾 [DA5401] DA Lab – Assignment 7 – Multi-Class Model Selection using ROC and Precision-Recall Curves

Name: Jigarahemad K Shaikh  Roll Number: DA25M014

📂 File Required for Evaluation – DA5401_DA25M014_Assignment_7.ipynb

Title: Model Selection in Multi-Class Classification using ROC and PRC Analysis

This notebook evaluates multiple classification algorithms using macro-averaged ROC-AUC and Precision–Recall (PRC) Average Precision (AP) metrics on a six-class satellite dataset.
It demonstrates advanced evaluation, visualization, and interpretation techniques for model comparison, culminating in a recommendation of the most balanced classifier.


⚙️ Libraries Used

pandas, numpy — data handling & numerical computation

matplotlib (pyplot, patches, colors) — custom multi-class ROC/PRC plots

seaborn — color-blind-friendly visualizations

scikit-learn — model training & metrics

Models: KNeighborsClassifier, DecisionTreeClassifier, LogisticRegression, GaussianNB, SVC, RandomForestClassifier, XGBClassifier, DummyClassifier

Metrics: roc_auc_score, average_precision_score, classification_report, precision_recall_curve

StandardScaler, train_test_split — feature scaling & dataset splitting

warnings, itertools, matplotlib.cm — utilities for presentation and color management


🎨 Color Palettes & Colormaps

Palettes: colorblind, Set2, Spectral, husl, Paul Tol TOL Colors

Colormaps: YlGnBu, PuBuGn, viridis, coolwarm

Accessibility: All plots use pattern fills and legible legends for color-blind safety and high contrast.



🧠 Assignment Overview

This assignment investigates the evaluation of multi-class models using threshold-independent metrics.
It highlights how ROC curves and Precision–Recall curves complement each other, especially in imbalanced data scenarios.

Six baseline models + two ensemble models (RandomForest, XGBoost) are trained and analyzed to understand their ranking power and precision–recall trade-offs.


🔧 Workflow Summary

Part A – Data Preparation & Baseline

Imported multi-class dataset and standardized features using StandardScaler.

Implemented baseline models (KNN, Decision Tree, SVM, Naive Bayes, Logistic Regression, Dummy).

Computed Accuracy and Weighted F1 to establish initial ranking.

✅ KNN and SVM emerged as early leaders.

Part B – ROC Curve Analysis

Computed macro-averaged ROC-AUC via OvR (one-vs-rest) scheme.

Plotted multi-class ROC curves with AUC labels for each model.

Ensembles (RandomForest, XGBoost) recorded outstanding scores:

RandomForest AUC = 0.9901 | AP = 0.9518

XGBoost AUC = 0.9903 | AP = 0.9527

Added an Inverted RandomForest variant to illustrate AUC < 0.5 (≈ 0.0099), demonstrating the effect of reversed ranking.

🧩 Insight: Both ensembles outperform linear and probabilistic models in ranking and discrimination capability.

Part C – Precision–Recall ( PRC ) Analysis

Computed macro-average Average Precision (AP) for each model.

Generated color-coded PRC plots with area fill representing precision stability.

Top models (by macro AP):

🥇 KNN ( 0.9217 )

🥈 SVM ( 0.9177 )

🥉 Logistic Regression ( 0.8116 )

Interpreted behavior under high-recall regions and linked precision drops to false-positive explosions.

Discussed the limitation of ROC when TN dominates and PRC’s relevance in imbalanced contexts.

Part D – Model Recommendation & Interpretation

Metric	Best Model	Score	Interpretation
F1 (Weighted)	KNN	0.9037	Balanced precision & recall
ROC-AUC (Macro)	SVM	0.9852	Excellent discrimination
PRC-AP (Macro)	KNN	0.9217	Stable precision across thresholds
Accuracy	KNN	0.9045	Most reliable overall

💡 Final Choice: K-Nearest Neighbors (k = 5) offers the best harmonized performance across all metrics.
It is robust, interpretable, and maintains high precision even at higher recall.


Brownie Points – Extended Experiments

Added RandomForest and XGBoost ensembles to contrast bagging vs boosting behaviors.

Introduced Inverted RandomForest (AUC < 0.5) to illustrate negative ranking concept.

Designed HTML-styled summary tables for visual clarity and color-blind accessibility.

🧩 Outcome: Both ensembles achieved AUC ≈ 0.99 and macro-AP ≈ 0.95, proving ensemble methods’ superiority for complex decision boundaries.

⚖️ Key Comparative Insights

Aspect	ROC-AUC	PRC-AP	Best Model
Ranking Power	Excellent for RF & XGB	Consistent	XGBoost
Precision Stability	Sensitive to imbalance	PRC reveals true reliability	KNN
Generalization	High AUC ≈ 0.99	High AP ≈ 0.95	RandomForest
Interpretability	Moderate	Good	KNN / LogReg

🧭 Recommended Strategy

KNN (k = 5) for balanced use cases where precision and recall both matter.
SVM (RBF) for recall-critical tasks.
RandomForest / XGBoost for production deployment requiring calibrated probabilities and high ranking quality.

💡 Insights & Conclusion

ROC and PRC together provide a multi-dimensional view of classifier behavior.

ROC may look optimistic under imbalance; PRC reveals true positive precision.

Ensemble models achieve near-perfect AUC/AP but at higher computational cost.

KNN strikes the most balanced trade-off between interpretability and performance.

📘 Core Takeaway: Precision without context can mislead — balanced ROC and PRC evaluation is the gold standard for multi-class model selection.

🧭 Summary (High-Level)

Section	Focus	Outcome
Part A	Data Preparation & Baseline	6 models evaluated on accuracy & F1
Part B	ROC Analysis	RF & XGB lead with AUC ≈ 0.99
Part C	PRC Analysis	KNN & SVM top macro AP ≈ 0.92
Part D	Recommendation	KNN final choice (robust & interpretable)
Bonus	Ensemble & Inversion	Demonstrated AUC < 0.5 concept


🧩 Final Takeaway

“ROC tells how well you rank classes; PRC tells how well you believe your positives.”
Evaluating both ensures scientific and ethical model selection — balancing sensitivity, specificity, and trustworthiness in data-driven decisions.

Date: 31/Oct/2025
