# CardioPath

## Outline
1. [Description](#description)
2. [Team Members and Their Roles](#team-members-and-their-roles)
3. [Objectives](#objectives)  
   3.1 [Benefits to the Customer](#benefits-to-the-customer)  
   3.2 [Key Things to Accomplish](#key-things-to-accomplish)  
   3.3 [Criteria for Success](#criteria-for-success)  
4. [Expected / Anticipated Architecture](#expected--anticipated-architecture)
5. [Anticipated Risks](#anticipated-risks)  
   5.1 [Engineering Challenges](#engineering-challenges)  
6. [Legal and Social Issues](#legal-and-social-issues)
7. [Initial Plans for First Release and Tool Setup](#initial-plans-for-first-release-and-tool-setup)
8. [Tooling Constraints and Preferences](#tooling-constraints-and-preferences)

---

## Description

### Problem
Many cardiology patients require multiple diagnostic tests (e.g., echocardiograms, stress tests, perfusion imaging) that are only available at specific clinics or hospitals. Patients often travel long distances from rural areas (e.g., Renfrew, Calabogie, Barry’s Bay), leading to:

- Inefficient transportation scheduling  
- Long wait times between tests  
- Underutilization of available testing equipment  
- Logistical challenges when patients are booked individually rather than as groups  

### Proposed Solution
The envisioned solution is a **centralized booking and transportation coordination system** that:

- Allows referring physicians to request **both appointments and transportation** for patients  
- Groups patients traveling from similar regions so they can be transported together  
- Aligns transportation schedules with clinic capacity (e.g., running multiple tests in parallel)  
- Reduces idle waiting time for patients and staff  
- Improves overall throughput and patient experience  

### Key Considerations
- **Privacy & Compliance:** The system must handle Personal Health Information (PHI) securely, in compliance with Canadian privacy laws (including health card numbers, dates of birth, etc.).
- **Integration:** Potential need to integrate with existing medical and booking systems in read/write or read-only modes.
- **Impact:** Better coordination could significantly improve access to cardiac care and, in critical cases, help save lives.

### Goal
To design a scalable, privacy-compliant transportation and booking workflow that optimizes cardiology testing logistics while reducing patient burden and operational inefficiencies.

---

## Team Members and Their Roles

| Team Member              | Role                    |
|--------------------------|-------------------------|
| Laurier Gascon-Miller    | Requirements Management |
| David Malek              | Algorithm R&D           |
| Racine Kane              | DevOps                  |
| Alvin-Thomas Tran        | Front-end Developer     |
| Kalan King               | Backend Developer       |

---

## Objectives

### Benefits to the Customer
The primary goal is to improve access to cardiology care for patients in remote communities by reducing travel burden, wait times, and fragmented scheduling, while minimizing additional workload for clinic staff.

The platform aims to help Capital Cardiology:
- Serve remote patients more efficiently  
- Reduce inequities between urban and rural access to cardiology diagnostics  
- Coordinate transportation and testing in a structured way  
- Reduce manual coordination effort for clinic staff  

### Key Things to Accomplish
Based on the meeting, the system should:
- Identify Capital Cardiology referrals coming from remote or distant communities  
- Group patients by geographic location for coordinated transportation  
- Recommend same-day or coordinated scheduling for multiple cardiology tests  
- Respect clinical constraints such as test duration and ordering (e.g., echocardiogram before nuclear imaging)  
- Support triage workflows where human review determines required tests  
- Assist staff in coordinating transportation for grouped patients  
- Notify stakeholders (clinic staff, patients, transportation providers) once bookings are approved  

### Criteria for Success
The project will be considered successful if:
- Clinic staff can review and approve system-generated recommendations  
- Scheduling recommendations respect clinical constraints  
- The system reduces manual coordination effort compared to the current process  
- The platform is suitable for a pilot at Capital Cardiology  

---

## Expected / Anticipated Architecture
<img width="960" height="720" alt="Context Diagram (1)" src="https://github.com/user-attachments/assets/ca7fa04d-c2fe-4b11-8534-ada47c28ec72" />


### Referral Intake
Uses existing referral methods such as fax, Ocean, or manual EMR entry.

---

## Anticipated Risks

### Engineering Challenges
- **Privacy and Security:** Managing sensitive health data across multiple systems raises the risk of data breaches and regulatory non-compliance.
- **Integration with External Applications:** Hospital systems, EHRs, fax services, and transport platforms may not expose APIs or may restrict access.
- **Edge Cases and Exceptions:** Emergency insertions, unusual patient needs, or last-minute cancellations may not be handled well by automation.
- **Transportation Uncertainty:** Traffic, weather, patient readiness, and long-distance travel into urban hospitals can cause cascading delays.
- **Consent Management:** Ensuring patients have given appropriate consent for data sharing and transportation coordination.

---

## Legal and Social Issues
- Handling confidential patient information (data protection, confidentiality, consent)
- Accommodation for persons with disabilities (accessibility)
- Risks associated with the use of AI for determining optimal transportation paths

---

## Initial Plans for First Release and Tool Setup
The first release will include a minimal subset of requirements showcasing core functionality:

- Allowing users to enter patient data including:
  - Address  
  - Tests to be completed  
- Displaying recommended test ordering and shuttle pick-up locations  
- No interactions with external systems  
- Limited automation in the first release  

---

## Tooling Constraints and Preferences
- Preference to avoid non-GitHub tools (e.g., Confluence, Jira) to reduce complexity
