# CareFirst-Doctor-Client-Web-Portal

CareFirst
(Online Checkup and Health Report Monitoring App)


SPS Team #84:
Aastha Anant Kumar
Adhya Nagpal
Yashika Aggarwal
Monu Agarwal (Project Advisor)

Project Links:
Deployed Website : https://summer20-sps-84.el.r.appspot.com/
Github Repo Link: https://github.com/EverCurious5/CareFirst-Doctor-Client-Web-Portal
Video Demo Link: https://drive.google.com/file/d/1bjixAsvCAm0hvd5_YgdpSOKuimn3KwiT/view

Objective:
To build a health monitoring web app which allows users to keep a systematic record of their routine health check-up reports and enables them to connect with medical practitioners, virtually, through video calling to get their test reports reviewed or consult them for certain health issues for which physical examination may not be necessary. The application maintains a repository of all the test reports uploaded by the user, for ready reference, both for the doctors attending them and the users themselves. It also lets users keep a track of their upcoming tests through integration with their Google Calendar. Appointments with doctors are set up as per the relevant doctor’s availability and the user’s preferences. Corresponding events are created in both their calendars and meeting invites sent to them via email at the time of the appointment.

Background:
Users have all past reports systematically compiled at one place for ready reference.
Users can connect with doctors virtually without having to visit medical centres or hospitals for consultations regarding issues that do not require clinical examination.
Users can maintain a systematic record of their routine tests through integration with Google calendars.


Non-Functional Requirements:
Information Security: Users’ personal information and data should be stored securely. To ensure user’s privacy, only the doctor looking into his request/ or with whom they have booked an appointment, should be able to view their medical history and records. Meeting invite links should be sent to both the participants (patient and doctor) securely via email.
Scalability: The application should be able to handle multiple user requests at any given time.
Fast Look-up: The application should provide for quick and easy access to the user's medical records to both the user himself and the concerned doctors.

Tech Stack:
Node.js as a JavaScript Runtime Environment- Lets us write server side code in JavaScript.
Express JS for creating http servers.
Database : Datastore(NoSQL)

Detailed Design :
Server:
Entry Route:
Get request at “/login/doctor”: Redirect to Doctors’ Login Page.
Get request at “/login/gen”: Redirect to General users’ Login Page.
Get request at “/sign-up/doctor”: Redirect to Doctor’s sign-up page.
Get request at “/sign-up/gen”: Redirect to General users’ sign-up page.
Post request at “/sign-up/doctor”: Create a new entry corresponding to the new user. Insert query to database. Redirect to doctors’ Login Page.
Post request at “/sign-up/gen”:  Create a new entry, insert query to database, redirect to general users’ login page.
Post request at “/login/doctor” or at “/login/gen”:
Authenticate request
Redirect back to login page in case of invalid requests
Redirect to user’s dashboard in case of valid request
Exit Route:
Get request at “/logout”: Terminate the login session by calling the logout() function on the request object.
Manage reports Route:
Get request at “/add-reports”: Redirect to uploads page wherein the user can enter the test results in a form or upload the test reports in pdf format.
Post request at “/add-report”: Insert query to database, redirect to user’s dashboard.
Get request at “/view-previous-reports”: Find Query to database, searching for all previous records of the user (test reports and results/ virtual consultations with doctors), return the list in json format.
Connect to doctor Route:
Get request at “/connect-to-doctor”: Redirect to connect with doctors page wherein the user would be required to fill a form regarding the type of specialist that they need to connect with, following which, the list of doctors available in that specialization is displayed, along with the timings of their availability, in the form of a dropdown and the user can choose among them if they have a preference. If the user presses “Next” without specifying a preference for any particular doctor, he’s asked about his timing preferences among the options provided by the doctors regarding their available time slots, and any doctor available in that time slot would be assigned the request.
Post request at “/connect-to-doctor”: Insert query to database to add the patient to the list of “Your Appointments” for the relevant doctor.
Manage routine check-up routes:
Get request at “/manage-routine-checkup-schedule”: Redirect to user’s Google calendar so as to enable them to create events regarding upcoming routine tests.
Attend to users:
Get request at “/attend-to-patient/patient_id”: Redirect to “/view-previous/reports” for that particular user and create and send Google meet invite links to both the doctor and the associated patient via Gmail (maybe using the Google meet API and Gmail API).

Website layout:

(Patient/Client side)
Sign up/Login page - Simple, centered form or options to signup with google+/gmail
Email id 
DashBoard
Header - Navigation bar
Profile
Reports
Connect to doctor
Log out
Display greetings
Profile
Personal information
Name
email_id
Contact details
Address
DOB
Blood group
Height 
Weight
Any mental/physical disability
Latest report
Edit profile button
Save profile button

Reports
Display latest report
Add new report - fill form or upload pdf
History
Connect to doctor
Filters
Specialisation of doctor
List of available doctors (on selecting one)
Fill form
Patient id
Health issue
suitable time for checkup
Send connection request

(Doctor side)

Sign up/Login page - Simple, centered form or options to signup with google+/gmail
Email id
DashBoard
Header - Navigation bar
Profile
Calendar
Attend to patients
Log out
Display greetings
Profile
Personal information
Name
Doc_id
Specialisation
Contact details
Hospital address
Hospital timings
Consultation fee
Qualification degree
Hospital facilities
Achievements
Edit profile
Save
Calendar
Google calendar
Attend to patients
Display list of pending requests
Accept request
View patient report
Schedule checkup meet
Send notification




Database Design :

Doctor
Primary Key : AutoID
Fields: Name, Mobile, E-Mail, Address, Qualification, Specialization, Consulting time, Consultation fees, Hospital address

Patient
Primary Key: AutoID
Fields: Name, Mobile, E-Mail, Address, DOB, Height, Weight, Blood group

Appointment
Primary Key: AutoID
Fields: Doctor Name, Doctor Mob, Patient Name, Patient Time, Appointment Time


Future Prospects:

Can integrate a payments system to facilitate payment of consultation fee to the doctors.
Can incorporate an option for users to describe their issue and requirement briefly while making an appointment, thus enabling doctors to float the appointment request in case they feel that they aren’t the right person to look into the issue.
Allow doctors to deny requests with appropriate messages and give reference about some other doctor who might be more suited to attend to the patient.
Incorporate an option for users to maintain a Daily update column comprising of:
Heartbeat rate
Body temperature
Blood Pressure



