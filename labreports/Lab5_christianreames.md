# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Christian Reames
**GitHub Handle:** @christianreames 
**Repository:** Your Forked Repository  
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository
https://github.com/christianreames/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "29a0f79b-5b97-4053-a6a6-d9286f000cd5",
      "name": "Christian Reames",
      "email": "cr1368@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cis411lab5']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > There isn't a set amount of time it takes for queries to do what they need to. Each is independent and takes it's own time. 
* Is performance even or uneven? 
  > The performance is uneven. 
* Between queries and mutations, what requests are less performant? 
  > I believe that the queries would be less performant due to the fact of having to get data from a larger source takes longer. 
* Among the less performant requests, which ones are the most problematic?
  > I had the most trouble with the gmail.com one (the 7th query). 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The remainder segment took the longest amount of time. 
* Using New Relic, identify and record the least performant request(s).
  > Both the 6th and 7th queries were the lowest performers for me. It seemed like it was the ones that dealt with finding words that struggled the most out of the 7 queries. That's probably because it had to go through more information in the database, though.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The remainder segment was the one that caused response times to drag out. This one caused the most issues for me. 
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > If the request could be made more in-depth or specific then that would probably help. It takes too long for the request to have to search the whole database, so doing this would shorten the response time. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

