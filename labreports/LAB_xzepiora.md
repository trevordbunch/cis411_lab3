# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2023

**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  

**Name:** Xavier Zepiora  

**GitHub Handle:** xzepiora

**Repository:** https://github.com/xzepiora/cis411_lab5_Monitoring

**Collaborators:** Ray Truex (rt1252)
___

# Step 1: Fork this repository
- [The URL of my forked repository](https://github.com/xzepiora/cis411_lab5_Monitoring)

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "21e7db50-40cf-44c1-915b-54c4c07041a4",
      "name": "Xavier Zepiora",
      "email": "xz1151@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<GitLab>']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  >Most of the calls performed very quickly with query 6 being the slowest followed by query 1. My average response time was 418ms while my median response time was 4.57ms. My throughput was 1.4 requests per minute and I had an error rate of 7.14%
* Is performance even or uneven? 
  > I would say that performance is uneven because if it was even the average and median would be much closer. Since the average is so much higher than the median we know that there is an outlier that is skewing the data on the high end. This to me would be query 6 since it took significantly longer than the rest. If this query did not exist then we would be even.
* Between queries and mutations, what requests are less performant? 
  > Mutations should take more time to execute than a query because a mutation is used to modify or add data. A query is simply only retrieving the data from the API. All of the test lines provided seem to be queries as they are only searching the data. Mutations should also take more time because they have to run sequentialy while queries can run parallel. All of them perform incredibly quick as well execpt for 6.
* Among the less performant requests, which ones are the most problematic?
  > The most problematic one is 7 because it returns an error. This is a problem because we want actual data back not just an error. 6 is also problamatic because of the time it takes as it is an outlier from the rest.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that took the most amount of time was the queryOrdersBySearchTerm. This took 97.71% of the time. The next closest was the Middleware <'anonymous'><'anonymous'> which took up 1.82% of the time.
* Using New Relic, identify and record the least performant request(s).
  > The requests that were the slowest were the ones that used query in the order section because it meant it had to check every single item instead of something specific like location. These requests were around 15 seconds to respond. With 6 being the slowest.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The most problematic segment is the queryOrdersBySearchTerm.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > I think the best solution is to always use a specific item when querying. So looking for a specific thing like a location or a bagel instead of a query. This would cut down on time. 



# Step 7: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
   
   The two queries that I plan on adjusting are numbers 6 and 7. For 6 I am going to attempt to fix the length of time it takes to respond and for 7 I am going to try and make it not error.
2. Verify the improved performance in New Relic.
   
   I fixed query 6 by changing query to bagel this meant that instead of looking through every item for something labled everythign it only looked through bagels labled everything. So the new query is below.
   ``` 
   orders(bagel: "everything") {
    id
    customer {
      id
      email
    }
    items {
      label
      quantity
    }
   }
  This query resulted in a significantly lower response time.
  ![Query 6 Response Time](Images/Query%206.png)

  The original query 6 was executed at just after 12:10am and the fixed query 6 was run at 12:25am since the numbers are not on the chart they are 15.4sec response on the first query and 0.2sec response on the second one. 


  For query 7 the fix to the issue was to change what the query was looking for. By including item it was searching for items in the account field and the accounts would not have items,lables, and quantities so it was throwing an error. The way to fix this was to remove the item field and the lable and quantity search which makes the code look like this.
  
  ```
  {
  accounts(query: "gmail.com") {
      id
      name
      email
    }
  }
  ```

  This query resulted in actual results being returned which looked like.
  ![Query 7 Results](Images/Query%207.png)

  After both of these fixes were implemented there was a significant decrese in the average response time. The original was 418ms while these changes brought it down to 45.2ms. I am sure that most of this was due to the change for query 6.
  ![New Average Response Time](Images/Avg%20Response.png)
