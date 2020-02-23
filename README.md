# Loan-Payback-prediction-using-Decision-Tree-and-Random-Forest

Here we explore some publicly available data from LendingClub.com. Lending Club connects people who need money (borrowers) with people who have money (investors). Hopefully, as an investor you would want to invest in people who showed a profile of having a high probability of paying you back. We will try to create a model that will help predict this.

Lending club had [a very interesting year in 2016](https://en.wikipedia.org/wiki/LendingClub#2016), so let's keep the context in mind.

Here, we use lending data from 2007-2010 and classify and predict whether or not the borrower paid back their loan in full. You can download the data from [here](https://www.lendingclub.com/info/statistics.action).

Here are what the columns represent:

- credit.policy: 1 if the customer meets the credit underwriting criteria of LendingClub.com, and 0 otherwise.
- purpose: The purpose of the loan (takes values "credit_card", "debt_consolidation", "educational", "major_purchase", "small_business", and "all_other").
- int.rate: The interest rate of the loan, as a proportion (a rate of 11% would be stored as 0.11). Borrowers judged by LendingClub.com to be more risky are assigned higher interest rates.
- installment: The monthly installments owed by the borrower if the loan is funded.
- log.annual.inc: The natural log of the self-reported annual income of the borrower.
- dti: The debt-to-income ratio of the borrower (amount of debt divided by annual income).
- fico: The FICO credit score of the borrower.
- days.with.cr.line: The number of days the borrower has had a credit line.
- revol.bal: The borrower's revolving balance (amount unpaid at the end of the credit card billing cycle).
- revol.util: The borrower's revolving line utilization rate (the amount of the credit line used relative to total credit available).
- inq.last.6mths: The borrower's number of inquiries by creditors in the last 6 months.
- delinq.2yrs: The number of times the borrower had been 30+ days past due on a payment in the past 2 years.
- pub.rec: The borrower's number of derogatory public records (bankruptcy filings, tax liens, or judgments).

The data is explored visually using **seaborn** by finding general relationships like:
- a histogram of two *FICO* distributions on top of each other, one for each *credit.policy* outcome.
- a histogram of two *FICO* distributions on top of each other, one for each *not.fully.paid* outcome.
- countplot showing the counts of loans by *purpose*, with the color hue defined by *not.fully.paid*.
- jointplot between *FICO* score and *interest rate*
- lmplots to see if the trend for *FICO* score and *interest rate* differed between *not.fully.paid* and *credit.policy*

A Decision Tree classifier and a Random Forest classifier model using the suitable number of estimators are created and then predictions are made with each for the test data.

Then the model performance is evaluated by calculating the Classification Report and Confusion matrix for each.

To conclude, the Random Forest classifier model performs very well i.e. approx. *85%* accuracy. We were able to improve approx. *10-12%* more accuracy here than by using only a single decision tree classifier.
