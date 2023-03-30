# Lab Report: Monitoring
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Jonah Robinson    
**GitHub Handle:** [jrmakr2123](https://github.com/jrmakr2123)  
**Repository:** [cis411_lab5_Monitoring](https://github.com/jrmakr2123/cis411_lab5_Monitoring)  
<!-- **Collaborators:**  -->
___

# Step 1: Fork this repository
- https://github.com/jrmakr2123/cis411_lab5_Monitoring

# Step 2: Running GraphQL from the command line
- My GraphQL response from adding myself as an account on the test project
```
{
  "data": {
    "mutateAccount": {
      "id": "ac2ab0d1-598a-4d66-be29-18e8ba693693",
      "name": "Jonah Robinson",
      "email": "jr1521@messiah.edu"
    }
  }
}
```

# Step 3: Signup for and configure New Relic
- The chosen name of your New Relic ```app_name``` configuration
```
app_name: ['<cis411_Lab>']
```

# Step 4: Exercising the application / generating performance data

<!-- _Note: No lab notes required._ -->

# Step 5: Explore your performance data
* What are your observations regarding the performance of this application? 
  > The performance fluctuates depending on the request. Through the charts of New Relic, we see that depending on the size of the request, more time is dedicated to that request. In a real life scenario, this could be seen in website load times to general application performance and speed. 
* Is performance even or uneven? 
  > The performance we uneven. Like stated before, depending on the request, more time was alloted so the charts peaked when the more resource heavy query ran. 
* Between queries and mutations, what requests are less performant? 
  > queries seem to be less performant. My understanding is that within the state class (like orders), query searches each variable and subclass variable. This means that every bit of information needs to be ran by query within the orders class. For mutations, an entirely new instance of the selected class is created. Thus mutations only deal with the created information and where to put it rather than the entire lot of information as a whole (like query does). 
* Among the less performant requests, which ones are the most problematic?
  > The most problematic is request 7. That churns out an error. Looking at the information the request is inquiring, we can assume this request is looking for the name, id, and email of all accounts with a "gmail.com." To fix this we can run the query like this . . .

  ~~~
  {
  #Query 7: all accounts that contain gmail.com
  accounts(query: "gmail.com") {
      id
      email
      name
    }
  }
  ~~~
  >The next problematic request is request 6. This queries all variables for the word "everything." The nature of the request is searching for the bagel in particular. In that case we can change query to bagel in the search parameters and the issue is fixed. 

  >The final problematic request is the request 1. This is actually fixed by request 2. In request 1, we query for the word PA. Like before this searches all possible variables for PA. This takes less time than request 6 because PA or the location data is closer to the top of the query chain. To fix this, like in request 2, we search through the location variable for PA thus we do not search in areas PA would not be in (increasing response time). I will detail more of this bellow in the extra credit tab :).


# Step 6: Diagnosing an issue based on telemetry data
* Within the transactions you're examining, what segment(s) took the most time?
  > The queryOrdersBySearchTerm segment took the longest time. This makes sense since this is the main function that is being ran for each request. 
* Using New Relic, identify and record the least performant request(s).
  > These, like stated before, are requests 7, 6, and 1. Request 7 does not work at all so that is the least performant (right now). Request 6 takes the longest time (thanks to the broadness of the query). Request 1 is the 3 least performant due to the same issues of request 6. 
* Using the Transaction Trace capability in New Relic, identify which segment(s) in that request permeation is/are the most problematic and record your findings.
  > The segment labeled queryOrdersBySearchTerm is the part that tanks the performance the most in each of the problematic requests, except for request 7. Request 7 never actually ran due to an error. 
* Recommend a solution for improving the performance of those most problematic request(s) / permeation(s).
  > For request 7, format the query to actually pertain to the accounts class type. This means not having an items section and only including the email, id, and name sections. A further improvement to request 7 is to use email instead of query since we know what variable we want to search. For request 6 and 1, like the further improvement to request 7, we should also stop using query and start utilizing the variable title. In request 6 utilizing the bagel variable will limit the number of variables the request needs to search, thus speeding up the process. In request 1, we can use the location variable like request 2. In fact, request 2 is the improved version of request 1 so we should use that formatting instead. 

# Step 7: Submitting a Pull Request
<!-- _Note: No lab notes required._ -->

# Step 8: [EXTRA CREDIT] Address the performance issue(s)
For the purposes of gaining 25% extra credit on the assignment, perform any of the following:
1. Adjust the diagnosed slow call(s) to improve performance. 
2. Verify the improved performance in New Relic, **including data and/or screenshots in your lab report**.
2. Check in those changes and **note your solution(s)** in your lab report.