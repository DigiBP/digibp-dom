![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/recruitment.jpg?token=AjCUhxHgVTWjl5CuNBnzQtnPd_1e-Ur3ks5bG7ZEwA%3D%3D)


# HR RECRUITMENT PROCESS
# Digitalization of Business Processes - Group Dom
## M. Adnan, T. Brändlin, C. Frank, L. Pfirter




## Introduction
In the following paragraphs the recruitment process for a new position is described, including all the artefacts and integrated services within the process.

### Process Scope
For this project, the scope of the HR recruitment process has been defined to start with the request for a new employee to join the team, and ends when a new employee is successfully hired. The onboarding and training of the new employee is for this example not within scope.

### Typical Challenges
HR recruitment processes are often considered inefficient and somewhat messy. In general, the reasons behind this perception are that there are many complex decisions and instances of collaboration that need to occur in order to hire the "right" candidate. This takes a great deal of time and often requires several rounds of interviews for HR and Management to feel confident in their hiring decision. In the following paragraphs, we have detailed an example of a more efficient and innovative recruitment process through the use of decision automation and intelligent service integration.


## Process Description
### Roles
#### Internal
HR assistant:
The HR assistant plays an integral role in the recruitment process and is responsible for the majority of the tasks, acting as the intermediary between the applicants and Manager and Interview Panel.
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
The recruitment process starts with the request of a department Manager for a new employee. The request goes to the Head of the department. Two possible routes can then be executed: 

- When the Department Head rejects the request, the process ends.
- When he/she approves, the process proceeds. 

When approved: The Department Head sends an approval notification to the Department Manager. When the 
manager gets the approval he/she then starts preparing the job description for the new position. 
Again, two possible routes can then be executed: 

- The open position is a new role in the company and a new job description needs to be prepared, or
- The open position is for a role that already exists in the company and has an existing job description. 

If it is the latter, the Manager will retrieve an existing job description by searching the job title. The Manager can use this file as is, but will most likely add or change some of the information to better fit the job that the new employee will perform. After finishing the job description, the Manager sends the description file to the HR Department. In the HR Department, an assistant can edit the file (adding things like the position start date, instructions to apply, etc.) before posting the job to the company's Facebook page. After the job is posted, the Manager and HR employee involved in this instance of the process wait for two weeks while interested candidates submit their applications via Facebook. By clicking on the job post on the company's page, potential applicants are shown a chatbot interface, which asks them a few questions. Their answers include the necessary data to create an applicant profile, that the HR assistant will later evaluate.

After the two weeks, applications will be reviewed by the HR assistant and unsuitable applications will be sorted out. The remaining suitable applications are recorded in a list, which is then forwarded to the Manager, who again sorts out unsuitable applicants, updates the list, and sends it back to HR.

Next, an HR employee conducts telephone interviews with the applicants that appear on the Manager's shortlist, in order to check the details of the candidates and to screen out anyone that the HR employee deems unsuitable. The telephone interviews are evaluated on the basis of a decision-making table, and any candidates that fail to meet all three criteria will be rejected. 

After the interviews, candidates are sorted and a rejection email is sent to all unsuccessful applicants. The list of applicants is updated once more and is sent to the Manager, who also sorts the list to include only candidates that he/she feels are worth interviewing in/person. Again, all applicants that are no longer being considered for the position will receive a rejection email from HR. The Manager then sends the new list back to HR, and based on this new list, personal interviews with the remaining candidates are arranged. To do this, the HR employee first checks the schedule availability of the interview panel members, and proposes certain dates and times to the candidates that will be interviewed. Once the candidates confirm their availability for the selected dates and times, the HR employee informs interview time confirmations to the candidates and the interview panel.

At the appropriate date and time, each candidate is evaluated by the interview panel through an in-person interview, using a decision table. Candidates that do not meet the decision table criteria are rejected, and from the remaining successful candidates the interview panel makes a selection of their favourite candidates. This list is sent to the Manager, who makes the final decision about which candidate he/she would like to hire for the open position.

This decision is communicated to the HR employee, who subsequently informs all unsuccessful candidates that the job has been offered to another candidate, and informs the chosen candidate that they are being offered the position. The HR employee then discusses the contract with the new employee. Once the contract has been signed, the process is completed.

### Decision Automation
#### Interview Evaluation: Telephone Interview
Only candidates that can provide references, are available to start on the position start date, and appear interested in the position will move forward in the process after the telephone interview.

