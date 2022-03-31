# Lab Report: UX/UI
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Alanah Inniss 
**GitHub Handle:** alanahinniss  
**Repository:** https://github.com/alanahinniss/cis411_lab4_CD2.git  
**Collaborators:** Gloria Houngbeke, Issac Ho, Ammanuel Tamrat, Azianna Yang
___

# Required Content

- [x] Generate a markdown file in the labreports directoy named LAB_[GITHUB HANDLE].md. Write your lab report there.
- [x] Create the directory ```./circleci``` and the file ```.circleci/config.yml``` in your project and push that change to your GitHub repository.
- [x] Create the file ```Dockerfile``` in the root of your project and include the contents of the file as described in the instructions. Push that change to your GitHub repository.
- [x] Embed _using markdown_ a screenshot of your successful build and deployment to Heroku of your project (with the circleci interface).  
> Example: ![Successful Build](../assets/Screen%20Shot%202022-03-28%20at%2012.49.50%20AM.png)

- [ ] Write the URL of your running Heroku app here (and leave the deployment up so that I can test it):  
> Example: [http://cis411lab2-trevordbunch.herokuapp.com/graphql](http://cis411lab2-trevordbunch.herokuapp.com/graphql)  

> ![Successful Test on Deployed URL](../assets/Screen%20Shot%202022-03-28%20at%201.20.45%20AM.png)
> 
- [x] Answer the **4** questions below.
- [x] Submit a Pull Request to cis411_lab4_CD and provide the URL of that Pull Request in Canvas as your URL submission.

## Questions
1. Why would a containerized version of an application be beneficial if you can run the application locally already?
It is useful to have a containerized verzion one because it will simpler to run and it is faster. It will aslo allow members of the project to the application without the process of downloading other programs. 

2. If we have the ability to publish directory to Heroku, why involve a CI solution like CircleCI? What benefit does it provide?
Using a CI solution along with Heroku is beneificial beacuse when publishing to Herokuo, the code should always be tested first and on a regular basis. Therfore, if the code is not deployable, the program will tell us and the errors can be fixed. 

3. Why would you use a container technology over a virtual machine(VM)?
VMs take a lot longer to set up than container technology because it requires less resources. Also, a container provides a portable due to the feature of packaging everything needed to run.

4. What are some alternatives to Docker for containerized deployments?
- OpenVZ
- Podman