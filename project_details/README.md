# SIH Patient Case-Taking Software

## Problem Statement

**Problem Statement:** Patient Case-Taking Software  
**Organization:** Ministry of Ayush  
**Department:** All India Institute of Ayurveda  
**Category:** Software  
**Theme:** MedTech / BioTech / HealthTech  
**Problem Statement ID:** 26047  

---

# Project Overview

The Patient Case-Taking Software is an AI-assisted healthcare platform designed to collect, organize, and document patient medical information before consultation with a doctor.

The system allows patients to register, interact with an AI-powered voice assistant, describe their health problems naturally, upload previous medical reports, generate a structured patient case report, manage previous reports, receive notifications, access hospital services, and communicate with hospital facilities.

The system is designed to reduce the time doctors spend collecting basic patient history while ensuring that the physician remains responsible for the final diagnosis and treatment.

The AI does **not provide an autonomous final diagnosis**.

Instead, the system:

- Collects patient information.
- Conducts an AI-assisted case-taking conversation.
- Dynamically asks relevant medical questions.
- Extracts information from previous medical documents.
- Structures patient history.
- Generates a physician-ready report.
- Allows the patient to review and correct the report.
- Provides hospital-related services.
- Maintains secure hospital administration.

---

# Complete Project Development Phases

The project is divided into the following major development phases.

1. Phase 1 – Patient Registration
2. Phase 2 – AI Consultation
3. Phase 3 – My Report History
4. Phase 4 – Notification Center
5. Phase 5 – My Profile & Settings
6. Phase 6 – Multi-Language Support
7. Phase 7 – Help & Support
8. Phase 8 – Hospital Services
9. Phase 9 – Hospital Admin Portal

---

# Phase 1 – Patient Registration Module

## Objective

The Patient Registration module is responsible for collecting the basic personal and health-related information of the patient before they start using the healthcare system.

The registration process must remain simple and user-friendly so that patients of different age groups can easily complete it.

---

## Features

The Patient Registration form contains the following fields:

### 1. Full Name

The patient enters their complete name.

**Type:** Text Field  
**Required:** Yes

---

### 2. Date of Birth

The patient selects their date of birth.

The system can use this information to determine the patient's age.

**Type:** Date Picker  
**Required:** Yes

---

### 3. Gender

The patient selects their gender.

**Type:** Selection Field  
**Required:** Yes

---

### 4. Mobile Number

The patient's mobile number is collected for account communication, notifications, appointments, and hospital-related services.

**Type:** Phone Number Field  
**Required:** Yes

---

### 5. Email Address

The patient's email address is used for account communication and digital report-related activities.

**Type:** Email Field  
**Required:** Yes

---

### 6. Address

The patient's residential address is stored as part of their basic profile.

**Type:** Text Area  
**Required:** Yes

---

### 7. Blood Group

The patient can provide their blood group if they know it.

Because some patients may not know their blood group, this field remains optional.

**Type:** Dropdown  
**Required:** No

---

### 8. Height

The patient enters their height.

**Required:** Yes

---

### 9. Weight

The patient enters their weight.

**Required:** Yes

---

### 10. Existing Diseases

The patient can select existing diseases from predefined checkbox options.

Examples may include:

- Diabetes
- Hypertension
- Asthma
- Thyroid-related conditions
- Heart-related conditions
- Other known diseases

Detailed information about these diseases can later be collected through the AI Consultation module.

---

## Registration Workflow

