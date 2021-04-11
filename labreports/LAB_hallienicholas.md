# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Hallie Nicholas  
**GitHub Handle:** hallienicholas  
**Repository:** [My Forked Repository](https://github.com/hallienicholas/cis411_lab5_Monitoring.git)  
**Collaborators:** 
___

# Step 1: Fork this repository
- The URL of my forked repository is: https://github.com/hallienicholas/cis411_lab5_Monitoring.git

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "a84d4ba1-df1d-4f43-b27f-fa18eb6b46aa",
      "name": "Hallie Nicholas",
      "email": "hn1182@messiah.edu"
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

**Query 1 results:**
![Query 1](/assets/query1.png)

**Results after Query 2**
![Query 2](/assets/query2.png)

**Results after Query 3**
![Query 3](/assets/query3.png)

**Results after Query 4**
![Query 4](/assets/query4.png)

**Results after Query 5**
![Query 5](/assets/query5.png)

**Results after Query 6**
![Query 6](/assets/query6.png)

**Results after Query 7**
![Query 7](/assets/query7.png)

**Query 7 Response Time**
![Response Time](/assets/responsetime.png)

**Overview of all Transactions**
![Overview](/assets/overview.png)
![All past Transactions](/assets/transactions_all.png)

**Time Consumed By Segment**
![Time by Segment](/assets/bySegment.png)

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > 
* Is performance even or uneven? 
  > For this application, performance was uneven based on my observations. For each of the queries, when looking at throughput which is the capacity of the app at each query, and as you can see from the overview, it varies with each. The average throughput was 3.44 rpm but the queries are each anywhere from 0 to 25. Also, if you look at the average duration after each query, it is always different, some varying more than others between queries. This shows that the time during each is not linear; therefore, this app is not very consistent in it's performance. 
* Between queries and mutations, what requests are less performant? 
  > The requests which were less performant were query 6 and 7. With query 6, it took the longest amount of time to even show results for it and when I looked at the  
* Among the less performant requests, which ones are the most problematic?
  > The seventh query is the most problematic due to the error returned. This one also produced an error, so no results were even given.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The sixth query took the most time. Upon running, there is a considerably long response time compared to the other queries.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request was the seventh. It resulted in an error saying that it could not validate the request, and could not query the field.
  ![Error](/assets/error.png)
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The two worriesome requests throughout this lab have been the sixth and seventh. When looking at the Transaction Traces which are shown below for each, it seems that the seventh one had a longer response time at 45,000 ms while the sixth had response time of 41,300 ms. This surprised me because while I was running each, the sixth took much longer to produce an outcome than the seventh one. In addition, for both of them the "queryOrdersBySearchTerm" took the longest time other than "remainder". The remainder took a significant amount of time which makes me wonder if the database simply contains too much unnecessary data which showed specifically in 6. It was able to come up with a result, but with so much time that it might've taken extra to sort through all the other data that wasn't needed.

  **Transaction Trace for 6**
  ![Transaction Trace 6](/assets/6_transaction.png)

  **Transaction Trace for 7**
  ![Transaction Trace 7](/assets/responsetime.png)

* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > The first thing I would suggest in order to improve performance would be to remove unnecessary data as I mentioned before. A big part of the response time could be that the program takes the query and needs to sort through information in the database that is not necessary and if some of that could be removed, response time could improve.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.