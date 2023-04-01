# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Ben Clarke 
**GitHub Handle:** BenOfTheOneRing
**Repository:** [Your Forked Repository  ](https://github.com/BenOfTheOneRing/cis411_lab5_Monitoring/)
**Collaborators:** Mike Shoul
___

# Step 1: Fork this repository
- [The URL of my forked repository](https://github.com/BenOfTheOneRing/cis411_lab5_Monitoring/)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "34231a6e-321f-4f58-bf17-26152ee0b833",
      "name": "YOUR FULL NAME",
      "email": "YOUR EMAIL"
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
  > It is lighting fast exempt for a one or two queries. 
* Is performance even or uneven? 
  > Uneven. On some queries its almost instant, others it takes a long time. 
* Between queries and mutations, what requests are less performant? 
  > Queries seem to be significantly less performant.
* Among the less performant requests, which ones are the most problematic?
  > Query 6 was by far the less performant request. 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The queryOrdersBySearchTerm takes the most time at 98 percent.
* Using New Relic, identify and record the least performant request(s).
  > The query requests by far took the longest time to complete. 
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The most problematic segment is by far queryOrdersBySearchTerm.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > The performance could be improved by modifying the Application code in the app. According to the trace details, the Application code itself was responsible for 98.58& of the time, at 46.69s. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

