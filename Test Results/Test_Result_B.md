
# Experiment B: Audit Task - Post Implementation Review

This protocol outlines the process for conducting a post implementation review.

The ChatGPT response for each prompt is listed as follows:

### 1. Task Explanation Prompt

```
Understood, your instruction has been set as Rule 1. I will not begin auditing until I receive the command "Audit!". Instead, I will return the output message "Processed - Waiting for next input."
```

### 2. Actions Explanation Prompt

```
Understood, your instruction has been set as Rule 2. The data extracted from plain text will be converted into JSON format, containing fields for PLAN_NAME, TYPE, DB_TYPE, CITY, and STATE. Duplicate records for plans within the same city will not be created. I will not start auditing until I receive the command "Audit!". Instead, I will return the output message "Processed - Waiting for next input."
```

### 3. Input Data Explanation Prompt

```
Understood, your instruction has been set as Rule 3. The input will be in the format:

[City, State]
[Description paragraph]

There may be one or multiple paragraphs provided. I will not start auditing until I receive the command "Audit!". Instead, I will return the output message "Processed - Waiting for next input."
```

### 4. Output Data Explanation Prompt

```
Understood, your instruction has been set as the output format. If the data extraction can be completed, I will print "Calculation Completed!" followed by the JSON file. If the extraction cannot be completed, I will print "Calculation Failed!" along with the explanation of why the task could not be completed. I will not start auditing until I receive the command "Audit!". Instead, I will return the output message "Processed - Waiting for next input."
```

### 5. Input-Output Example Prompt

```
Understood, your instruction has been processed. I have noted the example text and the expected output in the specified JSON format. I will not start extracting data from the text until I receive the command "Audit!". Instead, I will return the output message "Processed - Waiting for next input."
```

### 6. Task Specific Input Data Prompt 

```
Calculation Completed!

Here is the extracted data in JSON format:

json

[
  {
    "PLAN_NAME": "Texas Municipal Retirement System",
    "TYPE": "DB",
    "DB_TYPE": "A",
    "CITY": "Arlington City",
    "STATE": "TX"
  },
  {
    "PLAN_NAME": "Part-Time, Seasonal and Temporary Employees Deferred Income Plan",
    "TYPE": "DB",
    "DB_TYPE": "SE",
    "CITY": "Arlington City",
    "STATE": "TX"
  },
  {
    "PLAN_NAME": "Thrift Savings Plan",
    "TYPE": "DC",
    "DB_TYPE": "Null",
    "CITY": "Arlington City",
    "STATE": "TX"
  },
  {
    "PLAN_NAME": "Arkansas Public Employees’ Retirement System",
    "TYPE": "DB",
    "DB_TYPE": "SE",
    "CITY": "Fort Smith",
    "STATE": "AR"
  },
  {
    "PLAN_NAME": "Fire Relief and Pension Plan",
    "TYPE": "DB",
    "DB_TYPE": "A",
    "CITY": "Fort Smith",
    "STATE": "AR"
  },
  {
    "PLAN_NAME": "Police Relief and Pension Plan",
    "TYPE": "DB",
    "DB_TYPE": "A",
    "CITY": "Fort Smith",
    "STATE": "AR"
  }
]
Please note: For "TYPE", I used "DB" for defined benefits and "DC" for defined contribution. For "DB_TYPE", I used "SE" for single employer, "A" for agent, and "CS" for cost-sharing. In the case of defined contribution, "DB_TYPE" is set as "Null".
```