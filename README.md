<p align="center">
<img src="https://i.imgur.com/npSuccP.png" height="30%" width="30%" alt="Network File"/>
</p>

<h1>Network File Permissions/Shares</h1>
In this tutorial, I will be showing how to set network file permissions and sharing it with other users. This tutorial will give you a feel for how an Information Technology (IT) administrator would grant/deny access to users in regards to certain network files and folders. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machines
- Microsoft Remote Desktop
- Windows File Explorer

<h2>Steps</h2>

<h3>Create two virtual machines</h3>
First, you need to create two virtual machines: one will be the domain controller (DC-1) and the other will be a regular client (Client-1). This lab builds off of the Active Directory lab and will be setup the same way.

<p></p>

This lab will be building off of the Active Directory lab. If you have not done that lab yet, please see it [here](https://github.com/klcarpio/How-to-Install-and-Use-Active-Directory).

<p></p>

Log into DC-1 and Client-1 using Microsoft Remote Desktop. For Client-1, log in with a user that was created from the Active Directory lab. In this example, I used user "lox.viduw". Remember the password is "Password1."

<p>
<img src="https://i.imgur.com/R4KG59g.png" height="80%" width="80%" alt="1."/>
</p>
  
<p>
<img src="https://i.imgur.com/kXMmo8Y.png" height="80%" width="80%" alt="2."/>
</p>

<p>
<img src="https://i.imgur.com/8oCU2xv.png" height="80%" width="80%" alt="3."/>
</p>

<h3>Create network folders</h3>
Next, we'll create network folders. Go to Windows File Explorer in the Start Menu. Create the following folders:

- read-access
- write-access
- no-access
- accounting

<p>
<img src="https://i.imgur.com/jWkWIEe.png" height="80%" width="80%" alt="4."/>
</p>

<p>
<img src="https://i.imgur.com/jWkWIEe.png" height="80%" width="80%" alt="5."/>
</p>

Next, we'll go into each folder, right click -> Sharing. Do the following for each folder:
- read-access -> Add Domain Users -> Read Permissions
- write-access -> Add Domain Users -> Read/Write Permissions
- no-access -> Add Domain Admins -> Read/Write Permissions

<p></p>

Leave the accounting folder alone for now.

<p>
<img src="https://i.imgur.com/Iq3qb36.png" height="80%" width="80%" alt="6."/>
</p>

<p>
<img src="https://i.imgur.com/XpqSaoa.png" height="80%" width="80%" alt="7."/>
</p>

<p>
<img src="https://i.imgur.com/mpyCZiS.png" height="80%" width="80%" alt="8."/>
</p>

<p>
<img src="https://i.imgur.com/wR1tewS.png" height="80%" width="80%" alt="9."/>
</p>

<p>
<img src="https://i.imgur.com/VLD2O6h.png" height="80%" width="80%" alt="10."/>
</p>

<h3>Using Client-1 to access network folders</h3>
Next, go into Client-1. Go into Windows File Explorer and type in "\\dc-1". From here, try to access the folders and watch the results for each one. 

<p>
<img src="https://i.imgur.com/uTYL4VQ.png" height="80%" width="80%" alt="11."/>
</p>

<p>
<img src="https://i.imgur.com/lPUhMm5.png" height="80%" width="80%" alt="12."/>
</p>

<p>
<img src="https://i.imgur.com/P02Lx4V.png" height="80%" width="80%" alt="13."/>
</p>

<p>
<img src="https://i.imgur.com/oe4zyHA.png" height="80%" width="80%" alt="14."/>
</p>

<p>
<img src="https://i.imgur.com/AuxDhft.png" height="80%" width="80%" alt="15."/>
</p>

<h3>Create a new group in Active Directory</h3>
Go back into DC-1 and open Active Directory Users and Computers. Then go into the following: mydomain.com (domain that was created) -> _SECURITYGROUPS -> right click in the main window -> New -> Group. Then add "ACCOUNTANTS." Right click "ACCOUNTANTS" -> Properties -> Members -> add lox.viduw (or the account you have created).

<p></p>
Next go back into Windows File Explorer. Go accounting folder -> right click -> Properties -> Sharing -> Add ACCOUNTANTS -> Read/Write Permissions.

<p>
<img src="https://i.imgur.com/qtBkjIO.png" height="80%" width="80%" alt="16."/>
</p>

<p>
<img src="https://i.imgur.com/Qxd7YaC.png" height="80%" width="80%" alt="17."/>
</p>

<p>
<img src="https://i.imgur.com/kBIBepR.png" height="80%" width="80%" alt="19."/>
</p>

<p>
<img src="https://i.imgur.com/hCKGOWw.png" height="80%" width="80%" alt="20."/>
</p>

Once this is all completed, go back into Client-1. Then attempt go into the accounting folder and you should be able to.

<p>
<img src="https://i.imgur.com/nlEPa0z.png" height="80%" width="80%" alt="21."/>
</p>

<p>
<img src="https://i.imgur.com/kal6vzc.png" height="80%" width="80%" alt="22."/>
</p>

After doing this exercise, you should have some intuition on how to create network files and set the permissions. Thank you checking out my tutorial! 


**REMEMBER TO DELETE YOUR RESOURCES ONCE YOU ARE DONE WITH THE LAB!**
