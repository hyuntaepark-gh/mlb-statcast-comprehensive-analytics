# ⚾ MLB Statcast: Comprehensive Baseball Analytics & Predictive Modeling

![Python](https://img.shields.io/badge/Python-Data%20Analysis-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?logo=scikitlearn&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-Statistical%20Modeling-4B8BBE)
![R](https://img.shields.io/badge/R-Statistical%20Analysis-276DC3?logo=r&logoColor=white)
![Statcast](https://img.shields.io/badge/MLB-Statcast%20Analytics-002D72)
![Predictive Analytics](https://img.shields.io/badge/Predictive-Analytics-00897B)

This project examines **MLB pitching, hitting, pitch selection, and player performance** using pitch-level Statcast data from selected observation windows between 2015 and 2026.

The analysis investigates how pitch characteristics, hitter decisions, contact quality, game situations, and player matchups relate to observed baseball outcomes.

Beyond exploratory data analysis, the project integrates statistical inference, longitudinal comparisons, machine learning, probability calibration, and model validation. It also examines data completeness, measurement changes, sample selection, and uncertainty to evaluate the reliability of the findings.

The project combines a detailed 2024–2025 analysis with historical comparisons covering twelve annual observation windows from 2015 through 2026.

---

## 🔍 Project Overview

### Objective

- Analyze pitch characteristics, movement, velocity, spin rate, and repertoire composition.
- Evaluate hitter plate discipline, swing decisions, contact quality, and pitch-type weaknesses.
- Examine how pitch outcomes vary across counts, handedness matchups, and game situations.
- Compare observed pitching and hitting patterns across historical Statcast observation windows.
- Develop statistical and machine learning models for pitch-level outcomes.
- Assess prediction reliability, data quality, measurement consistency, and statistical uncertainty.

### Key Questions

1. How do pitch velocity, spin rate, movement, and repertoire composition relate to pitching effectiveness?
2. How do hitters respond to different pitch types, locations, counts, and pitcher-handedness matchups?
3. What distinguishes hard-hit contact from other batted-ball outcomes?
4. How do observed pitching and hitting patterns differ across the 2015–2026 observation windows?
5. Can statistical and machine learning models estimate pitch-level swing and whiff probabilities?
6. How stable are model predictions across seasons, pitch types, players, and data-quality conditions?

### Dataset Overview

| Dataset | Description |
|---|---|
| Data source | MLB Statcast, accessed through `pybaseball` |
| Historical analysis | 332,598 pitch records |
| Historical period | August 10–16 each year, 2015–2026 |
| Detailed analysis | 109,346 pitch records across 2024–2025 |
| Detailed analysis period | May 1–14 in 2024 and 2025 |
| Historical model training | 2020–2024 |
| Model validation | 2025 observation window |
| Exploratory evaluation | 2026 observation window |
| Main prediction target | Pitch-level whiff occurrence |

The historical analysis contains **332,598 pitches from twelve annual seven-day observation windows**. The separate 2024–2025 analysis contains **109,346 pitches across 376 games**.

These observation windows are not complete MLB seasons. Historical comparisons therefore describe the sampled periods rather than league-wide full-season trends.

The predictive analysis is retrospective and does not represent a validated real-time pitching recommendation system.

---

## 🧠 Methodology

### 1. Data Collection, Cleaning & Preparation

Pitch-level Statcast records were downloaded, cached, cleaned, and standardized for analysis.

The workflow includes:

- Downloading historical Statcast records through `pybaseball`.
- Caching downloaded data to reduce repeated requests.
- Removing duplicate pitch records and checking required identifiers.
- Standardizing dates, numerical measurements, and categorical variables.
- Creating swing, whiff, called-strike, chase, and contact-quality indicators.
- Evaluating missing values and measurement coverage across seasons.
- Separating eligible populations for pitch outcomes, swing outcomes, and tracked batted-ball events.

Metric definitions are kept consistent with their eligible populations.

For example:

- **Swing Rate:** Swings divided by eligible pitches.
- **Whiff Rate:** Swinging strikes divided by swings.
- **Whiff per Pitch:** Swinging strikes divided by eligible pitches.
- **Chase Rate:** Swings at pitches outside the strike zone divided by eligible out-of-zone pitches.
- **Hard-Hit Rate:** Tracked in-play batted-ball events with exit velocity of at least 95 mph divided by tracked in-play batted-ball events.

Missing tracking measurements are not automatically treated as negative outcomes.

### 2. Pitching Analytics & Pitch Design

The pitching analysis examines physical pitch characteristics and observed effectiveness.

The analysis includes:

- Pitch-type distribution and repertoire composition.
- Release velocity and spin-rate comparisons.
- Horizontal and vertical pitch movement.
- Pitcher-level pitch design and consistency.
- Pitch effectiveness and whiff-rate comparisons.
- Release-point variation.
- Repertoire diversity and concentration.
- Within-game workload and velocity changes.
- Pitch-to-pitch velocity and location differences.

Additional analyses investigate whether observed differences reflect changes in pitch characteristics, pitch selection, or player composition.

### 3. Hitting Analytics & Plate Discipline

Hitter analysis evaluates swing decisions and contact-related outcomes.

The analysis includes:

- Swing, chase, and whiff rates.
- Zone and out-of-zone swing behavior.
- Hitter performance by pitch type.
- Hitter–pitcher handedness matchups.
- Count-conditioned swing decisions.
- First-pitch approach.
- Hitter-specific pitch vulnerabilities.
- Contact and foul-ball outcomes.
- Empirical-Bayes adjustments for small samples.

These analyses distinguish hitter selectivity from swing-and-miss performance, since swinging more frequently and missing more frequently are different behaviors.

Player comparisons are restricted or adjusted when observed opportunity counts are insufficient.

### 4. Batted-Ball Quality & Game Context

Contact-quality analysis focuses on recorded in-play batted-ball events with the necessary tracking measurements.

The analysis includes:

- Exit velocity distributions.
- Launch-angle comparisons.
- Hard-hit rates.
- Statcast launch-category comparisons.
- Contact quality by pitch type and location.
- Count-dependent contact outcomes.
- Batted-ball quality across historical observation windows.
- Conditional exit-velocity prediction.

Situational analyses also examine:

- Ball-strike counts.
- Base occupancy and outs.
- Pitch selection by count.
- Pitch sequencing within plate appearances.
- Repeated versus changed pitch types.
- Batter–pitcher matchup context.

These relationships are observational. Pitch choices and game situations are not randomly assigned, so the results do not establish causal effects.

### 5. Historical & Longitudinal Analysis

Historical comparisons examine selected Statcast observation windows from 2015 through 2026.

The analysis includes:

- Pitch-type usage changes.
- Historical release-velocity and spin-rate patterns.
- Pitch-mix-standardized velocity comparisons.
- Repertoire composition and diversity.
- Historical hitter swing and whiff behavior.
- Matched-player comparisons.
- Contact-quality trends.
- Handedness and count-context differences.
- Tracking availability and measurement consistency.

Comparisons involving the same players or pitch types help distinguish some player-composition effects from aggregate changes.

However, player availability, opponent selection, pitch classifications, tracking technology, and the restricted observation windows limit broad historical interpretations.

### 6. Machine Learning & Predictive Modeling

Multiple classification models were evaluated for pitch-level whiff prediction.

The historical model comparison includes:

- **Dummy Classifier** — prevalence baseline.
- **Logistic Regression** — interpretable linear benchmark.
- **Random Forest** — nonlinear ensemble benchmark.
- **HistGradientBoosting** — nonlinear gradient-boosting model.

Additional experiments examine swing decisions, conditional whiff probability, hard-hit outcomes, and exit velocity.

The modeling workflow includes:

- Chronological training and validation.
- ROC-AUC and Average Precision evaluation.
- Brier Score and Log Loss.
- Probability calibration.
- Feature-set comparisons and ablation.
- Model performance across pitch types and player groups.
- Data distribution shift analysis.
- Game-cluster bootstrap uncertainty estimates.
- Retrospective probability recalibration.

The historical model uses 2020–2024 data for training, 2025 for model selection, and an already-inspected 2026 observation window for exploratory evaluation.

Some models use measured pitch velocity, movement, and location. Since these measurements are not fully available before a pitch is thrown, their performance should not be interpreted as pre-pitch operational forecasting performance.

### 7. Statistical Inference & Robustness

The project evaluates uncertainty alongside point estimates.

Methods include:

- Logistic regression.
- Statistical association tests.
- Confidence intervals.
- Bootstrap resampling.
- Game-clustered uncertainty estimation.
- Empirical-Bayes shrinkage.
- Quantile regression.
- Probability calibration.
- Model error and residual analysis.
- Subgroup reliability checks.
- Measurement and sampling sensitivity analysis.

Optional R-based analyses provide supplementary statistical modeling.

Statistical significance and predictive performance are interpreted in the context of sample size, repeated observations, measurement limitations, and observational study design.

---

## 📊 Key Insights

### 1. Pitching and Hitting Outcomes Vary Across Contexts

Pitch characteristics, pitch selection, hitter behavior, and swing-and-miss outcomes differ across pitch types, count situations, and player matchups.

These differences highlight the importance of evaluating baseball performance using multiple contextual measures rather than relying on a single overall statistic.

Aggregate comparisons can also be influenced by changes in the players, pitch types, and game situations represented in the sample.

### 2. Historical Whiff Rates Do Not Follow a Consistent Upward Trend

Observed whiff rates varied across the annual August observation windows.

| Historical Window | Whiffs per Swing |
|---|---:|
| 2015 | 21.83% |
| 2020 | 23.85% |
| 2026 | 22.20% |

The results do not show a consistently increasing whiff rate across these selected windows.

These values describe observed seven-day samples and should not be interpreted as complete-season MLB averages.

### 3. Contact Quality Requires the Correct Denominator

Hard-hit analysis was restricted to tracked in-play batted-ball events with measured exit velocity.

This distinction matters because not every pitch, swing, foul ball, or in-play event has the same contact-quality information available.

The analysis also reviews tracking coverage and missingness before interpreting historical contact-quality comparisons.

### 4. Machine Learning Models Identified Whiff Probability Differences

Historical model validation results for the 2025 observation window were:

| Model | ROC-AUC | Average Precision | Brier Score ↓ |
|---|---:|---:|---:|
| HistGradientBoosting | 0.7182 | 0.2195 | 0.0877 |
| Random Forest | 0.7169 | 0.2204 | 0.0881 |
| Logistic Regression | 0.6423 | 0.1545 | 0.0912 |
| Dummy baseline | 0.5000 | 0.1038 | 0.0931 |

HistGradientBoosting achieved the lowest Brier Score in the 2025 validation comparison.

The selected model was subsequently refitted using the available 2020–2025 modeling data.

### 5. Exploratory 2026 Evaluation Showed Improvement Over the Baseline

The previously inspected 2026 observation window produced the following results:

| Metric | HistGradientBoosting | Baseline |
|---|---:|---:|
| ROC-AUC | 0.7318 | 0.5000 |
| Average Precision | 0.2158 | 0.1050 |
| Brier Score ↓ | 0.0883 | 0.0940 |

The measured-pitch model improved Brier Score by approximately **6.1%** relative to the prevalence baseline.

A game-cluster bootstrap estimated a Brier improvement of approximately **0.00569**, with a 95% interval of **0.00348–0.00753** for the fixed predictions.

These results demonstrate predictive signal in the observed sample, but they do not establish prospective performance. The 2026 evaluation data had been reviewed during project development and are not a new independent holdout.

### 6. Prediction Reliability Depends on Available Information

The analysis compares models using different feature sets.

In the observed 2026 evaluation, a context-only model recorded a Brier Score of approximately **0.0933**, compared with **0.0883** for the model incorporating measured pitch characteristics and location.

This illustrates the predictive value of additional recorded information, while also showing why predictions made after pitch measurements are available must be distinguished from predictions made before the pitch.

The results reinforce the importance of data availability, calibration, subgroup evaluation, and validation design.

---

## 📈 Data Visualization

The executed analysis contains **162 inline image outputs**, covering pitching, hitting, contact quality, historical changes, model performance, and statistical diagnostics.

The submission package also includes **14 selected PNG figures** in the `figures/` directory.

The following figures highlight the main findings.

### 1. Historical Pitch-Type Composition

![Historical Pitch Mix](figures/pitch_mix_history.png)

This visualization compares pitch-type composition across the 2015–2026 August observation windows.

Changes in observed pitch usage may reflect strategic differences, player turnover, or changes in pitch classification.

### 2. Historical Pitch Velocity

![Historical Pitch Velocity](figures/velocity_history.png)

Historical velocity comparisons illustrate differences in observed pitch characteristics across the sampled seasons.

These results should be interpreted with consideration for pitch-type composition and changes in the observed pitcher population.

### 3. Historical Whiff Rates & Uncertainty

![Historical Whiff Rates](figures/annual_whiff_ci.png)

The figure compares observed whiff rates across historical windows and includes uncertainty intervals.

These intervals provide descriptive context but do not eliminate player-level dependence or sample-selection effects.

### 4. Batted-Ball Contact Quality

![Historical Hard-Hit Analysis](figures/hard_hit_history.png)

Hard-hit analysis compares observed contact quality across annual samples while accounting for available batted-ball tracking measurements.

The results depend on the eligible tracked batted-ball population.

### 5. Whiff Rates by Count

![Count-Conditioned Whiff Analysis](figures/count_whiff_history.png)

This visualization examines how observed swing-and-miss outcomes differ across ball-strike counts.

Count-specific comparisons help describe game-context effects but do not establish causal effects of pitch selection.

### 6. Predictive Feature Ablation

![Model Feature Ablation](figures/feature_ablation.png)

Feature ablation compares predictive performance using different groups of recorded variables.

The results help distinguish the contribution of game-context information from measured pitch characteristics and location.

### 7. Exploratory 2026 Probability Calibration

![2026 Model Calibration](figures/2026_calibration.png)

The calibration analysis compares predicted whiff probabilities with observed outcomes in the previously inspected 2026 evaluation sample.

Calibration is an important complement to ranking metrics such as ROC-AUC and Average Precision.

### 8. Subgroup Model Reliability

![Subgroup Calibration](figures/subgroup_calibration.png)

Subgroup analysis examines differences between predicted and observed outcomes across selected pitch or player categories.

This helps identify limitations that may be hidden by aggregate model performance.

**Additional visualizations**, including tracking coverage, pitcher repertoire changes, hitter profiles, standardized velocity, uncertainty estimates, and model diagnostics, are available in the `figures/` directory and the full Jupyter Notebook.

---

## 🛠 Tech Stack

**Languages**
- Python
- R (supplementary statistical analysis)

**Environment**
- Jupyter Notebook
- VS Code

**Data Collection & Processing**
- pybaseball
- pandas
- NumPy
- PyArrow

**Statistical Analysis**
- SciPy
- statsmodels
- R statistical modeling

**Machine Learning**
- scikit-learn

**Visualization**
- Matplotlib
- Seaborn

**Techniques**
- Exploratory Data Analysis
- Data Cleaning and Quality Validation
- Pitch Design and Movement Analysis
- Hitter Plate Discipline Analysis
- Batted-Ball Contact Quality Analysis
- Longitudinal and Matched-Player Comparisons
- Statistical Regression
- Classification and Regression Modeling
- Chronological Model Validation
- Feature Ablation
- Probability Calibration
- Bootstrap Confidence Intervals
- Bayesian Shrinkage
- Data Drift and Model Diagnostics

---

## 🗂️ Repository Structure

```text
MLB-Statcast-Comprehensive-Analytics/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│   └── MLB_Statcast_Comprehensive_Research_Final.ipynb
│
├── src/
│   ├── __init__.py
│   └── pipeline.py
│
├── research_tools/
│   ├── __init__.py
│   └── submission.py
│
├── figures/
│   └── ... 14 selected PNG visualizations
│
├── r/
│   └── historical_statcast_models.R
│
├── tests/
│   ├── test_submission.py
│   └── test_submission_notebook_run.py
│
├── docs/
│   ├── FINAL_SUBMISSION_AUDIT.md
│   └── SUBMISSION_MANIFEST.json
│
├── archive/
│   └── Executed_Notebook_Before_Final_Editorial_Cleanup.ipynb
│
└── MLB_Statcast_Research_Report_Standalone.html
```

The `figures/` directory contains selected visualizations from the executed analysis, while the HTML research report provides a shorter interpretation of the main findings.

The `notebooks/` directory contains the complete technical analysis.

The `src/` and `research_tools/` directories contain supporting data processing and analysis utilities. The `tests/` directory provides automated checks for selected project functions.

The `archive/` directory preserves an earlier executed notebook as supporting execution evidence.

Downloaded Statcast datasets and generated intermediate files are not required to be included in the public repository. They can be regenerated through the data collection workflow.

---

## 🚀 How to Run

### 1. Install the Required Libraries

Clone or download the repository and install the required Python packages.

```bash
pip install -r requirements.txt
```

Run the notebook using a Python environment with the installed dependencies.

### 2. Configure the Project Directory

The project uses `src/pipeline.py` and supporting files from the repository root.

If running the analysis from a different folder, update the project root path in the notebook when necessary.

The original Windows workspace was:

```text
I:\Potforlio\MLB Analytics
```

Keep the repository folders together so the notebook can locate its supporting modules.

### 3. Choose the Analysis Mode

The notebook supports sample-window and expanded data collection modes.

```python
SAMPLE_MODE = True
HISTORY_MODE = "sample"
```

The default settings reproduce the project's selected observation windows:

- May 1–14 for the detailed 2024–2025 analysis.
- August 10–16 for each historical year from 2015 through 2026.

For expanded regular-season collection, the corresponding settings can be changed to:

```python
SAMPLE_MODE = False
HISTORY_MODE = "full"
```

Full-season mode requires substantially more downloading, storage, and processing time. Results generated in that mode must be analyzed separately and should not be presented using the sample-window findings in this README.

### 4. Open the Jupyter Notebook

```bash
jupyter notebook notebooks/MLB_Statcast_Comprehensive_Research_Final.ipynb
```

Run the notebook cells in order.

The data collection workflow downloads Statcast records when required and uses cached files where available.

Generated figures, analysis tables, and model diagnostics are saved to the configured output directories.

### 5. Run Project Tests

```bash
python -m pytest tests/test_submission.py -q
```

These tests validate selected analytical utilities. They do not replace a full notebook execution or independently verify the scientific conclusions.

### 6. Review the Research Report

Open:

```text
MLB_Statcast_Research_Report_Standalone.html
```

The HTML report presents the main research questions, selected results, visualizations, predictive modeling findings, and study limitations without requiring readers to navigate the full technical notebook.

---

## ⚠️ Limitations

The analysis has several important limitations.

- **Historical scope:** The 2015–2026 analysis uses August 10–16 of each year, not complete MLB seasons. Results are sample-window comparisons rather than full-season league estimates.
- **Detailed analysis scope:** The separate 2024–2025 analysis covers May 1–14 of each year.
- **Sample selection:** Player availability, opponent composition, pitch selection, and game situations can differ across observation windows.
- **Measurement consistency:** Statcast tracking systems, available measurements, and pitch classifications have changed over time.
- **Pitch location:** The reference position for `plate_x` and `plate_z` changed in 2026, limiting direct comparisons with earlier seasons without additional harmonization.
- **Contact tracking:** Hard-hit and other contact-quality analyses depend on the availability of measured in-play batted-ball events.
- **Repeated observations:** Multiple pitches from the same players and games are not statistically independent.
- **Small samples:** Some matched-player and subgroup analyses have too few eligible observations to support reliable conclusions.
- **Causality:** Associations between pitch characteristics, hitter decisions, and outcomes do not establish causal relationships.
- **Prediction timing:** Some models use measured pitch characteristics that are not fully available before a pitch is thrown.
- **Model validation:** The 2025 and 2026 observation windows were reviewed during development. Their results are retrospective and exploratory, not new independent external validation.
- **Deployment:** The predictive models have not been validated for live baseball decision-making or production deployment.

Future improvements would require complete-season data, consistent measurement definitions, larger matched-player samples, and genuinely independent prospective model evaluation.

---

## 📌 Conclusion

This project provides a comprehensive analysis of MLB Statcast data, combining pitching analytics, hitter behavior, contact quality, game situations, historical comparisons, and predictive modeling.

The results identify meaningful differences in observed pitch characteristics and swing-and-miss outcomes across pitch types, player matchups, and selected historical observation windows.

Statistical analysis and longitudinal comparisons provide context for interpreting these patterns, while machine learning models demonstrate an ability to distinguish pitch-level whiff probabilities within the retrospective evaluation samples.

The project also highlights the importance of correct metric definitions, tracking completeness, statistical uncertainty, probability calibration, and time-based validation.

Overall, the findings demonstrate how Statcast data can support detailed baseball performance analysis while emphasizing the limitations of observational samples and retrospective predictive modeling.
