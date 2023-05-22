
# Experiment C: Audit Task - Journal Entry Testing

This protocol outlines the process for auditing journal entries. 

The ChatGPT response for each prompt is listed as follows:

### 1. Task Explanation Prompt

```
Understood. I've set the following as Rule 1:

"When provided with a tabular journal entry dataset and information about how to audit the data, break it down into a sequence of audit actions."

I will not start auditing until the command "Audit" is received and will not provide any other response besides "Processed - Waiting for next input" unless instructed otherwise.

```

### 2. Actions Explanation Prompt

```
Understood. I've set the following as Rule 2:

"As an auditor, your task is to examine journal entry data recorded in an audit client's Enterprise Resource Planning (ERP) system. You are responsible for detecting two types of anomalous journal entries within large datasets:

Global Anomalies: These anomalies involve an unusual combination of values for any single attribute when compared to the entire dataset.
Local Anomalies: These anomalies involve an unusual combination of values for a specific vendor and document type when compared to other entries with the same vendor and document type."

I will not start auditing until the command "Audit" is received and will not provide any other response besides "Processed - Waiting for next input" unless instructed otherwise.

Processed - Waiting for next input.
```

### 3. Input Data Explanation Prompt

```
Understood. I've set the following as Rule 3:

"Enterprise Resource Planning (ERP) systems generally store journal entries in a tabular database table format. Each row represents a single journal entry, while each of the six columns represents a distinct journal entry attribute: Fiscal_Year, Document_Number, Department_Title, Vendor_Name, Document_Type, and Transaction_Amount. The table data is formatted as a comma-separated values (CSV) file."

I will not start auditing until the command "Audit!" is received and will not provide any other response besides "Processed - Waiting for next input" unless instructed otherwise.
```

### 4. Output Data Explanation Prompt

```
Understood. I've set the following as Rule 4:

"Anomaly detection systems provide two types of information after successfully analyzing journal entries within a tabular database table: the detected anomalous journal entries themselves, and an explanation of why each entry was identified as an anomaly. An alert message format should be generated when a local or global anomaly is detected, containing placeholders for the detected anomalous journal entries and the rationale for their detection. If multiple global anomalies are detected, separate alert messages should be generated for each anomaly. If no anomalies are found, provide an explanation."

I will not start auditing until the command "Audit!" is received and will not provide any other response besides "Processed - Waiting for the next input" unless instructed otherwise.

```

### 5. Input-Output Example Prompt

```
Understood. Your example demonstrates how to identify a global anomaly based on a unique attribute value (in this case, "26 LICENSES & INSPECTIONS" as the Department_Title) compared to the rest of the dataset. This information will be useful for performing similar analyses in future tasks.

I will not start auditing until the command "Audit!" is received and will not provide any other response besides "Processed - Waiting for the next input" unless instructed otherwise.
```

### 6. Input-Output Example Prompt

```
Understood. Your example demonstrates how to identify a local anomaly based on a unique combination of attribute values (in this case, "28 WATER" as the Department_Title, "EAT AT JOE'S" as the Vendor_Name, and "petty cash" as the Document_Type) compared to other entries with the same vendor and document type. This information will be useful for performing similar analyses in future tasks.

I will not start auditing until the command "Audit!" is received and will not provide any other response besides "Processed - Waiting for the next input" unless instructed otherwise.
```

### 7. Task Specific Input Data Prompt 

```
Alert Message!

Detected Global Anomaly:

2017, CHEK17119771, 42 COMMERCE, EAT AT JOE'S, petty cash, 1,000,000.00

Dectection Rationale:

The journal entry exhibiting document number CHEK17119771 corresponds to a global anomaly. The transaction amount of 1,000,000.00 is significantly higher compared to all other journal entries in the dataset.

Alert Message!

Detected Local Anomaly:

2017, ACHD12343201, 25 FLEET MANAGEMENT, EAT AT JOE'S, petty cash, 292.22

Dectection Rationale:

The journal entry exhibiting document number ACHD12343201 corresponds to a local anomaly. The vendor name "EAT AT JOE'S" and document type "petty cash" are unusual when considering other journal entries within the "25 FLEET MANAGEMENT" department.

Alert Message!

Detected Local Anomaly:

2017, CHEK17394394, 26 FIREDEPARTMENT, EAT Even More AT JOESES's, petty cash, 72.23

Dectection Rationale:

The journal entry exhibiting document number CHEK17394394 corresponds to a local anomaly. The department title "26 FIREDEPARTMENT" and the vendor name "EAT Even More AT JOESES's" are unusual when considering other journal entries in the dataset.
```

