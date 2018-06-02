![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/recruitment.jpg?token=AjCUhxHgVTWjl5CuNBnzQtnPd_1e-Ur3ks5bG7ZEwA%3D%3D)


## Recruitment process - Process Description

In the following ReadMe file the recruitment process is documented with all it`s aspects and included services within 
the process.
The process starts with the request of a department manager for a new employee. The reqeust goes to the department 
head. When the Department head rejects the request the process ends, when he/she approves, the process proceeds. 

When approved: The department head sends an approval notification to the department manager. When the 
manager gets the approval he/ she than starts preparing the job description for the new position. 
Two possible roots can than be executed: 

- either the open position already refers to an existing job description, 
- or new job description needs to be prepared. 

After finishing up the job description the manager sends the description file to the HR 
Department. In the HR Department an Employee finishes up the description file and posts the description on company 
website. After the posting the waits for two weeks in order to gather applications.After the two weeks, inappropriate 
applications will be sorted out by HR staff and recorded in a list. The list is then forwarded to the manager, who 
again performs a sorting, updates the list and sends it to HR. In the HR, telephone interviews with the selected 
candidates are agreed on the basis of the list in order to check the details of the candidates and to screen out 
unsuitable candidates. 

The telephone interviews are evaluated on the basis of a decision-making table. After the 
interviews, candidates are sorted out again and the list of applicants re-updated. The new list is again sent to the 
manager, who again performs a sorting and sends the new list back to HR. Based on the new list, personal interviews 
with the candidates will now be arranged. Subsequently, the interview panel will be informed about the times to conduct 
the interviews.The evaluation of the personal interviews takes place via the interview panel.
Candidates are also evaluated using a decision table. then a candidate for the open position is decided.
The decision is communicated to the HR, which subsequently informs all candidates accordingly and sends the contract 
to the decided candidate. After the conclusion of the contract, the process is completed.

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Bildschirmfoto%202018-05-24%20um%2014.46.10.png?token=AjCUh2nvx1PEy67KM8kxTyxqFaXyMHREks5bG7auwA%3D%3D)

## Roles within the Process

- HR Department
- Department Manager
- Interview Panel
- Department Head

- Applicant/s


## Decision Tables

- Interview Evaluation: Telephone Interview
- Evaluate Candidate: In-Person Interview

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Evaluate%20Candidate%20DMN.png?token=AjCUh_MSHd6V2tEd2MXCfWVVbtRKIHyQks5bG7jNwA%3D%3D)

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Evaluate%20Candidate_BPM.png?token=AjCUh9xXjraeovD7gA7CM_atqyFnK2TFks5bG7kZwA%3D%3D)


## Service integration Tasks

- [Request for new employee](Request)
- [Get existing job description](GetJob)
- [Post Job](post)
- [Create Shortlist of applicants](Shortlist)
  - Upload Shortlist
  - Update Shortlist
  - Update candidate list with favorites
- Send mail Task
  - rejection of candidates


## Tools used for process automation

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


### Get existing job description

The service Task "Get existing job description" has been defined as a srvice task, in order to make it easier for the participants the retrieve data. For that purpose the GoogleSheet has been connected to the process, or rather within the Task. 

In this case the data is identified by a business key. The service tasks are connected to two Integromat scenario endpoints create-customer-data and read-customer-data as shown in the following animation:

For the integration with integromat and Camunda the Wiki page has been used, which was provided by the lectures.


### Request for new employee

The Task "Request for Employee" has been automated as follows: The department Manager doesnt need to write Email notification to make the Request for the new Employee. He can use the dialogflow by simply typing in the answer to the following questions:

1. Hi there, what is your prefered position? -> Answer: Position name
2. What is the role of the job? -> Answer: Role
3. Do you have salery expectation? -> Answer: negotianable

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/dialogflowOne.PNG?token=AjCUh2xTw6qZ3RrwyTKBPy3_XkVJAfb0ks5bG7oIwA%3D%3D)

- The input values/answers to the questions will than be summed up to one information base and sended to the Department Head.

### Create Shortlist of applicants

To automaticaly create and update the list with all the applicants which have applied for the job, we have decided to use Google Sheet, in order to automaticly update column values. This automation is done with the help of integromat, where we have connected the Google Sheet into the Camunda process.

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/updateexcel-select.PNG?token=AjCUh9N2k4rlLsKpMwgqnWEocnGaGbm8ks5bG75GwA%3D%3D)

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/updateexcel-update.PNG?token=AjCUh_ytaLz4OTE6YaYPyFI3obfq7qvGks5bG76QwA%3D%3D)


### Send mail Task

The mail task appears multiple times within the process. It is used to speacially communicate between the different parties: such as the applicants, to update them on their application and also to communicate with the manager, as well as the interview panel.

- For the mail integration Microsoft flow is used

- Inside the microsoft flow one HTTP request along with the send-mail gateway for Gmail and one HTTP response has been configured.

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/email1st.PNG?token=AjCUh1ms-uJRyl9456QzaUKDPpXjq1Tyks5bG7_lwA%3D%3D)

- In HTTP request we have used a json script containing the objects such as Emailadress, Emailsubject and emailbody

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/email2nd.PNG?token=AjCUhz-rg5AEx8j15pmi13HhWsglaBocks5bG8ALwA%3D%3D)

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/email3rd.PNG?token=AjCUh2hh0_lFpSx4lWRm0iUvCt5U3xjYks5bG8AVwA%3D%3D)

### Overall Challanges and future recommendation 

#### Challanges

- Service integration has been one of the biggest challanges regarding the automation
  - Specially integrating the Aleksa skill was very difficult. By the end we could integrate Aleksa into the process, but problems accured when we tryed to transfer the data to external platform.
 
#### Future recommendation

- For the further improvement of the process we would recommand to have a propour implemented of Alexa chatbot integration, to enable higher process efficiency and make the overall process more easy by higher automation rate.

