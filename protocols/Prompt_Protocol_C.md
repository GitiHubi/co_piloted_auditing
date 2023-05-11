
# Experiment C: Journal Entries Audit Protocols

This protocol outlines the process for auditing tabular financial transactions, also referred to as "journal entries".

## MIT License


Copyright (c) 2023 OpenAI

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
You are an excellent auditor of tabular financial transactions als referred to as "journal entries" . Given a tabular journal entry dataset and information about how to audit the data, you break it down into a sequence of audit actions.

Please do not start auditing until I say "Audit". Instead, just return the output message "Processed - Waiting for next input.

```

### 2. Actions Explanation Prompt

```
As an auditor, your task is to examine journal entry data recorded in an audit client's Enterprise Resource Planning (ERP) system. Specifically, you are responsible for detecting two types of anomalous journal entries within large datasets:

Anomalies are classified into two categories:

1. Global Anomalies: These anomalies involve an unusual combination of values for any single attribute when compared to the entire dataset. For example, a significantly higher or lower transaction amount for a specific department title or a rare department title in the dataset would be considered a global anomaly. Global anomalies are often related to an attribute that stands out across the entire dataset, regardless of other attributes' values.

2. Local Anomalies: These anomalies involve an unusual combination of values for a specific vendor and document type when compared to other entries with the same vendor and document type. For example, a rare department title found only within a specific vendor and document type combination, or an unusual transaction amount for that combination would be considered a local anomaly. Local anomalies are detected within a subset of the dataset, considering the context of similar entries.

Keep these definitions in mind when analyzing datasets for anomalies. As an auditor, your goal is to detect both types of journal entry anomalies. 

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```

### 3. Input Data Explanation Prompt

```
Enterprise Resource Planning (ERP) systems generally store journal entries in a tabular database table format. This table will serve as the input data for analyzing global and local anomalies. Each row in the table represents a single journal entry, while each of the six columns represents a distinct journal entry attribute. The six columns are defined as follows:

1. Fiscal_Year: The fiscal year during which the journal entry was posted, running from July 1st to June 30th.
2. Document_Number: A unique identifier for each journal entry, used for tracking individual entries within the organization's ERP system.
3. Department_Title: The department title used in the organization's finance and accounting system that denotes the department that posted the journal entry.
4. Vendor_Name: The name of the individual, vendor, or entity associated with the journal entry.
5. Document_Type: The classification of the journal entry within the organization's ERP system.
6. Transaction_Amount: The transaction or payment amount in USD.

The table may contain a large, yet arbitrary, number of journal entries, depending on the audit client's business activity. The table data is formatted as a comma-separated values (CSV) file. Below is a sample of a database table in CSV format, with the first row representing attribute names and the following rows representing individual journal entries.

Input Data:

Fiscal_Year, Document_Number, Department_Title, Vendor_Name, Document_Type, Transaction_Amount
2017, CHEK17119771, 42 COMMERCE, EAT AT JOE'S, petty cash, 50.00
2017, CHEK17119723, 26 LICENSES & INSPECTIONS, MARLENE BELL REPORTING INC., procurement, 454.20
2017, CHEK17119939, 44 LAW, RICOH AMERICAS CORPORATION, payment voucher, 127.33

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```

### 4. Output Data Explanation Prompt

```
In general, anomaly detection systems provide two types of information after successfully analyzing journal entries within a tabular database table. The first type of information is the detected anomalous journal entries themselves, and the second type is an explanation of why each entry was identified as an anomaly. Below is an example of an alert message format that should be generated when a local or global anomaly is detected:

Alert Message!

Detected Global Anomaly:

[Placeholder for the detected anomalous journal entries.]

Dectection Rationale:

[Placeholder for the explanation of why the journal entry was detected as an anomaly.]

If multiple global anomalies are detected, separate alert messages should be generated for each anomaly. Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.

```

### 5. Input-Output Example Prompt

```
In the following I'm providing you a global anomaly detection example. 

Input data:

