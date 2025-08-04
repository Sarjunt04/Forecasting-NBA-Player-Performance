# Forecasting-NBA-Player-Performance
Applying Bayesian hierarchical modelling to predict how NBA player's perform at different ages

This was a personal project undertaken March 2025. Using Box-Plus-Minus (an aggregate statistic) as a measure (proxy) for player performance, I first explored linear options, before utilising a Bayesian modelling scheme for more effective forecasting. The final formula involved a random effect for age given player, and one for team. So each age effects each player differently, and each team effects player performance differently. I used data from the last 20 seasons.

First, I scraped data from basketball-reference, filtered for players who'd played at least 400 minutes per season, and conducted an EDA. Having decided on some ideas for modelling, I first fit an OLS model, then a hierarchical OLS, and finally a Bayesian hierarchilcal model. Priors were determined using the EDA and inspection of model performance.

Model fit and forecasting was quite acceptable, even with the simple formula, a variety of age effects were captured. There were two key issues: modelling the first few years of athletes who performed exceptionally well early on, and forecasting players getting older (where the lack of data for 40+ year olds in the league meant that predictions didn't decline at a reasonable pace). To fix these, using splines could help, as the formula here, which is based on log(age) and log(age^2), has a gradient with constantly declining magnitude, once the value for age is past 27.
