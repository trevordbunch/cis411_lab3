# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Tim Diana  
**GitHub Handle:** Tim12-code  
**Repository:**   
**Collaborators:** 
___

# Step 1: Fork this repository
- https://github.com/trevordbunch/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
{
  "data": {
    "mutateAccount": {
      "id": "40e0c90e-3f1a-4426-92ca-e630abf5eab4",
      "name": "Timothy Diana",
      "email": "td1245@messiah.edu"
    }
  }
}

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```cislab``` configuration
```
app_name: ['<cislab>']
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