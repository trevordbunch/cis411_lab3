# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Kyle Luce  
**GitHub Handle:** kylebluce  
**Repository:** https://github.com/kylebluce/cis411_lab5_Monitoring  
**Collaborators:** @scribhneoir
___

# Step 1: Fork this repository
- https://github.com/kylebluce/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "c9e43701-a9a8-40b0-a322-0ac1c337bd9f",
      "name": "Kyle Luce",
      "email": "kylebluce@gmail.com"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
cislab
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > I am not quite sure what New Relic is doing, but I can tell it is responding to each query. It can tell that there is activity on the graphql localhost. New Relic seems to measure throughput and response time as well as error rate. This is clearly a good tool to monitor SLIs.
* Is performance even or uneven? 
  > The perfomance seems relatively uneven. Some queries take longer time to give a response. The "Everything" Query took 23.4 seconds according to New Relic, while some of the other ones were less than 2 seconds.
* Between queries and mutations, what requests are less performant? 
  > Queries are less performant because it takes a bit of time for the graphql to search through everything a provide a result. While mutations just add to the server, so they don't take as long.
* Among the less performant requests, which ones are the most problematic?
  > The most problematic request was for the "Everything" bagels. I am not sure why this was the case because the Onion and Raisin Queries did not take very long. Maybe it has something to do with the length of the string or maybe there was just a lot more Everything Bagels in the database.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that took the longest time is marked as the "Remainder".
* Using New Relic, identify and record the least performant request(s). </br>
![NewRelicRequestInfo](/assets/Request.PNG)
  > This was what I could find about the least performant request. It was a search query, I am assuming for the the query about Everything Bagels, although the email query gave an error, so that might have been it as well.
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings. </br>
![NewRelicSegments](/assets/segments.PNG)
  > Here is the information about the segments that were the most problematic. The "Remainder" category and the "QueryOrdersBySearchTerm" took the longest, but the Remainder was what took the most time. It's hard to tell what makes up that remainder.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > I think one possible solution would be to sort the database more easily. You could make separate tables for bagel types, so that you don't search through every single order to find the everything bagels or onion bagels. That would reduce the search time and get users the information they want quicker.
