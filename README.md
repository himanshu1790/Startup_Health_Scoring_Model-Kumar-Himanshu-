# 🚀 Startup Health Scoring Model

**Submitted for:** ScaleDux AI Internship – Task 1  
**Candidate:** Kumar Himanshu  
**Role:** Artificial Intelligence Intern

---

## 💡 What This Project Is About

This project simulates a scoring system for startups — kind of like a credit score, but based on business health. Using basic data points like team strength, market potential, user traction, and financials, I’ve built a model that gives each startup a score out of 100 to represent its overall health and potential.

---

## 📊 What's in the Dataset?

The dataset includes 100 fictional startups. For each startup, we have:

- `startup_id`: Unique startup name/ID  
- `team_experience`: Average years of experience on the core team (1–10 scale)  
- `market_size_million_usd`: Claimed market size in million USD  
- `monthly_active_users`: Number of users actively using the product each month  
- `monthly_burn_rate_inr`: Monthly spending in INR  
- `funds_raised_inr`: Total funds raised till now  
- `valuation_inr`: Current company valuation in INR

---

## ⚙️ How I Built the Scoring Model

First, I cleaned and normalized all the numeric features using Min-Max scaling (to bring them on a 0–1 scale). Since high burn rate is bad for a startup’s sustainability, I reversed that value so lower burn contributes to a better score.

Then, I assigned weights to each feature based on its importance:

| Feature                | Weight (%) | Why it matters                     |
|------------------------|------------|------------------------------------|
| Team Experience        | 15         | A solid team can execute better    |
| Market Size            | 20         | Bigger market = bigger opportunity |
| Monthly Active Users   | 25         | Shows real product traction        |
| Burn Rate (inverted)   | 10         | Low spending = longer runway       |
| Funds Raised           | 15         | Indicates external belief          |
| Valuation              | 15         | Reflects market confidence         |

Each startup’s final score is calculated based on this formula, scaled to 100.

---

## 🏆 What I Found

After ranking all 100 startups:

- The **Top 10 startups** had strong user engagement, experienced teams, and were operating in large markets.
- The **Bottom 10** often had high burn rates, small user bases, or limited funding.

It was interesting to see that just having high valuation or funds didn’t always mean a good score — team experience and traction played a huge role.

---

## 📉 Visuals Included

- A bar chart showing all startup scores ranked
- A correlation heatmap showing how different features relate
- A histogram showing how the scores are spread out

These help to quickly understand the patterns in the data.

---

## 📁 Project Structure

StartupHealthScoring/
│
├── Startup_Scoring_Dataset.csv
├── notebooks/
│ └── Startup_Health_Scoring_Model.ipynb
├── outputs/
│ ├── health_score_bar_chart.png
│ ├── correlation_heatmap.png
│ └── health_score_distribution.png
└── README.md

---

## 🛠 Tools & Technologies

- **Python** for coding
- **Pandas** and **NumPy** for data handling
- **Seaborn** and **Matplotlib** for visualization
- **Scikit-learn** for data normalization
- **Jupyter Notebook / Google Colab** as the development environment

---

## 🔭 Ideas for Improvement

- Try clustering startups based on their profiles (e.g., low burn, high growth)
- Use machine learning models like regression or XGBoost to predict valuation
- Include historical (time-based) data to make the model more dynamic

---

## 🙌 Thanks!

This project was a great way to apply data science to a business case.  
If you'd like to connect or provide feedback, feel free to reach out!

