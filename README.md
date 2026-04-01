<img width="625" height="362" alt="osTicket Logo" src="https://github.com/user-attachments/assets/78033097-08a8-47cd-af0e-103d201a7007" />



<h1>osTicket Ticket Lifecycle Simulation</h1>
This project expands on the previous osTicket configuration lab by moving beyond setup and into a realistic end-to-end ticket lifecycle. Building on previously created departments, roles, and permissions, this scenario simulates a business-critical outage from initial end-user ticket creation through triage, escalation, role-based access changes, and final resolution. The lab emphasizes proper permission boundaries, escalation procedures, SLA prioritization, and real-world support workflows across Tier I and SysAdmin roles.<br />


<!--
<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)
-->

<h2>Environments and Technologies Used</h2>
<p align="left">
<img src="https://skillicons.dev/icons?i=azure,windows" />&nbsp;&nbsp;<img width="180" height="67" alt="osTicket Logo" src="https://github.com/user-attachments/assets/52bad22a-c832-43fe-bfc2-49d830cf4084" />


- Hosting: Microsoft Azure (Virtual Machines/Compute)
- Access Methods: Remote Desktop
- Platform: osTicket
- Operating Systems: Windows 10/11 

<h2>High-Level Deployment and Configuration Steps</h2>


**Key Actions**
1. Clean up initial osTicket configuration to ensure tickets route correctly.
2. Create and review a ticket as an end user and a limited-permission agent.
3. Simulate ticket triage, escalation, and role-based access changes.
4. Transfer the ticket to the appropriate department for resolution.
5. Resolve and close the ticket after verifying service restoration.

> [!IMPORTANT]
> Each step includes written instructions followed by a corresponding screenshot.
<br>Expand the **See screenshots** section to view the images.

<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>



**Admin/Analyst/Agent Login Page:**
http://localhost/osTicket/scp/login.php 
<img width="321" height="467" alt="osTicket Help Desk" src="https://github.com/user-attachments/assets/d290add1-c842-4636-b4f6-4c5149e0ee98" />


<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>


**End Users osTicket URL:**
http://localhost/osTicket 
<img width="321" height="467" alt="osTicket End User page setup for Users to submit tickets" src="https://github.com/user-attachments/assets/310e9190-5427-494e-8756-eff00cb37640" />


<h2>osTicket Configurations</h2> 

<h3>DELETE DEFAULT DEPARTMENT</h3>
<p>We need to delete the default Maintenance Department, as new tickets get automatically assigned to this department and not to the departments we created in the prior lab. In Admin panel, select Agents tab, select Department section. Select the Maintenance Department, and select More near the top-right, and select Delete.</p>
1. Log into the osTicket Admin panel.
2. Navigate to the "Agents" tab.
3. Select the "Departments" section.
4. Choose the "Maintenance Departmengt".
5. Click on "More" in the top-right corner and select "Delete".

<details><summary>See screenshot 1</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="osTicket click &#39;Admin Panel&#39;" src="https://github.com/user-attachments/assets/8d4306a1-4144-47b1-a338-52c34ee58611" />

<details><summary>See screenshot 2</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Going from Users page to Admin Panel click &#39;Manage&#39; tab" src="https://github.com/user-attachments/assets/74deda8d-b2da-44ba-803d-31979f71a4d8" />

<details><summary>See screenshot 3</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Maintenace being deleted" src="https://github.com/user-attachments/assets/35859db2-5300-4819-9b91-aa5e4ea36ba5" />











<h4>2. TICKET CREATION AND REVIEW</h4>
<p>End-user reports that the online banking system is down.
Login the End Users osTicket URL and as an end-user, Karen, open a new ticket. Intentionally choose the proper Help Topic, General Inquiry/Other and then actually explain the online banking system is down, and submit.  </p>
- Instructions:
1. Access the End User osTicket URL.
2. Log in as "Karen", the end user.
3. Create a new ticket, selecting "General Inquiry/Other" as the Help Topic and describing the online banking system outage.
4. Submit the ticket.
5. Log intothe Admin portal as "Sam Hancock"
6. Review the ticket and leave an internal note:
 -"This ticket requires elevated permissions. I will reach out to the SysAdmin department to request a role upgrade".

 <details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>

 

<img width="303" height="330" alt="Step 6 Ticket Life cycle what the ticket look like inside that was created" src="https://github.com/user-attachments/assets/eb641e2b-2f48-471c-8662-540e4ff59a43" />


