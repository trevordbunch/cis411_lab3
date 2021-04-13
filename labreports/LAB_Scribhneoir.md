# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Josiah McCracken 
**GitHub Handle:** [Scribhnoeir] (https://github.com/scribhneoir) 
**Repository:** [Repo](https://github.com/scribhneoir/cis411_lab5_Monitoring) 
**Collaborators:** 
___

# Step 1: Fork this repository
[Repo](https://github.com/scribhneoir/cis411_lab5_Monitoring) 

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
![GraphQL](..\assets\graphql.png)

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```cislab``` configuration
```
app_name: ['cislab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The performance varries depending on the query
* Is performance even or uneven? 
  > Uneven
* Between queries and mutations, what requests are less performant? 
  > queries
* Among the less performant requests, which ones are the most problematic?
  > queries that look for a word in any spot rather than just in one area

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > Remainder
* Using New Relic, identify and record the least performant request(s).
  > 1 and 6
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > Remainder
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Query 1 is better optomized in query 2 because it specifies to look via location. Better specification of where to look is always a good idea.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.