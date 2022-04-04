# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Kemi Gloria Houngbeke
**GitHub Handle:** GlorKemH
**Repository:**  https://github.com/GlorKemH/cis411_lab5_Monitoring
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository

"https://github.com/GlorKemH/cis411_lab5_Monitoring"


# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "c436a371-07bb-4ab1-b670-bbf71dba3a1f",
      "name": "Kemi Gloria Houngbeke",
      "email": "gh1241@messiah.edu"
    }
  }
}



```


# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<cislab>']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > From my observation not all querries were working properly

* Is performance even or uneven? 
  > The performance was even for some queries

* Between queries and mutations, what requests are less performant? 
  > The less perfoming queries were #3 & #6

* Among the less performant requests, which ones are the most problematic?
  > #2 & #7 were not working

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > 50% for segment is query #3

* Using New Relic, identify and record the least performant request(s).
  > the least performing query was #3
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > Enter Response Here.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > I would switch up queries so that it could pull data better.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.