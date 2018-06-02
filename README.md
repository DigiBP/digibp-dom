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
- Post Job
- Create Shortlist of applicants
- Send rejection mail
- Upload Shortlist
- Update Shortlist
- Send mail task
- Send appointment confirmation to candidate
- Update candidate list with favorites
- rejection of candidates

## Tools used for process automation

- Camunda BPM modeler and DMN diagrams: To model the process
- Camunda Platform / BPM for executing BPMN workflows and DMN decision tables
- GitHub: For documentation, modelling and project artefacts and sharing the data within the Group
- Heroku: Cloud Platform as a Service (PaaS) provider; For the deployement of the Camunda BPM processes
- Postman: To transfer the data from Postman to Integromat
- Integromat: For process automation > connection & process integration
  - If trigger then action until loop (condition)
- Dialogflow: Chatbot integration


### Get existing job description

The service Task "Get existing job description" has been defined as a srvice task, in order to make it easier for the participants the retrieve data. For that purpose the GoogleSheet has been connected to the process, or rather within the Task. 

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Get%20Existing%20job%20description.png?token=AjCUh2d9IstZXTeX4bfLhBTrk1yojPKCks5bEAgawA%3D%3D)


In this case the data is identified by a business key. The service tasks are connected to two Integromat scenario endpoints create-customer-data and read-customer-data as shown in the following animation:

![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Intehromat-GSheet%20intergration.png?token=AjCUh04auLr47kK3YOvo0HE-45AaMgazks5bEArgwA%3D%3D)


For the integration with integromat and Camunda the Wiki page has been used, which was provided by the lectures:

![Link to Wiki](https://github.com/DigiBP/digibp.github.io/wiki/Getting-Started-Integromat)


### Request for new employee

The Task "Request for Employee" has been automated as follows: The department Manager doesnt need to write Email notification to make the Request for the new Employee. He can use the dialogflow by simply typing in the answer to the following questions:

1. Hi there, what is your prefered position? -> Answer: Position name
2. What is the role of the job? -> Answer: Role
3. Do you have salery expectation? -> Answer: negotianable



The input values/answers to the questions will than be summed up to one information base and sended to the Department Head.



- ake a request for new employee and send it to the department head.
- Aleksa makes the notification and sends it to the deprtment head.

Picture


