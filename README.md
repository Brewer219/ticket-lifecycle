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




**Admin/Analyst/Agent Login Page:**
http://localhost/osTicket/scp/login.php

<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="osTicket Help Desk" src="https://github.com/user-attachments/assets/d290add1-c842-4636-b4f6-4c5149e0ee98" />





**End Users osTicket URL:**
http://localhost/osTicket

<details><summary>See screenshots</summary>

<img src="images/Step 2b.png" width="60%">
</details>


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


<details><summary>See screenshot 4</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Deleting the Maintenance Depart" src="https://github.com/user-attachments/assets/6d2a79f2-1a5d-4719-aa19-299743530dbb" />

<details><summary>See screenshot 5</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Confirm Deleting the Maintence depart" src="https://github.com/user-attachments/assets/034dc4ce-1742-40e2-a0ef-43f7d5cb9110" />

<details><summary>See screenshot 6</summary>

<img src="images/Step 2b.png" width="60%">
</details>
<img width="321" height="467" alt="Maintence Depart successfully deleted in Departments Tab" src="https://github.com/user-attachments/assets/61fd96fd-62c6-40a0-8262-8ac2742414c6" />








<h4>2. TICKET CREATION AND REVIEW</h4>
<p>End-user reports that the online banking system is down.
Login the End Users osTicket URL and as an end-user, Karen, open a new ticket. Intentionally choose the proper Help Topic, General Inquiry/Other and then actually explain the online banking system is down, and submit.  </p>
- Instructions:
1. Access the End User osTicket URL.
2. Log in as "Joann", the end user.
3. Create a new ticket, selecting "General Inquiry/Other" as the Help Topic and describing the online banking system outage.
4. Submit the ticket.
5. Log into the Admin portal as "Samuel Hancock"
6. Review the ticket and leave an internal note:
 -"This ticket requires elevated permissions. I will reach out to the SysAdmin department to request a role upgrade".
Login into the Admin portal as Samuel Hancock. Do the Reviewing of the ticket. Then do the Observation that Sam can only view the ticket, and leave an internal note.  



Let's leave a note, <i>"This ticket requires elevated permissions. I will reach out to the SysAdmin department to request a role upgrade"</i>





In osTicket, we cant @ or send the ticket directly to SysAdmin, but we can simulate, Sam leaving a note, reaching out to the department by external email to request elevated permissions to his account.

<details><summary>See screenshot 1</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Triaging Samuels Ticket" src="https://github.com/user-attachments/assets/a3787f37-0b52-4b1a-9490-755fbe55ead6" />


<details><summary>See screenshot 2</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel doing a Ticket Review" src="https://github.com/user-attachments/assets/4c4d6653-3f3b-4a2d-8e22-b7ebc5c2746f" />

<details><summary>See screenshot 3</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Inside Samel portal posting the test and &#39;Read Only&#39; access" src="https://github.com/user-attachments/assets/409936c1-b427-4ee5-a16e-3ce508f19686" />

<details><summary>See screenshot 4</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Posting &#39;Read Only&#39; access inside Samuel portal" src="https://github.com/user-attachments/assets/5f7b5be9-397b-4ce8-ac50-cbc73b77027e" />

<details><summary>See screenshot 5</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="VBAdminuser me giving all access or confirming he has all access in steps" src="https://github.com/user-attachments/assets/788e6baf-ab20-4937-92a7-ec1f6febdc1e" />

<details><summary>See screenshot 6</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Going into my Portal to change Samuel access by clicking &#39;Agents&#39;" src="https://github.com/user-attachments/assets/a5f4ed8e-b22a-4293-a342-e32f5a252faa" />

<details><summary>See screenshot 7</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Me as admin changing or confirming For Samuel Hancock all permissions access" src="https://github.com/user-attachments/assets/892faa31-ab25-467a-9512-e24495628a89" />

<details><summary>See screenshot 8</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="321" height="467" alt="Clicking the Samuel hancock link and then clicking the &#39;Access&#39; tab again" src="https://github.com/user-attachments/assets/185a688d-6f1e-48a8-ae0b-ab3fb1dd85f0" />

