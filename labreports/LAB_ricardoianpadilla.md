# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Your Name  
**GitHub Handle:** Your GitHub Handle  
**Repository:** Your Forked Repository  
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project

![image.](/assets/image1.png)
# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cislab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > When it came to the performance of the application it seemed to be fast overall with the expection of 6 and 7 performing slightly diffrent.

* Is performance even or uneven? 
  > Peeks seemed to be uneven due to varying peaks
* Between queries and mutations, what requests are less performant? 
  > Queries seemed to less than mutation such as 6.
* Among the less performant requests, which ones are the most problematic?
  > I would say 6 was the most obvious when it came to problematic. 6 taking the longest to respond.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment "Remainder" within the 6th query took the most time. 
* Using New Relic, identify and record the least performant request(s).
  > 6 was the least performant. With a wait time of 21,980 ms
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment that was most problem was the "queryOrderBySearchTerm"
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > As 6 was the most problematic i feel figuring out a way to shorten the search "everthing" to search less fields instead of all field would help the issue.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
_Note: No lab notes required._