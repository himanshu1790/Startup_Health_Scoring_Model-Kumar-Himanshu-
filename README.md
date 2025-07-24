# Startup Health Scoring Model

**Candidate:** Kumar Himanshu  
**Submission for:** ScaleDux AI Internship – Task 1  
**Role Applied:** Artificial Intelligence Intern

---

## Project Summary

This project is about building a scoring system that helps evaluate the overall health of startups — kind of like how credit scores work for individuals. The goal is to analyze different business factors like team experience, market size, user engagement, and funding to generate a score (out of 100) that reflects a startup’s potential.

---

## About the Dataset

The dataset includes data from 100 fictional startups, each with the following details:

- **Team Experience**: Average experience (1 to 10 scale)
- **Market Size**: Total addressable market (in million USD)
- **Monthly Active Users**: Number of active users using the product
- **Burn Rate**: Monthly operational expenses (in INR)
- **Funds Raised**: Total money raised so far (in INR)
- **Valuation**: Current company valuation (in INR)

---

## My Approach

1. **Preprocessing**: I normalized all the numeric data to bring them to the same scale (0 to 1) using Min-Max scaling.

2. **Burn Rate Handling**: Since a high burn rate is a negative sign, I inverted it during normalization so that lower expenses result in a higher score.

3. **Weighted Scoring**: I created a custom formula by assigning weights to each feature based on how important I believe it is for a startup’s success.

4. **Final Score**: Each startup’s score is calculated out of 100 using the weighted sum of all features.

5. **Ranking**: Startups are ranked from best to worst based on their score.

---

## How I Designed the Score (Scoring Methodology)

I tried to keep the scoring logic simple, practical, and similar to how real investors might think.

- **Monthly Active Users (25%)**: The most direct measure of real-world traction.
- **Market Size (20%)**: Bigger market = more room to grow.
- **Team Experience (15%)**: A strong team is always a big plus.
- **Valuation (15%)**: Reflects market confidence.
- **Funds Raised (15%)**: Shows investor trust and backing.
- **Burn Rate (10%)**: High burn = high risk, so lower is better (inverted while scoring).

 All features were scaled to ensure fairness.  
 The final score was calculated as:  
```python
health_score = sum(normalized_feature × weight) × 100
```

This score offers a balanced view of how strong or risky a startup might be.

---

## Key Insights

- Startups with a healthy balance of strong user engagement, low burn, and experienced teams scored the highest.
- Surprisingly, high valuation alone didn’t guarantee a top rank — traction and team mattered more.
- Some low scorers had good funding but poor user numbers or high expenses.

---

## Visuals I Created

-  A bar chart showing ranked scores of all startups
-  A correlation heatmap to show how features relate
-  A histogram showing how health scores are spread

You can find these visuals inside the `outputs/` folder.

---

## Folder Structure

```
StartupHealthScoring/
├── Startup_Scoring_Dataset.csv
├── notebooks/
│   └── Startup_Health_Scoring_Model.ipynb
├── outputs/
│   ├── health_score_bar_chart.png
│   ├── correlation_heatmap.png
│   └── health_score_distribution.png
└── README.md
```

---

## Tools Used

- Python (main language)
- Pandas & NumPy for data handling
- Scikit-learn for normalization
- Matplotlib & Seaborn for visuals
- Jupyter Notebook / Google Colab for development

---

## What Can Be Improved

- Use clustering to group startups into types (e.g., high growth vs. high burn)
- Build a predictive model to estimate future valuation
- Add a dashboard to explore startups interactively
- Include time-based data if available to track performance over time

---

## Final Thoughts

This task was a great hands-on exercise that combines both business understanding and data science. It helped me think critically about how startup metrics connect and how we can use data to make better investment decisions.

Thanks to the ScaleDux team for the opportunity!  
Looking forward to learning more and contributing meaningfully to your projects.
