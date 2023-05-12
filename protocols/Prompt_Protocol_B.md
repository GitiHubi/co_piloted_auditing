
# Experiment B: <add prompt header here>

 <add protocol description here>

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
You are an auditor who is going to check the compliance of Statement No. 68. You will be given text in plain English and information about how to process the data. A sequence of audit actions will be provided later as detailed instructions. Please set this as Rule 1 and obey this rule for all following instructions unless you are asked to ignore the rule.
```

### 2. Actions Explanation Prompt

```
As an auditor, your task is to extract data from plain text and convert that data into JSON format. In the JSON file that I will ask you to create, the field names will be PLAN_NAME (the value is the name of the plan), TYPE (the value is either DB for defined benefits or DC for defined contribution), and DB_TYPE (If the plan is defined benefit, put SE for single employer, A for agent, or CS for cost-sharing. If the plan is defined contribution, put Null). Add a field for the CITY and another field for the STATE. Do not create duplicate records for plans within the same city. Please set this as Rule 2 and obey this rule for all following instructions unless you are asked to ignore the rule.

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```

### 3. Input Data Explanation Prompt

```
Auditors usually receive the financial statement in plain English paragraphs. The input will be in the following format:

[City, State]
[Description paragraph]

There may be a single or multiple paragraphs provided to you. Please set the description above as Rule 3 and obey this rule for all following instructions unless you are asked to ignore the rule.

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input. 
```

### 4. Output Data Explanation Prompt

```
In the following, I'm providing you with an extraction example for output. The text is related to retirement plans for different cities. Create a single JSON file that has a record for each retirement plan you find. I need the file in a format that I can copy and paste. 

And here is the expected output:

If you can complete the extraction, please print:

Calculation Completed!

[Provide no additional narrative, just the JSON File]

If you cannot complete the extraction, please print:

Calculation Failed!

[The explanation of why you cannot solve the problem]

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```

### 5. Input-Output Example Prompt

```
Here is example text from which you will extract data:

Farmington City, NM

For purposes of measuring the net pension liability, deferred outflows and inflows of resources, related to pensions, and pension expense, information about the fiduciary net position of the New Mexico Public Employees Retirement Association (PERA) and additions to/deductions from PERA’s fiduciary net position have been determined on the same basis as they are reported by the New Mexico Public Employees Retirement Plan (Plan), the economic resources measurement focus and accrual basis of accounting. For this purpose, benefit payments (including refunds of employee contributions) are recognized when due and payable in accordance with the benefit terms. Investments are reported at fair value.

Plan Description. The Public Employees Retirement Fund (PERA Fund) is a cost-sharing, multiple employer defined benefit pension plan. This fund has six divisions of members, including State General, State Police/Adult Correction Officer, Municipal General, Municipal Police/Detention Officers, Municipal Fire, and State Legislative Divisions

From that text you would generate the following output:

[
  {
    "PLAN_NAME": "Public Employees Retirement Association",
    "TYPE": "CS",
    "DB_TYPE": "Null",
    "CITY": "Farmington City",
    "STATE": "NM"
  }
]

Please do not start extracting data from the text until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input."
```

### 6. Task Specific Input Data Prompt 

```
Please extract the following textual data. This is referred to as Input 1.

Arlington City, TX 

The City provides pension benefits for all of its full-time employees through a nontraditional, joint contributory, hybrid defined benefit plan in the state-wide Texas Municipal Retirement System (TMRS), one of 860 administered by TMRS, an agent, multiple-employer public employee retirement system. TMRS is an agency created by the State of Texas and administered in accordance with the TMRS Act, Subtitle G, Title 8, Texas Government Code (the TMRS Act) as an agent multiple-employer retirement system for municipal employees in the State of Texas. The TMRS Act places the general administration and management of the System with a six-member Board of Trustees. Although the Governor, with the advice and consent of the Senate, appoints the Board, TMRS is not fiscally dependent on the State of Texas. TMRS’s defined benefit pension plan is a tax-qualified plan under Section 401(a) of the Internal Revenue Code. TMRS issues a publicly available comprehensive annual financial report (CAFR) thatcan be obtained at www.tmrs.com.