<details><summary>See screenshot 9</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel has &#39;view only&#39; access again" src="https://github.com/user-attachments/assets/279f2c0e-aacb-448f-9734-214e5511a86a" />

<details><summary>See screenshot 10</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="from &#39;Read Only&#39; to All Access for Samuel Hancock" src="https://github.com/user-attachments/assets/527eda38-713a-4b0a-88c6-70fc18c34dbf" />


<p>After I myself Victoria Brewer as the Administrator has changed the permissions from 'view only' to 'all access' successfully and now I'm successfully logging out my portal and logging back in as Samuel Hancock as Tech Support.</p>



## <h5>TICKET TRIAGING AND ESCALTION SIMULATION</h5>
- Objective: Triage the ticket and escalate it to the SysAdmin department.
- Instructions:
  1. Log  in as Sam.
  2. Update the ticket's priority to "Emergency"
  with the note:
      - "Called Joann and confirmed all teller systems have been down since lunch."
  3. Change the SLA Plan to "Sev-A" and the Help Topic to "Business Critical Outage"
  4. In response field, explain the steps taken and advise:
      -"Escalating and assigning ticket to SysAdmin Department after triaging."
  5. Post the reply and assign the ticket to "Susan Smith", transferring it to the "SysAdmin Department".

  <details><summary>See screenshot 1</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Triaging Samuels Ticket" src="https://github.com/user-attachments/assets/2a996241-a071-410b-814f-a877fc53a613" />


 <details><summary>See screenshot 2</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="321" height="467" alt="Samuel doing a Ticket Review" src="https://github.com/user-attachments/assets/f4cbada6-87d9-4e7c-8746-5180f175583a" />


<details><summary>See screenshot 3</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Updating the priority from normal to emergency for Joann as Samuel Tech Support " src="https://github.com/user-attachments/assets/dfc59958-2c19-4112-842b-c6cb6d40a4c9" />


<details><summary>See screenshot 4</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Back in portal after giving all access Updating Priority from Normal to Emergency with Samuel " src="https://github.com/user-attachments/assets/26b2f149-5da2-4022-ab43-57dc94f6ec12" />

<details><summary>See screenshot 5</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel has successfully updated Priority to say Emergency for Joann ticket" src="https://github.com/user-attachments/assets/8993ed4c-f62c-4697-9e6c-50c1155289a0" />


<details><summary>See screenshot 6</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel updating Joann ticket with &#39;Help Topics&#39; again from General Iquiry to Business Critical" src="https://github.com/user-attachments/assets/7637548b-dfdb-453d-a25d-50fc3a9363f3" />

<details><summary>See screenshot 7</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel updateing Joann ticket again for online banking system" src="https://github.com/user-attachments/assets/1394314e-d17c-4ff7-b980-9703f405db9d" />

<details><summary>See screenshot 8</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Explaining the Business Outage and updating Help Topic" src="https://github.com/user-attachments/assets/a7c836af-526c-4edd-a682-f43e715c814e" />




<details><summary>See screenshot 9</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Since Help Topics is Updated now look at Joann ticket for online banking system" src="https://github.com/user-attachments/assets/56817246-610b-41b7-81fc-bcaff5615486" />


<details><summary>See screenshot 10</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="321" height="467" alt="Samuel Updating the SLA for Joann ticket" src="https://github.com/user-attachments/assets/75f82d0c-d690-4ef8-a810-6df494a60562" />


<details><summary>See screenshot 11</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel updating the SLA to Sev-A for Joann Ticket for online banking again" src="https://github.com/user-attachments/assets/373104c6-b838-48a7-8f6a-fa9193d06fe2" />


<details><summary>See screenshot 12</summary>

<img src="images/Step 2b.png" width="60%">
</details>


<img width="321" height="467" alt="Samuel updated Sev-A Confirmed now take a look at the triage new ticket that needs finishing" src="https://github.com/user-attachments/assets/9a7f864b-c9ca-43f4-85a3-81889851a3d9" />


