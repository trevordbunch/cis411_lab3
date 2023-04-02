# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Jeff Sinsel  
**GitHub Handle:** JeffSinsel  
**Repository:** [Your Forked Repository](https://github.com/JeffSinsel/cis411_lab5_Monitoring)  
**Collaborators:** 
___

# Step 1: Fork this repository
- The [URL](https://github.com/JeffSinsel/cis411_lab5_Monitoring) of my forked repository

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "96932fbd-2b40-44c1-be67-3ff090610cd0",
      "name": "Jeff Sinsel",
      "email": "js2062@messiah.edu"
    }
  }
}
```

# Step 3: Sign up for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cislab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The application runs well but struggles when it comes to large queries with parameters that search every part of an order.
* Is performance even or uneven? 
  > The performance is very uneven, some queries were almost instant while other took over 30 seconds
* Between queries and mutations, what requests are less performant? 
  > Query 1 and 6 both took a a long time to complete
* Among the less performant requests, which ones are the most problematic?
  > Query 6 does not perform well and also does not 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The part of the query that took the longest is the part that actually went a searched through the database
* Using New Relic, identify and record the least performant request(s).
  > Query 1 and 6 were the least performant requests
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The querying part of the query was the most problematic with Query 1's querying taking 2742 ms and Query 6's querying taking 33590 ms.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Both of the queries searched through every value in the orders causing them to have to search through a lot more data than the other queries. An easy way to fix this is adjust the queries to be more specific. For example rewriting query 1 to the query below so it only searches through the location parameter
  ```{
    orders(location: "PA") {
      id
      customer {
        id
        email
      }
      items {
        label
        quantity
      }
    }
  }
  ```

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.