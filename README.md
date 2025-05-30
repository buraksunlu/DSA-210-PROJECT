# DSA-210-PROJECT

# Introduction 
The aim of this project is to investigate whether offering Turkish language support has a statistically significant impact on a game's popularity among Turkish players on Steam. The project spans from December 2020 to May 2025 and uses player count data and review scores to assess how Turkish localization affects game engagement. By comparing games with and without Turkish support, this study aims to reveal whether language accessibility influences player behavior and game success.


# Hypothesis
Games that offer Turkish language support receive significantly higher average user review scores and player counts from Turkish players, compared to similar games that lack such support.  

# Motivation  
I have observed that many games on Steam lack Turkish language support, yet Turkish players often request localization. This project aims to understand whether language support directly affects purchasing behavior. The findings may highlight the importance of localization for developers targeting the Turkish gaming community.  

# Data Source 
The dataset used in this project was compiled from publicly accessible sources such as Steam Charts, SteamDB, and the official Steam store pages. It includes daily player engagement metrics—such as average concurrent players, total followers, and user reviews—for multiple games over the period from December 2020 to May 2025.

Key features collected for each game include:

#### •Date

#### •Game Title

#### •Turkish Language Support (binary: 1 for Yes, 0 for No)

#### •Average Player Count

#### •Follower Count

#### •Positive Review Count

#### •Negative Review Count

Games were then grouped into two categories based on whether they offer Turkish language support. Since all data was gathered from public sources, there are no ethical or privacy concerns associated with this analysis.

# Project Plan 
#### 1.Data Collection: Gather average daily player counts, review statistics, and language support status from Steam Charts and SteamDB between December 2020 and May 2025.

#### 2.Data Cleaning: Format the data by converting Turkish support into binary values (1 = Yes, 0 = No) and ensure consistent numerical types for player counts and reviews.

#### 3.Exploratory Data Analysis (EDA): Use histograms, boxplots, bar charts, and regression plots to observe trends in player behavior with respect to Turkish language availability.

#### 4.Statistical Testing: Apply independent samples t-tests to determine whether Turkish language support significantly affects player count and engagement.

#### 5.Machine Learning Modeling: Build and evaluate regression models (Random Forest, KNN, SVR) to predict player count using Turkish language support as a feature.

#### 6.Conclusion and Interpretation: Interpret the results to validate the hypothesis and assess the influence of localization on Turkish players’ engagement.



# Data Analysis

## 1. Collecting Data
The dataset includes daily statistics of selected Steam games between December 2020 and May 2025, focusing on the following metrics:

#### •Average daily player counts

#### •Number of followers

#### •Positive and negative review counts

#### •Turkish language support (binary: 1 = Yes, 0 = No)

The data was gathered from SteamDB and Steam Charts, and compiled into an Excel file. For analysis, games were grouped into two categories based on Turkish language support:

### With Turkish Support (1):

#### •The Witcher 3: Wild Hunt

#### •Cyberpunk 2077

#### •Assassin’s Creed Odyssey

### Without Turkish Support (0):

#### •Dark Souls III

#### •Sekiro™: Shadows Die Twice

## 2. Exploratory Data Analysis (EDA)
Using pandas, matplotlib, and seaborn libraries, I conducted several exploratory data analyses to understand how Turkish language support affects player engagement in Steam games. I first created a histogram to visualize the overall distribution of average player counts across all games, revealing a heavy concentration in lower ranges with a few outliers. Next, I used a boxplot to compare the distribution of average players between games with and without Turkish support, which clearly showed higher median values and more variability for Turkish-supported games. I also included a bar chart to compare the mean average player counts in both groups. To explore potential linear trends, I used linear regression with a scatterplot to examine the relationship between Turkish support and player count, which suggested a positive association. Lastly, I performed a correlation analysis using Pearson’s coefficient to assess the strength of the relationship between Turkish language availability and average players.

