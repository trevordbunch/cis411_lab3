# Lab Report: Monitoring

___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Sebastian Alejos
**GitHub Handle:** SebastianAlejos
**Repository:**  <https://github.com/SebastianAlejos/cis411_lab5_Monitoring>
**Collaborators:**
___

# Step 1: Fork this repository

<https://github.com/SebastianAlejos/cis411_lab5_Monitoring>

# Step 2: Clone your forked repository from the command line

- My GraphQL response from adding myself as an account on the test project

``` SQL
{
  "data": {
    "mutateAccount": {
      "id": "e7473606-d54c-4bd3-a2ad-bd2eb476fe9c",
      "name": "Sebastian Alejos",
      "email": "sa1251@messiah.edu"
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

- What are your observations regarding the performance of this application?
  > The perfomance varies depending on the amount of requests it is getting at a given time.
- Is performance even or uneven?
  > It is uneven.
- Between queries and mutations, what requests are less performant?
  > Queries perform worse than mutations.
- Among the less performant requests, which ones are the most problematic?
  > The queries that request a specific keyword are the ones that take the most time.

# Step 6: Diagnosing an issue based on telemetry data

- Within the transactions you're examining, what segment(s) took the most time?
  > The remainder is what took most of the time.
- Using New Relic, identify and record the least performant request(s).
  > The ones that query by word are the least performing ones..
- Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The queryOrdersSearchByTerm is what took the longest.
- Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Filtering the number of items to search through would reduce the load.

# Step 7: Submitting a Pull Request

_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)

For the purposes of gaining 25% extra credit on the assignment, perform any of the following:

1. Adjust the diagnosed slow call(s) to improve performance.
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.
