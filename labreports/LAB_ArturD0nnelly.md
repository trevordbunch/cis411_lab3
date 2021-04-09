# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Artur Donnelly  
**GitHub Handle:** [ArturD0nnelly](https://github.com/ArturD0nnelly)  
**Repository:** [cis_lab5_Monitoring](https://github.com/ArturD0nnelly/cis411_lab5_Monitoring)  
**Collaborators:** 
___

# Step 1: Fork this repository
- [The URL of my forked repository](https://github.com/ArturD0nnelly/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "63116500-f0c7-4546-8b1c-ea100c05dbc8",
      "name": "Artur Donnelly",
      "email": "ad1425@messiah.edu"
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



# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The application performed well, regarding one query that end up with an arror.
* Is performance even or uneven? 
  > The performance is uneven, since the requests are diferent and each of them taking diferent amount of time to proccess.
* Between queries and mutations, what requests are less performant? 
  > The query that was less performed was the query number 7, since this query end up with and arror. Also, the query number 6 showed to be less performal in amount of time it took to execute it. 
* Among the less performant requests, which ones are the most problematic?
  > Among the less performant requests number 7 is most problematic. Request number 7 endup with an error, wich would be more problematink then the request that took longer and still gived the right output.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > Enter Response Here.
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