![telephoneevaluationdmn](https://user-images.githubusercontent.com/36928393/41066204-6683633c-69e1-11e8-9493-7a86f32555d6.png)

#### Evaluate Candidate: In-Person Interview
In order stay in the running and be considered for the position after the in-person interview, a candidate has to meet educational requirements, be a good or excellent fit for the team (according to the Interview Panel members), and not having any outstanding reasons why they should not be hired (according to the Interview Panel members, once again).

![in-personevaluationdmn](https://user-images.githubusercontent.com/36928393/41066274-a5bb4a92-69e1-11e8-9bd4-ecfcdd64fb17.png)

### Service Integration
#### Tools Used
- Camunda BPM modeler and DMN diagrams: To model the process
- Camunda Platform / BPM for executing BPMN workflows and DMN decision tables
- GitHub: For documentation, modelling and project artefacts and sharing the data within the Group
- Heroku: Cloud Platform as a Service (PaaS) provider; For the deployement of the Camunda BPM processes
- Postman: To transfer the data from Postman to Integromat
- Integromat: For process automation  
  - connection & process integration
  - If trigger then action until loop (condition)
![overviewscenarios_integromat](https://user-images.githubusercontent.com/36928393/41068600-86500400-69ea-11e8-87b8-7c88e7fa6d4b.PNG)

- Dialogflow: Chatbot integration

#### APIs
#### - Get existing job description (GetJob)
The task "Get existing job description" has been defined as a service task, in order to make it easier for the Manager to find out if there is already a job description existing for the open position that they will hire for. This reduces rework every time a new employee is hired, as the Manager just has to adapt an existing job description (already specific to the job title) to that specific position and department. For this purpose, the GoogleSheet has been connected within the Task. 

In this case the data is identified by a business key, which is the Job Title e.g. HR Director. The service task is connected to the Integromat scenario “getJob” to first provide the business key “HR Director” to the Google Sheet and retrieve all information from this position in the defined forms as shown in the following animation:

For the integration with integromat and Camunda the Wiki page has been used, which was provided by the lectures.

###### Get job overview
![getjob_overview](https://user-images.githubusercontent.com/36928393/41066376-ea908eac-69e1-11e8-8c23-596c570c010e.PNG)

###### Job data sheet
![jobdatasheet](https://user-images.githubusercontent.com/36928393/41066593-a0e67ec8-69e2-11e8-8e35-3e8627ccf113.PNG)

###### Get job - Select rows
![getjob_selectrows_1ststep](https://user-images.githubusercontent.com/36928393/41066390-f2127bcc-69e1-11e8-80f0-040311668600.PNG)

###### Get job - Update rows
![getjob_updaterows_2ndstep](https://user-images.githubusercontent.com/36928393/41066399-f9ebc448-69e1-11e8-8184-83b29fc0f199.PNG)

###### Get job - Response
![getjob_response_3rdstep](https://user-images.githubusercontent.com/36928393/41066408-ff5acf28-69e1-11e8-9556-6e8f017abcb5.PNG)

#### - Post job (Post)
In this service integration step, the HR assistant posts the job description to Facebook. The information for the post is provided by the given forms which have been filled with the service task “get job description”. The post is done into a page on Facebook and not in a company profile which would have been the correct way in order to get applicants, but Facebook does not allow to create fake-accounts. Therefore, the Facebook page “Digibp HR recruitment” is used. 

![facebook1](https://user-images.githubusercontent.com/36928393/41085490-77ed5e74-6a37-11e8-9c74-9c84b7550663.PNG)

The following figures show the Integromat services which result into the Facebook post.

###### Post to Facebook overview
![posttofb_overview](https://user-images.githubusercontent.com/36928393/41066352-d87632c6-69e1-11e8-89de-01a2a9743585.PNG)

###### Post to Facebook - Post
![posttofb_post](https://user-images.githubusercontent.com/36928393/41066443-1bb2da4e-69e2-11e8-88ec-6b7caea11c70.PNG)

###### Post to Facebook - Visible to users
![facebook2](https://user-images.githubusercontent.com/36928393/41066466-2dd08e10-69e2-11e8-8a53-0e7f91169f32.PNG)

#### - Retrieve applications (Get)
After the two week waiting period has expired, the HR assistant will retrieve all applications that were collected through the Dialogflow chatbot (see "Digital Assistant/Chatbot" section for more detail). In the process two weeks are defined as five seconds in order to not wait two weeks until the process continues. This service is triggered by the candidate ID which is defined within the application service with the chatbot. The applicant information from the Google Sheet is retrieved with this candidate ID. The service is the same as already described for getting the job description. 

![retrieveapplications_overview](https://user-images.githubusercontent.com/36928393/41066490-45ae2862-69e2-11e8-91d4-8faea66c7de4.PNG)

![retrieveapplications_select_1ststep](https://user-images.githubusercontent.com/36928393/41066495-4993eade-69e2-11e8-923f-f49b01029f5d.PNG)

![retrieveapplications_update_2ndstep](https://user-images.githubusercontent.com/36928393/41066506-4e5692ce-69e2-11e8-8f99-f07793e6f727.PNG)

#### - Create shortlist of applicants (Shortlist)
Creating and updating the candidate shortlist after each round of candidate evaluations is a critical piece of service integration for this process, as it effectively creates a sort of workflow management system between the HR assistant and the Manager to know what the status of a particular instantiation of the recruitment process is at all times. To automatically create and update the list with all the applicants which have applied for the job, we have decided to use Google Sheet, in order to automatically update column values. The first input is given from the applicants themselves with providing their information through the chatbot as described in that section. The automated updates of the Google Sheet are achieved several times throughout the process with the help of Integromat, where we have connected the Google Sheet into the Camunda process.

###### Create candidate shortlist
![createcandidatelist](https://user-images.githubusercontent.com/36928393/41066541-6d031026-69e2-11e8-9bb3-bbc32a432bdd.PNG)

###### Update shortlist
![update_overview](https://user-images.githubusercontent.com/36928393/41068591-788328f2-69ea-11e8-87b6-40fe4bcc126e.PNG)

#### - Send mail task (Send)
The mail task appears multiple times within the process. It is used to communicate between the HR of the company and the applicants, to The mail task appears multiple times within the process. It is used to communicate between the HR of the company and the applicants, to update them on their application (especially when they are no longer being considered for the position, and receive a rejection email), and also to provide them their interview appointment.

For the mail integration Microsoft flow is used. Inside the Microsoft flow one HTTP request along with the send-mail gateway for Gmail and one HTTP response has been configured. In the HTTP request, we have used a json script containing the objects such as Emailadress, Emailsubject and Emailbody. As the recipient of the email and the content varies in the process, variables have been used so that the HR can enter the information flexible. 

![overviewmailservices](https://user-images.githubusercontent.com/36928393/41068603-89e62a54-69ea-11e8-874f-1c84973fec86.PNG)

-For the mail integration Microsoft flow is used

-Inside the microsoft flow one HTTP request along with the send-mail gateway for Gmail and one HTTP response has been configured.

![maildetail](https://user-images.githubusercontent.com/36928393/41068609-92053c3e-69ea-11e8-9775-ba932e28eacb.PNG)

- In HTTP request we have used a json script containing the objects such as Emailadress, Emailsubject and emailbody

![email2nd](https://user-images.githubusercontent.com/36928393/41068614-9798a9f6-69ea-11e8-9a82-99be83b0a4b8.PNG)

![email3rd](https://user-images.githubusercontent.com/36928393/41068619-9d2ce51c-69ea-11e8-960c-20c8ce6f12ba.PNG)

#### Digital Assistant/Chatbot
The chatbot is used to offer the applicants a more personalized function like a chatbot where they can apply for the job. The link between the chatbot and the job is given by the Facebook post where the link is posted with every job description. By clicking the link, the chatbot opens and the communication can be started as soon as the applicants enters a trigger with an invocation text E.g. “hi”. The chatbot is then asking for the required information which are then automatically inserted into the Google Sheet for the candidate information. The concept used to realize this scenario is an inline intent while capturing values at the end of conversation. These values are then transferred to the webhooks and stored in the Google Spreadsheet.

Example Scenario:
The chatbot configuration is done with Dialogflow There, sentences are defined which are asked to the user, and the user answers to the questions, which are then fetched by the bot. the answers are scanned and compared to required values in order to make sure that the applicant is not given false information such as a date in a name field. To ease this, in our example we defined fix values which should be entered by the applicant to make sure that the process continues. In real life of course, the applicant can enter any values in the chat. 

![dialoghook](https://user-images.githubusercontent.com/36928393/41068660-d0b17538-69ea-11e8-8648-ac16d6dfc4fb.PNG)

![dialogscreen](https://user-images.githubusercontent.com/36928393/41068662-d37a6860-69ea-11e8-8bf4-ec8a1240d65c.PNG)

#### Project Challenges
Our main challenges in this project were to first get the process to an executable state, and of course, integrate services. Many ideas that we had at the beginning of the project did not materialize as they were too complex for our skill level. One particular challenge that we struggled with was making certain tasks or subproccesses able to instantiate multiple times, therefore allowing several applicants to be considered and move through the recruitment processes at the same time for the same role. Unfortunately, we were not successful in this, but have labelled the tasks that should be executed multiple times (to allow for multiple applicants to be considered) in blue.

![bluetasks](https://user-images.githubusercontent.com/36928393/41069223-3b9d1896-69ed-11e8-9519-3ccd71a8962c.png)

Another area of the service integration that we found particularly difficult was integrating the Alexa skill was very difficult. By the end we were able to integrate a Dialogflow chatbot into the process, but problems occurred when we tried to transfer the data to an external platform.

#### Recommendations
To improve the process further, we would of course recommend adapting the process to accommodate tasks that can have multiple instantiations, but also the integration of an Alexa chatbot that would (what would it do exactly, how would it improve efficiency), to enable higher process efficiency and make the overall process easier for those involved by increasing the amount of automation.

To ensure that candidates are also evaluated in a uniform and consistent manner, we would also recommend using Google Forms as an evaluation form that the Interview Panel members would file out during each candidates' interview, or shortly afterwards. This would ensure two things:
-Uniform, non-biased evaluation of candidates by grading each applicant against the same evaluation criteria
-Less rework, as these evaluation documents could be shared throughout the organization (like the job descriptions)
-Automated data collection from Interview Panel, which Manager could later analyze to make their final decision (instead of paper based notes and verbal conversation).




![](https://raw.githubusercontent.com/DigiBP/digibp-dom/master/Report%20Pics/Thank%20You.png?token=AjCUhxJRZf6stOqvFR5FIG0-Gpg_jdmEks5bG8aywA%3D%3D)
