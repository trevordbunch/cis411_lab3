# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Annika Kowalski  
**GitHub Handle:** AnnikaKowalski
**Repository:** https://github.com/AnnikaKowalski/cis411_lab5_Monitoring 
**Collaborators:** 
___

# Step 1: Fork this repository
  - This is the URL of my forked repository. https://github.com/AnnikaKowalski/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project  
{  
  "data": {  
    "mutateAccount": {  
      "id": "5456e9a2-475b-4dee-96f4-8d22ca9b0709",  
      "name": "Annika Kowaslki",  
      "email": "volleygirl21@comcast.net"  
    }  
  }  
}
# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cis411_Lab5']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > Enter Response Here.
* Is performance even or uneven? 
  > Enter Response Here.
* Between queries and mutations, what requests are less performant? 
  > Enter Response Here.
* Among the less performant requests, which ones are the most problematic?
  > Enter Response Here.

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