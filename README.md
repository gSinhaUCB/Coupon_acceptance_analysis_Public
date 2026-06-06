# Will_Customer_Accept_Coupon_Dev
Module-5 Assignment:   Will the customer accept the offered coupon?  Dev env

## 📁 Project Directory & Files

**Jupyter Notebook:** [View the Data Analysis Notebook](./Module_5.1_prompt.ipynb)
**Raw Dataset:** [Coupons CSV Data File](./data/coupons.csv)
**Main Chart:** [Coupon Distribution & Acceptance Rates](./images/coupon_distribution_chart.png)
**Temperature Study:** [Temperature Histogram](./images/temperature_histogram.png)
**Coffee Study:** [Coffee House Passenger Distribution](./images/coffee_passenger_dist.png)

## =================================================


# Predictive Analysis of In-Vehicle Coupon Acceptance

An exploratory data analysis (EDA) and behavioral study investigating the factors that influence whether a driver will accept a coupon delivered to a mobile phone while driving.  Using a UCI Machine Learning Repository dataset containing 12,684 observations, this project uncovers the precise demographic, environmental, and situational triggers that drive consumer decision-making.

# Key Executive Findings

**The Baseline**: Across all coupon categories, the baseline acceptance rate is 56.84%. Environmental Triggers: Temperature acts as a behavioral catalyst. Drivers are nearly 6% more likely to accept a coupon on warm, leisurely days (80°F, ~58.8% acceptance) than on freezing, high-urgency days (30°F, ~53.6% acceptance).

**The Bar Coupon Paradox**: Bar coupons underperform the baseline significantly at 41%. However, by isolating historical behavior (regular bar-goers) and immediate social context (traveling with adult peers), conversion rates rocket to over 71%.

**The Coffee House Dynamic**: Coffee house coupons sit at a volatile ~50% baseline. The presence of passengers acts as the primary differentiator: traveling with friends transforms a commute into a social outing, drastically increasing acceptance compared to driving alone or with children.


# Data Cleaning & Pipeline Integrity
Before conducting the deep-dive analysis, the raw dataset was  cleaned to ensure statistical integrity:

**Handling Extreme Sparsity:** The `car` column was dropped entirely after it was discovered to be missing 99.1% of its values, preventing data distortion.

**Imputation of Behavioral Data:** Minor missing values (<2%) in key behavioral columns (`Bar`, `CoffeeHouse`, etc.) were filled using `'unknown'` placeholders to maintain sample size without inventing artificial trends.

**Schema Fixes:** Resolved structural inconsistencies, including fixing a character typo (`passanger` ➔ `passenger`) and parsing categorical, string-encoded demographic bins (like `age`).



##  Deep-Dive Cohort Analyses

### 1. Bar Coupons: Habit Over Impulse
While blanket distribution of bar coupons yields poor results, advanced conditional filtering isolated highly lucrative target segments:

**Cohort A (High-Yield Social):** Drivers who visit bars more than once a month, have adult peers in the car (friends/partners), and work outside primary outdoor industries yielded a massive 71.3% acceptance rate.

**Cohort B (All Others):** The rest of the driving population dropped to a meager 37.8% acceptance rate.

### 2. Coffee House Coupons: The Passenger Effect
By isolating age (under 30) and timing (peak coffee slots: 7 AM, 10 AM, 2 PM), the direct psychological impact of passengers was mapped:

**With Friends:** Acceptance spiked dramatically, indicating that coffee houses are treated as social destinations when peers are present.
**Driving Alone:** Acceptance dropped significantly, proving that solitary drivers operate on strict routines where detours are viewed as an inconvenience.



## Visualizations Generated

The repository features high-resolution data visualizations mapping out these human behaviors:
1. `coupon_distribution_chart.png`: A comprehensive overview mapping raw distribution vs. acceptance metrics for all 5 major coupon models.

2. `temperature_histogram.png`: A stacked histogram isolating the sharp contrast in driver behavior between 30°F, 55°F, and 80°F environments.

3. `coffee_passenger_dist.png`: A targeted visualization proving the direct shift in Coffee House acceptance based on passenger makeup.



## Actionable Strategic Recommendations

1. **Deploy Social Geofencing:** The advertising engine should prioritize high-margin Bar and Coffee House coupons exclusively when real-time smartphone telemetry detects multiple passengers traveling together during leisure hours.

2. **Implement Structural Blackouts:** Scale back coupon delivery automatically during 30°F snowy/rainy commutes, or pivot entirely to low-friction "Carry-Away & Takeaway" coupons where drivers do not have to leave their climate-controlled vehicles.

3. **Anchor on Behavioral Frequency:** Historical consumer frequency is a vastly superior predictor of coupon acceptance than standard demographic variables like income alone. Marketing capital should heavily weight past visitation data.

More details in the Jupyter notebook itself


