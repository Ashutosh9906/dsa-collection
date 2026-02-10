# 📚 Data Structures & Algorithms (DSA) Repository

Welcome to my **DSA Practice Repository**!  

This repository is dedicated to storing all my **Data Structures and Algorithms** practice problems, solutions, and notes. I am following **Striver's A to Z DSA Course**, and this repo will serve as a record of my learning journey.

---

## Leetcode Stats
![LeetCode Stats](https://leetcard.jacoblin.cool/Ashutosh4069?theme=dark)

## Geeks For Geeks Stats
[![GeeksForGeeks Stats](https://gfgstatscard.vercel.app/ashutoshg7y6d)](https://www.geeksforgeeks.org/profile/ashutoshg7y6d)

```mermaid
flowchart LR

%% ======================
%% CLIENT LAYER
%% ======================
User[User]
WebApp[Web Application]

User --> WebApp

%% ======================
%% AUTHENTICATION
%% ======================
AuthService[Authentication Service]

WebApp -->|Login or Register| AuthService

GoogleOAuth[Google OAuth]
OTPService[OTP Service]

AuthService -->|OAuth Authentication| GoogleOAuth
AuthService -->|Send OTP| OTPService
OTPService -->|Verify OTP| AuthService

%% ======================
%% USER MANAGEMENT
%% ======================
UserService[User Management Service]

AuthService -->|Auth Success| UserService
WebApp -->|Submit User Details| UserService

%% ======================
%% CLUB AND APPROVAL
%% ======================
ClubService[Club and Approval Service]

UserService -->|Role is Club Member| ClubService

%% ======================
%% EVENT MANAGEMENT
%% ======================
EventService[Event Management Service]

WebApp -->|Fetch Events| EventService
WebApp -->|Create Event| EventService

%% ======================
%% DATABASES
%% ======================
UserDB[(User Database)]
ClubDB[(Club Database)]
RequestDB[(Membership Request Database)]
EventDB[(Event Database)]

UserService -->|Create or Update User| UserDB
AuthService -->|Validate Login| UserDB

ClubService -->|Store Club Data| ClubDB
ClubService -->|Create Join Request| RequestDB
ClubService -->|Approve or Reject Request| RequestDB
ClubService -->|Update User Role| UserDB

EventService -->|Store Event| EventDB
EventService -->|Read Events| EventDB

%% ======================
%% ROLE BASED USERS
%% ======================
Student[Student]
ClubMember[Club Member]
ClubHead[Club Head]
Admin[Admin]

User --> Student
User --> ClubMember
User --> ClubHead
User --> Admin

%% ======================
%% STUDENT FLOW
%% ======================
Student -->|View Events| WebApp
WebApp -->|Get Event Details| EventService
Student -->|Register via Link| ExternalApp[External Registration Application]

%% ======================
%% CLUB MEMBER FLOW
%% ======================
ClubMember -->|Request Club Join| WebApp
WebApp --> ClubService
ClubMember -->|Host Event| WebApp

%% ======================
%% CLUB HEAD FLOW
%% ======================
ClubHead -->|Approve Members| WebApp
WebApp --> ClubService

%% ======================
%% ADMIN FLOW
%% ======================
Admin -->|Verify Club Head| WebApp
WebApp --> ClubService
ClubService -->|Verify Club| ClubDB
```
