+++
date = 2017-12-01
title = "Missing data analysis"
subtitle = "Missing data analysis when you are *happy* that your data is missing at random"

+++

## Motivation

Data, data, data... you hear about it all the time, perhaps in the news, chatting with friends, or maybe at your place of work. But how much data is there, how do we collect it, and what happens when data collection goes wrong?

There is so much data in the world that it is hard to imagine how it all gets stored. For example, Google was said to process 20 petabytes of data per day, and the IDC predicts that there will be 175 zettabytes of data by 2025.

*"Wait a sec, what was that, petabytes and zettabytes?"*

My head is hurting already. A zettabyte is 1000 exabytes, an exabyte is 1000 petabytes, a petabyte is 1000 terabytes, and a terabyte is 1000 gigabytes. Now, considering that an iPhone can hold 256 gigabytes, then holding a zettabyte in your hand is the equivalent of holding approximately 4 trillion of these iPhones in your hand... *"woah, this is heavy!"* In other words, if you stacked a zettabyte's worth of data on CD-ROMs then you would be able to reach the moon and a quarter beyond it and then be able to do it again another 999 times until which point you ran out of data.  

This abundance of data can be collected in any number of ways. For example, information on patients who have been tested for the coronavirus (the devastating global pandemic of 2020) is usually collected by healthcare professionals and stored on a government database (if the country has this electronic system in place). Depending on how many patients are tested, and how much information was collected on each patient, the data that is stored could be as small as 1 gigabyte or as large as a terabyte, maybe even more. However, having more data does not necessarily guarantee that you have more information. For example, if you were to routinely collect data on your health (e.g. blood pressure, heart rate, height, weight, etc.) for 30 days you would probably have a record for each of those health factors on each of those days. But when it comes to big data that is collected on multiple patients at multiple time points, such as coronavirus cases or cancer cases, then the quality of the data (i.e. the completeness of the records) can start to dwindle. There are as many reasons for the dwindling of the records as there are zettabytes in the world.

*"Okay, so big data is not necessarily always a good thing because there can be an incompleteness of records. But, what can we do about it?"*

This is where missing data analysis can be an extremely useful tool.

## Clarification

Continuing with our coronavirus example, imagine we wanted to understand which patient characteristics are associated with an increased chance of having coronavirus, or dying from coronavirus. Imagine we sample 20 patients from a hospital and collected information on their age, gender, and whether: they received a test, the test was positive, they died, and had died due to coronavirus. The table below shows ours data...

![image](https://user-images.githubusercontent.com/33094651/79448285-14187780-7fd9-11ea-8680-24161a1c9937.png)

So far, no problems. But if we were to gather data on all patients (from 1, ..., n patients) with coronavirus then we may miss a few records. The data below shows that there are now some empty cells for age, positive test, and death due to COVID-19.

![image](https://user-images.githubusercontent.com/33094651/79450586-f9480200-7fdc-11ea-8094-75dda28598ab.png)

We could select only those patients with complete records for each variable, such as out of the first 25 patients. However, selecting only patients with complete records would result in having only 11 patients within our sample... (Note: a variable is a set of measurements for n number of patients).

![image](https://user-images.githubusercontent.com/33094651/79451608-b5ee9300-7fde-11ea-9d7e-c7142703153d.png)

Reducing our dataset to only a few patients would bias our results and lose efficiency (i.e. large standard errors). Modern statistical methods can utilise all of the available data to reduce the bias and increase efficiency. So, what statistical methods are available to us, and how can we use them?

## Statistical Methods

**Missing data pattern**

Knowing the pattern of the missing data is important for several reasons. Firstly, it can indicate why the data is missing and whether we can physically recover the data. Secondly, it provides a justification of the choice for our statistical method, which we will discuss later. Lastly, having a monotone missingness pattern can simplify the methods used to reduce bias and increase efficiency.

Suppose we have a set of **J** partially-observed variables measured on a set of *i* patients, the dataset will have a monotone missingness pattern if:

1. the measurement for patient *i* is observed for all variables of *x*, where *x* = 2, ..., *J*, up to *x*' < *x*, and

2. the measurement for patient *i* is missing for all variables *x*' > *x*.

Less formally, an example of a monotone missingness pattern could arise in a longitudinal study where patients are required to attend a clinic on regular timely occasions (such as every month) and an aspect of their health status was measured (such as blood pressure). If a patient decided not to follow through with the study on any particular occasion and subsequently did not attend the following check-ups, the remaining measurements of their health status would be 'missing'. A non-monotone missingness pattern would arise if this patient (and other patients) attended the clinic after already missing previous check-ups.

**Missing data mechanism**

Before embarking on running a "magical" software package to, for example, impute our missing data, we must first consider what we are assuming about the missing data.




## Multiple Imputation


(Constantly updated, the author is lethargic...)
