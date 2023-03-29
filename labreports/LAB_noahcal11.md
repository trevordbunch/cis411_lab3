# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Noah Calisti  
**GitHub Handle:** noahcal11  
**Repository:** [My Forked Repository](https://github.com/noahcal11/cis411_lab5_Monitoring)  
**Collaborators:** 
___

# Step 1: Fork this repository
- [The URL of my forked repository](https://github.com/noahcal11/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "6c7293c8-8ca4-4de2-af36-153ee74c3891",
      "name": "Noah Calisti",
      "email": "noahcal48@gmail.com"
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
  > Response time spiked up to 23 seconds before coming back down with the faster final query. It noted the error with the final query before I changed it. Query six was by far the slowest and query 7 gave me an error before I slightly modified it and then it was nearly instant. I had an average response time of 79.2ms, throughput 0.100 rpm, 0.32% CPU utilization, using 23.9 MB of memory
* Is performance even or uneven? 
  > Performance was very uneven. Some queries took a long time while others were instant.
* Between queries and mutations, what requests are less performant? 
  > Queries were definitely less performant. Queries required searching which can take a long time. For example, query 6 took over 20 seconds to return.
* Among the less performant requests, which ones are the most problematic?
  > As noted before, query 6 took a long time to return. Additionally, query 7 returned an error. It did not let me search through accounts for items; I fixed this by simply returning the id and email for emails containing "gmail.com".

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > I examined query 6 because it took by far the longest time. I noticed that queryOrdersBySearchTerm took 98.04% of the total time.
* Using New Relic, identify and record the least performant request(s).
  > The least performant requests search the whole dataset using the "query:" command as opposed to searching one specific category (ex: bagels). This makes searching much slower because the dataset to search is much larger, causing slower response times.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > In all transactions, the segment queryOrdersBySearchTerm took by far the longest.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > The query: command should not be used unless absolutely necessary. In query 6, it could be replaced by bagel: because "everything" was only going to be found in everything bagels. In query 1, query could be replaced by location: given that the command was searching for "PA". Query 2 did that exactly and was predictably much faster.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.