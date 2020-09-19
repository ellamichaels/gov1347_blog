# Economy
## September18, 2020

**_"It's the economy, stupid."_**

Bill Clinton’s campaign manager, James Carville, famously [coined this phrase](https://www.cnn.com/2020/05/08/opinions/economy-2020-election-trump-biden-zelizer/index.html) leading up to the 1992 presidential election. Candidate Clinton’s campaign played up the early 90s recession in order to unseat successfully incumbent president George H. W. Bush. This quip only dates back to 1992, but the general wisdom that the economy plays a major role in election outcomes is probably about as old as democracy itself.

But “the economy” is a big concept. It includes indicators like stock market performance or annual gross domestic product (GDP) that measure the health of the national economy. It also includes things like real disposable income (RDI) or local unemployment rates that reveal less about national-level economic health but paint a clearer picture of the state of voters’ pocketbooks. While each measure is certainly related to the others, they tell slightly different stories about election outcomes. Here, we’ll assess the relationship between a variety of different economic indicators and past election outcomes, and what the data suggest about the upcoming 2020 presidential election.

### Methodology and Terms
For these purposes, we’ll focus on economic indicators from the second fiscal quarter of presidential election years. Research suggests that voters weigh the year or few months leading up to an election more heavily than the rest of an incumbent’s term in office. [(Healy and Lenz, 2014)](https://hollis.harvard.edu/primo-explore/fulldisplay?docid=TN_cdi_gale_infotracacademiconefile_A354446646&context=PC&vid=HVD2&search_scope=everything&tab=everything&lang=en_US)


We’ll build predictive models around three variables to identify how they impact the popular vote share of incumbent political parties:
- Second quarter GDP growth
- Second quarter RDI growth
- The change in the unemployment rate between Q1 and Q2

If it is true that voters consider each of these indicators at the ballot box, stronger economic performance (i.e. higher GDP and RDI growth and larger decreases in unemployment rates) would track with higher popular vote shares for incumbents.

In order to evaluate the performance of each model, we’ll consider the following tests:
- **Statistical significance** (cutoff: p < 0.05)
- **R-squared value:** This is a measure of how much variance in a data set is explained by the model. The R-squared value evaluates the _in-sample fit_ of the model, namely how well the model fits the data it is based on. Formula: R^2 = 1 - (unexplained variance / total variance in data set)
- **Cross-validation:** Cross validation applies a model to random subsets of its original sample. It evaluates the _out-of-sample fit_ of the model, namely how well it fits data sets it is not based on.
