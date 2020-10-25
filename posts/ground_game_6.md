# Demographics and Turnout
## October 17, 2020

### Introduction
We’ve learned over the past few weeks that campaigns sometimes have more power to mobilize voters and increase turnout than they do to persuade them of a certain political ideology. When people think about what factors influence election outcomes, overall public opinion is probably the first that comes to mind. But when less than half of eligible voters go to the polls even during national-level elections, it’s worth bearing in mind that turnout might be even more decisive. How many people turn out to vote? Who are they? And whom do they vote for?

### Turnout Over Time

The US is home to about [233 million eligible voters](https://www.pewresearch.org/2020/09/23/the-changing-racial-and-ethnic-composition-of-the-u-s-electorate/) but far fewer than cast a ballot in the typical election 

![](../figures/turnout_trends.png)

Between 1980 and 2014, **the average turnout for a presidential election was 52% and the average turnout for a midterm election was 42%**. This is consistent with the general trend that higher profile elections generate more attention and discourse which is associated with higher turnout. There has been some fluctuation in turnout since 1980, with a spike in 2008 during Obama’s first campaign, but no distinct trends over time apart from the clear pattern that midterm elections mobilize fewer voters.

2020, however, likes to be an outlier. Experts anticipate [record turnout](https://www.brookings.edu/blog/fixgov/2020/08/14/election-2020-a-once-in-a-century-massive-turnout/) as polling suggests that a record number of Americans consider the results of this election to be of great importance. Increased VBM and early voting access which theoretically make it easier to vote also play a role. 


### Turnout by State
Turnout is not evenly distributed across states. In 2014, Maine had the highest turnout at about 58%, more than twice that of Indiana which had the lowest turnout at about 28%. 

![](../figures/state_turnout_2014.png)

**States with higher Black and Hispanic populations tend to have lower turnout**. Modeling the effect of higher URM populations on turnout reveals that on average, a one percentage point increase in a state’s African American population is associated with a 0.38 point decrease in turnout. Similarly, a one percentage point increase in a state’s Hispanic population is associated with a 0.31 point decrease in turnout. Histories of disenfranchisement and [voter suppression](https://www.brennancenter.org/our-work/research-reports/new-voter-suppression) are likely behind these figures.

![](../figures/race_turnout.png)

### Democrats and Demographics
While underrepresented minorities ([URM](https://diversity.ucsf.edu/URM-definition)) generally vote at lower rates, their numbers are growing. Between 1990 and 2018, the URM share of the US population increased by about 50% from 20% to about 30%. 

![](../figures/urm_share.png)

What implications do demographic changes and turnout have for election outcomes. Modeling the effect of turnout and URM population share on win margins for the democratic party demonstrates that **higher turnout and more diverse populations benefit Democrats and disadvantage Republicans**.
- A one-point increase in turnout is associated with a 0.14 point increase in the win margin for Democrats
- A one-point increase in URM population share is associated with a 0.23 point increase in the win margin for Democrats.

And by extension Republicans experience a commensurate decrease in response to each of these changes. 

![](../figures/turnout_race_dmargin.png)

### Predictive Implications

**Race**

As the US population grows increasingly diverse, the Democratic party will benefit electorally.

**Turnout**

Higher turnout typically favors Democrats, and turnout is expected to hit record highs in 2020. Turnout volatility, however, also makes it more difficult to predict election outcomes.

538’s explanation of its 2020 forecast [explicitly addresses](https://fivethirtyeight.com/features/how-fivethirtyeights-2020-presidential-forecast-works-and-whats-different-because-of-covid-19/) both of these considerations. They note that higher turnout tends to increase Democrat vote shares. They also note that not only is turnout harder to predict during the pandemic, large swings in turnout also make projections more volatile. They estimate a 20% increase in error when predicting each party’s vote share.

While the [Economist’s model](https://projects.economist.com/us-2020-forecast/president/how-this-works) certainly takes turnout into account, it does not address the unique problems that 2020 poses head on in the same way that 538’s approach does. Given how much of an outlier 2020 is, and the centrality of turnout to election predictions, particularly the binomial logit approach the Economist model is built around, this seems like an oversight. 

