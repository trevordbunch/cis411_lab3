# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Garrett Nissley  
**GitHub Handle:** ggn10  
**Repository:** [ggn10/cis411](https://github.com/ggn10/cis411_lab0_req) 
___

# Step 1: Fork this repository
[forked repo](https://github.com/ggn10/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "11bb97ef-8e86-4fd6-add7-0fa745ef9740",
      "name": "Garrett Gerard Nissley",
      "email": "gn1166@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
```
app_name: ['cislab']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > My GraphQL service performed fairly well. There were a few queries that took longer due to the size of them.
* Is performance even or uneven? 
  > Performance is uneven depending on the size of the query.
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant.
* Among the less performant requests, which ones are the most problematic?
  > The queries that queried a large pool of data.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > Query 6 was the longest.
* Using New Relic, identify and record the least performant request(s).
  > Query 6 was the least performant cause it took the longest.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The remainder took the longest.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Hone in our queries to make them more efficient and less time-consuming. This will also get us better and cleaner data.

# Step 7: Submitting a Pull Request

_Note: No lab notes required._
