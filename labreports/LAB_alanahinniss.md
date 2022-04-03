# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Alanah Inniss  
**GitHub Handle:** alanahinniss  
**Repository:** https://github.com/alanahinniss/cis411_lab5_Monitoring.git  
**Collaborators:** 
___

# Step 1: Fork this repository
- https://github.com/alanahinniss/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "d6f0489b-0008-46a6-87c3-61fa4e63476c",
      "name": "Alanah Inniss",
      "email": "ai1177@messiah.edu"
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
  > From what was observed, the response times for majority of them were steady except for the GraphQL 6 from step 4; it took a longer time to complete. Also each query required different amount of data. 

* Is performance even or uneven? 
  > For this application, the performance was uneven; varying with each query. The average throughput was 0.433 rpm. 

* Between queries and mutations, what requests are less performant? 
  > The requests that were less performant were query 6 and 7. With query 6, it took the longest amount of time for results to be shown. However, with query 7 an error was shown as the outpout. 

* Among the less performant requests, which ones are the most problematic?
  > The most problematic was the seventh query due to the error returned. As a result of this, the results were not helpful. 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The transaction that took the most time was query 6. 

* Using New Relic, identify and record the least performant request(s).
  > Query 7 was the least performant request. The error was that it could not validate the request. 

* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment of the process that seemed to be the most problematic based on the results was the remainder, which took most time.
  
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Narrowing down the result of the queries, for example; combining both queries. Another recommendation is a cache control which would lower the data load. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

Extra note: http://localhost:4001/graphql had to be used instead of 4000 as this is what npm generated for this lab when it was installed in the files for it.  