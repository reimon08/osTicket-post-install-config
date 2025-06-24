
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

- 🌐 Acknowledge Agent Panel vs Admin Panel
- 🔧 Configured Roles - Create roles to manage permissions.
- 🏢 Set Up Departments - Create departments to control ticket visibility.
- 👥 Create Teams - Built cross-department teams to group agents from multiple departments.
- 🛂 Allowed Unregistered Users to Submit Tickets - Modify user settings to allow end users to create tickets without prior registration.
- 👩‍💼 Add Agents - Add workers for (SysAdmins) and (Support) to handle tickets.
- 👨‍💻 Add End Users (Customers) - Added test users to simulate ticket creation.
- ⏱ Configure SLA Policies - Set different SLA levels with varying grace periods and schedules.
- 📝 Set Up Help Topics - Created topics for better ticket categorization.
  






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

<h4>Configure Roles (for grouping permissions) 
- Create "Supreme Admin"
</h4>

<p>So I go to Admin Panel → Agents → Roles, and then I create a new role called Supreme Admin and give it full permissions on everything. </p>



https://github.com/user-attachments/assets/c38b789c-9ff0-4fd4-a36d-fef4780386ca

<h4>Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)
- Create "SysAdmins"
</h4>

<p>Next up, I’m gonna configure Departments — this controls ticket visibility. For example, if a ticket comes in for Networking, only the networking team should be able to see and work on that ticket. This way, tickets are only visible to the right departments, like Help Desk, SysAdmins, or Networking, depending on who it’s assigned to. For this im creating Sysadmins with full access to everything.

So I go to Admin Panel → Agents → Departments to create SysAdmins.


</p>



https://github.com/user-attachments/assets/7117b802-c2f1-4ad0-9b48-bcab072fce91

<h4>Configure Teams(Pull Agents from different Departments)
-Create "Online banking"
</h4>

<p>Now we’re gonna configure Teams. We’re doing this so you can pull agents from different departments into one team. Like, let’s say you work at a bank and you want an Online Banking Team, you’d want that team to include a SysAdmin who’s responsible for the system, plus some people from the Help Desk who handle banking-related tickets. So basically, you’re building a team made up of people from different departments who work together on specific types of issues.</p>

<p>I go to Admin Panel → Agents → Teams and then create an online banking team./p>



https://github.com/user-attachments/assets/784dbc41-989b-4311-9dfc-652c56c5307c

<h4>Allow anyone to create tickets
</h4>

<p>Now we’re gonna allow end users to create tickets even if they haven’t registered yet. This option is usually unchecked by default, but we’re gonna make sure it’s disabled so anyone can submit a ticket without having to sign up first.

Admin Panel -> Settings -> Users -> (UNCHECK- Registration Required: Require registration and login to create tickets)
</p>


https://github.com/user-attachments/assets/11c2dbab-5f1f-4696-a19a-4e3979b5003d

<h4>Configure Agents (workers)</h4>

<p>Now we’re gonna configure Agents, which are basically the actual workers who’ll be handling the tickets.<p/>

<h4>We are going to create two agents</h4>

<p>
jane (Dept: Sysadmins, Role: Supreme Admin) username: jane| password: Password1<p/>                                      

<p>I also added Jane to the Online banking team</p>  



https://github.com/user-attachments/assets/514b90f2-49d8-4984-ac44-d21dfd3de79d



<p>john (Dept: Support, Role: View only) username: john | password: Password1<p/>



https://github.com/user-attachments/assets/45de64d6-8ca5-4ef0-a0b4-bb2fb82e13d3

<h4>Configure Users (customers)</h4>

<p>We’re gonna assign one end user named Karen, this will be the account we’ll use to create trouble tickets for testing. We are also gonna give her an email address.</p>

<p>Agent Panel -> Users -> Add New</p>



https://github.com/user-attachments/assets/8306ed6c-5c5c-48e8-bdf3-b656d83d484a


<h4>Configure SLA</h4>

<p>So now I'm going to configure the SLA, SLA is a time frame where you have to finish a specific task. It sets a deadline for how long you have to respond to or resolve a ticket. </p>

<p>We're gonna create three different SLA.</p>

<h4>Sev-A (Grace Period: 1 hour, Schedule: 24/7) - Critical problem</h4>
<h4>Sev-B (Grace Period: 4 hours, Schedule: 24/7) - High problem</h4>
<h4>Sev-C (Grace Period: 8 hours, Business Hours) - Medium or low problem</h4>

<p>So the grace period is basically a buffer that gives you time to respond before the SLA timer kicks back in after a new update on the ticket.</p>

<p>So for critical tickets, I’d keep the grace period low because you wanna start the SLA timer right away and stay on top of it. But for less important tickets, you can afford to give yourself a longer grace period since it’s not as urgent.</p>

<p>To configure go, Admin Panel -> Manage -> SLA</p>



https://github.com/user-attachments/assets/60686ebd-7169-45e2-9e74-72c53793be5b

<h4>Configure Help Topics (For when users create a ticket)</h4>

<p>So now we’re gonna configure Help Topics. You can kinda think of it like a category, when an end user is creating a ticket, they can pick which topic it falls under. As a help desk worker, you can also change the topic later if it needs to be updated or moved to a different category.</p>

<p>We're going to create these help topics:</p>

<h4>-Business Critical Outage</h4>
<h4>-Personal Computer Issues</h4>
<h4>-Equipment Request</h4>
<h4>-Password Reset</h4>
<h4>-Other</h4>


<p>To configure, Admin Panel -> Manage -> Help Topics</p>



https://github.com/user-attachments/assets/022c83fa-0b5e-4a8f-adef-0de36cc5ca37


<p>So we’ve done all the configuration to get osTicket fully set up and ready to go. We installed the system, set up roles, departments, teams, agents, users, SLAs, and help topics, basically building out a full help desk environment. Now we’ve got a system where end users can submit tickets, agents can work on them, and admins can manage everything behind the scenes. This setup provides a clear view of how a real-life help desk operates and how different roles interact with tickets based on their respective responsibilities.
</p>

<h4>I hope this tutorial was helpful, and hopefully there were no mistakes along the way! 😄.</h4>

































