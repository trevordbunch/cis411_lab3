# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Joseph Tonnies  
**GitHub Handle:** Jmtonnies  
**Repository:** https://github.com/Jmtonnies/cis411_lab5_Monitoring
**Collaborators:** alecclyde
___

# Step 1: Fork this repository
- https://github.com/Jmtonnies/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "a10db030-ded8-4397-a78f-30b79d3497ab",
      "name": "Joseph Tonnies",
      "email": "Jmtonnies@gmail.com"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['DaLab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > That it is actually pretty slow. If amazon took that long to load it would be pretty annoying.
* Is performance even or uneven? 
  > ZThe performance was uneven depending on the query.
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant becasue they are scanning and finding info while mutations are just changing data.
* Among the less performant requests, which ones are the most problematic?
  > The Everything requests took a long time to execute and bogged down the system. Also, the Gmail.com request did not go through just came back with errors

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment	Expressjs: post / 
* Using New Relic, identify and record the least performant request(s).
  > The request that requested everything
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segments of the trasaction trace go post / then Middleware: getOrders
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Re-label the search term Everything so that literally everything on the website pops up does not pop up and instead just everything bagels.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._