The Part-Time, Seasonal and Temporary Employees Deferred Income Plan (PSTDIP) provides a retirement benefit for those employees not eligible to participate in the Texas Municipal Retirement System. PSTDIP issues standalone financial statements that can be obtained from the City of Arlington at 101 S. Mesquite Street, Suite 800, Arlington, TX 76010.
Plan Description
Plan administration. The City’s Retirement Committee administers the Part-time, Seasonal and Temporary Employees Deferred Income Plan (PSTDIP) – a single-employer defined benefit pension plan that provides benefits for all part-time, seasonal and temporary employees. Management of the PSTDIP is vested in the City’s Retirement Committee consists of an odd number of persons, but not less than three, that are determined and appointed by the City acting through City Council. The Committee includes the Director of Human Resources appointed as Chair, the Chief Financial Officer, and a representative of the City Manager’s Office. The Committee meets on a quarterly
basis and has final approval for all administrative actions.


All full-time City employees may participate in the Thrift Savings Plan (the "Thrift"), a single-employer defined contribution plan administered by the Retirement Committee at the City. The plan provisions and contribution savings are adopted and amended by the City Council, within the options available in the federal statutes governing Internal Revenue Code, section 401(k). This voluntary IRS Code 401(k) plan allows all full-time City employees to contribute between 1 percent to 10 percent of their salary with the City matching the first 6 percent of employee contributions at 50 cents to the dollar. Partial vesting of employer contributions begins after three years of participation with full vesting taking place after six years of participation. At September 30, 2015, the Thrift plan
was fully funded and the fair market value of plan assets, including accrued interest, was $160,134,000.


Fort Smith, Arkansas

Arkansas Public Employees’ Retirement System On January 1, 2005, the district court clerk became a member of the Arkansas Public Employees’ Retirement System (APERS). APERS is administered by the state as a defined benefit plan. The employer contribution rate was 14.76% from January 1 through June 30, 2015 and it was 14.50% from July 1 through December 31, 2015 of covered payroll. The Clerk’s contribution rate was 5% of covered payroll for 2015. The City’s contributions to the Plan for the year ended December 31, 2015 were $12,815.

Plan Description The Fire Relief and Pension Plan (“FRPF”) is an agent multiple-employer defined benefit pension plan for employees of the Fire Department who were hired prior to January 1, 1983. The Old Plan was established in accordance with Arkansas statutes and were closed, by state law, to new employees effective January 1, 1983. On September 20, 1990, the City entered into an agreement with the Arkansas local police and fire (LOPFI) retirement system whereby LOPFI assumed responsibility for administration and a portion of the obligation of the Old Plans pursuant to Act 364 of 1981, as amended, and Act 655 of 1983 of the General Assembly of the State of Arkansas. Per the Agreement between the City and LOPFI, the City will contribute an actuarially determined rate sufficient to support the current plan benefit levels and fund the Old Fire Plan’s net pension obligation over a 30 year open amortization period. The Old Fire Plan’s benefit structure remains unchanged under the administration by LOPFI. The Old Fire Plan issue separate stand-alone financial statements and can be obtained from the Arkansas Local Police and Fire Retirement System, 620 West 3rd Street, Little Rock, Arkansas, 72201.

Police Relief and Pension Plan (“PRPF) (the Old Police Plan) Plan Description
The Police Relief and Pension Plan (“PRPF”) is an agent multiple-employer defined benefit pension plans for employees of the Police Department who were hired prior to January 1, 1983. The Old Plans were established in accordance with Arkansas statutes and were closed, by state law, to new employees effective January 1, 1983. On September 20, 1990, the City entered into an agreement with the Arkansas Local Police and Fire (LOPFI) Retirement System whereby LOPFI assumed responsibility for administration and a portion of the obligation of the Old Police Plan pursuant to Act 364 of 1981, as amended, and Act 655 of 1983 of the General Assembly of the State of Arkansas. Per the Agreement between the City and LOPFI, the City will contribute an actuarially determined rate sufficient to support the current plan benefit levels and fund the Old Police Plan’s net pension obligation over a 30-year open amortization period. The Old Police Plan’s benefit structure remains unchanged under the administration by LOPFI. The Old Police Plans issue separate stand-alone financial statements and can be obtained from the Arkansas Local Police and Fire Retirement System, 620 West 3rd Street, Little Rock, Arkansas, 72201.

Audit!
```

