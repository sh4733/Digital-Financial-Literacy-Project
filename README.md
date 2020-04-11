# Digital-Financial-Literacy-Project
This is a repository for my data analysis project back in 2018, on digital financial inclusion and literacy in Korea.
The dataset is from [Global Findex Database 2017](https://globalfindex.worldbank.org/#data_sec_focus), a worldwide survey conducted by World Bank.

_Tools used: tidyverse (especially ggplot for visualization)_

## Motivation
Traditional measures of wealth like GDP per capita does not successfully capture the financial inclusion in the current era of digital finances and mobile banking. 
The project attempted to assess where Korea stands with regards to digital transformation and financial services.
This survey contains 1000 responses for 81 variables, and variables of interest were sorted out for further analysis.

Y variable: measure of financial inclusion
- _account ("has an account")_
- _fin5 ("used mobile phone or internet for payment")_
- _saved ("saved in the past year")_

X variable: selected ones that would likely affect the above Y values
- _female ("respondent is female")_
- _age_
- _educ ("respondent education level")_
- _emp in ("respondent is in workforce")_
- _inc q ("income level in quantiles")_

More details about the dataset and variables can be found in [this data dictionary](http://microdata.worldbank.org/index.php/catalog/3374/datafile/F3)

## Method
I set up 3 hypotheses for testing: that there is a gender gap in finance accessibility and education (females lagging), 
that older people tend to use online transactions less and save less due to lack of awareness and stable income, and that people become more vulnerable to financial insecurities with decreasing education and income levels

### Effect of Gender on Account Ownership
The tabulation of account holders by gender showed little difference; neither did the hypothesis testing showed significant difference 
in the probability of having an account by males and females. At least in Korea's case, both gender groups have a fairly similar proportion of account holders.

### Effect of Education Level on Account Ownership
I modeled for the probability of having an account on one's education levels with logistic regression, and in fact higher education translates to large 
proportion of people owning accounts. 98.6% of college degree holders have their own accounts, while only 84% of primary-educated people utilize this service.

### Effect of Age on Probability of Using Internet Banking
Compared to the youth population under the age of 30, older people are less likely to make use of the digital banking services. The probability
of using internet banking decreases from 90% for people under 30 to 75% for people aged 50, then barely 30% to people around 70 or older.

### Effect of Age on Saving Habit
Under the hypothesis that unemployment and increasing age will lower the likelihood of saving, I conducted a logistic regression with _age_ and _emp in_:
for every year older, the probability of saving decreased by -0.018 log odds.
