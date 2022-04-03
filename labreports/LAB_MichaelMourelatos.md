# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2022  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Michael Mourelatos  
**GitHub Handle:** [MichaelMourelatos](https://github.com/MichaelMourelatos)  
**Repository:** [My Forked Repository](https://github.com/MichaelMourelatos/cis411_lab5_Monitoring)  
**Collaborators:** [Grace Schlauder](https://github.com/grace-schl) and [Andrew Coldsmith](https://github.com/andrewcoldsmith)
___

# Step 1: Fork this repository
- [The URL of my forked repository](https://github.com/MichaelMourelatos/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "17d932e1-ba6d-4631-8510-0fcc3645a213",
      "name": Michael Mourelatos",
      "email": "mm1682@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: [MichaelM-cislab]
```

# Step 4: Exercising the application / generating performance data

*Note: No lab notes required.*



# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > All the queries ran smoothly for the most part. The "Everything" query took the most time to output, and the "Onion" query was one of the quickest to output. The "gmail.com" query did not run because of a syntax error.
* Is performance even or uneven? 
  > The performances were uneven due to a difference in spikes. Some queries led to an output of a big spike. Some other queries had small spikes.
* Between queries and mutations, what requests are less performant? 
  > Queries can take a variety of time, as we saw through the multiple queries of bagel information. Mutations don't take up too much time compared to queries and are more consistent with how long the response time will be. So, generally, queries will be quicker than mutations, but a few queries took longer than most queries.
* Among the less performant requests, which ones are the most problematic?
  > Bagel names and locations were quicker than a broader search such as "everything" or "PA." To help with efficiency in searches, it is good to be specific in your searches.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that took the longest time was the "Remainder" segment. This was most evident when the query would run long in general. The next noteworthy long segment would be "queryOrderBySearchTerm"
* Using New Relic, identify and record the least performant request(s).
  > The "everything" query took the longest to run with a 35,500 ms response time.  

  **Longest Run Time**:
  ![Longest Run Time](/Longest_Run_Time.png)

* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The "remainder" segment was not very helpful, and I would consider it problematic. It is what caused a longer response time, and it does not specify or elude to what is going on with the remainder segment.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > If the longest segment could provide more information as to what is going on or break up the segment up a little, that would be beneficial to understand what is making response time take longer. However, those adjustments target how to improve New Relic. To improve the response time and reduce the "remainder" segment would be to be more specific in the queries to allow for a more efficient output time. Such as using keywords.

# Step 7: Submitting a Pull Request

*Note: No lab notes required.*

# Step 8: [EXTRA CREDIT] Address the performance issue(s)

1. The last query gave me an error when running it so I removed the "items" section with "label" and "quantity". I also was able to add in different columns such as "cell" and "name." The error was causd by the field "items" not being on type Account.

**Fixing Error**:
![Fixing Error](/Fixing_Error_for_Last_Query.png)



2. The first slow query was Query 1. Changing the word query to location allowed for the same output but a quicker response time.

**Fixing Query 1**:
![New Query](/Changing_Query_to_Location_for_PA.png)
![Transaction Trace](/Transaction_Trace_Response_Time_After_Changes_to_PA.png)


3. The query that searched for "everything" was changed by removing "query" for "bagel." This gave me the same information. Changing query to bagel made the response time be more efficient.