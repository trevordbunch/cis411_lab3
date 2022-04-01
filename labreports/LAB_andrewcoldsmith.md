# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2022  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Andrew Coldsmith  
**GitHub Handle:** [andrewcoldsmith](https://github.com/andrewcoldsmith)  
**Repository:** [Forked Repository](https://github.com/andrewcoldsmith/cis411_lab5_Monitoring)  
**Collaborators:** [Grace Schlauder](https://github.com/grace-schl); [Michael Mourelatos](https://github.com/MichaelMourelatos)
___

# Step 1: Fork this repository
- The URL of my forked repository [https://github.com/andrewcoldsmith/cis411_lab5_Monitoring](https://github.com/andrewcoldsmith/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "9ac31cb2-a8ef-4b4a-b7e6-b327f1b234e8",
      "name": "Andrew Coldsmith",
      "email": "ac1500@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['cis411lab5']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > For the most part, it ran just fine. However, query 1 and query 6 were very slow compared to the others, and query 7 had errors preventing it from running.

* Is performance even or uneven? 
  > The performance was uneven. There were a few huge spikes from the startup and query 6.
* Between queries and mutations, what requests are less performant? 
  > Mutations seemed to take more time than most queries, but a few queries took way more time.
* Among the less performant requests, which ones are the most problematic?
  > Queries for words in general were much slower than more specific requests like locations and bagel names.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The remainder segment always took the most time, especially with requests that were extra long. Also, the query segment was always the second longest.
* Using New Relic, identify and record the least performant request(s).
  > Query 6 took the most time by far. It took 105,285 ms to complete, which is nearly two minutes.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The remainder segment always seems to be the problem with requests that are too long. Unfortunately, it’s also the most vague of all the segments and doesn’t give much explanation of what it represents.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > It seems like what could easily improve the problematic requests is simply altering the queries so they don’t search the entire database for a keyword. If a specific table like bagel or location was specified, there wouldn’t be as much slow-down.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)

* Query 1 ran faster when I changed “query” to “location”, and it produced the same results.
![Query 1](..\assets\q1.png)
![Transaction for Query 1](..\assets\tq1.png)

* Query 6 ran much faster when I changed “query” to “bagel”, and it produced the same results.
![Query 6](..\assets\q6.png)
![Transaction for Query 6](..\assets\tq6.png)

* Query 7 ran just fine after I replaced the “items” table and subtables with “email”.
![Query 7](..\assets\q7.png)