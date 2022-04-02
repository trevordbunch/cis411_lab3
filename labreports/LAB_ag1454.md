# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Abigail Garrido  
**GitHub Handle:** ag1454  
**Repository:** https://github.com/ag1454/cis411_lab5_Monitoring  
**Collaborators:** n/a
___

# Step 1: Fork this repository
- https://github.com/ag1454/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project

![GraphQL Response](/assets/graphql.png)

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cislab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The overall performance of the application was decent. Only one query didn't perform, which was Query 7.
* Is performance even or uneven? 
  > The performance was more uneven than even. Peaks occured with Queries 1 and 6.
* Between queries and mutations, what requests are less performant? 
  > The queries were less performant due to the results taking more than a milisecond to appear. Queries 1 and 6 in particular took a good couple of seconds to produce output.
* Among the less performant requests, which ones are the most problematic?
  > Between Queries 1 and 6, Query 6 was very problematic. It took much longer for Query 6 to produce results in comparison to the other queries.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that took the most time was the one that recorded Query 6's performance.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request happened at 9:02 PM.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The most problematic segment was one that took 67,900ms of response time. This is likely Query 6, as it took the longest to return data.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Narrowing down Query 6 should improve its performance. It's a valid search on its own (you're free to search for whatever), but the results that the queries return would be more helpful if the search is narrowed.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.