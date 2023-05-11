
# Experiment A: <add prompt header here>

Experiment A: Audit Task - Financial Ratio Analysis

## MIT License


Copyright (c) 2023 Continous Audit and Reporting (CAR) Lab 
at Rutgers University, 1 Washington Park, NJ, USA

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


### 1. Task Explanation Prompt
```
You are an auditor who is going to perform a financial ratio analysis. You will be given a company’s financial statement and information about how to utilize the data. A sequence of audit actions will be provided later as detailed instructions. Please keep this role in mind, set this as Rule 1 and obey this rule for all following instructions unless you are asked to ignore it.

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```
Understood. I am now functioning under the role of an auditor who will perform a financial ratio analysis when instructed. I will await the command "Audit!" before beginning my task, and until then, I will respond with "Processed - Waiting for next input." Please provide further instructions as needed.
### 2. Actions Explanation Prompt
```
As an auditor, your task is to calculate financial ratios from financial statements. Specifically, you aim to calculate three common financial ratios as follows:

Gross profit margin: Measures how much profit a company makes on its sales after accounting for the cost of goods sold. It is calculated by dividing the gross profit by the revenue.
Gross profit margin = Gross profit / Total revenue

Operating profit margin: Measures how much profit a company generates from its operations before accounting for taxes and interest expenses. It is calculated by dividing the operating profit by the revenue.
Operating profit margin = EBIT / Total revenue

Net profit margin: Measures how much profit a company generates after accounting for all expenses, including taxes and interest expenses. It is calculated by dividing the net income by the revenue.
Net profit margin = Net income / Total revenue

Please keep these definitions in mind when calculating financial ratios, set this as Rule 2, and obey this rule for all following instructions unless you are asked to ignore the rule.

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input."
```
Understood. I have internalized the definitions and formulas for the gross profit margin, operating profit margin, and net profit margin calculations. This is now set as Rule 2 and will be used for subsequent instructions unless otherwise specified. I will wait for the command "Audit!" before I start my tasks.

Processed - Waiting for next input.
### 3. Input Data Explanation Prompt

```
Auditors usually receive the financial statement in tabular database table format. This table is an income statement for calculating financial ratios. Each column represents a distinct line item. Because the line items can be different in different companies’ income statements, I cannot give you explanations for all possible column names.

Please keep the description in mind when calculating financial ratios, set this as Rule 3, and obey this rule for all following instructions unless you are asked to ignore the rule. Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input."
```
Understood. I am now aware of the two types of output scenarios after performing financial ratio calculations. This rule is now set as Rule 4 and will be followed for future instructions unless otherwise specified.

I will wait for the command "Audit!" before starting my tasks.

Processed - Waiting for next input.
### 4. Output Data Explanation Prompt

```
There are two types of output scenarios after calculating financial ratios within a tabular database table.

The first output scenario is that you are able to successfully calculate the ratio. Below is an example of the message format that should be generated when the ratio is successfully calculated:

Calculation Completed!

[Placeholder for the calculated ratios]

The second output scenario is that you are not able to successfully calculate the ratio. Below is an example of the message format that should be generated when the ratio is successfully calculated:

Calculation Failed!

[Placeholder for the rationale]

Please keep the output format in mind when calculating financial ratios, set this as Rule 4, and obey this rule for all following instructions unless you are asked to ignore the rule. Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input."
```

### 5. Input-Output Example Prompt