Login into the Admin portal as Sam Hancock. Do the Reviewing of the ticket. Then do the Observation that Sam can only view the ticket, and leave an internal note.  
<img width="376" height="392" alt="Step 7 Life cycle Internal note section to type" src="https://github.com/user-attachments/assets/961cbb10-cd56-4923-9243-f7745438d320" />


Let's leave a note, <i>"This ticket requires elevated permissions. I will reach out to the SysAdmin department to request a role upgrade"</i>

<img width="368" height="307" alt="Step 8 Life cycle Giving all access to Sam as SysAdmin" src="https://github.com/user-attachments/assets/9ff853fb-9acd-4e9a-a000-cbdd0f276c27" />




In osTicket, we cant @ or send the ticket directly to SysAdmin, but we can simulate, Sam leaving a note, reaching out to the department by external email to request elevated permissions to his account.

<h5>TICKET TRIAGING AND ESCALTION SIMULATION</h5>
- Objective: Triage the ticket and escalate it to the SysAdmin department.
- Instructions:
  1. Logout as Sam and log in as the Admin user.
  2. Elevate Sam's role to "Super Admin".
  3. Log back in as Sam.
  4. Update the ticket's priority to "Emergency"
  with the note:
      - "Called Joann and confirmed all teller systems have been down since lunch."
  5. Change the SLA Plan to "Sev-A" and the Help Topic to "Business Critical Outage"
  6. In response field, explain the steps taken and advise:
      -"Escalating and assigning ticket to SysAdmin Department after triaging."
  7. Post the reply and assign the ticket to "Susan Smith", transferring it to the "SysAdmin Department".

  <details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="325" height="375" alt="Step 16 Life cycle as SysAdmin looking at the Notes" src="https://github.com/user-attachments/assets/88b845d6-8ce2-4906-8975-2805a9d936f4" />










 
  
    
>[!NOTE]: Examine that Sam no longer has access to the original ticket, because of how our permissions are configured.



<h6>TICKET RESOLUTION</h6>
- Objective: Resolve the ticket based on actions taken by the SysAdmin.
  - Instructions:
   1. Logout as Sam and log in as "Susan", the SysAdmin.
   2. Review the ticket timeline and notes from Joann and Sam.
   3. Document the cause of the outage in the ticket reply:
    -"We accidentally restarted the online banking system's backend server during business hours due to a configuration issue."
   4. Restart the backend server and verify service restoration.
   5. Post an update:
      -"Server successfully restarted. Online banking systems appear to be operational. Confirmed with Joann. Do closing ticket"
   6. Set the Ticket status to "Resolved".
   7. Logout as Sam, and log back in as Susan, our SysAdmin. Review the ticket as Susan, and observe the timeline, review the actions and notes given by Joann and Sam. 



 


In a real work environment, system outages can be caused by many different factors. For the purposes of this lab, we will assume the issue was caused by an accidental restart of the online banking system’s backend server during business hours due to a configuration issue.

Post the following message as a ticket reply:

“We accidentally restarted the online banking system’s backend server during business hours due to a configuration issue. We will review the settings and attempt to restart the service.”

<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="372" height="387" alt="Step 17 Life cycle SysAdmin documenting fix solution in Post Reply section" src="https://github.com/user-attachments/assets/fdbc4ba5-d618-4f22-90e1-35e256809c8c" />


   





In this scenario, Susan restarts the server and verifies the online banking system status. Once service is confirmed to be restored, post the following update:
“Server successfully restarted. Online banking systems appear to be operational. Confirmed with Karen. Do closing ticket." Set the ticket status to Resolved. 
<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="324" height="376" alt="Step 18 Life cycle Finished Documenting Post Reply" src="https://github.com/user-attachments/assets/ac6c422a-ac0e-4b16-b6ea-b2ef6bd569b7" />







> [!NOTE]: In osTicket, setting a ticket’s status to Resolved automatically marks the ticket as Closed. Other ticketing systems may separate these steps, where a ticket is marked as Resolved after a fix is applied and Closed only after confirmation that no further action is required.
<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="353" height="293" alt="Step 21 Life cycle Ticket status closed resolved" src="https://github.com/user-attachments/assets/8120aa4e-d747-4deb-8838-8c7666d4ecd6" />

    
