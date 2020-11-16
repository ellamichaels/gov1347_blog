# Final Prediction
## November 1, 2020


[**Appendix**](final_appendix.md)

### Prediction
![](../figures/final_prediction.png)
![](../figures/final_prediction_bar.png)

Using a model based on polling, demography, and incumbency, I predict that **Joe Biden will win the 2020 presidential election with 312 electoral college** votes to Donald Trump’s 226. In ten states, with a collective 163 electoral college votes (more than enough to tip the balance of the election) the difference in predicted vote shares between the two candidates is less than 5%, within the margin of error. 

State-by-state predictions roughly parallel [aggregated forecasts](https://www.270towin.com/maps/consensus-2020-electoral-map-forecast). In this forecast, some notable results include the following: Biden wins Georgia, Iowa, and most of the Rust Belt but Trump picks up Florida, Ohio, and North Carolina (incredibly narrowly). To see state-by-state vote shares, see the [appendix](final_appendix.md). 

## Model Overview
For each party, I created a weighted ensemble of two linear regression models to predict state-by-state two-party vote share using data from elections between 1976 and 2016 (demographic variables were available starting in 1988).

**Model 1:** ``lm(party_pv2p ~ state + party_polling + incumbent, data = full)``

The first model incorporated the following independent variables:

- _**Weighted candidate polling average from September and October.**_ I used polling data from [FiveThirtyEight]( https://data.fivethirtyeight.com/), current as of 2pm ET on October 29. Ideally, I would have just used October polling because polling numbers closer to an election date are far more predictive, but data available from credible pollsters (i.e. not [banned](https://projects.fivethirtyeight.com/pollster-ratings/) by FiveThirtyEight) only included numbers for 40 states. As such, I included September polling to cover the entire country. I created a weighted average for each state weighting proportionally based on sample size.
- _**Incumbency Term**_  
- _**State Term**_ to calibrate for historical voting behavior by state

**Model 2:** ``lm(party_pv2p ~ change*White, data = full)``

The second model incorporated the following independent variables:

- **_Change in non-white (POC) population_** share (percentage) since the previous presidential election
- **_White population share_**
- **_Interaction term_** between POC population change and White population

**Weighting**

I weighted the two models based on their R^2 values (what Nate Silver does for FiveThirtyEight’s election forecast, according to the Election Analytics Glossary™). The weights varied slightly by party, but hovered around an 85-90% weight for Model 1 and a 10-15% weight for Model 2. 

## Explanation

I selected my predictive metrics in large part based on the fact that 2020 is a very atypical year and election, and many independent variables that might normally work very well in a model are likely to be far less predictive this year than most. Economic fundamentals, for example, tend to generate incredibly skewed results given COVID and its implications. As for shocks, it is generally challenging to predict exactly what the impact of fairly unprecedented events will be. COVID deaths and other follow-on effects are almost certainly going to affect election outcomes, but it is difficult to know precisely how much.

This year more than most, polling is likely to be our best predictive bet. As we’ve observed throughout the course, while polling is hardly perfect, it’s tough to beat their predictive power with other measures, even in a typical election year. Furthermore, polling is often a [measure](https://hollis.harvard.edu/primo-explore/fulldisplay?docid=TN_cdi_gale_infotracacademiconefile_A14564056&context=PC&vid=HVD2&search_scope=everything&tab=everything&lang=en_US) of how much fundamentals and other electoral factors are impacting voters. Other survey-based measures like presidential approval seemed a little redundant given that I was incorporating polling and I didnt’ want to overfit.

Another factor I incorporated was demographic data. Given the effect of response bias on polling numbers, the demographics of the electorate can certainly influence how much to weight different polling results and impact predictions (just ask 2016 pollsters). Finally, I also incorporated incumbency. I [frankly think](incumbency_4.md) incumbency won’t have a huge impact in this election, and as discussed below, my models don’t either in terms of predicted vote share (less than a 1% bump for Trump). That said, I was a little spooked by how bullish my predictions are for Biden and amenable to incorporating more factors that might give Trump an advantage. Notably, **omitting incumbency from my model flips North Carolina** to a Biden state. Guess we’ll see on Tuesday. 


### Model 1 Results

Note that this model included a calibration term for each state. Full model results with coefficients for each state are in the [appendix](final_appendix.md) but omitted here for space. Coefficients, standard error, confidence intervals, and p-values are below:

![](../figures/r_poll_gt.png)
![](../figures/d_poll_gt.png)

Democrat and Republican iterations of Model 1 had R-squared values of .835 and .738, respectively, indicating strong in-sample performance (explaining 70+% of in-sample variation)

## Model 2 Results

Coefficients, standard error, confidence intervals, and p-values are below:

![](../figures/r_demo_gt.png)
![](../figures/d_demo_gt.png)

Democrat and Republican iterations of Model 1 both had R-squared values of .075. Demographics can only explain so much of an election's result, but results were statistically significant.

## Uncertainty

Notably, many states have razor thin margins of victory. There are margins of less than 5% in ten states (shaded lighter) and less than 3% in AZ, FL, GA, IA, NC (collectively 163 electoral votes, more than enough to sway the election) and well within the margin of error of this model.



