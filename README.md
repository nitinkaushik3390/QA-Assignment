# QA Assignment Overview

##    TASKS Performed

1. **Part 1 - QA Automation**
2. **Part 2 - Manual Testing**

# **Part 1 - QA Automation**

## Objective:

Automate testing of GitHub's API to update a user's profile bio and validate responses, including handling errors.

## Pre-requisites:

- A GitHub account.
- A personal access token with the necessary permissions.

## Generating a Personal Access Token:

Before you begin, you'll need to generate a personal access token on GitHub with the appropriate permissions. Please follow these steps to create one:

1. Log in to your GitHub account.
2. Navigate to Settings > Developer settings > Personal access tokens.
3. Click on "Generate new token".
4. Give your token a descriptive name, such as "QA Automation Test".
5. Under scopes, select the ***user*** to update your profile information.
6. Click "Generate token" at the bottom of the page.
7. Copy the generated token and store it securely.

**Tutorial to Setup the Access token:**

https://jam.dev/c/18457560-a451-44c7-b695-34fadecb134c

## Task 1

### **Github API:**

https://docs.github.com/en/rest/users/users?apiVersion=2022-11-28#get-the-authenticated-user

## Test Cases:

### Failure Cases:

1. No Token Provided:
    - Method: GET
    - Endpoint: /user
    - Expected Status Code: 401 Unauthorized
2. Invalid Token Provided:
    - Method: GET
    - Endpoint: /user
    - Expected Status Code: 401 Unauthorized
3. Forbidden Access (Token Without Necessary Permissions):
    - Method: GET
    - Endpoint: /user
    - Expected Status Code: 403 Forbidden

### Success Cases:

1. Get User With Valid Token:
    - Method: GET
    - Endpoint: /user
    - Expected Status Code: 200 OK
2. Update User Bio With Valid Token:
    - Method: PATCH
    - Endpoint: /user
    - Body: {"bio": "Your new bio content here."}
    - Expected Status Code: 200 OK
  
  ### Directory & File details

  Go to the Folder 'Task 1' in this repository. Postman JSON file is attached in which all the above mentioend cases have been automated. In order to run these tests, Download & Import this JSON file into your postman app and then execute this collection using the Postman Runner.

  To run this collection through Command Line, Download this JSON file and then setup nodejs & newman on your local machine. After that, open command prompt on your machine and run this command - newman run <path of the downloaded postman collection file> -r cli

## Task 2

## Load Testing:

### Test Case:

Simulate Concurrent Users Accessing the GET /users Endpoint: (Public endpoint)

- Set up a load testing script with JMeter.
- Define the number of concurrent users and spawn rate.
- Test for a specific time period or a number of requests.
- Measure response times, error rates, and system behavior under load.

### Execution and Reporting:

- Execute the load test using the specified tool.
- Capture and analyze the results.
- Generate a report detailing throughput, response times, error rates, and any performance bottlenecks identified.

## Integration with Test Management Tools:

### Test Case Tracking:

- Document all test cases within the chosen test management tool.
- Each test case should have a unique identifier, title, steps, expected results, and actual results.

### Reporting:

- Use the test management tool to report the status of each test execution.
- Link any issues found directly to the corresponding test case in the tool.
- For load testing, attach the detailed performance report to the related test case.

### Submission Requirements:

- **Task 1:** Provide GitHub code for the automation
- **Task 2:** Provide the following:-
    - Provide the scripts for load.
    - Include documents and sample reports or screenshots from the test management tool showing the test cases and results.
 
  ### Directory & File details

  Locate and navigate to the folder 'Task 2' in this repository. In this folder, JMeter test suite file 'User API Load Thread.jmx' is attached. Open this file in your JMeter tool (UI) to view & execute the Test Suite. The following APIs have been included as a part of this load test:

  1. GET User: No. of users - 200, Ramp up period - 10s. The CSV file 'testdata.csv' is used to pass the data of the concurrent users.
  2. Update User (Methos Used - PATCH): No. of users - 200, Ramp up period - 10s. The CSV file 'testdata1.csv' is used to pass the data of the concurrent users & their updated fields along with the respective value.
 
  Additional Attachments:

  1. testdata.csv - Used to pass the data of concurrent users for GET User API.
  2. testdata1.csv - used to pass the data of the concurrent users & their updated fields along with the respective value for Update User API.
  3. Summary.csv - Summary report of the executed load test. It captures these details - Average time taken (ms.), Min time, Max time, Std. Dev., Error %, Throughput,	Received KB/sec,	Sent KB/sec,	Avg. Bytes.
  4. Part 1-Testcases.xlsx - In this sheet, all the executed test cases have been listed.

# **Part 2 - Manual Testing**

Thoroughly review the subsequent user story and create test scenarios and test cases based on it.

## **User Story: Managing Report Templates**

**As a** report creator,

**I want** to select a report template based on specific columns,

**So that** I can customize the report layout and data model according to my needs.

### **Acceptance Criteria:**

1. **Selecting a Template:**
    - When I create a new report, I can choose from existing report templates.
    - The template options include a list of predefined columns and layouts.
2. **Customizing Columns:**
    - After selecting a template, I can modify the columns included in the report.
    - I can add or remove columns based on my requirements.
    - The changes should be reflected in the report layout.
3. **Saving as New Template:**
    - If I customize a template, I can save it as a new template.
    - The new template retains the modified column selection and layout.
    - I can provide a name and description for the new template.
4. **Updating Existing Templates:**
    - For existing templates, I can edit the column selection and layout.
    - Any changes made to an existing template should not affect reports created using the original template.
5. **Deleting Templates:**
    - I can delete unnecessary templates that I no longer need.
    - Deleting a template should not impact any reports already generated from that template.

### **Notes:**

- Templates do not contain actual report data; they only define the structure and column selection.
- The ability to manage templates ensures consistency and efficiency in report creation.
- Once a report is generated from a template, it becomes an independent report.
- It is language agnostic. You can use a language which you are comfortable in.
- You can use any tool want.

### Directory & File details

  Locate and navigate to the folder 'Part 2 - Manual Testing' in this repository. Inside this folder, an excel sheet named 'Part 2-TestSuite.xlsx' is attached. In this sheet, test scenarios & test cases have been listed.