```
In the following, I'm providing you with a ratio calculation example.

Input Data:
asOfDate, periodType, currencyCode, BasicAverageShares, BasicEPS, CostOfRevenue, DilutedAverageShares, DilutedEPS, DilutedNIAvailtoComStockholders, EBIT, EBITDA, EarningsFromEquityInterestNetOfTax, GainOnSaleOfBusiness, GeneralAndAdministrativeExpense, GrossProfit, ImpairmentOfCapitalAssets, InterestExpense, InterestExpenseNonOperating, InterestIncome, InterestIncomeNonOperating, MinorityInterests, NetIncome, NetIncomeCommonStockholders, NetIncomeContinuousOperations, NetIncomeFromContinuingAndDiscontinuedOperation, NetIncomeFromContinuingOperationNetMinorityInterest, NetIncomeIncludingNoncontrollingInterests, NetInterestIncome, NetNonOperatingInterestIncomeExpense, NormalizedEBITDA, NormalizedIncome, OperatingExpense, OperatingIncome, OperatingRevenue, OtherGandA, OtherIncomeExpense, OtherNonOperatingIncomeExpenses, PretaxIncome, ReconciledCostOfRevenue, ReconciledDepreciation, ResearchAndDevelopment, SalariesAndWages, SellingGeneralAndAdministration, SpecialIncomeCharges, TaxEffectOfUnusualItems, TaxProvision, TaxRateForCalcs, TotalExpenses, TotalOperatingIncomeAsReported, TotalRevenue, TotalUnusualItems, TotalUnusualItemsExcludingGoodwill

2022-12-31, 12M, USD, 566000000.0, 10.21, 1.923200e+10, 567600000.0, 10.18, 5777000000.0, 4086000000.0, NaN, 11000000.0, 2724000000.0, 8801000000.0, 1.499700e+10, 271000000.0, 462000000.0, 462000000.0, 67000000.0, 67000000.0, -14000000.0, 5777000000.0, 5777000000.0, 5791000000.0, 5777000000.0, 5777000000.0, 5791000000.0, -395000000.0, -395000000.0, 1633000000.0, 3559488000.0, 1.091100e+10, 4086000000.0, 3.422900e+10, 9049000000.0, 2306000000.0, -147000000.0, 6392000000.0, 1.923200e+10, 1831000000.0, 1862000000.0, -248000000.0, 9049000000.0, 2453000000.0, 235488000.0, 612000000.0, 0.096, 3.014300e+10, 6539000000.0, 3.422900e+10, 2453000000.0, 2453000000.0

And here is the expected output:

Calculation Completed!

Gross profit margin = 1.499700e+10/3.422900e+10 = 0.4381372520377458
Operating profit margin = 4.086000e+09/3.422900e+10 = 0.11937246194747145
Net profit margin = 5.777000e+09/3.422900e+10 = 0.1687750153378714

If you cannot calculate, please print:

Calculation Failed!

I cannot find the value of [name of the line items], which is essential for calculating the ratios.

Please do not start auditing until I say "Audit!". Instead, just return the output message
"Processed - Waiting for next input."
```
Understood. The provided ratio calculation example has been noted, and the expected output formats have been understood for both successful and unsuccessful calculations.

I will wait for the command "Audit!" before starting my tasks.

Processed - Waiting for next input.
### 6. Task Specific Input Data Prompt 

```
Please analyze the following income statement to calculate the three financial ratios.

asOfDate, periodType, currencyCode, BasicAverageShares, BasicEPS, CostOfRevenue, DilutedAverageShares, DilutedEPS, DilutedNIAvailtoComStockholders, EBIT, EBITDA, GrossProfit, InterestExpense, InterestExpenseNonOperating, InterestIncome, InterestIncomeNonOperating, NetIncome, NetIncomeCommonStockholders, NetIncomeContinuousOperations, NetIncomeFromContinuingAndDiscontinuedOperation, NetIncomeFromContinuingOperationNetMinorityInterest, NetIncomeIncludingNoncontrollingInterests, NetInterestIncome, NetNonOperatingInterestIncomeExpense, NormalizedEBITDA, NormalizedIncome, OperatingExpense, OperatingIncome, OperatingRevenue, OtherIncomeExpense, OtherNonOperatingIncomeExpenses, PretaxIncome, ReconciledCostOfRevenue, ReconciledDepreciation, ResearchAndDevelopment, SellingGeneralAndAdministration, TaxEffectOfUnusualItems, TaxProvision, TaxRateForCalcs, TotalExpenses, TotalOperatingIncomeAsReported, TotalRevenue

2022-09-30, 12M, USD, 1.621596e+10, 6.1500, 2.235460e+11, 1.632582e+10, 6.1100, 9.980300e+10, 1.194370e+11, NaN, 1.707820e+11, 2931000000.0, 2931000000.0, 2825000000.0, 2825000000.0, 9.980300e+10, 9.980300e+10, 9.980300e+10, 9.980300e+10, 9.980300e+10, 9.980300e+10, -106000000.0, -106000000.0, 1.305410e+11, 9.980300e+10, 5.134500e+10, 1.194370e+11, 3.943280e+11, -334000000.0, -334000000.0, 1.191030e+11, 2.235460e+11, 1.110400e+10, 2.625100e+10, 2.509400e+10, 0.0, 1.930000e+10, 0.162045, 2.748910e+11, 1.194370e+11, 3.943280e+11

Audit!
```
Audit initiated. I am now calculating the three financial ratios based on the provided income statement data.

Gross profit margin = Gross profit / Total revenue
Operating profit margin = EBIT / Total revenue
Net profit margin = Net income / Total revenue

Here are the calculated ratios:

Gross profit margin = 1.70782e+11 / 3.94328e+11 = 0.4330258827965754
Operating profit margin = 1.19437e+11 / 3.94328e+11 = 0.3029328940914151
Net profit margin = 9.9803e+10 / 3.94328e+11 = 0.25315486389767526

So, the results are as follows:

Calculation Completed!

Gross profit margin = 0.4330258827965754
Operating profit margin = 0.3029328940914151
Net profit margin = 0.25315486389767526
