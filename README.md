# Market Value Analytics: Informed Decision Making for Soccer Clubs

This repository contains code files associated with my capstone reseach project, which was completed during the Spring 2026 semester. Various types of predictive modeling were applied to the realm of soccer analytics, as a way to blend academic and personal interests. Sports analytics is a rapidly growing field and there is a desire for data driven insights, especially in terms of recruiting. Clubs want to add players that will add value to their rosters, while also limiting cost. Therefore, they may try to find "undervalued" players, meaning their potential value is higher than what their current market value suggests. 

To attempt to address this challenge, a regression model was developed to predict an individual player's market value based on performance statistics and a time series forecasting model was developed to predict average player market value in the long term. In addition, interactive dashboard was created to showcase these results in a way that is accessible to non-technical stakeholders. 

## Data Background

The data for this project originally came from Transfermarkt, a popular soccer website, and was then posted on Kaggle. It contains information on a variety of topics, but I focused on data related to player market valuations, which was included for the last 20 years, and individual performance, which was included for the last 13 years. The target feature for this analysis is a player's market value and predictors include demographic information (age, position, club, etc.) and performance statistics (minutes played, goals, assists, etc.).   

## Analytic Approach

The first type of model developed for this project was the time series forecasting model. This allows executives to estimate how much, on average, they will be spending on players in the future, which is important for salary cap allocation and long-term planning. Since the data contains players from many leagues, each with different revenue and salary levels, the time series was split into two groups: players in the Big Five leagues (Premier League, La Liga, Serie A, Ligue 1, Bundesliga) vs. all others. The baseline forecast was created by simply projecting the historical average value. Due to the lack of clear trend and high variability in the data, this was a reasonable starting point. Next, an ARIMA model was developed, which creates forecasts for each time series based on properties of the historical data. The RMSE was computed for each each model to determine which provides the most accurate forecasts. 

Next, a regression model was developed. This helps executives estimate how much a specific player will be worth next season, allowing them to make informed roster decisions. To begin, a linear regression model was considered, but it was not able to capture the complex relationships between features. Then, multiple boosting algorithms were considered, including Random Forest, XGBoost, and CatBoost. These models are fast, accurate, and can capture nonlinear relationships, making them more suitable for this project. In order to assess the performance of each model, the in-sample and out-of-sample RMSE were computed to determine the most accurate algorithm, while avoiding overfitting. The results were fairly similar and all were significantly better than a linear regression, but it was important to consider computational cost and interpretability for stakeholders.  

## Results

After comparing the forecasts from the two models, the historical average was selected due to its lower RMSE values for each time series. While the forecasts clearly do not capture the variability in the data, this is not too much of a concern. The variability is likely due to superstar players signing huge contracts, and since this is not very common, the forecasts shown below will likely be closer to actual values for the majority of players that clubs are considering signing. 

<p align = "center">
<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/be56af1d-070a-492d-857b-25423b4c8ebc" />
</p>

The chosen regression model was CatBoost due to its performance and ability to handle categorical features without encoding. Since this is a complex model, SHAP values were computed to explain each feature's impact on the final prediction. The plot below illustrates this for one observation. For example, a high market value last season increases the predicted market value for the next season, while being 30 years old and in the Super Lig (a smaller league) decreases predicted market value. 

<p align = "center">
<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/5760aff3-eefc-4a19-952f-c8178e61376b" />
</p>

Finally, an interactive dashboard for use by club executives. It contains predictions from both the forecasting and regression model and can be filtered based on a variety of criteria, including current market value, position, and age. Players meeting this criterion are sorted by their “potential value add,” which is their residual from the regression model, because a large, positive value represents an undervalued player. This helps executives find players that meet their budget and personnel requirements, meaning they can make informed decisions that will add value to their club. 

<p align = "center">
<img width="600" height="300" alt="Screenshot 2026-06-25 160613" src="https://github.com/user-attachments/assets/25fbb3e1-bab1-41ff-b278-dc95f6b54497" />
</p>

To view and interact with the dashboard, visit [this link](https://public.tableau.com/app/profile/megan.mattingly5449/viz/TransferMarktViz/Dashboard1). 

## Areas for Future Analysis

The biggest limitation for this analysis is the lack of publicly available data. Soccer clubs spend a lot of time, money, and resources trying to answer this same question, so it's fair to assume that they are not going to share the information used in their models. Also, they likely have access to more complete, higher quality data, which creates better results. However, if data was available, it would be interesting to incorporate the following concepts into future analysis:

- International performance (if applicable): players that compete for their country typically earn higher contracts
- Injury history: players that struggle with chronic injuries are riskier signinings
- Level of competiton: this may be difficult to quantify, but good performance against high-quality opponents is more impressive than against lesser-quality opponents

Finally, it would be worthwhile to experiment further with other types of algorithms and/or other methods of feature selection. This analysis was completed during the course of a single semester, but if time was not a constraint, more thorough experimentation could be done, creating a better model in the end. 
