# Finance Forecasting & Churn Risk – scikit‑learn & Python
This project is my next step after the SaaS Finance Analytics – dbt, DuckDB & Power BI work, where I focused on clean modeling and executive‑style dashboards for MRR and churn. Here, I wanted to stay in the finance world but go deeper into predictive analytics, using real churn data to estimate expected revenue, churn risk, and risk‑adjusted MRR at a segment level.

## About the project
In the earlier SaaS project, I learned how to structure revenue data with dbt, expose it through DuckDB, and design a Power BI report that a finance or RevOps stakeholder could actually use. This project builds on that foundation and pushes into the FP&A and ML side of the story: I model customer‑level finance data from a churn dataset, then train two scikit‑learn Pipelines to predict monthly revenue and churn probability, and finally roll those outputs up into segment‑level views that look and feel like something teams could discuss in a forecast review.

I treated this as a chance to learn how a Finance Data Analyst might think: start with questions like “Where is our revenue concentrated?”, “What do we expect to earn from customers like this?”, and “How much of that revenue is actually at risk?”, and then build just enough modeling and ML around those questions to give a clear, honest answer.

## What I focused on
I focused less on building a huge system and more on getting a few key finance and ML building blocks right:

Creating a fact_customer_finance table with tenure, contract type, total spend, churn flag, and an explicit approximation of monthly revenue per customer using a real churn dataset.

Rolling that into segment views that show customer count, MRR, ARR and churn rate for each subscription type and contract length, so it is easy to see where revenue really sits and how risky each segment is.

Training two scikit‑learn Pipelines – a regression model for expected monthly revenue and a classification model for churn probability – with proper preprocessing and evaluation on separate train/test splits.

Combining model outputs into risk‑adjusted MRR and a segment_risk view that highlights high‑revenue, high‑risk segments, which feels like a natural next step from my earlier descriptive SaaS dashboard into forecasting and strategic finance questions.

## How to run it
Open notebooks/Kaggle_Notebook.ipynb.

Point the notebook at the original Kaggle churn dataset (or use the processed CSVs under data/processed/).

Run the notebook cells to rebuild fact_customer_finance, the segment tables, and both ML pipelines, and then inspect the final segment and risk tables.

This project is mainly about showing how I am starting to connect finance modeling and ML: first by structuring the data in a way Finance can trust, and then by layering on predictive models that help explain not just how much revenue there is today, but how much we can realistically count on going forward.
