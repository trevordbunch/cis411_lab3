# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Tim Kratz 
**GitHub Handle:** timkratz 
**Repository:** https://github.com/timkratz/cis411_lab5_Monitoring.git  
**Collaborators:** N/A
___

# Step 1: Fork this repository
- https://github.com/timkratz/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "b9a76e97-c9a6-4191-8c57-936df61f9b0b",
      "name": "Tim Kratz",
      "email": "tk1264@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<Cis411>']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > There are different amounts of time that it takes for each of the queries to run. Query #6 took the longest and query #7 gave me an error when I was trying to run it
* Is performance even or uneven? 
  > The performance is uneven
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant. They take more time to perform than mutations
* Among the less performant requests, which ones are the most problematic?
  > The most problematic was query #7. This was due to the fact that it produced an error. Another one that was probelmatic was query #6. This was due to the fact that it took long to run. Query #1 was also problematic because it was a little slow to run.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that took the most time was queryOrdersBySearchTerm. It took 96.27% of the time. 
* Using New Relic, identify and record the least performant request(s).
  > The least performant requests are the ones that are searching by using the query command. There is no specific category to return different specific results.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment that was the most problematic was the queryOrdersBySearchTerm segment. 
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > A solution to improving the performance of the most problematic requests would be to refrain from searching using the word query. You could add in specific detailed categories is order to speed up the process. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.
