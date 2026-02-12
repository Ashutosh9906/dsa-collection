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

User[User]
WebApp[Web Application]

User --> WebApp

Auth[Authentication Service]
Backend[Backend Services]
Events[Event Service]
GetEvents[Get All Club Events]

WebApp -->|Register or Login| Auth
Auth -->|Google or OTP| ExternalAuth[External Auth Services]

WebApp -->|User Data and Requests| Backend
Backend --> UserDB[(User Database)]
Backend --> ClubDB[(Club Database)]

WebApp -->|Request Events| GetEvents
GetEvents --> Events
Events --> EventDB[(Event Database)]

WebApp -->|Event Registration| ExternalApp[External Registration App]
```
