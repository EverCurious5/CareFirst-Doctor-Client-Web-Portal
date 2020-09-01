
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
Database : Datastore.
