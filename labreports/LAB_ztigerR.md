# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2022  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Tyler Regitz  
**GitHub Handle:** [ztigerR](https://github.com/ztigerR)   
**Repository:** [Repo](https://github.com/ztigerR/cis411_lab5_Monitoring)  
___

# Step 1: Fork this repository
- [Repo](https://github.com/ztigerR/cis411_lab5_Monitoring) 

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
![GraphQl Response](..\\assets/graphql.png "GraphQl Response")

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```Lab5``` configuration
```
app_name: ['Lab5']
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The performance of this application is very fast. After the first querry of getting connected to the database it is able to return the results of the queries rather quickly. A lot of the querries get a response in 6400ms, with a score of .75.
* Is performance even or uneven? 
  > I would say that the performance is even because out of the seven queries only three are very slow to get a response.
* Between queries and mutations, what requests are less performant? 
  > Overall queries are less performant compared to the mutations. The mutation got a score of 1 the highest you can get.
* Among the less performant requests, which ones are the most problematic?
  > The most problematic are querry number 1, 6. This search for the tag Everything took the longest to process. 14300ms and getting a score of .46. But the other one also took a long time.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > queryOrdersBySearchTerm, and Remainder
* Using New Relic, identify and record the least performant request(s).
  > Remainder
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > Remainder is the most problematic it took 41,500 ms to finish.
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > Get rid of remainder the time it takes to finish is 9 times bigger than the rest of the method. But I don't know what Remainder does so maybe you cant get rid of it. However this problem does not affect the account querry that searches by a string so what gives.

  >I editted the transaction trace to trace transations that took longer than .001 seconds so I could see the calls in querry number 7. This one does not have the remiander call in it but is still able to search using a string. This makes me think that remainder was something add to make the response slower.
  ![Orders Trace](..\\assets/OrdersTrace.png "Orders Trace With Remainder")
  ![Accounts Trace](..\\assets/AccountsTrace.png "Accounts Trace Without Remainder")

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.