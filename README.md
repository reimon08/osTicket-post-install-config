
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket. If you haven't done the pre-installation, go ahead and do that first.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>Post-Install Configuration Objectives</h2>

- osTicket: Installation
- Setting up a VM in Azure

<h2>Configuration Steps</h2>

<b>So there are two URLs that we’re mainly gonna use, one is for the admin/analyst side, where we manage and work on tickets, and the other is for the end user, where they can submit tickets and check their status.</b>

<h4>Admin/analyst page</h4>

<p>http://localhost/osTicket/scp/login.php</p>

![Screenshot 2025-06-23 at 9 24 48 AM](https://github.com/user-attachments/assets/4208c80d-d359-4b99-b575-d9f450ccc6f5)


<p>After logging in.</p>

<img width="800" alt="Screenshot 2025-06-23 at 9 25 21 AM" src="https://github.com/user-attachments/assets/fa461926-40ae-472c-92ac-1633409fecc3" />

<h4>End-user page</h4>

<p>http://localhost/osTicket</p>

<img width="800" alt="Screenshot 2025-06-23 at 9 25 32 AM" src="https://github.com/user-attachments/assets/ef3143a1-91c3-4f02-a321-92be8b2e6137" />


<h4>Acknowledge Agent Panel vs Admin Panel
</h4>

<p>So this is for the sys admin, where you configure all the settings on the back end, like departments, email settings, and user permissions.

<p/>
  
<img width="800" alt="Screenshot 2025-06-23 at 9 39 47 AM" src="https://github.com/user-attachments/assets/39b94e5b-7aa3-4e52-b8d8-a7556b2e7daf" />

<p>And then there’s the agent panel, which is for the help desk workers who actually work on the tickets, assigning them, responding to users, and resolving issues.</p>

<h4>As you can see, the options on each panel are different; that’s how you can tell which one you’re using, whether you’re in the admin side or the agent side.</h4>

<img width="800" alt="Screenshot 2025-06-23 at 9 45 08 AM" src="https://github.com/user-attachments/assets/8c60e779-dba5-46ca-b3ba-c4a5a55aa82a" />

<h4>Configure Roles (for grouping permissions) </h4>

<p>So I go to Admin Panel → Agents → Roles, and then I create a new role called Supreme Admin and give it full permissions on everything. </p>



https://github.com/user-attachments/assets/c38b789c-9ff0-4fd4-a36d-fef4780386ca

<h4>Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)
</h4>

<p>Next up, I’m gonna configure Departments — this controls ticket visibility. For example, if a ticket comes in for Networking, only the networking team should be able to see and work on that ticket. This way, tickets are only visible to the right departments, like Help Desk, SysAdmins, or Networking, depending on who it’s assigned to.

So I go to Admin Panel → Agents → Departments to start setting up the different departments.


</p>


















