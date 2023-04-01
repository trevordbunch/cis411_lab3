# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Tim Comerford
**GitHub Handle:** Tcomerford1972  
**Repository:** [My Forked Repository](https://github.com/TComerford1972/cis411_lab5_Monitoring.git)
**Collaborators:** 
___

# Step 1: Fork this repository
- [The URL of my forked repository](https://github.com/TComerford1972/cis411_lab5_Monitoring.git)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "4e982611-217a-41b9-8efa-f07efba2edcf",
      "name": "Tim Comerford",
      "email": "tc1280@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```Lab5``` configuration
```
app_name: ['Lab5'],
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The performance for queries seems pretty awful for some queries, and fast for others.
* Is performance even or uneven? 
  > Very uneven some queries were very fast , other really slow in response time.
* Between queries and mutations, what requests are less performant? 
  > Queries, I believe had more performance issues.
* Among the less performant requests, which ones are the most problematic?
  > The seventh query returned all errors.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > I dont know was only able to glean information based off search query respnse time.
* Using New Relic, identify and record the least performant request(s).
  > Unknown.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  >Unknown.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Unknown.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._