### 2.1 Histogram
![histogram](https://github.com/user-attachments/assets/f18471d8-2049-4289-9872-af549ef90638)

The histogram displays the distribution of average player counts across all games. Most games have relatively low average players, but a few outliers show significantly high engagement.

### 2.2 Boxplot
![boxplot](https://github.com/user-attachments/assets/07545017-e07c-41a7-a717-3a945e5d16b7)

The boxplot compares the distribution of average player counts between games with and without Turkish language support. Turkish-supported games show a higher median and a wider spread, suggesting greater player engagement.

### 2.3 Bar Chart
![barchart](https://github.com/user-attachments/assets/6c0edf39-6190-45f3-b40a-2687ac5c82fb)

This bar chart shows the average player counts for games with and without Turkish language support:

##### •Games with Turkish support have an average of approximately 40702 players.

##### •Games without Turkish support have an average of approximately 12450 players.

This clear difference in player count highlights the potential impact of language accessibility on player engagement.

### 2.4 Scatterplot with Regression Line
![linear reg](https://github.com/user-attachments/assets/6f8f920c-60f4-4206-ac9f-8f31bfe2cefc)

This scatterplot displays the relationship between Turkish language support (0 = No, 1 = Yes) and average player count. Each point represents a game, and a regression line is fitted to observe the trend.

##### •Intercept (β₀): -10437.39
##### •Slope (β₁): 0.06

This means that when Turkish support is not provided (value 0), the expected average player count is -10,437, which is not meaningful in isolation but helps define the linear model. The positive slope of 0.06 suggests that enabling Turkish language support is associated with a steady increase in average player count. While the intercept is negative due to the linear fit, the upward trend implies a positive relationship between Turkish support and player engagement.

### 2.5 Correlation Analysis

I conducted both correlation analysis and an independent samples t-test to test the hypothesis that Turkish language support increases average player counts in Steam games.

##### •Pearson Correlation Coefficient: 0.20
→ This indicates a weak but positive relationship between Turkish language support and player count.

##### •P-Value: 0.0010
→ Since the p-value is well below the 0.05 threshold, the correlation is statistically significant.

These findings support the hypothesis from a correlational perspective. Although the relationship is not very strong, the results suggest that the presence of Turkish language support is associated with higher player engagement.

## 3. Hypothesis Testing
#### Null hypothesis (H₀): There is no significant difference in average player counts between games with and without Turkish language support.

#### Alternative hypothesis (H₁): Games with Turkish language support have significantly higher average player counts.

I conducted an independent samples t-test to compare the means of the two groups. The results are:

#### •T-statistic: 4.06

#### •P-value: 7.6e-05

Since the p-value is well below the significance threshold of 0.05, I reject the null hypothesis.
This provides strong evidence supporting the claim that Turkish language support in games is associated with significantly higher player engagement on Steam.

## 4. Visualization Summary
I created a histogram to visualize the overall distribution of average player counts, highlighting that most games have relatively low engagement, with a few outliers attracting significantly more players. A boxplot revealed higher median values and greater variance in average players for games with Turkish language support. To further emphasize this difference, I used a bar chart comparing the average player count between games with and without Turkish support. A scatterplot with a regression line was added to assess the linear relationship, which showed a clear upward trend. These visual tools collectively support the hypothesis that Turkish language support is associated with greater player engagement. Finally, actual vs. predicted plots were used to visualize machine learning model performance.

## 5. Machine Learning Prediction
To predict average player counts based on Turkish language support, I trained and evaluated three regression models: Random Forest, K-Nearest Neighbors (KNN), and Support Vector Regression (SVR). Cross-validation was used to ensure robust evaluation.

### 5.1 Random Forest Regressor
##### •MAE (Mean Absolute Error): 17062.94
##### •RMSE (Root Mean Squared Error): 69341.77
##### •R²: 0.009522

### Actual vs. Predicted Plot (RF)
![RANDOM FOREST](https://github.com/user-attachments/assets/df486f3a-0809-4824-8803-406dec0e1aa3)

This scatter plot displays how closely the Random Forest model's predictions align with the actual average player counts for the games analyzed. Each point represents a daily observation. The red diagonal line indicates perfect predictions—points closer to this line indicate more accurate estimates.

### Matrix (RF)
![matrix random forest](https://github.com/user-attachments/assets/a56281be-0a84-4bfc-9981-2c4ba0965c39)

The confusion matrix illustrates how well the Random Forest model categorizes average player counts into predefined usage bins (e.g., low, medium, high). Most predictions are concentrated along the diagonal, meaning the model generally predicted the correct or neighboring player range.

### 5.2 K-Nearest Neighbors (KNN) Regressor
##### •MAE (Mean Absolute Error): 32159.83
##### •RMSE (Root Mean Squared Error): 75138.05
##### •R²: -0.162987

### Actual vs. Predicted Plot (KNN) 
![KNN](https://github.com/user-attachments/assets/833acaca-a3ae-4b97-90e7-36cf29ff0354)

This scatter plot illustrates the relationship between the actual and predicted average player counts using the K-Nearest Neighbors (KNN) model. Most of the predictions are clustered in the lower player count range, indicating that the model captures general trends for less popular games. However, it struggles to accurately predict higher engagement levels, and the spread around the diagonal line suggests that individual predictions are not consistently close to actual values. The model shows limited sensitivity to variations across games with or without Turkish language support.

### Matrix (KNN)
![matrix KNN](https://github.com/user-attachments/assets/40b9c9ef-3aa7-40f6-a89c-2520686a5e05)

The confusion matrix for the KNN model reveals that while many predictions fall within the correct or neighboring average player count bins, there is noticeable misclassification, especially in mid-level ranges. This suggests that while the model can somewhat differentiate between general engagement levels, it lacks the nuance to distinguish between games with closer player counts, particularly when Turkish language support is a factor.

### 5.3 Support Vector Regression (SVR)
##### •MAE (Mean Absolute Error): 17028.37
##### •RMSE (Root Mean Squared Error): 69192.49
##### •R²: 0.013782

### Actual vs. Predicted Plot (SVR)
![matrix svr](https://github.com/user-attachments/assets/890dae77-8cbe-4fd9-8783-2b31bbc209d6)

This scatter plot displays the SVR model’s predictions against actual average player counts. A clear pattern of underpredicting high engagement games and overpredicting low engagement ones is observed, with many points straying from the red diagonal line. This suggests that SVR struggles to capture the true variance in the data, particularly when Turkish support influences game popularity.

### Matrix (SVR)
![matrix svr](https://github.com/user-attachments/assets/6013c9af-d25a-4141-83bb-8c13efd0562d)

The SVR model's confusion matrix shows that most predictions fall into central average player count bins, indicating a strong bias toward moderate values. Games with either very high or very low player engagement are often misclassified into these middle ranges, reducing the model’s overall reliability for nuanced prediction based on Turkish language support.

### Model Comparison

Among the three regression models tested—Support Vector Regression (SVR), Random Forest, and K-Nearest Neighbors—the SVR model achieved the best performance with the lowest MAE, lowest RMSE, and the highest R² score. While all models used a single binary feature (Turkish language support), SVR showed a better ability to generalize and estimate player engagement patterns compared to others. Its balanced predictions across different engagement levels made it the most reliable model for estimating average player counts based on the availability of Turkish language support in Steam games.

## 6. Limitations and Future Work

### 6.1 Limitations
##### •Turkish language support is treated as a binary variable (1 = Yes, 0 = No), which may not capture varying levels of localization quality or cultural relevance.

##### •Player engagement is influenced by many external factors (e.g., seasonal sales, game updates, global events) that are not accounted for in the dataset.

##### •The dataset includes only five games and a limited time window, which constrains the generalizability of the results.

##### •Review scores and player counts can be affected by temporary spikes in popularity, game patches, or controversies unrelated to language support.

### 6.2 Future Work
In this study, I focused solely on whether Turkish language support is available or not. Future research could enhance the dataset by including additional features such as pricing, game genre, DLC availability, marketing campaigns, and localization depth. Furthermore, expanding the number of games analyzed and incorporating other regions’ language preferences could provide a more comprehensive view of how localization affects global engagement. Tracking engagement trends across longer time spans (e.g., pre- and post-localization periods) would also offer more dynamic insights. Finally, player sentiment analysis from review texts could complement numerical metrics like average players and scores.

## 7. Findings
This project aimed to determine whether Turkish language support in Steam games affects player engagement and user reviews. Several key findings were obtained through exploratory data analysis, hypothesis testing, and machine learning:

#### •Games that offer Turkish language support had significantly higher average player counts than those that did not.

#### •A two-sample t-test confirmed the difference is statistically significant, returning a t-statistic of 4.06 and a p-value of 7.6e-05, allowing us to reject the null hypothesis.

#### •Correlation analysis between Turkish support and average players yielded a Pearson correlation coefficient of 0.20 with a p-value of 0.0010, indicating a weak but statistically significant positive relationship.

#### •A linear regression revealed a positive slope (β₁ = 0.06) and intercept (β₀ = -10437.39), suggesting that Turkish support is associated with increased player counts.

#### •Among the machine learning models tested (SVR, Random Forest, KNN), Support Vector Regression achieved the best performance, with the lowest MAE and RMSE and the highest R² value, indicating better generalization despite using a simple binary feature.

#### •Visualizations such as boxplots, histograms, and scatter plots supported the statistical findings and revealed clear distributional differences in player activity

## 8. Conclusion 
The analysis supports the original hypothesis: Games with Turkish language support tend to have higher player counts and more favorable user review scores from Turkish players. While the relationship is not extremely strong, it is statistically significant across multiple methods.

This suggests that localization—in this case, providing Turkish language options—can positively influence user engagement in the Turkish gaming market. The insights derived from statistical testing, correlation, and machine learning models reinforce this conclusion. The findings highlight the importance of language accessibility in game design and international marketing strategies.

Although the dataset was limited in scope, the methodology demonstrates how data analysis and predictive modeling can uncover meaningful patterns in user behavior. Further expanding the dataset and refining features could strengthen these results and contribute to better-informed decisions in the gaming industry.




