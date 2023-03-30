# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Noah Brenneis  
**GitHub Handle:** NoahBrenneis  
**Repository:** github.com/NoahBrenneis/cis411_lab5_Monitoring  
**Collaborators:** 
___

# Step 1: Fork this repository
- github.com/NoahBrenneis/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "18305459-aeff-4599-b782-6c248be51cc4",
      "name": "Noah Brenneis",
      "email": "nb1317@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['CIS411 Lab5 - Monitoring']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The application has a relatively stable performance, although it can sometimes take some time for queries to finish.
* Is performance even or uneven? 
  > The performance of this application is uneven. While most queries finish in a relatively short amount of time, some queries take over a whole minute to complete.
* Between queries and mutations, what requests are less performant? 
  > Queries are far less performant than mutations. Whereas mutations take mere milliseconds to process, queries can take anywhere from a few seconds to a minute to complete.
* Among the less performant requests, which ones are the most problematic?
  > The least performant request is when performing a query using the query keyword. While other keywords such as location and bagel have relatively short response times, searching using the query keyword takes over 40 seconds each time, and takes even longer the longer the search term is.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that takes the most time is the queryOrdersBySearchTerm component, which takes around 5 seconds on shorter queries and over 40 seconds on longer queries, up to over a minute.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request was the query orders(query: "blueberry"). I tested this query after performing the example queries given, and it took 1 minute and 16 seconds to process. The last query from the examples (orders(query: "everything")), meanwhile, only took 58.2 seconds.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment that is most problematic is the queryOrdersBySearchTerm component. This segment takes up 99% of the response time for the longest request, and in and of itself lasted over a minute.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > The simplest solution to improving the performance of these queries is to avoid using the query keyword entirely. By specifying a specific category, such as specifying "bagel: everything" instead of "query: everything", only a small portion of the data needs to be searched through instead of the whole thing, drastically improving performance.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.