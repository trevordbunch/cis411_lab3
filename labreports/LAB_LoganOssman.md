# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Logan Ossman  
**GitHub Handle:** loganossman  
**Repository:** https://github.com/loganossman/cis411_lab5_Monitoring  
**Collaborators:** 
___

# Step 1: Fork this repository
- https://github.com/loganossman/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "427f6bcb-d59a-46b9-b57c-32f7392acdcd",
      "name": "Logan Grant Ossman",
      "email": "loganossman@gmail.com"
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
  > Queries 1, 6, and 7 all had performance issues. Seven, in particular, was a problem. While 1 and 6 were slow, 7 did not even complete it's job, as it threw an error immediately upon running it.
* Is performance even or uneven? 
  > Very uneven. 1, 6, and 7 were all huge problems, although there were still noticable performance differences among the other 4. This can likely be attributed to the amount of data gathered by each.
* Between queries and mutations, what requests are less performant? 
  > It might be because there are far more queries, but the mutations are far more performant! One of the queries straight up does not work. 1 of 1 is still a better percentage than 6 of 7.
* Among the less performant requests, which ones are the most problematic?
  > The aforementioned queries of 1, 6, and 7 are the most problematic. As mentioned before, 1 and 6 are slow, while 7 immediately crashes.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > It depends for the query. For the smaller transactions, post dominated the transaction. However, larger transactions have some strange remainder and a domineering load. 
* Using New Relic, identify and record the least performant request(s).
  > The least performant requests are 1, 2, 6 and 7.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > As of the biggest timewasters, remainder seems to be the largest problem.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > The query command seems incredibly slow. The Location or Bagel command works much better, especially for speed and specificity. Note, the Location command should still be used sparingly, as it has large start-up due to middleware.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.