<img width="365" height="331" alt="Microsoft Active Directory Logo" src="https://github.com/user-attachments/assets/d59c7b9a-08ac-49d7-b186-bef10d5e27c7" />

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


> [!NOTE] 
> This project builds upon a prior lab where the Azure environment, virtual machine, osTicket and various users and teams were created. <br /> **[Part 2. osTicket: Configurations](https://github.com/MikeSays-1/osTicket-Config/)**

**Admin/Analyst/Agent Login Page:**
http://localhost/osTicket/scp/login.php 

**End Users osTicket URL:**
http://localhost/osTicket 

<h2>osTicket Configurations</h2> 

<h3>DELETE DEFAULT DEPARTMENT</h3>
<p>We need to delete the default Maintenance Department, as new tickets get automatically assigned to this department and not to the departments we created in the prior lab. In Admin panel, select Agents tab, select Department section. Select the Maintenance Department, and select More near the top-right, and select Delete.</p>
1. Log into the osTicket Admin panel.
2. Navigate to the "Agents" tab.
3. Select the "Departments" section.
4. Choose the "Maintenance Departmengt".
5. Click on "More" in the top-right corner and select "Delect"




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



Login into the Admin portal as Sam Hancock. Do the Reviewing of the ticket. Then do the Observation that Sam can only view the ticket, and leave an internal note.  

Let's leave a note, <i>"This ticket requires elevated permissions. I will reach out to the SysAdmin department to request a role upgrade"</i>



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







> [!NOTE]
> Examine that Sam no longer has access to the original ticket, because of how our permissions are configured.



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




In this scenario, Susan restarts the server and verifies the online banking system status. Once service is confirmed to be restored, post the following update:
“Server successfully restarted. Online banking systems appear to be operational. Confirmed with Karen. Do closing ticket." Set the ticket status to Resolved. 





> [!NOTE]
> In osTicket, setting a ticket’s status to Resolved automatically marks the ticket as Closed. Other ticketing systems may separate these steps, where a ticket is marked as Resolved after a fix is applied and Closed only after confirmation that no further action is required.
