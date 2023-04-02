# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Mitch DiFante  
**GitHub Handle:** @mitchdifante
**Repository:** https://github.com/mitchdifante/cis411_lab5_Monitoring.git 
**Collaborators:** Joe McGillen (@jm1959)


# Step 1: Fork this repository
- https://github.com/mitchdifante/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "7fb9a014-4266-460b-85bc-4a2501743eb4",
      "name": "MITCH DIFANTE",
      "email": "md1430@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cis411_app']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > Some observations regarding the performance of this application was everything ran very quickly and with a lower error possibility with error only happening about 4% of the time. Additionally, the response time of the application was within the 99th percentile which is an incredible performance overall by the application.
* Is performance even or uneven? 
  > The performance here is even. 
* Between queries and mutations, what requests are less performant? 
  > Between queries and mutations, queries requests seem to be less performant than mutation requests. Query order by search term was the slowest request with an increase in slowness by 75.32% while mutations were mere miliseconds and were only a few tenths of a percentage.
* Among the less performant requests, which ones are the most problematic?
  > Overall, the requests that were morst problematic were query order by search terms. Compared to others, the average search time was 2.52 seconds which was 75.32% of the time for searches. This is the most problematic because users are going to wish to search for more items and with a slow response time, it is not prioritizing users time.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segments that took the most amount of time were QueryOrdersbySearchTerm and loadOrderByld.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request was QueryOrdersbySearchTerms.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segments that are the most problematic are error rates, the query orders by search terms and load orders.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > A possible solution for improving the performance of these problematic requests are to limit the number of available search terms, this will allow for the system to search for less items and increase response time and put user time as a main focus. Second, for load orders, Implement a progressive loading technique which allows users to interact with the app while data is still being loaded in the background. This can help reduce perceived load times and improve user experience.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.