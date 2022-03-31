# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2022  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Kylie Firestone  
**GitHub Handle:** kfirestone25   
**Repository:** https://github.com/kfirestone25/cis411_lab5_Monitoring 
___

# Step 1: Fork this repository
- https://github.com/kfirestone25/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "0ddba02d-fd9e-4548-a347-01d0a2c9f1e1",
      "name": "Kylie Lynne Firestone",
      "email": "kf1322@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<YOUR APP NAME>']
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
