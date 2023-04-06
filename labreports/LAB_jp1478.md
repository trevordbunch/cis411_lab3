# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Joshua Phillips  
**GitHub Handle:** jp1478  
**Repository:** https://github.com/jp1478/cis411_lab5_Monitoring  
**Collaborators:** 02NRA
___

# Step 1: Fork this repository
- The URL of my forked repository

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "28cad9c2-ed51-458e-9828-13969a2c9082",
      "name": "Joshua Phillips",
      "email": "jp1478@messiah.edu"
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
  > Most queries and mutations took less than a second, but queries that searched through an entire order for a keyword caused excessive delay, up to over a minute. 
* Is performance even or uneven? 
  > Uneven; Certain queries took much longer than others.
* Between queries and mutations, what requests are less performant? 
  > Queries had the largest runtimes and the higher average runtime, but some of the more performant queries were about the same speed or quicker than the mutations. 
* Among the less performant requests, which ones are the most problematic?
  > Queries that searched each entire order for a keyword, rather than giving a parameter, took the longest by far. In addition, the final query gave an error ("Cannot query field \"items\" on type \"Account\"."). 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > "queryOrdersBySearchTerm" was the longest segment, taking up 98.22% of runtime.
* Using New Relic, identify and record the least performant request(s).
  > Queries that searched an entire order for a keyword were slowest. The least performant request searched for the word "everything" in the entire order. The slowest query ran for 64 seconds, while the next slowest ran for 6 seconds.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > "queryOrdersBySearchTerm" took the longest because it had to search through everything in the database without narrowing down the parameters at all. 
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Specify certain attributes of an order to search in, rather than searching through the whole order. For example, in query 6, replace the word 'query' with 'bagel', assuming that the query is intended to search for everything bagels. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.