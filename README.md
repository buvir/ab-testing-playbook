# ab-testing-playbook
Practical A/B testing end-to-end: dataset prep, exploratory analysis, statistical testing (t-test, chi-square), uplift/ATE, power &amp; sample size, visualization, and a short results report. Includes a Colab notebook for reproducibilit


This project demonstrates a complete A/B testing workflow to evaluate whether a new product variation (Variant B) performs better than the existing version (Variant A). Using Python in Google Colab, I analyzed conversion rates and revenue per user through statistical tests such as the Z-test and T-test. Visualizations were created to compare group performance, and results were saved automatically for reporting. Effect size and sample-size calculations were included to validate the strength of the findings. The notebook concludes with a clear, automated business recommendation based on statistical significance. Overall, the project showcases practical skills in experiment design, statistical analysis, and data-driven decision-making.
**Practical, end-to-end A/B testing notebook designed for Google Colab.**  
Run a reproducible experiment walk-through: data load, EDA, hypothesis testing (z-test / t-test), uplift/ATE, power & sample size, bootstrapping, visualizations, and exportable results.

---

## One-click Colab


[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1mOgjxl1q8b1ishicwq1XFMejkWlX5t8a?usp=sharing)


---
### 📊 Average Revenue per User
![Average Revenue](revenue_chart.png)

### 📈 Conversion Rate
![Conversion Rate](conversion_rate_chart.png)


### 📁 A/B Test Results CSV

You can view the full raw results here:

👉 [**ab_test_results_summary.csv**](ab_test_results_summary.csv)



## Repo structure (Colab-focused)
notebooks/ab_testing_colab.ipynb # main Colab notebook
colab/ # helper scripts & snippets for Colab usage
data/ # small sample CSVs for quick testing
reports/ # executive summary & results
assets/ # saved charts/screenshots
requirements.txt # Python packages (optional for local)

```
ab-testing-playbook/

├── notebooks/
│   └── ab_testing_colab.ipynb      # main Colab notebook 
├── colab/                          # small helper scripts for Colab
│   ├── mount_drive.py              # optional: snippet to mount drive
│   └── kaggle_download.sh          # optional: Kaggle download script
├── data/                           # small sample CSVs or README linking to data sources
│   └── sample_ab_data.csv
├── reports/
│   └── ab_test_report.md
├── assets/
│   └── conv_chart.png              # screenshots exported from notebook (optional)
├── requirements.txt
└── README.md                       # (paste content below)

```
📘 A/B Test Design & Methodology

This project evaluates Variant A vs Variant B using conversion rate and revenue per user as key performance indicators (KPIs).
The workflow follows standard industry A/B testing methodology.

🎯 1. Hypothesis Setup
Null Hypothesis (H₀):

There is no difference in performance between Variant A and Variant B.

Alternative Hypothesis (H₁):

Variant B performs better than Variant A in terms of conversion rate and revenue per user.

🧮 2. Experiment Metrics
Metric	Variant A	Variant B
Conversion Rate	9.61%	11.77%
Revenue per User	$1.94	$2.53
🔬 3. Statistical Tests Applied
📌 Proportion z-test (Conversion Rate)

Used to determine whether the difference in conversion rates is statistically significant.

p-value = 1.0000

Conclusion: Not significant at α = 0.05

The observed conversion uplift could be due to random variation.

📌 Two-Sample t-test (Revenue per User)

Used to compare average revenue between the two groups.

Result: Statistically significant

Interpretation: Variant B users generate meaningfully higher revenue per user.

📊 4. Visual Comparison
Conversion Rate vs Revenue
<p align="center"> <img src="average_revenue.png" width="45%" /> <img src="conversion_rate.png" width="45%" /> </p>

These charts visualize the performance differences between the variants.

📌 5. Final Conclusion

Conversion rate difference is not statistically significant

Revenue per user is significantly higher for Variant B

The experiment has mixed results, indicating that conversion uplift may not be reliable yet


---

## Recommended workflow (Colab)
```
1. **Open the notebook in Colab** using the badge above (or File → Open notebook → GitHub → paste repo URL).  
2. **Runtime**: default (CPU) is fine for this work. No GPU required.  
3. **Mount Google Drive** (optional, recommended) to save outputs and larger datasets. Example cell (already in notebook):
```python
from google.colab import drive
drive.mount('/content/drive')
# set a path to save outputs:
OUT_DIR = '/content/drive/MyDrive/ab-testing-playbook-outputs'
import os
os.makedirs(OUT_DIR, exist_ok=True)
```
