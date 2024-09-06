<h1>Remote Administration Methods(IN PROGRESS)</h1>

<br />
<h2>Description</h2>
Text

<h2>Utilities Used</h2>

- <b>Remote Desktop</b> 
- <b>Active Directory Users and Computers</b>

<h2>Environments Used </h2>

- </b>Windows Sever 2022 through Oracle Virtual Box</b>
- </b>Windows 10 Pro</b>

<h2>Lab Overview:</h2>

<p align="center">
The first and most obvious method of remote support is to use one of the native tools to Windows machines, Remote Desktop (RDP). This was set to off to default on john (the user/client machine). It had the message "Sign in as an administrator to change this setting", yet it did have the pop-up windows for me to input my admin credentials so I literally had to log of john smith, log in helpdesk, change the setting, then log back in as john. Maybe their was an easier way that I am not aware of. I started up the Lab-Desktop-1, (helpdesk's machine), and tried to RDP into john's computer with the domain name "Desktop2" rather than the IP address of 10.1.10.4 and it suprisingly worked. <br/>
<img src="https://github.com/user-attachments/assets/ec134ca9-bbea-4782-8c07-1d218f68fc23" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/c1216232-0c18-487e-8365-4c8a43a9d4a9" alt="Remote Methods"/>
  <img src="https://github.com/user-attachments/assets/906065b4-f0e9-450e-8e1e-22db7cac63cc" alt="Remote Methods"/>
   <img src="https://github.com/user-attachments/assets/afbbbd17-1a74-4211-bfe9-202f7af07fc2" alt="Remote Methods"/>
<br />
<br />
Another mode of remote administration can be done through registry editor. As helpdesk, I opened regedit, and under file I the option, "Conenct Network Registry", allows for remote connection to other domain user's registry. I input Desktop2 or john's computer and got an error message stating that remote administration needs to be enabled on this computer, and that both computers need be running remote registry service. After configuring the propert settings on each computer, and trying again, I was able to successfully see and edit Desktop2 registry from Lab-Desktop-2 remotely.<br/>
<img src="https://github.com/user-attachments/assets/dc93ea58-db10-4f1d-892d-823a911eed3c" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/29364794-3d21-489c-85d2-cd5755801e6a" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/40098ad1-6b28-437d-b917-e09cd451b7fe" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/bc9a3bba-1ffb-448a-bf30-0f228a78a26f" alt="Remote Methods"/>
<br />
<br />
A simple, but seemingly very powerful option that I was not aware of, is being able to see (AND EDIT) the entire file system of Desktop2 through file explorer while on Lab-Desktop-2 logged in as helpdesk that has administrator rights. Similar to mapping access a shared drive, but in file explorer, I input "\\Desktop2\c$" and it brings me to the C:\ drive of Desktop 2 from Lab-Desktop-1.<br/>
<img src="https://github.com/user-attachments/assets/1fe179fb-66f0-4444-acd7-b1286f22f679" alt="Remote Methods"/>
<br />
<br />
Another native Windows remote assistance tool is Windows Remote Assitance, which I created an invitation on john's computer (Desktop2), saved it to my desktop, and from helpdesk on Lab-Desktop-2, I used the trick, to access john's file ssytem go to his desktop and open the invitation from there. This opened a windows for john revealing a password and a password field for helpdesk. After inputting the password on the helpdesk Pc, john is given one last prompt to allow helpdesk to view the screen of john. After clicking yes, helpdesk can now see the screen of john and if helpdesk requests access, and john accepts, helpdesk can freely use the computer as if they were there moving the mouse.<br/>
<img src="https://github.com/user-attachments/assets/f9d6eeb3-1bec-48a1-97cf-d5c851d8035c" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/0bf15699-ff6b-4a6f-94fa-1625d650c8e9" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/8bed95d0-60f0-48e1-82ac-ee853b558ba0" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/542de3a9-cce5-4358-a686-b2968a69c6eb" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/7bc54043-7553-4e64-87fb-fcdf73753012" alt="Remote Methods"/>
<br />
<br />
Within Virtual I installed guest additions which allowed me to mount a drive that I share with my host computer which allows me in this case to download applications from the internet and drop them into the folder that my VM is connected to so I can keep the Windows Server on the private domain network. I first installed Deploy by PDQ and moved it into the the mounted folder ADLab. Seeing that I could access the folder and see the application in it proves I was successful.<br/>
<img src="https://github.com/user-attachments/assets/63773f46-c452-4027-9bbb-df76bc5130e5" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/7c74e0e3-7093-4b91-af18-6726ef5b8bc2" alt="Remote Methods"/>
<br />
<br />
PDQ Deploy allows for administrators to remotely download applications and packages on users' machines without them knowing or disrupting their work flow making it a very useful tool. Due to me having the free version many of the features were nto availible but I was still able to successfully remotely deploy PDFsam Basic from the Windows Server to Desktop2.<br/>
<img src="https://github.com/user-attachments/assets/b28291fc-7cd5-424f-804e-7ae5bab0c87e" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/6571b946-12b3-49b2-b63c-26abe2fa02c5" alt="Remote Methods"/>
 <img src="https://github.com/user-attachments/assets/1d0f9c58-d613-4c1c-86c5-2c8f26c0cbf8" alt="Remote Methods"/>
<br />
<br />
Text<br/>
<img src="" alt="Remote Methods"/>
<br />
<br />
Text<br/>
<img src="" alt="Remote Methods"/>
<br />
<br />
Text<br/>
<img src="" alt="Remote Methods"/>
<br />
<br />
Text<br/>
<img src="" alt="Remote Methods"/>
<br />
<br />
Text<br/>
<img src="" alt="Remote Methods"/>
<br />
<br />


<h2>Thoughts</h2>
text
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
