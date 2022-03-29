# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Adam Lenker  
**GitHub Handle:** al1412  
**Repository:** https://github.com/al1412/cis411_lab5_Monitoring  
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository
 https://github.com/al1412/cis411_lab5_Monitoring    

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "2ed1e4f2-de97-4cfc-81d5-8362e43f1b95",
      "name": "Adam Lenker",
      "email": "al1412@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cis411_lab5_Monitoring']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The application's performance overall went pretty well for the most part, with the exception of the last GraphQL query from Step 4, which gave an error, resulting in the query to be altered to work properly. 
* Is performance even or uneven? 
  > The performance is mostly even, with peaks occurring when a query or mutation is being processed, then going back down to null when the processes are completed.
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant as they take longer amounts of time for the server to generate the results. The particular queries which fell under this category were queires 5 and 6 from step 4, with the one from step 5 taking the lomgest amount of time to generate the results.
* Among the less performant requests, which ones are the most problematic?
  > The most problematic one was query 6, though it had more to do with the syntax of the query than the server, the query had to be altered to work properly.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The transaction which took the most time was query 5 from step 4.
* Using New Relic, identify and record the least performant request(s).
  > Enter Response Here.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > Enter Response Here.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Enter Response Here.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.
