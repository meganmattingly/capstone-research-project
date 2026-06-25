# Market Value Analytics: Informed Decision Making for Soccer Clubs

This repository contains code files associated with my capstone reseach project, which was completed during the Spring 2026 semester. I wanted to apply various types of predictive modeling to the realm of soccer analytics, as a way to blend academic and personal interests. I developed a regression model to predict an individual player's market value based on performance statistics and a time series forecasting model to predict average player market value in the long term. In addition, I created an interactive dashboard to showcase these results in a way that is accessible to non-technical stakeholders. 

## Data Background

The data for this project originally came from Transfermarkt, a popular soccer website, and was then posted on Kaggle. It contains information on a variety of topics, but I focused on data related to player market valuations, which was included for the last 20 years, and individual performance, which was included for the last 13 years. The target feature for this analysis is a player's market value and predictors include demographic information (age, position, club, etc.) and performance statistics (minutes played, goals, assists, etc.).   

## Analytic Approach

TBD

## Results

Forecasting results
<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/be56af1d-070a-492d-857b-25423b4c8ebc" />

CatBoost results
<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/5760aff3-eefc-4a19-952f-c8178e61376b" />

Tableau dashboard

<img width="600" height="300" alt="Screenshot 2026-06-25 160613" src="https://github.com/user-attachments/assets/25fbb3e1-bab1-41ff-b278-dc95f6b54497" />


## Areas for Future Analysis

The biggest limitation for this analysis is the lack of publicly available data. Soccer clubs spend a lot of time, money, and resources trying to answer this same question, so it's fair to assume that they are not going to share the information used in their models. Also, they likely have access to more complete, higher quality data, which creates better results. However, if data was available, it would be interesting to incorporate the following concepts into future analysis:

- International performance (if applicable): players that compete for their country typically earn higher contracts
- Injury history: players that struggle with chronic injuries are riskier signinings
- Level of competiton: this may be difficult to quantify, but good performance against high-quality opponents is more impressive than against lesser-quality opponents

Finally, it would be worthwhile to experiment further with other types of algorithms and/or other methods of feature selection. This analysis was completed during the course of a single semester, but if time was not a constraint, more thorough experimentation could be done, creating a better model in the end. 
