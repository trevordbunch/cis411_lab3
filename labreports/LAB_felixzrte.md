# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Felix Zarate 
**GitHub Handle:** felixzrte   
**Repository:** https://github.com/felixzrte/cis411_lab5_Monitoring 
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "75d29cea-3519-4e62-b132-ff2a446f6c6d",
      "name": "Felix Zarate",
      "email": "fz1151@messiah.edu"
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
  > My observations are that not all the queries took the same amount of time to run and one of them didn't work completely. 
* Is performance even or uneven? 
  > Performance was even for some of the queries. The first one took a while compared to the rest.
* Between queries and mutations, what requests are less performant? 
  > The queries that were less performant were #1 #6 and #7
* Among the less performant requests, which ones are the most problematic?
  > Query #7 because it didnt work

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The remainder segment took about 90% for query #6
* Using New Relic, identify and record the least performant request(s).
  > Least performant was query #6
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > queryOrdersBySearchTerm	(2,620ms) was 7% of query #6. Remainder (34,500ms) was 90% of #6 so that was the most problematic.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > A possible solution could be to change up the query so that it could pull the data in a more efficient way.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.