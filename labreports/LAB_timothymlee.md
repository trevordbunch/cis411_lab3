# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Timothy Lee  
**GitHub Handle:** timothymlee  
**Repository:** [Forked Repository](https://github.com/timothymlee/cis411_lab5_Monitoring)  
**Collaborators:** 
___

# Step 1: Fork this repository
- The [link](https://github.com/timothymlee/cis411_lab5_Monitoring) of my forked repository

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "7cda460f-ecbb-425f-8c30-795aff404e62",
      "name": "Timothy Lee",
      "email": "tl1261@messiah.edu"
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

| Case | Response Time (ms) | Apdex Score | Errors Per Minute | Longest Section |
|----------------|---|---|---|---|
| Query #1 | 5600 | 1 | 0 | Remainder, loadOrderByld | 
| Query #2 | 94.3 | 0.5 | 0 |  | 
| Query #3 | 301 | 0 | 0 |  | 
| Query #4 | 52.1 | 0.5 | 0 |  | 
| Query #5 | 310 | 0 | 0 |  |
| Query #6 | 38163 | 0 | 0 | remainder, queryOrdersBySearchTerm | 
| Query #7 | 8.42 | 0 | 1 |  | 
| Mutation #1 | 5 |  |  |  | 

  > The duration of the running varies greatly and the last one fails.
* Is performance even or uneven? 
  > The performance is uneven. Responses take from 8.42 ms to 38,163 ms.
* Between queries and mutations, what requests are less performant? 
  > Queries were much less performant than mutations.
* Among the less performant requests, which ones are the most problematic?
  > The query for all ordering containing the word "everything" and the query for all orderings containing the word "PA" were the most problematic. In general, making a query for something containing something was the most problematic.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > queryOrdersBySearchTerm, a branch of Middleware, took the longest time.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request was Query #7, followed by Query #1.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > queryOrdersBySearchTerm made 890 fast method calls and took 37,800 ms of the 38,163 ms.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > One way to improve the problematic requests would be to add a second parameter to the requests that would reduce the number of items that must be examined. Another way that it could be improved is by creating a more organized database that would link larger categories to subcategories. A third way to improve the performance would be to store the results so that subsequent calls of that query could be returned faster.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.