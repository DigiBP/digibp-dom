![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/recruitment.jpg?token=AjCUhxHgVTWjl5CuNBnzQtnPd_1e-Ur3ks5bG7ZEwA%3D%3D)


# HR RECRUITMENT PROCESS
# Digitalization of Business Processes - Group Dom


## Introduction
In the following paragraphs the recruitment process for a new position is described, including all the artefacts and integrated services within the process.

### Process Scope
For this project, the scope of the HR recruitment process has been defined to start with the request for a new employee to join the team, and ends when a new employee is successfully hired. Therefore, the onboarding and training of the new employee is not within scope.

### Typical Challenges
HR recruitment processes are often considered inefficient and somewhat messy. In general, the reasons behind this perception are that there are many complex decisions and instances of collaboration that need to occur in order to hire the "right" candidate. This takes a great deal of time and often requires several rounds of interviews for HR and Management to feel confident in their hiring decision. In the following paragraph we have detailed an example of a more efficient and innovative recruitment process through the use of decision automation and intelligent service integration.


## Process Description
### Roles
#### Internal
HR assistant:
The HR assistant plays an integral role in the recruitment processand is responsible for the majority of the tasks, acting as the intermediary between the applicants and Manager and Interview Panel.
- Department Manager:
The Manager initiates the recruitment process by requesting a new headcount for his/her team from the Department Head. The Manager can be seen as the Hiring Manager for the position's recruitment, as they will make the final decision about with candidate will be offered the role.
- Interview Panel:
The Interview Panel is a group of employees (3-5) assembled by the Manager, chosen for their experience in hiring employees, because they will work with the new employee hired, or because the Manager values their judgement. The Interview Panel together with the Manager will evaluate all candidates that make it to the second round of interviews.
- Department Head:
The Department Head is responsible for the department budget, and makes the decision about whether having a new headcount is possible or not.

#### External
- Applicants/Candidates
Applicants are interested in the posted position and apply for the job.

### Process Flow
The recruitment process starts with the request of a department Manager for a new employee. The request goes to the Head of the department. Two possible routes can than be executed: 

- When the Department Head rejects the request, the process ends.
- When he/she approves, the process proceeds. 

When approved: The Department Head sends an approval notification to the Department Manager. When the 
manager gets the approval he/she then starts preparing the job description for the new position. 
Again, two possible routes can than be executed: 

- either the open position is for a role that already exists in the company and has an existing job description, 
- or a new job description needs to be prepared. 

After finishing the job description, the Manager sends the description file to the HR Department. In the HR Department, an assistant finishes up the description file (adding things like the position start date, instructions to apply, etc.) and posts the description on the company website. After the job is posted, the Manager and HR employee involved in this instance of the process wait for two weeks while interested candidates submit their applications.

After the two weeks, unsuitable applications will be sorted out by HR staff and the remaining suitable applications are recorded in a list. This list is then forwarded to the Manager, who again sorts out unsuitable applicants, updates the list, and sends it to HR.

Next, an HR employee conducts telephone interviews with the applicants that appear on the Manager's shortlist, in order to check the details of the candidates and to screen out anyone that the HR employee deems unsuitable. The telephone interviews are evaluated on the basis of a decision-making table. 

After the interviews, candidates are sorted again and a rejection email is sent to all unsuccessful applicants. The list of applicants is updated once more and is sent to the Manager, who also sorts the list to include only candidates that he/she feels are worth interviewing in/person. Again, all applicants that are no longer being considred for the position will receive a rejection email from HR. The Manager then sends the new list back to HR, and based on this new list, personal interviews with the remaining candidates are arranged. To do this, the HR employee first checks the schedule availability of the interview panel members, and proposes certain dates and times to the candidates that will be interviewed. Once the candidates confirm their availibility for the selected dates and times, the HR employee informs interview time confirmations to the candidates and the interview panel.

At the appropriate date and time, each candidate is evaluated by the interview panel through an in-person interview, using a decision table that gives each candidate a score. Candidates are then ranked from highest to lowest score, and the interview panel makes a selection of their favourite candidates. This list is sent to the Manager, who makes the final decision about which candidate he/she would like to hire for the open position.

