# Project Background
Telco Communications is a European telecommunications provider offering internet, phone, and streaming services to both individual and business customers. Founded in the early 2000s, the company operates across multiple countries and serves over 10 million subscribers.

The business model is subscription-based, with key metrics including monthly recurring revenue, customer lifetime value (CLTV), and churn rate. Churn — when customers cancel their contracts — directly impacts revenue and customer acquisition cost recovery.

As a data analyst within the retention strategy team, I was tasked with uncovering patterns in customer attrition and recommending ways to reduce churn.

Insights and recommendations are provided on the following key areas:

- **Churn-Prone Profiles:** Identifying customer groups with the highest churn risk.
- **Service Engagement:** Evaluating activity levels among high-value customers.
- **Contract and Payment Type:** Assessing which plans and billing methods predict churn.
- **Customer Lifetime Value (CLTV):** Understanding what drives long-term value.


# Data Structure & Initial Checks

The company’s dataset includes 7,043 customer records with the following key tables/features:
- **Customer Demographics:** Gender, age, tenure, senior citizen status
- **Account Information:** Contract type, payment method, paperless billing
- **Service Usage:** Phone service, internet type, streaming services
- **Churn Indicator:** Whether the customer has churned (Yes/No)

[Entity Relationship Diagram here – optional]

Initial checks:
- Missing values in TotalCharges field cleaned and imputed
- Categorical values encoded using one-hot or label encoding
- Customers with less than 1 month of tenure grouped for special attention


# Executive Summary

### Overview of Findings
Three churn-prone profiles were identified based on clustering analysis. Paperless billing and month-to-month contracts were strong churn predictors. High-value customers were not always engaged, showing that CLTV is not solely dependent on charges. Strategic retention can begin with Profile 1, which accounts for ~25% of churn cases.



# Insights Deep Dive

### Churn-Prone Profiles
* **Main insight 1.** Customers with electronic check and no internet service had a churn rate of ~25%.
* **Main insight 2.** Younger customers with fewer products and low tenure are more likely to churn.
* **Main insight 3.** Month-to-month contract customers churn more frequently than those on annual plans.
* **Main insight 4.** Paperless billing increases churn likelihood when paired with certain payment types.


### Service Engagement
* **Main insight 1.** Customers with streaming services and multiple lines tend to stay longer.
* **Main insight 2.** High monthly charges alone do not indicate loyalty—usage matters more.
* **Main insight 3.** Customers with high product overlap (internet + streaming + phone) show stronger retention.
* **Main insight 4.** Customers inactive in their first month tend to churn within the first quarter.

![Engagement vs. Tenure Plot](link-to-engagement-viz.png)


### Contract and Payment Type
* **Main insight 1.** Churn is highest among customers with month-to-month contracts and electronic check payments.
* **Main insight 2.** Annual contract users show higher CLTV and lower churn overall.
* **Main insight 3.** Auto-pay and credit card users are 15% more likely to stay beyond 12 months.
* **Main insight 4.** Customers who manually pay bills each month churn at double the rate of those on auto-pay.



### Customer Lifetime Value (CLTV)
* **Main insight 1.** Tenure and product count are stronger CLTV predictors than monthly charges.
* **Main insight 2.** Paperless billing does not guarantee loyalty—it's best paired with long-term contracts.
* **Main insight 3.** CLTV is highest among engaged users with multiple services.
* **Main insight 4.** Credit score was not included but could enhance future predictive models.


# Recommendations:
Based on the findings above, I recommend the retention and customer success teams prioritize the following:

* Customers with electronic check and month-to-month plans should be targeted with incentives to switch to annual auto-pay options.
* Provide onboarding education and support for customers with low tenure to build trust and product understanding.
* Cross-sell bundled services (e.g., phone + streaming) to customers with only one active service.
* Alert customer success managers when high-balance users show signs of inactivity in the first 30 days.
* Launch loyalty campaigns focused on high-CLTV customers to protect long-term revenue.


# Assumptions and Caveats:
To conduct this analysis, the following assumptions and limitations were applied:

* Customers with missing TotalCharges were assumed to be new and were retained with imputed values.
* Data was treated as static — i.e., no seasonal or monthly churn patterns were considered.
* Tenure was used as a proxy for engagement in lieu of detailed session-level data.
* The churn label was binary; reasons for churn (voluntary/involuntary) were not differentiated.
* Feature selection was based on available columns in the dataset; financial creditworthiness was not included.