Fiscal_Year, Document_Number, Department_Title, Vendor_Name, Document_Type, Transaction_Amount
2017, CHEK17119393, 42 COMMERCE, EAT AT JOE'S, petty cash, 68.17
2017, CHEK17119771, 42 COMMERCE, EAT AT JOE'S, petty cash, 23.85
2017, CHEK17118549, 42 COMMERCE, EAT AT JOE'S, petty cash, 50.00
2017, CHEK17113292, 42 COMMERCE, EAT AT JOE'S, petty cash, 84.23
2017, CHEK17119504, 26 LICENSES & INSPECTIONS, EAT AT JOE'S, petty cash, 72.23
2017, CHEK17137637, 42 COMMERCE, EAT AT JOE'S, petty cash, 23.03
2017, CHEK17119893, 42 COMMERCE, EAT AT JOE'S, petty cash, 58.17
2017, CHEK13829239, 42 COMMERCE, EAT AT JOE'S, petty cash, 67.85
2017, CHEK17183932, 42 COMMERCE, EAT AT JOE'S, petty cash, 72.00
2017, CHEK17323423, 42 COMMERCE, EAT AT JOE'S, petty cash, 39.28

And here is the expected output:

Alert Message! 

Detected Global Anomaly:

2017, CHEK17119504, 26 LICENSES & INSPECTIONS, EAT AT JOE'S, petty cash, 72.23

Dectection Rationale:

The journal entry exhibting document number CHEK17119504 corresponds to a global anomaly. The journal entry contains the department title "26 LICENSES & INSPECTIONS" which in unusual when compared to all other journal entries in the dataset.

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```

### 6. Input-Output Example Prompt

```
In the following I'm providing you a local anomaly detection example. 

Input data:

Fiscal_Year, Document_Number, Department_Title, Vendor_Name, Document_Type, Transaction_Amount
2017, CHEK17119393, 42 COMMERCE, EAT AT JOE'S, petty cash, 68.17
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 932.32
2017, CHEK17119771, 42 COMMERCE, EAT AT JOE'S, petty cash, 23.85
2017, CHEK17118549, 42 COMMERCE, EAT AT JOE'S, petty cash, 50.00
2017, CHEK17113292, 42 COMMERCE, EAT AT JOE'S, petty cash, 84.23
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 352.29
2017, CHEK17119504, 42 COMMERCE, EAT AT JOE'S, petty cash, 72.23
2017, CHEK17137637, 42 COMMERCE, EAT AT JOE'S, petty cash, 23.03
2017, ACHD17144101, 28 WATER, EAT AT JOE'S, petty cash, 292.22
2017, CHEK17119893, 42 COMMERCE, EAT AT JOE'S, petty cash, 58.17
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 93.92
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 833.59
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 26.59
2017, CHEK13829239, 42 COMMERCE, EAT AT JOE'S, petty cash, 67.85
2017, CHEK17183932, 42 COMMERCE, EAT AT JOE'S, petty cash, 72.00
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 252.19
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 68.38
2017, CHEK17323423, 42 COMMERCE, EAT AT JOE'S, petty cash, 39.28
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 103.39
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 632.84
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 342.50
2017, ACHD17144101, 28 WATER, XEROX CORPORATION, procurement, 294.23

And here is the expected output:

Alert Message! 

Detected Local Anomaly:

2017, ACHD17144101, 28 WATER, EAT AT JOE'S, petty cash, 292.22

Dectection Rationale:

The journal entry exhibting document number CHEK17119504 corresponds to a local anomaly. The journal entry contains the department title "28 Water" which is usually not observed with the vendor name "EAT AT JOE'S" and document type "petty cash".

Please do not start auditing until I say "Audit!". Instead, just return the output message "Processed - Waiting for next input.
```

### 7. Task Specific Input Data Prompt 

```
Please analyze the following journal entries for both global and local anomalies. For each anomaly detected, please generate an alert message that includes the anomaly and an explanation for why it was flagged. It is crucial to detect all anomalies present in the dataset. Return all anomalies detected in a single response.

