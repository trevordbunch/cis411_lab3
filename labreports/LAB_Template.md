# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Robbie Dorsey  
**GitHub Handle:** airgo32  
**Repository:** [Link](https://github.com/airgo32/cis411_lab5_Monitoring)    
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository   
[https://github.com/airgo32/cis411_lab5_Monitoring](https://github.com/airgo32/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "a57f9b39-d05c-4a95-85a9-00c4027a4fb0",
      "name": "Robbie Dorsey",
      "email": "rd1288@messiah.edu"
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
  > Overall I think it's fine. Some requests definitely took longer than others and I think a user who is not expecting a long wait will be surprised.
* Is performance even or uneven? 
  > It's fairly uneven. Some requests finish almost immedietley, some take about one second, and some take several seconds to finish.
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant, but that makes sense to me because mutations only add one item at a time, whereas queries have to search through hundreds or thousands of records.
* Among the less performant requests, which ones are the most problematic?
  > The first query and the query about everything bagels were noticeably worse. 

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The section labelled "Remainder" took the longest amount of time. The section queryOrdersBySearchTerm also took a long time relative to everything else.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request is definitely queryOrdersBySearchTerm
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > queryOrdersBySearchTerm is definitely the most problematic. It calls `loadByOrderId` hundreds of times, and each time executes pretty quickly but it adds up over time.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > I think the way to fix the worst request (the one that looks for everything bagels) is to search by `bagel: everything` instead of `query: everything`

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
I managed to get better performance for the sixth query by changing the line `query: everything` to `bagel: everything`. While this could theoretically return different data if one person's email contained the word "everything", this change sped up the time by a ton.