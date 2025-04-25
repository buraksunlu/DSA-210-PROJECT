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
Using pandas and matplotlib, I examined how the player counts differ between these two groups.

### 2.1 Histogram

This histogram shows the overall distribution of daily average concurrent players across both games. You can see two distinct clusters:

![output](https://github.com/user-attachments/assets/052652bc-d99b-430c-87ee-546a8774972c)


### 2.2 Boxplot

This boxplot compares “No Turkish Support” vs. “Turkish Support.” The median and interquartile range for Witcher 3 are substantially higher than those for Sekiro, indicating consistently more players.
![output (1)](https://github.com/user-attachments/assets/469586f3-9151-4390-96a4-d36c1e4884fb)


### 2.3 Bar Chart

Average daily concurrent players by group:

![output (2)](https://github.com/user-attachments/assets/60753d38-267a-4987-af83-56a50adf4605)


## 3. Hypothesis Testing
H₀: There is no significant difference in average concurrent players between games with and without Turkish support.

H₁: Games with Turkish support have a higher average concurrent player count.

I performed an independent‐samples t-test on the two groups:

T-statistic: 38.42  
P-value:     3.10e-15 

Since p ≪ 0.05, we reject H₀, confirming that Turkish-supported games (The Witcher 3) attract significantly more concurrent players than similar titles lacking Turkish localization.

## 4. Visualization Summary
Histogram to view overall player‐count distribution.

Boxplot to compare medians and variability by support group.

Bar chart to illustrate the clear difference in mean player counts.

Further analyses might include time‐series line plots of daily trends or scatterplots relating price or review score to player counts.