This decision is communicated to the HR employee, who subsequently informs all unsuccessful candidates that the job has been offered to another candidate, and informs the chosen candidate that they are being offered the position. The HR employee then sends the contract 
to the decided candidate. Once the contract has been signed, the process is completed.

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Bildschirmfoto%202018-05-24%20um%2014.46.10.png?token=AjCUh2nvx1PEy67KM8kxTyxqFaXyMHREks5bG7auwA%3D%3D)

### Decision Automation
#### Interview Evaluation: Telephone Interview
![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/TelephoneEvaluationDMN.png?token=AjCUh_MSHd6V2tEd2MXCfWVVbtRKIHyQks5bG7jNwA%3D%3D)

#### Evaluate Candidate: In-Person Interview
![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/In-personEvaluationDMN.png?token=AjCUh9xXjraeovD7gA7CM_atqyFnK2TFks5bG7kZwA%3D%3D)

### Service Integration
#### Tools Used
- Camunda BPM modeler and DMN diagrams: To model the process
- Camunda Platform / BPM for executing BPMN workflows and DMN decision tables
- GitHub: For documentation, modelling and project artefacts and sharing the data within the Group
- Heroku: Cloud Platform as a Service (PaaS) provider; For the deployement of the Camunda BPM processes

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/updateexcel.PNG?token=AjCUh0mOJWg8CT0kiXZRUEu8VX5SqNWyks5bG71swA%3D%3D)

- Postman: To transfer the data from Postman to Integromat
- Integromat: For process automation  
  - connection & process integration
  - If trigger then action until loop (condition)
- Dialogflow: Chatbot integration

#### APIs
##### Get existing job description (GetJob)
The service task "Get existing job description" has been defined as a service task, in order to make it easier for the participants to retrieve data. For that purpose the GoogleSheet has been connected to the process, or rather within the Task. 

In this case the data is identified by a business key. The service tasks are connected to two Integromat scenario endpoints create-customer-data and read-customer-data as shown in the following animation:

For the integration with integromat and Camunda the Wiki page has been used, which was provided by the lectures.

##### Post job (Post)

##### Create shortlist of applicants (Shortlist)
- Upload Shortlist
- Update Shortlist
- Update candidate list with favorites

To automaticaly create and update the list with all the applicants which have applied for the job, we have decided to use Google Sheet, in order to automaticly update column values. This automation is done with the help of integromat, where we have connected the Google Sheet into the Camunda process.

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/updateexcel-select.PNG?token=AjCUh9N2k4rlLsKpMwgqnWEocnGaGbm8ks5bG75GwA%3D%3D)

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/updateexcel-update.PNG?token=AjCUh_ytaLz4OTE6YaYPyFI3obfq7qvGks5bG76QwA%3D%3D)

##### Send mail task (Send)
The mail task appears multiple times within the process. It is used to communicate between the different parties such as the applicants, to update them on their application (especially when they are no longer being considered for the position), and also to communicate with the Manager, as well as the interview panel.

- For the mail integration Microsoft flow is used

- Inside the microsoft flow one HTTP request along with the send-mail gateway for Gmail and one HTTP response has been configured.

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/email1st.PNG?token=AjCUh1ms-uJRyl9456QzaUKDPpXjq1Tyks5bG7_lwA%3D%3D)

- In HTTP request we have used a json script containing the objects such as Emailadress, Emailsubject and emailbody

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/email2nd.PNG?token=AjCUhz-rg5AEx8j15pmi13HhWsglaBocks5bG8ALwA%3D%3D)

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/email3rd.PNG?token=AjCUh2hh0_lFpSx4lWRm0iUvCt5U3xjYks5bG8AVwA%3D%3D)

#### Digital Assistant/Chatbot
xxx

#### Challenges
- Service integration has been one of the biggest challanges regarding the automation.
  - In particular, integrating the Alexa skill was very difficult. By the end we were able to integrate Alexa into the process, but problems occured when we tried to transfer the data to an external platform.

#### Recommendations
- To improve the process further, we would recommend the integration of an Alexa chatbot, to enable higher process efficiency and make the overall process easier for those involved by increasing the amount of automation.



![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Thank%20You.png?token=AjCUhxJRZf6stOqvFR5FIG0-Gpg_jdmEks5bG8aywA%3D%3D)
