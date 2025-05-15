# Waze-User-Behavior-Analysis-Investigating-Ride-Frequency-by-Device-Type
This project delves into Waze user data to explore potential differences in driving behavior based on mobile device type. The primary objective is to determine if there's a statistically significant difference in the average number of rides between users on iPhone and Android devices. This analysis is a component of a broader user churn project, aiming to provide actionable insights for the Waze team.

## Project Context:
The Waze leadership team requested an analysis to understand the relationship between the mean number of rides and the type of device used by drivers. This investigation seeks to answer the research question: "Do drivers who open the application using an iPhone have the same number of drives on average as drivers who use Android devices?"

## Methodology & Analysis:
The project follows a structured data analysis approach:

* ### Data Loading and Preparation:
  The Waze dataset (`waze_dataset.csv`) was loaded using Pandas. A new column, `device_type`, was created by mapping the 'device' column string values ('iPhone', 'Android') to numerical representations (1, 2) for 
  easier analysis.
* ### Exploratory Data Analysis (EDA):
  Descriptive statistics were computed to understand the data, specifically focusing on the average number of drives for each device type. Initial observations suggested a slight difference, with iPhone users 
  appearing to have a higher average number of drives.
* ### Hypothesis Testing:
  To rigorously assess the observed difference, a two-sample t-test for independent samples was conducted.

  * Null Hypothesis (H₀): There is no difference in the average number of drives between drivers who use iPhone devices and drivers who use Android devices.
  * Alternative Hypothesis (Hₐ): There is a difference in the average number of drives between drivers who use iPhone devices and drivers who use Android devices.
  * A significance level of 5% was chosen for the test. The `stats.ttest_ind()` function from the SciPy library was used, with `equal_var` set to `False` to account for potentially unequal variances between the 
    two groups (Welch's t-test).

## Key Findings:
The t-test yielded a p-value of approximately 0.143. Since this p-value is greater than the significance level of 0.05, the null hypothesis was not rejected.

## Conclusion & Business Insights:
The statistical analysis indicates that there is no statistically significant difference in the average number of drives between Waze users on iPhone and Android devices. This key business insight suggests that device type, in isolation, may not be a primary driver of ride frequency.

Further exploration could involve investigating other factors that might influence the variation in the number of drives and conducting additional hypothesis tests to gain deeper insights into user behavior.

## Technologies Used:
* Python
* Pandas (for data manipulation and analysis)
* SciPy (for statistical testing)
