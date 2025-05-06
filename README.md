# DSA-210-PROJECT

# Introduction 
The aim of this project is to analyze whether games with Turkish language support on Steam are purchased and preferred more by the Turkish gaming community compared to similar games that lack Turkish language support.  

# Hypothesis
Games that offer Turkish language support on Steam are more likely to be purchased and preferred by Turkish players than similar games that do not provide Turkish language support. I believe that language accessibility plays a significant role in game selection among Turkish gamers.  

# Motivation  
I have observed that many games on Steam lack Turkish language support, yet Turkish players often request localization. This project aims to understand whether language support directly affects purchasing behavior. The findings may highlight the importance of localization for developers targeting the Turkish gaming community.  

# Data Source 
I will collect data from Steam, including sales figures, user reviews, and community discussions. I will compare the sales and popularity of games with and without Turkish language support within the same genre. Since all the data will be publicly available on Steam, there should be no ethical or privacy concerns.  

# Project Plan 
- Identify and list games with and without Turkish language support in specific genres.  
- Collect relevant data such as sales numbers, user reviews, and ratings.  
- Analyze the data using charts and descriptive statistics to compare trends.  
- Test the hypothesis by evaluating whether Turkish-supported games have a higher purchase rate and preference among Turkish players.  
- Draw conclusions on the impact of Turkish language support on game sales and player choices.

# Data Analysis

## 1. Collecting Data
I gathered daily Steam concurrent‐player data for two games—The Witcher 3: Wild Hunt (with Turkish language support) and Sekiro™: Shadows Die Twice (without Turkish support)—over a two‐week period (13/04/2025–26/04/2025). For each date and each game, I recorded:

Average Concurrent Players

Peak Concurrent Players

Review Score (%)

Price (USD)

All data were pulled from Steam’s official store page, SteamDB, and Steam Charts and stored in an Excel file for analysis.

I then grouped entries by whether the game offers Turkish support:

Turkish Support: The Witcher 3

No Turkish Support: Sekiro

## 2. Exploratory Data Analysis (EDA)
Using pandas, matplotlib, and seaborn, I carried out exploratory data analysis to examine whether Turkish language support in games affects player engagement, focusing on average player counts. After cleaning and formatting the dataset, I produced several visualizations to uncover usage patterns.

A histogram revealed that while most games have lower average player numbers, a few titles attract significantly higher engagement. The boxplot comparison showed that games with Turkish support tend to have both higher median values and a wider distribution, indicating greater player interest. The bar chart confirmed this, with Turkish-supported games averaging 11,730 players, compared to 4,849 for others. Lastly, a regression scatterplot showed a clear upward trend, suggesting a positive linear relationship between Turkish language support and player count.

### 2.1 Histogram

![histogram](https://github.com/user-attachments/assets/0f85db01-da63-44ee-a9eb-57fd97a0cba8)

The histogram shows the distribution of average players across all games. Most values are spread widely, but a noticeable peak exists at lower player counts.


### 2.2 Boxplot

![boxplot](https://github.com/user-attachments/assets/94c76a04-6ce2-4c09-93f1-e32c740ec0c3)

This boxplot compares the average player count between games with and without Turkish language support. The median and spread are significantly higher for games that offer Turkish.


### 2.3 Bar Chart

![barchart](https://github.com/user-attachments/assets/f5325973-8c35-46df-918a-561d7a8190e0)

This bar chart visualizes the average player count by language support:

Games with Turkish support: ~11,730 average players

Games without Turkish support: ~4,849 average players


### 2.4 Scatterplot with Regression Line

![linear](https://github.com/user-attachments/assets/70a0e3d0-9383-4709-8296-09fe905364c2)

This scatterplot with a regression line shows the relationship between Turkish support (0 = No, 1 = Yes) and average player count. The clear positive slope suggests that Turkish language support correlates with higher player numbers.


## 3. Hypothesis Testing
I formulated the following hypotheses to test the statistical difference in player engagement between games with and without Turkish support:

Null Hypothesis (H₀): There is no significant difference in average player counts between the two groups.

Alternative Hypothesis (H₁): Games with Turkish support have significantly higher average player counts.

An independent samples t-test was applied, resulting in a t-statistic of 38.42 and a p-value of 5.494828e-19. Since the p-value is far below the 0.05 threshold, the null hypothesis is rejected. This means the difference in player engagement is statistically significant and supports the idea that Turkish language support has a meaningful impact on a game's popularity among players.

## 4. Visualization Summary
To better understand the player engagement patterns, I visualized several aspects of the dataset. A histogram was used to display the overall distribution of average player counts, highlighting the concentration of player activity across games. Then, a boxplot allowed me to examine how the central tendencies and variability differ between games that support Turkish and those that do not, making the contrast in median values and outliers visually apparent. I also included a bar chart to present the mean average players for each group, emphasizing the performance gap between the two categories. Lastly, a scatterplot with a regression line was plotted to capture the trend between Turkish language support and player activity, clearly suggesting a positive linear association. Additional visualizations such as segmented trend lines over time or comparative density distributions could further enrich the analysis if temporal or genre-based insights are desired.
