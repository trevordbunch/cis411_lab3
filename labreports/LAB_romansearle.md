# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Roman Searle  
**GitHub Handle:** RomanSearle
**Repository:** [Your Forked Repository](https://github.com/RomanSearle/cis411_lab5_Monitoring) <br>
**Collaborators:** @Alecclyde - Setp 5 + 6 questions
___

# Step 1: Fork this repository
- https://github.com/RomanSearle/cis411_lab5_Monitoring

# Step 2: Clone your forked repository from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "e2f3d43b-f16f-4429-a2cb-4c11306e7598",
      "name": "Roman Searle",
      "email": "romanpsearle@gmail.com"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: [LAB5]
```

# Step 4: Exercising the application / generating performance data

_Note: No lab notes required._

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application?
   
  > This application performs quite well, unless asked something that is a large query request or that results in an error.

* Is performance even or uneven? 
  
  > The performance of each query varied in overall length quite a lot. For the queries that returned a similar amount of information the times were closer. In the trace itself the remainder takes up by far the most time of any step.

* Between queries and mutations, what requests are less performant? 
  
  > The requests that asked to query for "everything" and the request that results in an error were the least performant as it took by far the longest or resulted in an error. 

* Among the less performant requests, which ones are the most problematic?
  
  > The requests that returned an error was the most problematic. This is the case because an error is always worse than a slow response.

# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  
  > The remainder segment took the most time.

* Using New Relic, identify and record the least performant request(s).
  
  > The least preformant request was the request that contained the word "everything".

* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  
  > The remainder request is the most problematic because they take by far the longest to run.

* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  
  > Do not write a request that results in an error.

# Step 7: Submitting a Pull Request
_Note: No lab notes required._
