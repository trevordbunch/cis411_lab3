# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Julina Metz  
**GitHub Handle:** julinametz  
**Repository:** https://github.com/julinametz/cis411_lab5_Monitoring   
___

# Step 1: Fork this repository
- https://github.com/julinametz/cis411_lab5_Monitoring 

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "2966a17b-40e5-41b2-b35f-221580da7816",
      "name": "Julina Metz",
      "email": "jm1879@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<CISLAB>']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > Most requests were returned quickly and performed well. There were two requests that took much longer to respond, so the overall performace of the application is uneven.
* Is performance even or uneven? 
  > The performance is uneven. Most transactions completed between 0.1 - 0.3 seconds, but some took much longer. 
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant than mutations.
* Among the less performant requests, which ones are the most problematic?
  > The most problematic by far was query #6 which took 46.8 seconds. The second most problematic query was #1 which took 3.36 seconds. All other requests took somewhere between 0.1 - 0.3 seconds. 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > For query #1 the queryOrdersBySearchTerm segment took the longest at 4.4 seconds. The second longest segment was loadOrderById at 1.32 seconds. For query #6 the queryOrdersBySearchTerm segment took the longest at 44.1 seconds.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request was query #6.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment that is the most problematic in query #6 is queryOrdersBySearchTerm which took 44.1 seconds.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Query #6 should be rewritten so that it doesn't query everything in the database, it only queries records with everything bagels. This will significantly reduce the transaction time. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

