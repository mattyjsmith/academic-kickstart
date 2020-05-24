+++
date = 2017-12-01
title = "Net Survival"
subtitle = "Survival analysis in observational studies when the cause of death is unknown"

+++

## Motivation
A common question asked by researchers, and members of the public, is "*how long are people expected to survive beyond their diagnosis of cancer*?" For several reasons, this can be a very tricky question to answer. To answer this question we could start by looking at the current population of people with cancer and record how long they have been alive since their diagnosis. We could then take an average over all of these people and come up with a probability for a certain time period; for example, an interpretation of this calculation could be "70% of people with cancer were alive at 5 years after their diagnosis". However, there are a number of factors which we have not taken into account, which can bias our estimate of "70%". One of these factors could be whether or not the patient died of their cancer or from other causes (also known as competing risks). So, how can we obtain an estimate of survival that is unbiased?

## Clarification
There are many measures of survival in both randomised controlled trials and observational studies. Here, I focus on one measure of survival that is most commonly used for cancer survival estimates in population (observational) studies: this estimate is called **Net Survival**.

Before we go any further, it is beneficial to give some clear definitions. *Survival* is the percentage of the population alive at a certain time, given that these people have survived up to that time. *Net survival* is the estimated survival of patients, where this estimate accounts for the competing risks of death. In other words, and in this context, it is the survival of cancer patients that would be observed if their cancer were the only possible cause of death. Survival is commonly mistaken as a rate; this is because the estimate for a survival probability is derived from an estimate of the *hazard*, which is a rate. I do not go into the specifics here, but it is only correct to use the term *survival* as a *probability* statement and **not a rate**.

There are two settings when exploring survival of patients with cancer: the cause-specific setting (where the cause of death is known), and the relative survival setting (where the cause of death is unknown or unreliable). In the cause-specific setting, we can estimate the average length of time until death due to the cancer amongst only the patients who have died from the cancer; and we censor the cancer patients who have died from other causes. When the cause of death is not known, patients who have died could have died from the cancer or another cause; in which case, we cannot simply select the patients who have died only from the cancer. Instead, we can estimate the survival amongst all of the patients in our study and "account" for the other causes of death by weighting the survival of each patient by the mortality rate in the population: the information for the mortality rate is found using population life tables. We now explain this process in further detail.

## Net Survival
Net survival was more clearly defined by [Maja Pohar Perme *et al*](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1541-0420.2011.01640.x) in 2012: this method is called the **Pohar Perme** estimate of net survival. Prior to the Pohar Perme method, other methods of survival were thought to have been estimating net survival but were in fact estimating something slightly different: the relative survival ratio. Such methods were [Ederer I](https://scholar.google.com/scholar_lookup?hl=en&publication_year=1961&pages=101-121&author=F.+Ederer&author=L.+M.+Axtell&author=S.+J.+Cutler&title=The+Relative+Survival+Rate%3A+A+Statistical+Methodology), [Hakulinen](https://www.jstor.org/stable/2529873?origin=crossref&seq=1), and [Ederer II](https://scholar.google.com/scholar_lookup?hl=en&publication_year=1961&pages=101-121&author=F.+Ederer&author=L.+M.+Axtell&author=S.+J.+Cutler&title=The+Relative+Survival+Rate%3A+A+Statistical+Methodology).

To estimate net survival, we first decompose the *observed hazard* (i.e. the hazard across all patients in our dataset) into the *population hazard* (i.e. assumed to be the hazard due to other causes) and the *excess hazard*, that is:
![image](https://user-images.githubusercontent.com/33094651/74594443-60255b00-502e-11ea-86bf-25e0ebc7f237.png)

A survival estimate derived directly from the excess hazard is termed **Net Survival**. Notice in the diagram above that the observed hazard is the summation of the population hazard and the excess hazard, so we are assuming the observed hazard will always be greater than the population hazard.

Here we are making some very important assumptions. We first assume that the time to death due to the cancer and the time to death due to other causes are conditionally independent given a set of known covariates (i.e. the patient's age at diagnosis, gender, deprivation, and calendar year at time of diagnosis). It is by this very assumption that cancer survival estimates from one country can be compared to survival estimates from another country, because accounting for the background population mortality for a country makes the survival estimate for that country independent of the background population mortality.

Estimating the excess hazard requires allocating each cancer patient with an expected mortality rate from population life tables. Life tables are usually stratified by at least age and gender because the mortality rate can differ greatly between the young and older, or male and female, patients. Another demographic variable considered for stratification is socioeconomic status; however, much like ethnicity or comorbidity status, the records for these variables are not always available. The [inclusion of additional demographic variables](https://academic.oup.com/biostatistics/advance-article-abstract/doi/10.1093/biostatistics/kxz017/5499194) have been shown to improve the estimate of net survival and should be included where possible.


(Constantly updated, the author is lethargic...)