<details><summary>See screenshot 13</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="After fully triaging Joanns ticket as Samuel Hancock then post an reply once ready to reassign ticket to Susan the SysAdmin" src="https://github.com/user-attachments/assets/cea73c37-643a-4858-8268-13bfd1fdace2" />

<details><summary>See screenshot 14</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel assigning Joanns ticket to Susan the SysAdmin again" src="https://github.com/user-attachments/assets/df7deceb-eac3-4646-8c81-1014936f628d" />


<details><summary>See screenshot 15</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Finally Samuel assigning ticket to Susan with the &#39;Assign&#39; button" src="https://github.com/user-attachments/assets/0912df1f-d872-4f5b-9464-dade5241ac47" />


<details><summary>See screenshot 16</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Looking at ticket Susan is successfully assigned Joanns Ticket by Samuel" src="https://github.com/user-attachments/assets/e3d27bcc-5ef5-4e5b-a8ed-4789d2382467" />

<details><summary>See screenshot 17</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel transferring Joann ticket to &#39;Support&#39; to &#39;SysAdmin&#39;" src="https://github.com/user-attachments/assets/75394acd-6018-4977-8298-ffca9cc4c95b" />


<details><summary>See screenshot 18</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel clicked the Trasferred button to transfer Joann ticket the SysAdmin depart" src="https://github.com/user-attachments/assets/0c8c25dc-0840-4918-9200-b9fb46ee9ff7" />


<details><summary>See screenshot 19</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Samuel Tech Support doing the affects of transferring ticket successfully after fully going through the triaging process" src="https://github.com/user-attachments/assets/3d2449d3-1b37-4eb1-a295-843bdd2f77d1" />



    
>[!NOTE]: Examine that Samuel no longer has access to the original ticket, because of how our permissions are configured and it was now trasnferred to Susan Smith as the System Admin.



## <h6>TICKET RESOLUTION</h6>
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

 <details><summary>See screenshot 1</summary>

<img src="images/Step 2b.png" width="60%">
</details>
       

<img width="321" height="467" alt="Now logged in as Susan the SysAdmin" src="https://github.com/user-attachments/assets/14f02f9b-3e5f-402d-84b2-fc0570ad832d" />


<details><summary>See screenshot 2</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Susan reviewing Joann and Samuel notes" src="https://github.com/user-attachments/assets/f1cb1b23-a884-4640-925a-70255d1137b9" />





In a real work environment, system outages can be caused by many different factors. For the purposes of this lab, we will assume the issue was caused by an accidental restart of the online banking system’s backend server during business hours due to a configuration issue.

Post the following message as a ticket reply:

“We accidentally restarted the online banking system’s backend server during business hours due to a configuration issue. We will review the settings and attempt to restart the service.”

<details><summary>See screenshot 3</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Susan the system admin retarting the system accidentally related to business outage" src="https://github.com/user-attachments/assets/1e00272b-d3dc-4ec4-a0eb-992922083461" />


  



In this scenario, Susan restarts the server and verifies the online banking system status. Once service is confirmed to be restored, post the following update:
“Server successfully restarted. Online banking systems appear to be operational. Confirmed with Karen. Do closing ticket." Set the ticket status to Resolved. 

<details><summary>See screenshot 4</summary>

<img src="images/Step 2b.png" width="60%">
</details>

<img width="321" height="467" alt="Susan system admin confirming with Joann the online server is backup" src="https://github.com/user-attachments/assets/a1df79dc-c6a1-4c3c-b1b7-f25bb8206488" />




> [!NOTE]: In osTicket, setting a ticket’s status to Resolved automatically marks the ticket as Closed. Other ticketing systems may separate these steps, where a ticket is marked as Resolved after a fix is applied and Closed only after confirmation that no further action is required.


<details><summary>See screenshot 5</summary>

<img src="images/Step 2b.png" width="60%">
</details>






    
