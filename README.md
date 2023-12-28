<p align="center">
<img src="https://i.imgur.com/wMEyTiC.png" alt="osTicket logo"/>
</p>

<h1 align="center">Post-Install Configuration</h1>

Here I outline the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems</h2>

- Windows 10</b> (22H2)

<h2>Post-Installation Objectives</h2>

- Configure Roles and Departments
- Configure Teams and allow anyone to create tickets
- Now we will configure agents/workers and user/customers
- Configure SLA
- Configure Help Topics

<h2>Prerequisites</h2>

- _This walkthrough assumes that you went through the <a href="https://github.com/Emq17/osTicket-Prerequisites-and-Installation/tree/main">"Prerequisites and Installation"</a> demonstration to successfully install osTicket_

<h1>Configuration Steps</h1>

# Admin Panel

> **Note***
>**Admin vs Agent:** *The Admin panel is used by the Administrator of the osTicketing System carrying out tasks like setting up the tickets, defining roles & SLA's, and general administrative duties (ex. Sys Admins) whereas Agent is used by the Workers (Helpdesk Professionals) who actually uses the platform instead of setting things up and solving user problems.*

<h3>Creating Roles</h3>

>**Note***
>*"Roles are the permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to. An unlimited number of roles can be created and assigned to Agents with access to various departments."* - [osTicket Documentation ](https://docs.osticket.com/en/latest/Admin/Agents/Roles.html)

- So right now we are on the `Agent` panel because we can see it give us the option to switch to `Admin` on the top right of your screen

![Screen Shot 2023-12-27 at 2 51 38 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/b1a40ba4-72dd-4a62-ac8e-0fe3b03d2daa)

- Click `Admin` 
- Double Click `Agents` 

![Screen Shot 2023-12-27 at 3 16 33 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/925df49a-14a3-47ee-9f75-a8d425ef50bd)

- And then `Roles`

![Screen Shot 2023-12-27 at 3 19 22 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/054aa932-2f82-47ce-8af4-5878b8a7be0f)

- Find `Add New Role`
- Name it "Supreme Admin"
- Click on `Permissions` and check every single box ("Assign", "Close", "Create", etc). Use `tab` and `spacebar`

![Screen Shot 2023-12-27 at 3 23 16 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/32e4d098-b3ff-45b6-bb4c-2cbd003a2a7e)

- Click on `Tasks` and `Knowledgebase` and do the same
- Click on `Add Role` 

![Screen Shot 2023-12-27 at 3 23 59 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/4305978c-886d-4b99-8d78-8587be9221e7)

![Screen Shot 2023-12-27 at 3 24 18 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/9b162427-beaf-4c46-a913-b12ef9502bca)

> **Note***
>This role should now have all permissions over the Ticketing System

---

<h3>Creating Departments</h3>

>**Note***
>*Departments are just the collection of Agents in a department.* 

- Click `Departments` to the right of `Roles`
- Click `Add New Department`

![Screen Shot 2023-12-27 at 3 30 03 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/b10286f7-5232-4a60-b28d-000a21957293)

- Create a Department called "System Administrators" with its default settings

![Screen Shot 2023-12-27 at 5 21 13 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/e865b3d6-5505-4adb-8a3b-fb5522c08fe8)

<h3>Creating Teams</h3>

>**Note***
>*Having Agents from different Departments assigned to a Team will supersede the parameters of the Agents’ Department rules. For example, you can create a Help Topic associated with a particular product you produce, and assign it to a Team of specialist Agents from different Departments.*

- Inside the `Admin Panel`
- Click on `Agents`
- Click on `Teams`
- Click on `Add New Team`

![Screen Shot 2023-12-27 at 5 28 02 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/175235cb-76c7-4f78-bde2-086151f7d1fe)

- Create a Team called **Level II Support**
- Add yourself as a member to the team under `Members`
- Click on `Create Team`

![Screen Shot 2023-12-27 at 5 35 02 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/5c1226ad-2f35-4430-9ff1-5ea6b18b1e11)

![Screen Shot 2023-12-27 at 5 35 26 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/46204f10-ec9b-46cf-8d01-2ba88af8fd15)

- Now go to `Settings`
- Click `Users`
- Make sure `Registration Required` is not checked
- Save changes

![Screen Shot 2023-12-27 at 5 39 49 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/e4eaf3d3-1cee-4571-9cc2-b908d0a73352)

<h3>Creating Agents</h3>

>**Note***
>*Agents are given access to the help desk with the intent to respond and resolve the tickets.*

- Inside the `Admin Panel`
- Click on `Agents`
- CLick on `Agent`
- Click on `Add a New Agent`
- Using the Required Credenitals **(In Bold)**
     - `First Name:` **Jane**
     - `Last Name:` **Doe**
     - `Email Address:` **janedoe@osTicket.com**
     - `Username:` **jane.doe**
     - Click on `Set Password`
     - Uncheck `Send the agent a password reset email` then use "Password1234" for password
     - Uncheck `Require password change at next login`
     - Click `Set`

![Screen Shot 2023-12-27 at 5 47 07 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/839c7ef8-c29f-421b-af6e-7b44d2caed77)

- CLick the `Access` tab:
   - Assign Jane's `Primary Department` to **System Administrators**
   - Assign Jane's `Role` to **Supreme Admin**

![Screen Shot 2023-12-27 at 5 55 47 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/cc3ec3e2-7cf4-4b25-b616-71351f5c9f1a)

 
- Underneath `Teams`tab:
    - Assign Jane to `Level II Support`
    - Click `Add`
    - Click `Create`

![Screen Shot 2023-12-27 at 5 56 50 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/89e5c107-3ff0-49ba-a113-0febe5b8569d)

- Create another Agent following the same steps, using the name **John Doe**
 - Don't forget to set password

![Screen Shot 2023-12-27 at 5 59 56 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/094e3a5d-e3ba-4972-82c2-cf65d45b91a5)

- Make John's `Primary Department`: **Support**
- Assign John's `Role`: View Only
- Underneath `Extended Access`: Support
- Click on `Create`

![Screen Shot 2023-12-27 at 6 01 53 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/4936b9ba-1edd-4c74-b096-46510cc89211)

<h3>Creating Users</h3>

>**Note***
>*Users are the individuals who submit tickets to your support team.*

- Click on the `Agent Panel`
- Navigate to `Users`
- Click `Add User` 

![Screen Shot 2023-12-27 at 6 04 15 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/e607ec23-2d23-4571-a705-add63cd243cc)

- Make the User's `Email Address`: **Karen@osticket.com**
- `Username`: **Karen Karen**
- Click `Add User`

![Screen Shot 2023-12-27 at 6 07 04 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/73953ab6-c599-4cc1-8feb-7856975dbfcf)

- Create another user, following the same steps but `Email address`: **Ken@osticket.com**
- `Username`: **Ken Ken**
- Click `Add User`

![Screen Shot 2023-12-27 at 6 08 25 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/c02811af-1bcd-4b48-947d-cee545beeb2e)

<h3>Creating SLA's</h3>

>**Note***
>*The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed.*


- Click on `Admin Panel`
- Navigate to `Manage` tab
- Click `SLA`
- Click `Add New SLA Plan`

![Screen Shot 2023-12-28 at 3 29 15 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/dffca15c-4192-4cc4-a874-2e7a199d03eb)

- Create the following plans:
  - **SEV-A**
    - Grace Period: **1 hour** *(Amount, in hours, before tickets with this SLA will become overdue if not closed in allotted time.)*
    - Schedule: **24/7**
  - **SEV-B**
     - Grace Period: **4 hours**
     - Schedule: **24/7**
  - **SEV-C**
      - Grace Period: **8 hours**
      - Schedule: **Monday - Friday: 8 a.m - 5 p.m (with U.S Holidays)**
- Click `Add Plan` for each

![Screen Shot 2023-12-28 at 3 33 15 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/2a5f7cb4-ffb5-43e0-b38a-54aaf30677fa)

![Screen Shot 2023-12-28 at 3 31 07 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/349b47fb-31b0-406a-8002-dad127bb741c)

![Screen Shot 2023-12-28 at 3 32 03 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/76052909-f7d1-4217-b6f8-2f8810d57121)

![Screen Shot 2023-12-28 at 3 32 27 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/c171277d-cbe6-4791-b6a5-098bdbaa619f)

<h3>Creating Help Topics</h3>

>**Note***
>*Help Topics will determine what Department the ticket is routed to which will determine which Agents have access to the ticket. The Help Topic also can determine other configurations of the ticket, such as the ticket’s SLA (or Service Level Agreement) and priority of a ticket, i.e. Emergency to Low.*

- Click on the `Admin Panel`
- Navigate to the `Manage` tab
- Click on `Help Topic`
- Click `Add New Help Topic`

![Screen Shot 2023-12-28 at 3 35 13 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/d8d220d3-5c38-4f5a-b2b2-0f6af8430d7e)

- Create Help Topics with the following names:
    - **Business Critical Outage**
    - **Personal Computer Issues**
    - **Equipment Request**
    - **Password Reset**
- Leave everything with default settings
- `Internal Notes` can be used, but not necessary
- Click `Add Topic`

![Screen Shot 2023-12-28 at 3 37 55 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/e0f7c732-4c39-4981-89f3-5add336ea2b2)

![Screen Shot 2023-12-28 at 3 44 47 AM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/f425077e-67f3-4f56-a648-be3f1dfb2730)

---

- Great job. You have configured everything that we needed
- We'll go ahead and wrap things up for this lab & I'll meet you on over to the next one where we will practice creating, triaging, and solving tickets.
  <h3>NEXT TUTORIAL:  <a href="https://github.com/Emq17/osTicket-Ticket-Lifecycle-Examples">"Ticket Lifecycle Examples"</a>  </h3>
