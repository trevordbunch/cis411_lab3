# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Grace Taylor  
**GitHub Handle:** gracet712  
**Repository:** https://github.com/gracet712/cis411_lab5_Monitoring      
**Collaborators:** N/A
___

# Step 1: Fork this repository
- https://github.com/gracet712/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project:
```
{
  "data": {
    "mutateAccount": {
      "id": "eb9cfa57-40cf-4de7-8b73-0da452ba9d72",
      "name": "Grace",
      "email": "test@email.com"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```cislab5``` configuration
```
app_name: ['cislab5']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > It responds quickly when searching a particular field for a value. If searching multiple fields for a given value, it takes longer. For example, searching for orders with the location "PA" responded fast, but searching for orders containing the word "PA" took longer. Searching for orders containing the word "everything" took the longest.
* Is performance even or uneven? 
  > Performance is uneven based on the difficulty of the query. Queries that must search through more data take longer.
* Between queries and mutations, what requests are less performant? 
  > The queries run in this lab are less performant, but only those that require searching through a large amount of data. Presumably mutations that required changing large amounts of data would also be less performant.
* Among the less performant requests, which ones are the most problematic?
  > The most problematic request is # 6 - retrieving all orders that contain the word "everything." This query needs to search through multiple fields for the word "everything," but based on the results, it appears that "everything" is always a label - so it would be more efficient to search for the value just in this field if that is what is intended.

  > Request # 1 - searching for all orders containing the word "PA" - also took a while, though not as long as request # 6. Assuming this is what is intended, it would be best to rewrite this like request # 2, searching specifically for location.

  > The last request has a syntax error - the application cannot search for order information such as item labels and quantity when searching through user accounts. However, the error result is returned very quickly. The following request is presumably what was intended:
  ```
  {
    #Query 7: all accounts that contain gmail.com
    accounts(query: "gmail.com") {
      id
      name
      email
    }
  }
  ```

  > In spite of being a generic query that doesn't reference a particular field, it runs quickly, possibly because it has fewer fields to look through. It would still be better practice to query the email field specifically.

  ##### Overview Screenshot:
  ![New Relic Overview Screenshot](/assets/newrelic_overview_screenshot.png)

  This overview describes several important metrics, including error rates, time spent on web transactions, throughput, host performance, and more.

##### Host Screenshot:
![New Relic Host Health Screenshot](/assets/newrelic_host_Screenshot.png)

This table describes how much CPU and memory on my computer are being used by the application. It also indicates its performance in terms of response time, throughput, and error rate. The CPU utilization and memory usage are fairly low. The response time and error rate both seem rather high to me, a result of the particular queries run.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The "queryOrdersBySearchTerm" segment took the most time (98.6 % for the longest transaction visible). This indicates that searching through the data is the most time-consuming part of the process.
* Using New Relic, identify and record the least performant request(s).
  > The least performant request visible on New Relic had a response time of 1.27 minutes, 98.6 % of which was"queryOrdersBySearchTerm" segment. Based on my experience running the queries, I assume this is #6, querying orders for the term "everything."
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The most problematic segment is the "queryOrdersBySearchTerm" segment, which took 1.25 minutes out of 1.27 on the least performant request. This is presumably because it must search through a lot of fields, rather than one specific field as in most of the other requests.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Since the results of query #6 indicate that "everything" was really just being looked for in the label field, I would query just the label field (associated with the "bagel" argument) instead of every field associated with the order. I would adjust query #1 in the same way, and fix query #7, as shown below:

```
{
  #Query 1: all orders in PA - same as #2, assuming this is the intention
  orders(location: "PA") {
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
}
```

```
  {  
    #Query 6: retrieve all orders w/ label that contains everything
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
  }
```
  ```
 {
  #Query 7: all accounts w/ email that contains gmail.com
  accounts(query: "gmail.com") {
    id
    name
    email
  }
}
  ```

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)

The following slow calls were adjusted to improve performance:

(Note - the performance metrics are all averaged, but the time spacing is adjusted so the average only reflects the query in question for each screenshot below.)

#### Query 1 - Original:
###### Query:
![Query 1 - Original](/assets/q1_orig_query.png)
###### Performance:
![Query 1 - Performance - 7.77 s](/assets/q1_orig_performance.png)

> POST response time was 7.77 seconds.
#### Query 1 - Adjusted:
###### Query:
![Query 1 - Adjusted](/assets/q1_new_query.png)
> This is the same as Query 2 - searching for PA in location - assuming this is the intended behavior.
###### Performance:
![Query 1 - Performance -  81.8 ms](/assets/query1_new_performance.png)
> POST response time was 81.8 ms.
#### Query 6 - Original:
###### Query:
![Query 6 - Original](/assets/q6_orig_query.png)
###### Performance:
![Query 6 - Performance - 1.39 minutes](/assets/q6_orig_performance.png)
> POST response time is 1.39 minutes.
#### Query 6 - Adjusted:
###### Query:
![Query 6 - Adjusted](/assets/q6_new_query.png)
> Searching for "everything" in the label (bagel) field instead of anywhere - assuming this is the desired behavior.
###### Performance:
![Query 6 - Performance - 451 ms](/assets/q6_new_performance.png)
> POST response time is 451 ms.
#### Query 7 - Original:
###### Query:
![Query 7 - Original](/assets/q7_orig_query.png)
###### Performance:
![Query 7 - Performance - 14.7 ms](/assets/q7_original_performance.png)
> POST response time: 14.7 ms (for error message)
#### Query 7 - Adjusted:
###### Query:
![Query 7 - Fixed Syntax](/assets/q7_new_query.png)
> This fixes the syntax error and presumably delivers the required information.
###### Performance:
![Query 7 - Performance - 16.3 ms](/assets/q7_new_performance.png)
> POST response time is 16.3 ms