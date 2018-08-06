---
Title: COMPAS
Template: ListSubPages
---

### WIP

## COMPAS

COMPAS is a risk assessment tool originally created by Tim Brennan in 1998.\cite{toby1} It takes data from both a questionnaire presented to an arrested individual and an interview performed with them\cite{calliope1} to output recidivism risk in deciles.\cite{calliope3}
Originally intended to be used as a tool to help determine probation periods\cite{joseph_brennan}, COMPAS is now employed in several states to determine sentence lengths, notably in Wisconsin.\cite{joseph_loomis}

## ACCURACY

The Practitioners Guide to the COMPAS score\url{https://assets.documentcloud.org/documents/2840784/Practitioner-s-Guide-to-COMPAS-Core.pdf} indicates that COMPAS gathers 5 main scores from the data collected and performs a weighted average of those scores, ie

$$R=\sum_{n=1}^Nw_nx_n$$

For the scores $x_n$ and weights $x_n$, $N=5$. This is a troubleingly simple model, where most would suspect some complexity or machine learning to take place. Dressel and Farid (2018) found that even with only two variables, their own algorithm can emulate the accuracy of COMPAS.\\
Furthermore, 400 humans from Amazon's Mechanical Turk were asked to perform the same task as COMPAS using the same information available. The results were that the humans had approximately the same accuracy as COMPAS.

## FAIRNESS

ProPublica has published multiple articles criticizing the fairness of COMPAS. Here, fairness specifically refers to disproportionately classifying people of one race as recidivists or violent recidivists despite being similar to members of another race. That is to say, the algorithm being racist. While COMPAS itself doesn't take race as a factor in its data, it does have input the postcode and family history of a convict. In many areas of America, neighbourhoods are heavily segregated by race, and the history of one's family being arrested can be used as a proxy for someone's race.

## PROPUBLCIA ANALYSIS

ProPublica’s analysis of COMPAS (Julia Angwin, n.d.) makes use of datasets obtained from the
Broward County sheriff’s office in Florida detailing risk scores assigned to defendants prior to trial as
well as sentencing statistics for the county. It consists of two main tests.
The first test involved fitting a logistic regression model to the data and looking at how individual
features are weighted in the model to study their correlation with high COMPAS scores, adjusting for
controlling for variation amongst classes in the population. From this ProPublica were able to
conclude that women are 19% more likely than men to be predicted high recidivism scores, black
defendants are 45% more likely, and defendants younger than 25 are 250% more likely.
The same test was done looking at scores for violent recidivism. Black defendants were 77.3% more
likely to receive a high score and young defendants were found to be 640% more likely.
The second statistical technique was a Cox proportional hazard model, the same test used by
Northpointe in their analysis of COMPAS’ effectiveness. On the whole ProPublica found less
significant scores from the test, although Northpointe dispute the correctness of ProPublica’s
methods (William Dieterich, 2016).