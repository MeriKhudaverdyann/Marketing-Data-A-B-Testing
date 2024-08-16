# Marketing Analysis

## Project Overview
This project conducts a thorough analysis of a marketing dataset, evaluating the effectiveness of two different advertising strategies: traditional ads (`ad`) and public service announcements or no ads (`psa`). The analysis encompasses data exploration, visualization, cross-tabulation, and statistical testing to derive insights about the impact of each strategy on user conversion rates.

## About Dataset
Marketing companies aim to run successful campaigns in a complex market. To determine the best strategy, they often use A/B testing, a randomized experimentation process where different versions of a variable (e.g., web page, banner) are shown to different segments of people simultaneously. The objective is to identify the version that maximizes business metrics.

The companies are interested in answering two key questions:
1. Would the campaign be successful?
2. If successful, how much of that success could be attributed to the ads?

To answer these questions, the dataset simulates an A/B test where the experimental group (majority) is exposed to ads, while the control group (minority) sees a Public Service Announcement (PSA) or nothing.

### Data Dictionary:
- **Index**: Row index
- **user_id**: Unique User ID
- **test_group**: Group assignment; "ad" for those who saw the advertisement, "psa" for those who saw the public service announcement
- **converted**: Conversion status; `True` if the person bought the product, otherwise `False`
- **total_ads**: Number of ads seen by the person
- **most_ads_day**: Day of the week the person saw the most ads
- **most_ads_hour**: Hour of the day the person saw the most ads

## Objectives
- Assess the impact of `ad` and `psa` on user conversion rates.
- Identify user behavior patterns based on different advertising strategies.
- Evaluate the statistical significance of differences in characteristics and observations between the `ad` and `psa` groups, considering factors such as day of the week, hour of the day, and number of ads viewed.

## Project Structure
1. **Data Exploration**
    - Initial Data Cleaning: Removed unnecessary columns and inspected the dataset for missing values.
    - Unique User IDs: Ensured the uniqueness of user IDs to maintain data integrity.

