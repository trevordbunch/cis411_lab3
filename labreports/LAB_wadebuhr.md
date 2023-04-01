# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Wade Buhr   
**GitHub Handle:** wadebuhr  
**Repository:** https://github.com/wadebuhr/cis411_lab5_Monitoring/blob/main/  
**Collaborators:** None  
___

# Step 1: Fork this repository
- https://github.com/wadebuhr/cis411_lab5_Monitoring/blob/main/

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "b744eda5-4fed-4865-b532-9bd2040b721b",
      "name": "Wade Buhr",
      "email": "wb1206@messiah.edu"
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
  > The performance of this application seems to be good. There was response times of 1.725, .1, .112, 4.334, 8.532 seconds, with an average of 2.16 seconds. The appdex score to see how good our app is performing was .56 which means that our app is performing satisfactory, since it is about half of 1. We hit a 11.11% error rate which is not good.
* Is performance even or uneven? 
  > The performance was uneven becauase the query of all the orders containing the word "everything," took the longest time of 8.5 seconds while the others were much faster other than querey that took 4.3 seconds. 
* Between queries and mutations, what requests are less performant? 
  > Queries seem to be less performant than mutations. The mutations performed seemed to happen in an instant while some queries took much more time to respond. 
* Among the less performant requests, which ones are the most problematic?
  > The request of the orders conatining the word "everything" was the most problematic, and the request of the orders containing the word "PA" was next in line. It seems that the requests that ask for specific words take longer than the others.  

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The segment that took the most time was the request of the orders containing the word "everything"
* Using New Relic, identify and record the least performant request(s).
  > The least performant requests was the request of searching for accounts with gmail.com. This was the least performant because it gave an error. Other than that, the least performant requests were the queries asking for specific words in the querey such as the word "everything" and the orders containing the word "PA."
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment in the queries that was the most problematic, was the request of the orders that contained the word "everything" because people love their everything bagels. 
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > A solution for improving the performance could be restricting some of the fields. In the most problematic request, we can get rid of the customers email and the label since we have their ID and we already know it is the word "Everything." This can reduce the amount of data that needs to be retrieved and thus speeds up the query. We could also use pagination to limit the number of results returned, but this would only be good if we only want a small subset of the results and not all of them. 

# Step 7: Submitting a Pull Request
_Note: No lab notes required._

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.