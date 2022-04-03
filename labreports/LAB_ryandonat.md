# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Ryan Donat  
**GitHub Handle:** ryandonat 
**Repository:** https://github.com/ryandonat/cis411_lab5_Monitoring.git  
**Collaborators:** Jamie Padovano answered questions and helped with errors
___

# Step 1: Fork this repository
- The URL of my forked repository
https://github.com/ryandonat/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "c95650d8-7ce8-4ea1-b28c-q46a35801da6",
      "name": "Ryan Donat",
      "email": "rydonat@gmail.com"
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
  > Each query takes a different amount of time to complete, some much longer than others. Each results in a list of results that have something to do with a keyword from the query.
* Is performance even or uneven? 
  > Preformance is uneven.
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant, possibly because they are sorting data instead of changing data, which would take signifigantly more time with large amounts of data.
* Among the less performant requests, which ones are the most problematic?
  > A few of my requests had some errors in them which was most likely user error/fault. The query that got all acounts with "gmail.com" was the most problematic aside from that.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segmemt titled "Remainder" took the most time for the transactions examined.
* Using New Relic, identify and record the least performant request(s).
  > Query 6 took the longest time with over 28000ms response time, the next closest was less than half that.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment remainder is the most problematic in almost every request, taking up the most time in all but one request.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > It appears that the more data that come up in the request, the more the request has to sift through and display which takes the most time in the remainder stage. By removing or decreasing the quantity of times "everything" appears or comes up, the speed of the query will increase/time will decrease.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._