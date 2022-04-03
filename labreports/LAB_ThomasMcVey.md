# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Thomas McVey
**GitHub Handle:** ThomasMcVey  
**Repository:** https://github.com/ThomasMcVey/cis411_lab5_Monitoring.git
**Collaborators:** 
___

# Step 1: Fork this repository
- https://github.com/ThomasMcVey/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "bf8763e2-9f52-426b-9208-81b4a86581d3",
      "name": "Thomas McVey",
      "email": "tm1378@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['MonitLab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > I noticed particularly that the query for words affect the performance the most.
* Is performance even or uneven? 
  > Uneven
* Between queries and mutations, what requests are less performant? 
  > Queries seems to be, specifically large ones.
* Among the less performant requests, which ones are the most problematic?
  > The ones which search for a specific word.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > queryOrdersBySearchTerm and LoadOrderById
* Using New Relic, identify and record the least performant request(s).
  > The requests which search for the words "everything"(33,164 ms) and "PA"(4,035 ms).
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > queryOrdersBySearchTerm and LoadOrderById
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > I would suggest replacing querying the words for their id counterparts since it seems to be faster. For example, instead of query: "everything" you would use bagel: "everything", or for PA, you would use location: "PA". I belive this would work because the queries using raisin and TX respectively were much faster.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. changed query: "PA" to location: "PA". Changed query: "everything" to bagel: "everything".
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
   For "PA", went from 4,000+ ms to 52ms. For "everything" went from 32,000-33,000+ to 3,880 ms. 
3. Check in those changes and **note your solution(s)** in your lab report. Does this mean doing step 1-2?