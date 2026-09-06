# PATIENT CASE-TAKING SOFTWARE
# COMPLETE SYSTEM ARCHITECTURE & WORKFLOW

## Document Name

Architecture and Workflow

## Purpose of this Document

This document defines the complete architecture and workflow of the Patient Case-Taking Software.

It explains:

- Complete project architecture
- All 9 main modules
- Relationship between modules
- How data moves between modules
- Patient-side workflow
- AI Consultation workflow
- Report generation workflow
- Hospital Services workflow
- Notification workflow
- Admin-side workflow
- Database relationship
- Authentication and authorization flow
- Security architecture
- Module-to-module communication
- Complete end-to-end system workflow

The purpose of this file is to act as the central architectural reference for development of the complete project.

---

# 1. PROJECT OVERVIEW

The Patient Case-Taking Software is an AI-assisted healthcare platform designed to collect patient information before doctor consultation and provide additional digital hospital services through one integrated system.

The platform combines:

- Patient Registration
- AI Voice Consultation
- Previous Medical Report Processing
- AI Patient Report Generation
- Report History
- Notifications
- Patient Profile Management
- Hindi and English Language Support
- Help & Support
- Doctor Appointment Booking
- Hospital Pharmacy
- Lab Test Booking
- Doctor Directory
- Hospital Departments & Services
- Ambulance Request
- Hospital Contact & Location
- Hospital Admin Portal

The AI system assists with patient case-taking but does not independently provide the final diagnosis or treatment.

The doctor remains the final clinical decision-maker.

---

# 2. TOTAL PROJECT MODULES

The complete platform contains 9 major modules.

Module 1 – Patient Registration

Module 2 – AI Consultation

Module 3 – My Report History

Module 4 – Notification Center

Module 5 – My Profile & Settings

Module 6 – Multi-Language Support

Module 7 – Help & Support

Module 8 – Hospital Services

Module 9 – Hospital Admin Portal

---

# 3. HIGH-LEVEL SYSTEM ARCHITECTURE

The complete system can be divided into the following major architectural layers:

1. User Layer
2. Frontend Layer
3. Authentication & Authorization Layer
4. Application Backend Layer
5. AI & Voice Processing Layer
6. Medical Document Processing Layer
7. Hospital Services Layer
8. Notification Layer
9. Data Storage Layer
10. Admin Management Layer
11. External Integration Layer

---

# 4. HIGH-LEVEL ARCHITECTURE DIAGRAM

