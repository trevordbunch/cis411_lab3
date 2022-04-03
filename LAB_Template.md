# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Nathan Bowman  
**GitHub Handle:** bowman3239  
**Repository:** bowman3239 / cis411_lab5_Monitoring  
**Collaborators:** 
___

# Step 1: Fork this repository
- https://github.com/bowman3239/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "3288e7d7-8d6e-43ce-9096-612abca4b27b",
      "name": "YOUR FULL NAME",
      "email": "YOUR EMAIL"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```cislab``` configuration
```
app_name: ['<cislab>']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The performance of the application will demend on what query is being run. New relic shows frustration of users throughout most of the application.
* Is performance even or uneven? 
  > The performance is uneven. As mentioned previously, it depended on what query was being run, creating a differece in run time.
* Between queries and mutations, what requests are less performant? 
  > The queries were less performant than the mutations.
* Among the less performant requests, which ones are the most problematic?
  > The queries which dealt with finding specific words took a greater response time than that of the other queries.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?

The remainder took the longest amount of time and therefore was the most problematic.
* Using New Relic, identify and record the least performant request(s).
  > 
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The remainded once again is the most problematic segment according to the Transaction Trace from New Relic.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.