Fiscal_Year, Document_Number, Department_Title, Vendor_Name, Document_Type, Transaction_Amount
2017, CHEK17323423, 42 COMMERCE, EAT AT JOE'S, petty cash, 39.28
2017, CHEK19393092, 42 COMMERCE, EAT AT JOE'S, petty cash, 93.23
2017, CHEK17119393, 26 LICENCES, THE MCS GROUP, INC., petty cash, 68.17
2017, CHEK17119393, 42 COMMERCE, EAT AT JOE'S, petty cash, 68.17
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 932.32
2017, CHEK17119771, 26 LICENCES, THE MCS GROUP, INC., petty cash, 23.85
2017, CHEK17118549, 26 LICENCES, THE MCS GROUP, INC., petty cash, 50.00
2017, CHEK19959593, 26 LICENCES, THE MCS GROUP, INC., petty cash, 23.83
2017, CHEK17183822, 26 LICENCES, THE MCS GROUP, INC., petty cash, 42.00
2017, CHEK17137637, 42 COMMERCE, EAT AT JOE'S, petty cash, 23.03
2017, CHEK17139393, 42 COMMERCE, EAT AT JOE'S, petty cash, 293.23
2017, CHEK17113292, 26 LICENCES, THE MCS GROUP, INC., petty cash, 84.23
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 352.29
2017, CHEK17119504, 26 LICENCES, THE MCS GROUP, INC., petty cash, 72.23
2017, CHEK17119932, 42 COMMERCE, EAT AT JOE'S, petty cash, 19.75
2017, CHEK13829292, 42 COMMERCE, EAT AT JOE'S, petty cash, 28.79
2017, ACHD17234101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 222.20
2017, CHEK17132932, 42 COMMERCE, EAT AT JOE'S, petty cash, 20.72
2017, CHEK13842292, 42 COMMERCE, EAT AT JOE'S, petty cash, 22.34
2017, ACHD24454101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 493.19
2017, CHEK17137637, 26 LICENCES, THE MCS GROUP, INC., petty cash, 23.03
2017, ACHD17144101, 25 FLEET MANAGEMENT, EAT AT JOE'S, petty cash, 292.22
2017, CHEK17119771, 26 LICENCES, THE MCS GROUP, INC., petty cash, 23.85
2017, CHEK17113243, 26 LICENCES, THE MCS GROUP, INC., petty cash, 52.00
2017, CHEK17324423, 26 LICENCES, THE MCS GROUP, INC., petty cash, 93.17
2017, CHEK17119771, 42 COMMERCE, EAT AT JOE'S, petty cash, 1,000,000.00
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 93.92
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 833.59
2017, CHEK17118549, 42 COMMERCE, EAT AT JOE'S, petty cash, 50.00
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 26.59
2017, ACHD17144102, 25 FLEET MANAGEMENT, THE MCS GROUP, INC., petty cash, 229.59
2017, CHEK13829239, 26 LICENCES, THE MCS GROUP, INC., petty cash, 67.85
2017, CHEK17183932, 26 LICENCES, THE MCS GROUP, INC., petty cash, 72.00
2017, CHEK17394394, 26 FIREDEPARTMENT, EAT Even More AT JOESES's, petty cash, 72.23
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 252.19
2017, ACHD17144101, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 68.38
2017, CHEK12022932, 42 COMMERCE, EAT AT JOE'S, petty cash, 66.72
2017, CHEK13322292, 42 COMMERCE, EAT AT JOE'S, petty cash, 93.33
2017, CHEK12023332, 42 COMMERCE, EAT AT JOE'S, petty cash, 83.77
2017, CHEK13343492, 42 COMMERCE, EAT AT JOE'S, petty cash, 192.33
2017, ACHD17545542, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 34.64
2017, ACHD17132343, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 29.32
2017, CHEK17323423, 26 LICENCES, THE MCS GROUP, INC., petty cash, 39.28
2017, CHEK17119893, 42 COMMERCE, EAT AT JOE'S, petty cash, 58.17
2017, CHEK13829239, 42 COMMERCE, EAT AT JOE'S, petty cash, 67.85
2017, CHEK29292932, 18 POLICE, DUNKIN DONUTS, petty cash, 72.00
2017, CHEK17113292, 42 COMMERCE, EAT AT JOE'S, petty cash, 84.23
2017, ACHD17144121, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 103.39
2017, ACHD17144122, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 632.84
2017, CHEK17113292, 42 COMMERCE, EAT AT JOE'S, petty cash, 34.73
2017, ACHD17144142, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 342.50
2017, ACHD17144143, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 294.23
2017, ACHD17144432, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 43.53
2017, ACHD17324233, 25 FLEET MANAGEMENT, CHAPMAN FORD SALES, procurement, 4.23

Audit!
```