```text
                         PATIENT / USER
                              |
                              v
                    +--------------------+
                    |  PATIENT FRONTEND  |
                    +--------------------+
                              |
                              v
                    +--------------------+
                    | AUTHENTICATION &   |
                    | AUTHORIZATION      |
                    +--------------------+
                              |
                              v
               +-----------------------------+
               |      BACKEND API LAYER      |
               +-----------------------------+
                    |       |       |
                    |       |       |
                    v       v       v
             +----------+ +----------+ +----------------+
             | PATIENT  | | HOSPITAL | | NOTIFICATION   |
             | SERVICES | | SERVICES | | ENGINE         |
             +----------+ +----------+ +----------------+
                    |
                    v
           +-----------------------+
           |   AI CONSULTATION     |
           |       ENGINE          |
           +-----------------------+
              |                |
              v                v
       +-------------+   +------------------+
       | SPEECH /    |   | MEDICAL DOCUMENT |
       | VOICE       |   | PROCESSING       |
       +-------------+   +------------------+
              |                |
              +-------+--------+
                      |
                      v
             +------------------+
             | STRUCTURED       |
             | PATIENT REPORT   |
             | GENERATOR        |
             +------------------+
                      |
                      v
             +------------------+
             | DATABASE / FILE  |
             | STORAGE          |
             +------------------+
                      ^
                      |
             +--------------------+
             | HOSPITAL ADMIN     |
             | PORTAL             |
             +--------------------+

1. PATIENT-SIDE MAIN ARCHITECTURE

Patient
   |
   v
Registration / Login
   |
   v
Patient Dashboard
   |
   +-----------------------------+
   |                             |
   v                             v
AI Consultation             Hospital Services
   |                             |
   v                             |
AI Patient Report                |
   |                             |
   v                             |
My Report History                |
   |                             |
   +-------------+---------------+
                 |
                 v
        Notification Center

Additional Global Modules:

My Profile & Settings
Multi-Language Support
Help & Support

2. AI CONSULTATION INTERNAL ARCHITECTURE

Patient Opens AI Consultation
            |
            v
     Language Confirmation
            |
            v
      Voice Assistant
            |
            v
      Patient Speaks
            |
            v
     Speech-to-Text
            |
            v
   Conversation Processing
            |
            v
   Context / Case-Taking Engine
            |
            v
  Dynamic Follow-Up Question
            |
            v
       AI Response
            |
            v
       Text-to-Speech
            |
            v
        Patient Hears AI
            |
            v
      Patient Responds
            |
            +------------------+
            |                  |
            | Optional         |
            v                  |
 Previous Medical Report       |
            |                  |
            v                  |
      OCR Processing           |
            |                  |
            v                  |
 Medical Data Extraction       |
            |                  |
            +--------+---------+
                     |
                     v
           Structured Case Data
                     |
                     v
              Patient Submit
                     |
                     v
           AI Patient Report

3. AI VOICE CONSULTATION WORKFLOW

Start
  |
  v
Load Patient Information
  |
  v
Confirm English / Hindi
  |
  v
AI Welcome Message
  |
  v
AI Asks:
"What problem are you facing today?"
  |
  v
Patient Describes Problem Naturally
  |
  v
Speech-to-Text
  |
  v
AI Understands Context
  |
  v
Extract Available Information
  |
  v
Identify Missing Relevant Information
  |
  v
Generate Dynamic Follow-Up Question
  |
  v
Patient Answers
  |
  v
Update Consultation Context
  |
  v
More Relevant Information Required?
  |
  +---- YES ----> Ask Next Relevant Question
  |
  +---- NO -----> Ready for Submission

4. CONSULTATION CONTEXT ARCHITECTURE

Consultation Context
|
|-- Chief Complaint
|
|-- Duration
|
|-- Symptom Progression
|
|-- Severity
|
|-- Associated Symptoms
|
|-- Medicines Already Taken
|
|-- Patient-Reported Medicine Response
|
|-- Existing Diseases
|
|-- Previous Relevant History
|
|-- Uploaded Report Information
|
|-- Conversation Transcript

5. PREVIOUS MEDICAL REPORT PROCESSING ARCHITECTURE

Patient Uploads Report
        |
        v
File Validation
        |
        v
Secure File Upload
        |
        v
Document Type Processing
        |
        v
OCR
        |
        v
Raw Text Extraction
        |
        v
Text Cleaning
        |
        v
Medical Information Extraction
        |
        +----------------------------------+
        |              |                   |
        v              v                   v
Medicine Data       Lab Data        Previous History
        |              |                   |
        +--------------+-------------------+
                       |
                       v
              Structured Document Data
                       |
                       v
              AI Consultation Context
                       |
                       v
               AI Patient Report

6.Language Architecture

Patient Opens Application
        |
        v
Check Saved Language
        |
        +---- Available ----> Load Preference
        |
        +---- Not Available -> Use Default
        |
        v
Global Language State
        |
        +-------------------------------+
        |                               |
        v                               v
Interface Translation            AI Voice Language
        |                               |
        v                               v
English / Hindi             Speech-to-Text / TTS

6. MODULE 8 – HOSPITAL SERVICES ARCHITECTURE

Module 8 contains:

Doctor Appointment Booking
Hospital Pharmacy
Lab Test Booking
Hospital Departments & Services
Doctor Directory
Ambulance Request
Hospital Contact & Location

Hospital Services Architecture

Hospital Services
|
|-- Doctor Appointment
|
|-- Hospital Pharmacy
|
|-- Lab Test Booking
|
|-- Departments & Services
|
|-- Doctor Directory
|
|-- Ambulance Request
|
|-- Hospital Contact & Location

DOCTOR APPOINTMENT ARCHITECTURE

Patient
   |
   v
Doctor Appointment
   |
   v
Select Department
   |
   v
Select Doctor
   |
   v
Doctor Schedule
   |
   v
Select Date
   |
   v
Available Slots
   |
   v
Select Slot
   |
   v
Backend Revalidates Slot
   |
   +---- Unavailable ---> Refresh Slots
   |
   +---- Available -----> Create Appointment
                              |
                              v
                         Notification

Appointment Data Relationship

Patient
   |
patientId
   |
Appointment
   |
doctorId
   |
Doctor
   |
departmentId
   |
Department

DOCTOR DIRECTORY ARCHITECTURE

Doctor Management in Admin Portal
        |
        v
Doctor Database
        |
        v
Doctor Directory
        |
        +-- Name
        |
        +-- Specialization
        |
        +-- Department
        |
        +-- Working Days
        |
        +-- Timing
        |
        +-- Availability
        |
        v
Book Appointment

HOSPITAL PHARMACY ARCHITECTURE

Hospital Admin
      |
      v
Pharmacy Inventory
      |
      v
Patient Hospital Pharmacy
      |
      v
Search Medicine
      |
      v
Check Availability
      |
      v
Prescription Required?
      |
      +---- YES ---> Follow Hospital Policy
      |
      +---- NO / Valid ---> Select Service
                              |
                              +-- Pickup
                              |
                              +-- Delivery

LAB TEST BOOKING ARCHITECTURE

Patient
   |
   v
Lab Test Booking
   |
   v
Select Test
   |
   v
View Test Information
   |
   v
View Preparation Instructions
   |
   v
Select Date / Time
   |
   v
Create Booking
   |
   v
Notification
   |
   v
Test Completed
   |
   v
Admin / Lab Staff Uploads Report
   |
   v
Secure Report Storage
   |
   +-------------------------+
   |                         |
   v                         v
Notification Center     Report Access
                             |
                             v
                    My Report History
                    where configured


DEPARTMENTS & SERVICES ARCHITECTURE

Hospital Admin
      |
      v
Department / Service Management
      |
      v
Hospital Database
      |
      v
Patient Hospital Services
      |
      +-- Department Details
      |
      +-- Working Hours
      |
      +-- Available Doctors
      |
      +-- Service Availability
      |
      +-- Contact Information

AMBULANCE REQUEST ARCHITECTURE

Patient
   |
   v
Ambulance Request
   |
   v
Contact Information
   |
   v
Pickup Location
   |
   v
Submit Request
   |
   v
Emergency Request Database
   |
   v
Hospital Admin / Authorized Staff
   |
   v
Assign Ambulance / Resource
   |
   v
Update Status
   |
   v
Patient Sees Status

EMERGENCY ACCESS RULE

Emergency Patient
      |
      v
Hospital Services
      |
      +-- Emergency Information
      |
      +-- Ambulance Request
      |
      +-- Hospital Contact

HOSPITAL CONTACT & LOCATION ARCHITECTURE

Hospital Configuration
       |
       v
Hospital Contact & Location
       |
       +-- Hospital Name
       |
       +-- Address
       |
       +-- Main Contact
       |
       +-- Emergency Contact
       |
       +-- Map Coordinates
       |
       +-- Working Hours
       |
       v
Patient

7. MODULE 9 – HOSPITAL ADMIN PORTAL ARCHITECTURE

The Hospital Admin Portal controls hospital-side operational information.

It contains:

Admin Login & Authentication
Patient Management
Doctor Management
Appointment Management
Pharmacy Management
Lab Test Management
Departments & Services Management
Emergency & Ambulance Management
Notifications & Announcements
Reports & Analytics

ADMIN PORTAL ARCHITECTURE

Authorized Hospital User
        |
        v
Admin Login
        |
        v
Authentication
        |
        v
Role-Based Authorization
        |
        v
Admin Dashboard
        |
        +--------------------------------------------+
        |                                            |
        v                                            v
Patient Management                           Doctor Management
        |
        +--------------------------------------------+
        |                                            |
        v                                            v
Appointment Management                      Pharmacy Management
        |
        +--------------------------------------------+
        |                                            |
        v                                            v
Lab Management                         Departments & Services
        |
        +--------------------------------------------+
        |                                            |
        v                                            v
Emergency / Ambulance                 Notifications / Announcements
        |
        v
Reports & Analytics

ADMIN AUTHENTICATION FLOW

Admin Login
   |
   v
Credentials
   |
   v
Backend Authentication
   |
   v
Account Valid?
   |
   +---- NO ----> Reject Login
   |
   +---- YES
          |
          v
      Check Role
          |
          v
     Check Permission
          |
          v
     Create Session
          |
          v
      Admin Portal

ROLE-BASED ACCESS ARCHITECTURE

Pharmacy Staff
      |
      +-- Pharmacy Access
      |
      X-- No Full Patient Medical Record Access

Lab Staff
      |
      +-- Lab Management
      |
      X-- No Pharmacy Management

Appointment Staff
      |
      +-- Appointment Management
      |
      X-- No Lab Report Administration

PATIENT MANAGEMENT FLOW

Registered Patient
      |
      v
Patient Database
      |
      v
Admin Patient Management
      |
      +-- View
      |
      +-- Search
      |
      +-- Create where allowed
      |
      +-- Update permitted data
      |
      +-- Deactivate / authorized action

DOCTOR MANAGEMENT FLOW

Admin Adds / Updates Doctor
          |
          v
Doctor Database
          |
          +--------------------+
          |                    |
          v                    v
Doctor Directory        Appointment Booking
          |
          v
Department Information

APPOINTMENT MANAGEMENT FLOW

Patient Books Appointment
          |
          v
Appointment Database
          |
          v
Admin Appointment Management
          |
          +-- Confirm
          |
          +-- Reschedule
          |
          +-- Cancel
          |
          +-- Complete
          |
          v
Notification Generator
          |
          v
Patient Notification Center

PHARMACY MANAGEMENT FLOW

Registered Patient
      |
      v
Patient Database
      |
      v
Admin Patient Management
      |
      +-- View
      |
      +-- Search
      |
      +-- Create where allowed
      |
      +-- Update permitted data
      |
      +-- Deactivate / authorized action

LAB MANAGEMENT FLOW

Admin Lab Management
       |
       +-- Add Tests
       |
       +-- Manage Availability
       |
       +-- Manage Bookings
       |
       +-- Mark Completed
       |
       +-- Upload Report
       |
       v
Lab Database
       |
       +---------------------+
       |                     |
       v                     v
Patient Lab Services    Notification Center
       |
       v
Report History
where configured

8. COMPLETE PATIENT JOURNEY

START
  |
  v
Patient Registration
  |
  v
Patient Profile Created
  |
  v
Patient Dashboard
  |
  +----------------------------------------------------+
  |                                                    |
  |                                                    |
  v                                                    v
AI Consultation                                 Hospital Services
  |                                                    |
  v                                                    |
Choose Language                                         |
  |                                                    |
  v                                                    |
Voice Consultation                                      |
  |                                                    |
  v                                                    |
Dynamic Case-Taking                                     |
  |                                                    |
  v                                                    |
Optional Previous Report                                |
  |                                                    |
  v                                                    |
OCR + Medical Extraction                                |
  |                                                    |
  v                                                    |
Submit Consultation                                     |
  |                                                    |
  v                                                    |
AI Patient Report                                       |
  |                                                    |
  v                                                    |
Review / Edit                                           |
  |                                                    |
  v                                                    |
Confirm                                                 |
  |                                                    |
  v                                                    |
Final PDF Report                                        |
  |                                                    |
  v                                                    |
My Report History                                       |
  |                                                    |
  +-------------------------+--------------------------+
                            |
                            v
                    Notification Center
                            |
                            v
                       Patient Uses
                     Required Services

9. COMPLETE AI CONSULTATION JOURNEY

Patient
  |
  v
AI Consultation
  |
  v
Language Selection
  |
  v
Welcome
  |
  v
Chief Complaint
  |
  v
Speech-to-Text
  |
  v
AI Context Engine
  |
  v
Dynamic Follow-Up Questions
  |
  v
Patient Responses
  |
  +-------------------------------+
  |                               |
  v                               |
Previous Report Upload            |
  |                               |
  v                               |
OCR                               |
  |                               |
  v                               |
Medical Data Extraction           |
  |                               |
  +---------------+---------------+
                  |
                  v
         Structured Case Data
                  |
                  v
               Submit
                  |
                  v
          AI Patient Report
                  |
                  v
          Review / Correction
                  |
                  v
              Confirm
                  |
                  v
            Final Report
                  |
                  v
           PDF + Database
                  |
                  v
          My Report History

9. COMPLETE ADMIN WORKFLOW

Hospital Admin
      |
      v
Admin Authentication
      |
      v
Role Validation
      |
      v
Admin Dashboard
      |
      +----------------------------+
      |                            |
      v                            v
Manage Patients               Manage Doctors
      |                            |
      v                            v
Manage Appointments           Manage Pharmacy
      |                            |
      v                            v
Manage Lab                   Manage Departments
      |                            |
      v                            v
Manage Ambulance             Manage Notifications
      |
      v
View Operational Analytics

67. FRONTEND ARCHITECTURE
Application
|
|-- Authentication
|
|-- Patient Dashboard
|
|-- Patient Registration
|
|-- AI Consultation
|
|-- My Report History
|
|-- Notification Center
|
|-- My Profile & Settings
|
|-- Multi-Language System
|
|-- Help & Support
|
|-- Hospital Services
|
|-- Shared Components
      |
      |-- Header
      |-- Navigation
      |-- Language Selector
      |-- Profile Menu
      |-- Notification Bell
      |-- Loading Components
      |-- Error Components

68. ADMIN FRONTEND ARCHITECTURE

Admin Application
|
|-- Admin Authentication
|
|-- Dashboard
|
|-- Patient Management
|
|-- Doctor Management
|
|-- Appointment Management
|
|-- Pharmacy Management
|
|-- Lab Management
|
|-- Departments & Services
|
|-- Emergency & Ambulance
|
|-- Notifications & Announcements
|
|-- Reports & Analytics
|
|-- Shared Admin Components
      |
      |-- Sidebar
      |-- Tables
      |-- Filters
      |-- Forms
      |-- Confirmation Modals
      |-- Loading States
      |-- Error States

69. BACKEND ARCHITECTURE

Backend
|
|-- Authentication Service
|
|-- Patient Service
|
|-- Profile Service
|
|-- AI Consultation Service
|
|-- Document Processing Service
|
|-- Report Service
|
|-- Notification Service
|
|-- Appointment Service
|
|-- Pharmacy Service
|
|-- Lab Service
|
|-- Department Service
|
|-- Ambulance Service
|
|-- Support Service
|
|-- Admin Service
|
|-- Analytics Service
|
|-- File Storage Service

70. AI SERVICE ARCHITECTURE
AI Consultation Service
|
|-- Conversation Session Manager
|
|-- Speech-to-Text Integration
|
|-- Case-Taking Context Manager
|
|-- Dynamic Question Generator
|
|-- Medical Document Processor
|
|-- OCR Processor
|
|-- Medical Information Extractor
|
|-- Structured Report Generator
|
|-- Summary Generator
|
|-- Safety Rules

73. COMPLETE END-TO-END PROJECT WORKFLOW

START
  |
  v
Patient Registration
  |
  v
Patient Account / Profile
  |
  v
Patient Dashboard
  |
  +-------------------------------------------------------------+
  |                                                             |
  v                                                             v
AI Consultation                                           Hospital Services
  |                                                             |
  v                                                             |
Language Selection                                               |
  |                                                             |
  v                                                             |
Voice Consultation                                               |
  |                                                             |
  v                                                             |
Dynamic Questioning                                              |
  |                                                             |
  v                                                             |
Optional Previous Report                                         |
  |                                                             |
  v                                                             |
OCR / Medical Extraction                                         |
  |                                                             |
  v                                                             |
Consultation Submit                                              |
  |                                                             |
  v                                                             |
AI Patient Report                                                |
  |                                                             |
  v                                                             |
Review / Edit                                                    |
  |                                                             |
  v                                                             |
Confirm                                                          |
  |                                                             |
  v                                                             |
Final Report                                                     |
  |                                                             |
  v                                                             |
PDF + Storage                                                    |
  |                                                             |
  v                                                             |
My Report History                                                |
  |                                                             |
  +------------------------------+------------------------------+
                                 |
                                 v
                         Notification Center
                                 |
                                 v
                        Patient Continues Using
                           Healthcare Services


Meanwhile:

Hospital Admin Portal
        |
        +-- Manages Patients
        +-- Manages Doctors
        +-- Manages Appointments
        +-- Manages Pharmacy
        +-- Manages Lab
        +-- Manages Departments
        +-- Manages Ambulance
        +-- Publishes Notifications
        +-- Views Analytics
        |
        v
Patient-Side Modules Receive Updated Hospital Data

74. COMPLETE PROJECT DATA FLOW
PATIENT INPUT
     |
     v
FRONTEND
     |
     v
AUTHENTICATION
     |
     v
BACKEND
     |
     +-------------------------------+
     |                               |
     v                               v
PATIENT SERVICES                HOSPITAL SERVICES
     |                               |
     v                               v
AI SERVICES                    OPERATIONAL SERVICES
     |                               |
     v                               |
STRUCTURED DATA                      |
     |                               |
     +---------------+---------------+
                     |
                     v
                  DATABASE
                     |
          +----------+----------+
          |                     |
          v                     v
 PATIENT APPLICATION      ADMIN PORTAL

76. FINAL SYSTEM ARCHITECTURE SUMMARY

                    PATIENT CASE-TAKING SOFTWARE

                              |
          +-------------------+-------------------+
          |                                       |
          v                                       v
   PATIENT APPLICATION                     ADMIN PORTAL
          |                                       |
          |                                       |
          +-- Patient Registration                +-- Authentication
          |                                       |
          +-- AI Consultation                     +-- Patient Management
          |                                       |
          +-- Report History                      +-- Doctor Management
          |                                       |
          +-- Notification Center                 +-- Appointment Management
          |                                       |
          +-- Profile & Settings                  +-- Pharmacy Management
          |                                       |
          +-- Multi-Language                      +-- Lab Management
          |                                       |
          +-- Help & Support                      +-- Departments & Services
          |                                       |
          +-- Hospital Services                   +-- Emergency Management
                                                  |
                                                  +-- Notifications
                                                  |
                                                  +-- Analytics

                              |
                              v
                       BACKEND SERVICES
                              |
          +-------------------+-------------------+
          |                   |                   |
          v                   v                   v
     AI SERVICES        HOSPITAL SERVICES    NOTIFICATION ENGINE
          |                   |                   |
          +-------------------+-------------------+
                              |
                              v
                         DATA STORAGE
                              |
         +--------------------+--------------------+
         |                    |                    |
         v                    v                    v
   PATIENT DATA         MEDICAL REPORTS      HOSPITAL DATA

