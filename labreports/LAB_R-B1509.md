# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Rachel Beattie
**GitHub Handle:** [Your GitHub Handle](https://github.com/R-B1509)  
**Repository:** [Your Forked Repository](https://github.com/R-B1509/cis411_lab5_Monitoring)  
**Collaborators:** 
___

# Step 1: Fork this repository
- (https://github.com/R-B1509/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "bac13462-8ea5-43f9-bd03-3ce6302e586c",
      "name": "Rachel Beattie",
      "email": "rb1509@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cis411Lab5']
```

# Step 4: Exercising the application / generating performance data
<p> First query took about a minute or two, 1.5 minute? second one took only a minute/was faster, third one was also relatively fast, fourth one took about 2 seconds, fifth 5 seconds. 6th took a lot more time, 3 minutes? 7th one took less than a second.
</p>
<p> Summary: The pattern is that the ones querying through everything for specific item without searching through the category in which it was in took longer.
/<p>
<p> Response time: 69ms, Throughput: 1.87 rpm, Error rate: 1.79%, CPU Utilization: .18%, Memory Usage: 127.4 MB
</p>

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > There were spikes of activity in the performance depending on the query run, but mostly it was one to one.
* Is performance even or uneven? 
  > Fairly evenish? Or perhaps unevenish? About half of the queries do hold the possibilities of issues.
* Between queries and mutations, what requests are less performant? 
  > Mutations require way less performances. Query order by search term is the most time consuming. That being said, mutations don't seem to do much besides input data.
* Among the less performant requests, which ones are the most problematic?
  > Order by Bagel type query shows more time processing the order rather than the query search, but in terms of problematic queries, the search for "everything" query takes a longer time to find, probably because it's going through the whole database rather than a category like the "Bagel". Query one's code also holds this issue, but to a lesser extent.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The search for "Everything" took the most time in the component of "queryOrdersBySearchTerm".
* Using New Relic, identify and record the least performant request(s).
  > Query 6, and to a lesser extent, query one.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > orders(query: ) in the broadest definition holds the most trouble.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Rather than querying through the whole order system for "everything", search in the bagel so replace order(query: "Everything") with something like order(bagel: "Everything") because the semantics is searching for who ordered every type of bagel from what I can guess. Same with Query one, it was fixed with the change in code that Query two had.