2. **Data Visualization**
    - **Group Distribution**: Visualized the distribution of users in the `ad` and `psa` groups.
      ![ad_and_psa_grouping](https://github.com/user-attachments/assets/06ed9476-3c57-4115-9972-52c2359f3427)

    - **Conversion Status**: Analyzed and visualized conversion status across the dataset.
      ![conversion_status](https://github.com/user-attachments/assets/76e5ba90-f2a1-4dcd-8ed5-98a56c14c60b)

    - **Ad Activity Analysis**:
        - **By Day of the Week**: Examined advertisement activity by day of the week.
          ![count_of_ads_by_week](https://github.com/user-attachments/assets/b5d8ee22-7493-45c2-8e47-4a51215dbded)

        - **By Hour of the Day**: Analyzed ad activity based on the hour of the day.
          ![count_of_ads_by_hour](https://github.com/user-attachments/assets/8e8e9619-e6a2-4ca4-8782-e08b3df9402b)

        - **Ad Views Distribution**: Explored the distribution of the number of ads seen by users.
          ![ad_view_distribution](https://github.com/user-attachments/assets/d35b3573-d946-40bb-a023-93ec4352cf8c)


3. **Cross-Tabulation Analysis**
    - **Test Group vs. Conversion**:
        - Created a crosstab to analyze conversion rates within the `ad` and `psa` groups.
        - Employed styling to highlight significant differences.
          
          ![crosstab_for_ad_psa](https://github.com/user-attachments/assets/3760386a-b27f-479b-8164-94ffa7bce59a)

    - **Conversion Rates by Day of the Week**:
        - Created and styled crosstabs to compare conversion rates across different days of the week for the `ad` group.
        - Applied the Chi-Square test to assess the independence of conversion rates and specific days.
          
          ![Снимок экрана 2024-08-17 013217](https://github.com/user-attachments/assets/9827d32e-a18c-43e8-87c7-a0a0f206154f)

    - **Conversion Rates by Hour of the Day**:
        - Analyzed conversion rates across different hours of the day using crosstabulations.
        - Sorted and styled the results to identify peak hours for ad effectiveness.
          
          ![Снимок экрана 2024-08-17 013237](https://github.com/user-attachments/assets/93adb195-4230-4107-8619-e70d09be3faf)


4. **Statistical Testing**
    - **Z-Test for Conversion Rates**:
        - Objective: Conducted a two-proportion Z-test to determine if the difference in conversion rates between the `ad` and `psa` groups is statistically significant.
        - Result: Identified a significant difference, suggesting that the `ad` group outperforms the `psa` group in conversion rates.
          ![Снимок экрана 2024-08-17 013251](https://github.com/user-attachments/assets/20144506-63fe-402d-97dd-bea9c42dec66)

    - **Chi-Square Test for Independence**:
        - Objective: Tested the independence of conversion rates with respect to the day of the week and hour of the day within the `ad` group.
        - Result: Certain days and hours were found to have a significant impact on conversion rates.
          ![Снимок экрана 2024-08-17 013259](https://github.com/user-attachments/assets/250956b0-8025-494e-9f1e-35beb00555b3)
          ![Снимок экрана 2024-08-17 013305](https://github.com/user-attachments/assets/e44ba0c8-e676-4a3f-8fbb-6b1bfe3f3db0)

    - **Effect Size Calculation (Cohen's d)**:
        - Objective: Calculated Cohen's d to measure the magnitude of the difference in conversion rates between the `ad` and `psa` groups.
        - Result: Provided a quantitative measure of the effect size, indicating how much the `ad` strategy influences conversion rates.
          ![Снимок экрана 2024-08-17 013311](https://github.com/user-attachments/assets/f5c1cf59-5625-4549-a41d-ae2ce1af4250)


5. **Detailed Analysis**
    - **Crosstabs and P-Value Matrices**:
        - Objective: Generated detailed crosstabs and p-value matrices to explore relationships between conversion rates and specific days within the `ad` group.
        - Focus Areas: Emphasized the percentage loss on weekdays, weekends, and all days compared to specific days, such as Monday and Tuesday.
          ![Снимок экрана 2024-08-17 013337](https://github.com/user-attachments/assets/e868da91-64d0-44cb-93e4-66988c96f552)

    - **Hourly Ad Analysis**:
        - Objective: Evaluated the effectiveness of ad displays by hour of the day using crosstabs and statistical testing.
        - Key Findings: Identified peak hours that maximize conversion rates, providing insights for optimizing ad schedules.
          ![Снимок экрана 2024-08-17 013351](https://github.com/user-attachments/assets/c3fe7312-7ebd-453c-aa70-9da7bb62d6e6)

    - **Shapiro-Wilk Test for Normality**:
        - Objective: To determine if the distributions of users who saw ads and made purchases, and those who saw ads but did not make purchases, were normally distributed.
        - Process: Conducted the Shapiro-Wilk test for both groups.
        - Result: Both groups were found to be non-normally distributed, as indicated by the test results. This non-normality was further confirmed through visual inspection of the distribution plots.
          ![Снимок экрана 2024-08-17 013404](https://github.com/user-attachments/assets/85b3adac-bdfc-4893-a083-d74742c8809e)

    - **Mann-Whitney U Test**:
        - Objective: Given the non-normal distribution, a Mann-Whitney U test was conducted to assess whether the number of ads viewed had a significant impact on conversion rates.
        - Result: The test revealed that the number of ads viewed significantly influences conversion rates.
          ![Снимок экрана 2024-08-17 013410](https://github.com/user-attachments/assets/bc5c1feb-7e20-4987-95a7-6b81a3083b7c)


## Conclusion
The analysis provides actionable insights into the effectiveness of traditional ads compared to public service announcements. Key findings suggest that optimizing ad exposure by time of day and specific days of the week could significantly enhance conversion rates. Based on the analysis, it is recommended to focus ad displays on Mondays and Tuesdays, particularly during the time slots of 14:00 to 17:00 and 20:00 to 21:00. Additionally, the optimal number of ads to show should be between 64 and 103, as this range has been shown to maximize conversion rates.
