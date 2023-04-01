# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** [Joseph McGillen](https://github.com/jm1959) 
**GitHub Handle:** jm1959 
**Repository:** cis411_lab5_Monitoring  
**Collaborators:** 
___

# Step 1: Fork this repository
- [https://github.com/jm1959/cis411_lab5_Monitoring](https://github.com/jm1959/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "9fea6a94-f542-4d7f-96ee-2258fed2ed8c",
      "name": "Joseph McGillen",
      "email": "jm1959@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cislab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > Many of the queries ran quickly but there where a few outliers. Such as one and six taking a little longer then the others. Also query number seven failed. The average response time was 1.64 seconds with a error rate of 4.17%
* Is performance even or uneven? 
  > The performance was very uneven. The run time depended on the queries and how much data they need to search through.
* Between queries and mutations, what requests are less performant? 
  > The queries where less performant then the mutations. This was due to the queries having no filter and having to search through every container.
* Among the less performant requests, which ones are the most problematic?
  > The ones that were most problematic was the 1st, 6th and 7th request. The 1st and 6th worked but had a long run time. The 7th request threw a syntax error.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that tool the most time was "queryOrdersBySearchTerm". It took 30.4 seconds and 98.14% of the overall process.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request are the ones that use the query command and do not use parameters. Like performant request one and six.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The most problematic request permeation is the "queryOrdersBySearchTerm". With a run time of 30.4 seconds because it needed to search through all the data without any parameters.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > A solution for improving the performance is to replace the query operator with the specific category that the data is stored in. For example for query 1 instead of it having (query: "PA") it should be something like (location: "PA") so that it will only filter through the locations not every part of the query.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._