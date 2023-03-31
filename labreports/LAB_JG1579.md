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
```
{
  "data": {
    "mutateAccount": {
      "id": "5f0b14dd-e034-4ac6-8786-74e7fa987575",
      "name": "Jonathan Gaston",
      "email": "JG1579"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<cisLAb5>']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* Enter you computer's health
[image](/assets/My%20Laptop.jpg)
* What are your observations regarding the performance of this application? 
  >  The average response time is 407.83 ms throughout the searches. The longest was 1864.225 ms during number 6. The average error rate was 4.29%. My average throughput was 4.67rpm.
* Is performance even or uneven? 
  > For the most part the queries took up a consistently quick amount of time. Except for 1 and 6 which took up considerably  more time. Number 7 didn't start up and jst returned errors.
* Between queries and mutations, what requests are less performant? 
  > The queries were the least preformat and consistently took up the most time.
* Among the less performant requests, which ones are the most problematic?
  > Number 7 is the most problematic solely because it gave back no useful information. Number 6 is a runner-up because it took enough time that users may become frustrated or annoyed.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment "queryOrdersBySearchTerm" consistently took up the most time. It on average took up 83.7% of the overall time per transaction. 
* Using New Relic, identify and record the least performant request(s).
  > The least performant requests were the query's
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment "queryOrdersBySearchTerm" was the least efficient by an incredibly large margin.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Enter Response Here.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.