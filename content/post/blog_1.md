+++
date = 2017-12-01
title = "Net Survival"
subtitle = "Survival analysis in obervational studies when the cause of death is unreliable"

+++

A common question asked by researchers, and members of the public, is "*how long are people expected to survive beyond their diagnosis of cancer*?". For several reasons, this can be a very tricky question to answer. To answer this question, we could start by looking at the current population of people with cancer and recording how long they have been alive since their diagnosis. We could then take an average over all of these people and come up with a probability for a certain time period, for example 70% of people with cancer were alive at 5 years after their diagnosis. However, there are a number of factors which we have not taken into account, which can make our estimate of '70%' biased. One of these factors could be whether or not the patient died of their cancer or from other causes (also known as competing risks). So, how can we obtain an estimate of survival that is unbiased?

There are many measures of survival in both randomised controlled trials and observational studies. Here, I focus on one measure of survival that is most commonly used for cancer survival estimates in population (observational) studies: this estimate is called **Net Survival**. 

Before we go any further, it is beneficial to give some clear definitions. *Survival* is the percentage of the population alive at a certain time, given that these people have suvived up to that time. *Net survival* is the survival of patients where the cause of death is due only to the disease under study. In other words, and in this context, it is the survival of cancer patients that would be observed if cancer were the only possible cause of death. Survival is commonly mistaken as a rate; the reason for this is because the estimate for a survival probability is derived from an estimate of the *hazard*, which is a rate. I do not go into the specifics here, but it is only correct to use the term *survival* as a *probability* statement and **not a rate**.

Net survival is an estimate of survival that was more clearly defined by [Maja Poher Perme *et al* in 2012](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1541-0420.2011.01640.x).  