```text
User Opens Platform
        ↓
Patient Registration Page
        ↓
Enter Personal Information
        ↓
Enter Basic Health Information
        ↓
Validate Required Fields
        ↓
Submit Registration Form
        ↓
Create Patient Profile
        ↓
Open Patient Dashboard


Important Design Rule

The registration module should collect only basic patient information.

Detailed symptoms, medical history, medicines, previous treatments, and current health problems are collected through the AI Consultation module.

Profile photo upload is not part of patient registration.

The patient can upload or change their profile picture later through:

My Profile & Settings → Edit Profile

Phase 2 – AI Consultation Module
Objective

AI Consultation is the core module of the Patient Case-Taking Software.

Its primary purpose is to communicate with the patient naturally, understand the patient's health problem, collect relevant case history, digitize previous reports, and create a structured physician-ready patient case report.

The AI Consultation module contains three major sub-modules:

Voice Assistant
AI Patient Report
AI Consultation Guide
Phase 2.1 – AI Voice Assistant
Objective

The Voice Assistant allows patients to explain their medical problem naturally using voice interaction.

Instead of filling out long medical forms, patients can speak directly with the AI assistant.

Consultation Start

When the patient opens AI Consultation:

Patient Dashboard
        ↓
AI Consultation
        ↓
Welcome Message
        ↓
Language Confirmation
        ↓
Start Voice Conversation
Welcome Interaction

The AI assistant first welcomes the patient.

Example:

Welcome to the AI Patient Consultation.
I will help collect information about your current health problem.
Language Confirmation

Before starting the consultation, the system confirms the patient's preferred language.

Currently supported languages:

English
Hindi
Chief Complaint Question

The AI begins the medical conversation using an open question.

Example:

What problem are you facing today?

The AI should not initially suggest specific illnesses.

The patient should describe their problem naturally.

For example:

I have had fever and cough for the last three days.
Dynamic Follow-Up Questions

The AI analyzes the patient's answers and asks relevant follow-up questions.

The conversation is not based on one fixed questionnaire.

Questions are dynamically generated according to the patient's symptoms.

The AI may collect information such as:

Main health problem
Duration of symptoms
Symptom progression
Severity
Associated symptoms
Previous similar episodes
Medicines already taken
Response to medicines
Relevant medical history
Existing illnesses
Other clinically relevant information
Example Conversation Flow
AI:
What problem are you facing today?

Patient:
I have had fever and cough for three days.

AI:
When did the fever first start?

Patient:
Around three days ago.

AI:
Is the fever continuous or does it come and go?

Patient:
It comes and goes.

AI:
Are you experiencing any difficulty breathing?

Patient:
No.

AI:
Have you taken any medicine?

Patient:
Yes, I took paracetamol.

AI:
Did the fever improve after taking it?

Patient:
It improved temporarily.

The exact questions depend on the patient's response.

Previous Medical Report Upload

During the consultation, the patient can optionally select:

Upload Previous Report

Supported medical document types may include:

Previous prescriptions
Laboratory reports
Discharge summaries
Previous consultation reports
Diagnostic reports
Medical Document Processing

The system should process uploaded reports using OCR and medical information extraction.

The OCR system should aim to support:

Printed documents
Handwritten documents
Multilingual medical documents
Information Extraction

The system may extract structured information such as:

Medicine names
Medicine dosage information
Diagnosis mentions
Laboratory values
Test results
Previous procedures
Surgery history
Previous treatment details
Relevant clinical information

Extracted information is passed to the AI Patient Report generation process.

End of AI Voice Consultation

When the patient has finished answering the AI questions, they select:

Submit Consultation

After submission:

Voice Conversation Ends
        ↓
Collected Information is Structured
        ↓
Previous Reports are Processed
        ↓
AI Generates Patient Case Documentation
        ↓
Open AI Patient Report
Phase 2.2 – AI Patient Report
Objective

The AI Patient Report converts the collected consultation data into structured documentation that can be presented to a physician.

Report Content

The generated report may contain:

Patient Details
Name
Age
Gender
Height
Weight
Basic patient information
Chief Complaint

The main health problem described by the patient.

History of Present Problem

Structured information about:

Symptom duration
Severity
Progression
Associated symptoms
Relevant details collected during AI consultation
Existing Medical Conditions

Previously known diseases or medical conditions.

Medication Information

Medicines already taken by the patient and their response.

Previous Medical Information

Relevant information extracted from uploaded documents.

AI Structured Summary

A concise physician-ready summary of the collected patient case.

Review and Edit

Before generating the final report, the patient receives two options:

Review
Edit

The patient can verify the information captured during the AI consultation.

If any information is incorrect, the patient can edit it before confirmation.

Final Confirmation

After reviewing the information, the patient selects:

Confirm

The system then generates the final patient case report.

Final Report Output

The final report can be generated in a printable digital format such as PDF.

The patient can:

View the report
Download the report
Print the report
Present the report to the doctor
Clinical Safety Rule

The AI Patient Report is a structured patient history document.

It is not a final medical diagnosis.

The doctor remains responsible for:

Clinical examination
Diagnosis
Treatment
Prescriptions
Medical decisions
Phase 2.3 – AI Consultation Guide
Objective

The AI Consultation Guide helps patients provide better and more accurate information during the voice consultation.

Patient Guidance

Patients should follow these instructions:

Speak slowly and clearly.
Describe your problem in your own words.
Provide truthful and complete symptom information.
Mention when your problem started.
Mention medicines you have already taken.
Upload your previous medical report if available.
Review the generated report before confirming.
Use Hindi or English according to your selected preference.
Phase 3 – My Report History Module
Objective

The My Report History module stores previous AI-generated patient case reports.

Patients can access their past consultation documentation whenever required.

Features

The patient can:

View previous reports
Review previous reports
Download reports
Print reports
Share reports with doctors or hospitals
Search previous reports
Filter previous reports
Report Search

Patients can search reports using information such as:

Report name
Report type
Consultation information
Report Filters

Reports can be filtered by:

Date
Report type
Report History Workflow
Patient Dashboard
        ↓
My Report History
        ↓
List of Previous Reports
        ↓
Search / Filter
        ↓
Select Report
        ↓
View Report
        ↓
Download / Print / Share
Record Protection

Patients should not have permission to permanently delete formal medical reports.

Administrative record management should be handled by authorized hospital administrators according to hospital policies.

Phase 4 – Notification Center Module
Objective

The Notification Center provides important healthcare-related updates to the patient.

Notification Categories

The module contains four major notification types.

1. Appointment Notifications

Patients receive notifications related to:

Appointment confirmation
Upcoming appointments
Appointment timing
Appointment changes
Appointment cancellation
Rescheduling updates
2. Medicine Reminders

The system can remind patients about medicine schedules.

A reminder may include:

Medicine name
Medicine timing
Dosage information if available
Reminder time
3. Report Notifications

Patients receive notifications when:

AI patient report is ready
Laboratory report becomes available
New medical report is added
4. Hospital Notifications

Hospitals can send important announcements such as:

Hospital updates
Department announcements
Service availability
Important healthcare notices
Notification Workflow
System / Hospital Event
        ↓
Generate Notification
        ↓
Notification Center
        ↓
Patient Opens Notification
        ↓
Relevant Action / Information
Phase 5 – My Profile & Settings Module
Objective

The My Profile & Settings module allows patients to manage their personal information, profile preferences, privacy settings, and application settings.

Sub-Modules
1. Profile Information

Displays basic patient information such as:

Name
Date of birth
Gender
Mobile number
Email
Address
Blood group
Height
Weight
2. Edit Profile

Patients can update permitted personal information.

3. Profile Photo

Patients can:

Upload profile photo
Change profile photo
Remove profile photo

Profile photo management happens here instead of during patient registration.

4. Account Settings

Patients can manage general account-related settings.

5. Privacy & Permissions

Patients can manage relevant permissions and privacy preferences.

Healthcare information should only be accessible according to authorized roles and patient consent.

6. Notification Preferences

Patients can control the types of notifications they want to receive.

For example:

Appointment alerts
Medicine reminders
Report notifications
Hospital notifications
Phase 6 – Multi-Language Support Module
Objective

The Multi-Language Support module improves accessibility by allowing patients to interact with the platform in Hindi or English.

The initial implementation supports:

English
Hindi
Sub-Modules
1. Language Selection

Patients can select their preferred interface language.

2. Voice Language Selection

Patients can choose the language used during the AI voice consultation.

3. Text Translation

Important application text can be displayed according to the selected language.

4. Speech-to-Text Support

The system converts patient speech into text during the AI consultation.

Supported consultation languages:

Hindi
English
5. Language Preference Save

The selected language preference can be saved in the patient's profile.

The system can automatically use the saved preference during future sessions.

Accessibility Goals

The user interface should also provide:

Large and clear buttons
Readable fonts
Simple navigation
Voice-assisted interaction
Clear icons
Elderly-friendly design
Phase 7 – Help & Support Module
Objective

The Help & Support module assists patients who experience difficulty while using the platform.

Sub-Modules
1. User Guide

Provides step-by-step instructions explaining:

Registration
AI Consultation
Report generation
Appointment booking
Hospital services
Profile management
2. Contact Support

Patients can contact the support team for assistance.

3. Frequently Asked Questions

Common questions and answers can be provided regarding:

AI consultation
Reports
Appointments
Pharmacy
Lab tests
Account settings
4. Feedback & Suggestions

Patients can submit feedback regarding the platform.

5. Report an Issue

Patients can report technical problems such as:

Login problems
Voice assistant issues
Report generation issues
Appointment problems
Application errors
6. Tutorials / Video Guide

Visual tutorials may be provided to demonstrate important system functionality.

Phase 8 – Hospital Services Module
Objective

The Hospital Services module allows patients to access important hospital-related facilities directly through the platform.

Patients are not required to complete an AI Consultation before using hospital services.

For example, emergency patients should be able to access emergency-related services immediately.

Phase 8.1 – Doctor Appointment Booking

Patients can search for doctors and book appointments.

Doctor information may include:

Doctor name
Specialization
Department
Working days
Available timings
Appointment slots
Appointment Workflow
Hospital Services
        ↓
Doctor Appointment
        ↓
Select Department
        ↓
Select Doctor
        ↓
Check Doctor Availability
        ↓
Select Date
        ↓
Select Time Slot
        ↓
Confirm Appointment
        ↓
Appointment Notification

Patients can later view:

Appointment date
Appointment time
Doctor details
Appointment status
Phase 8.2 – Hospital Pharmacy

The hospital pharmacy section provides information about medicines available through the hospital pharmacy.

Patients can:

Search medicines
Check medicine availability
View pharmacy information
Purchase permitted medicines online
Select hospital pickup
Select delivery where supported

The pharmacy section can also display:

Opening hours
Closing hours
Availability status

Medication sales remain subject to hospital and prescription policies.

Phase 8.3 – Lab Test Booking

Patients can view available diagnostic tests and book laboratory tests online.

Information may include:

Test name
Test availability
Price if applicable
Date
Time
Preparation instructions
Laboratory Workflow
Hospital Services
        ↓
Lab Test Booking
        ↓
Select Test
        ↓
Select Date / Time
        ↓
Confirm Booking
        ↓
Visit Laboratory
        ↓
Test Completed
        ↓
Report Uploaded
        ↓
Patient Receives Notification

Patients can later view or download their reports when available.

Phase 8.4 – Hospital Departments & Services

Patients can explore all available hospital departments and healthcare services.

Examples may include:

Emergency Care
OPD Services
Doctor Consultation
Laboratory Diagnostics
Surgery
ICU
Blood Bank
Vaccination Services
Pharmacy
Diagnostic Services
Phase 8.5 – Doctor Directory

The Doctor Directory provides detailed information about hospital doctors.

It may show:

Doctor name
Specialization
Department
Working days
Consultation timing
Availability status

This allows patients to determine whether a specific doctor is available before visiting the hospital.

Phase 8.6 – Ambulance Request

Patients can access ambulance-related services.

The system may allow a patient to:

Request ambulance assistance
Provide pickup location
Provide contact information
Check request status

Emergency functionality should remain simple and quick.

Phase 8.7 – Hospital Contact & Location

Patients can access:

Hospital address
Contact number
Emergency contact information
Hospital location
Navigation information
Hospital opening information
Emergency Care

Emergency care is included within Hospital Services.

Patients experiencing an emergency should not be required to complete an AI Consultation before requesting or accessing emergency medical help.

Emergency pathways must remain clearly visible and easy to access.

Phase 9 – Hospital Admin Portal
Objective

The Hospital Admin Portal allows authorized hospital administrators to manage hospital-side information and platform operations.

This portal is completely separate from the patient dashboard.

Only authenticated and authorized hospital staff can access it.

Phase 9.1 – Admin Login & Authentication

Hospital administrators must authenticate before accessing the Admin Portal.

Security features should include:

Secure login
Role-based access
Authorized account verification
Session management
Phase 9.2 – Patient Management

Authorized administrators can manage patient records according to hospital policies.

Possible CRUD operations:

Create patient
Read patient information
Update permitted information
Delete records where legally and administratively permitted
Phase 9.3 – Doctor Management

Administrators can manage doctor information.

They can:

Add doctor
Update doctor profile
Add specialization
Assign department
Set working days
Set consultation timings
Update availability
Remove doctor records where permitted
Phase 9.4 – Appointment Management

Administrators can manage patient appointments.

Actions may include:

View appointments
Approve appointment
Reschedule appointment
Cancel appointment
Update appointment status
Manage doctor time slots
Phase 9.5 – Hospital Pharmacy Management

Administrators can manage pharmacy information such as:

Medicine inventory
Medicine availability
Stock quantity
Pharmacy timings
Medicine information
Pickup availability
Delivery availability
Phase 9.6 – Laboratory Management

Administrators can manage hospital laboratory services.

Functions may include:

Add lab tests
Update test information
Manage booking slots
Update test availability
Upload test reports
Manage report status
Phase 9.7 – Departments & Services Management

Administrators can manage hospital departments and services.

They can:

Add department
Update department
Add hospital services
Update service information
Manage service availability
Phase 9.8 – Emergency & Ambulance Request Management

Hospital administrators can monitor emergency-related requests.

They may:

View ambulance requests
Update request status
Assign available resources
Monitor emergency requests
Phase 9.9 – Notifications & Announcements

Hospital administrators can send notifications to patients.

Examples:

Hospital announcements
Appointment updates
Service availability
Department notices
Important healthcare notices
Phase 9.10 – Reports & Basic Analytics

The hospital dashboard may display basic operational statistics such as:

Total registered patients
Total appointments
Today's appointments
Total AI consultations
Lab bookings
Pharmacy activity
Doctor availability
Ambulance requests

These analytics help hospital administrators understand system activity.

Admin CRUD Operations

The Admin Portal follows CRUD principles.

Create

Add new records.

Example:

Add doctor
Add medicine
Add lab test
Read

View existing records.

Update

Modify existing information.

Delete

Remove authorized records according to hospital policy.

Security and Privacy

Healthcare applications handle sensitive patient information.

Therefore, the system should implement:

Secure authentication
Role-based access control
Patient consent
Secure communication
Protected medical records
Access restrictions
Audit logging for important administrative operations

Patients should only access their own medical information.

Hospital administrators should only access information permitted by their role.

ABDM / ABHA / Healthcare Integration Direction

The platform should be designed so that future integration with healthcare infrastructure can be supported.

Possible integration areas include:

Hospital Information Systems
Electronic Medical Records
ABHA
ABDM ecosystem
FHIR-based healthcare information exchange

These integrations depend on the hospital infrastructure and available APIs.