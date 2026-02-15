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


- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- osTicket

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>


**Key Actions**
- Clean up initial osTicket configuration to ensure tickets route correctly
- Create and review a ticket as an end user and a limited-permission agent
- Simulate ticket triage, escalation, and role-based access changes
- Transfer the ticket to the appropriate department for resolution
- Resolve and close the ticket after verifying service restoration

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

<h3>1. DELETE DEFAULT DEPARTMENT</h3>
<p>We need to delete the default Maintenance Department, as new tickets get automatically assigned to this department and not to the departments we created in the prior lab. In Admin panel, select Agents tab, select Department section. Select the Maintenance Department, and select More near the top-right, and select Delete.</p>

<img width="342" height="333" alt="Step 1 Ticket life cycle maintenace delete depart" src="https://github.com/user-attachments/assets/7d166bfd-724b-479d-be33-ac52e6a1df76" />


<h3>2. TICKET CREATION AND REVIEW</h3>
<p>End-user reports that the online banking system is down.

Login the End Users osTicket URL and as an end-user, Karen, open a new ticket. Intentionally choose the proper Help Topic, General Inquiry/Other and then actually explain the online banking system is down, and submit.  </p>

<img width="374" height="333" alt="Step 3 Ticket Life cycle creating ticket in the end user portal" src="https://github.com/user-attachments/assets/fa14fcc3-3508-4419-81f8-060628bea4f8" />



Login into the Admin portal as Sam Hancock. Do the Reviewing of the ticket. Then do the Observation that Sam can only view the ticket, and leave an internal note.  

Let's leave a note, <i>"This ticket requires elevated permissions. I will reach out to the SysAdmin department to request a role upgrade"</i>
<img width="346" height="392" alt="Step 7 Life cycle Internal note section to type" src="https://github.com/user-attachments/assets/1933c3ff-215d-4410-ae16-aae8f06ffb08" />

<img width="368" height="307" alt="Step 8 Life cycle Giving all access to Sam as SysAdmin" src="https://github.com/user-attachments/assets/e2036c5c-9711-42e9-8feb-b088c7d6b1e3" />


In osTicket, we cant @ or send the ticket directly to SysAdmin, but we can simulate, Sam leaving a note, reaching out to the department by external email to request elevated permissions to his account.

<h3>3. TICKET TRIAGING AND ESCALTION SIMULATION</h3>

Logout as Sam, and log back in as the Admin user, and elevate Sam to Super Admin role. Log back in as Sam, and we'll triage the ticket as best as we can as Tier I support Agent. Update priority to Emergency, and the reason for update: <i>"Called Joann and confirmed all tellers systems have been down since lunch."</i>. Update the SLA Plan to Sev-A, as the issue is Business Critical. Update the Help Topic to Business Critical Outage and note <i>"Entire branch system is offline."</i> In response text field, explain the steps taken, and advise "Escalating and assigning ticket to SysAdmin Department after triaging." and Post Reply.  Lastly, assign the ticket to Susan Smith, transfer the ticket out of Support Department and into SysAdmin Department. 

<img width="383" height="312" alt="Step 9 Life cycle in Level 1 changing priority status" src="https://github.com/user-attachments/assets/bcb29ca4-7e24-4fc7-99da-700a932e7ff4" /><img width="370" height="302" alt="Step 10 Life cycle Level 1 put notes in the Priority" src="https://github.com/user-attachments/assets/e59d8949-a76f-482f-94ea-f1e5f2a6a38d" /><img width="317" height="336" alt="Step 11 Life cycle updating the SLA and putting in notes" src="https://github.com/user-attachments/assets/a74e6a23-64bf-4737-bfff-0cf8a2bd4d49" /><img width="304" height="307" alt="Step 12 Life cycle post reply button to escalate ticket to SysAdmin" src="https://github.com/user-attachments/assets/ed90ee19-f225-43ca-b438-50c105b8891c" />





> [!NOTE]
> Examine that Sam no longer has access to the original ticket, because of how our permissions are configured.
<img width="392" height="299" alt="Step 13 Life cycle Ticket the reassignment of depart Lev 1,2, or SysAdmin" src="https://github.com/user-attachments/assets/40bf72fd-5409-4413-9612-ece6b1ba21a9" />


<h3>4. TICKET RESOLUTION</h3>

Logout as Sam, and log back in as Susan, our SysAdmin. Review the ticket as Susan, and observe the timeline, review the actions and notes given by Joann and Sam. 

<img width="356" height="283" alt="Step 14 Life cycle Transferring Ticket to SysAdmin based on issue" src="https://github.com/user-attachments/assets/21556fa2-983b-4709-8489-25e7d23d1498" /><img width="334" height="327" alt="Step 15 Life cycle logged in as SysAdmin susan" src="https://github.com/user-attachments/assets/59d04b67-4403-4880-9214-964207dcb0b7" /><img width="325" height="395" alt="Step 16 Life cycle as SysAdmin looking at the Notes" src="https://github.com/user-attachments/assets/91461621-be1e-4850-bce0-815a52dc2ce1" />

 


In a real work environment, system outages can be caused by many different factors. For the purposes of this lab, we will assume the issue was caused by an accidental restart of the online banking system’s backend server during business hours due to a configuration issue.

Post the following message as a ticket reply:

“We accidentally restarted the online banking system’s backend server during business hours due to a configuration issue. We will review the settings and attempt to restart the service.”

<img width="372" height="387" alt="Step 17 Life cycle SysAdmin documenting fix solution in Post Reply section" src="https://github.com/user-attachments/assets/bc4ff29d-99fe-4b41-897c-75e9e165dd61" /><img width="324" height="356" alt="Step 18 Life cycle Finished Documenting Post Reply" src="https://github.com/user-attachments/assets/8d545f77-a781-4f5b-81aa-5018f281cebf" />



In this scenario, Susan restarts the server and verifies the online banking system status. Once service is confirmed to be restored, post the following update:
“Server successfully restarted. Online banking systems appear to be operational. Confirmed with Karen. Do closing ticket." Set the ticket status to Resolved. 

<img width="364" height="305" alt="Step 19 Life cycle of Ticket talk with End user and fixed issue, Ticket Resolved" src="https://github.com/user-attachments/assets/f02a779e-0c00-4f0e-a171-3d331dd6d054" /><img width="309" height="387" alt="Step 28 Life cycle Tickect verified with Joann Adobe up and running" src="https://github.com/user-attachments/assets/d103a079-dbf7-4c98-93c4-14e303e8104f" /><img width="309" height="387" alt="Step 28 Life cycle Tickect verified with Joann Adobe up and running" src="https://github.com/user-attachments/assets/42be1496-9cae-47f1-8561-d9d288bec3b9" />




> [!NOTE]
> In osTicket, setting a ticket’s status to Resolved automatically marks the ticket as Closed. Other ticketing systems may separate these steps, where a ticket is marked as Resolved after a fix is applied and Closed only after confirmation that no further action is required.

> 
