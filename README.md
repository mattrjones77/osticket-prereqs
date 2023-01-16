<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure
- Virtual Machine
- osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Installation Steps</h2>

<h3>Step 1: Connect to your Virtual Machine with Remote Desktop</h3>

<p>
<img src="https://i.imgur.com/5hrj6P1.png" height="50%" width="50%" alt="Remote Desktop to VM"/>
</p>

<p>
<img src="https://i.imgur.com/QdKosPW.png" height="50%" width="50%" alt="Remote Desktop to VM"/>
</p>

- Copy and Paste the VM's Public IP Address into your Remote Desktop program (Mac users will need Microsoft Remote Desktop)
- Enter the username/password you used when creating the VM

<h3>Step 2: Install/Enable IIS in Windows WITH CGI</h3>

<p>
<img src="https://i.imgur.com/iQs1K4w.png" height="80%" width="80%" alt="Install/Enable IIS"/>
</p>

- Navigate to Control Panel -> Programs -> Turn Windows features on or off -> World Wide Web Services -> Application Development Features -> [X] CGI
- Open the Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<p>
<img src="https://i.imgur.com/gvx1EG5.png" height="80%" width="80%" alt="Installation Files"/>
</p>

<h3>Step 3: Install Additional Files</h3>

- Download & Install the following files:
  - PHP Manager for IIS
  - Rewrite Module
  - PHP 7.3.8
    - File Explorer ->
    - This PC ->
    - Windows (C:) ->
    - New Folder ->
    - Name new folder 'PHP' ->
    - Unzip 'PHP 7.3.8' into this new folder
  - VC_redist.x86.exe
  - MySQL 5.5.62
    - Typical Setup ->
    - Launch Configuration Wizard (after install) ->
    - Standard Configuration ->
    - Set password as 'Password1'

<h3>Step 4: Register PHP from within IIS</h3>

- Open IIS as an admin (right click and select 'Run as administrator' ->
- PHP Manager ->
- Register new PHP version ->
- Browse to newly created 'PHP' folder ->
- php-cgi.exe ->
- Reload IIS (Open IIS, Stop and Start the server)

<p>
<img src="https://i.imgur.com/dEPguY1.png" height="40%" width="40%" alt=""/>
</p>

<p>
<img src="https://i.imgur.com/5IMvkqq.png" height="40%" width="40%" alt=""/>
</p>

<p>
<img src="https://i.imgur.com/JwPamBr.png" height="40%" width="40%" alt=""/>
</p>

<p>
<img src="https://i.imgur.com/41zWIj9.png" height="40%" width="40%" alt=""/>
</p>

<p>
<img src="https://i.imgur.com/Ow9u7wR.png" height="40%" width="40%" alt=""/>
</p>

<h3>Step 5: Install osTicket</h3>

- Install osTicket v1.15.8
  - Download osTicket from the Installation Files Folder
  - Extract and copy "upload" folder to c:\inetpub\wwwroot
  - Within c:\inetpub\wwwroot, rename "upload" to "osTicket"

<p>
<img src="https://i.imgur.com/QyjQMA9.png" height="40%" width="40%" alt=""/>
</p>

<p>
<img src="https://i.imgur.com/yUSt3TI.png" height="40%" width="40%" alt=""/>
</p>


<p>
<img src="https://i.imgur.com/hgvj9qn.png" height="40%" width="40%" alt=""/>
</p>

- Reload IIS
- Go to sites -> Default -> osTicket 
  - On the right, click "Browse *:80"

<p>
<img src="https://i.imgur.com/lDra8Uu.png" height="40%" width="40%" alt=""/>
</p>

- Note that some extensions are not enabled
  - Go back to IIS, sites -> Default -> osTicket
  - Double-click PHP Manager
  - Click “Enable or disable an extension”
  - Enable: php_imap.dll
  - Enable: php_intl.dll
  - Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes

<p>
<img src="https://i.imgur.com/6Oj3sqA.png" height="40%" width="40%" alt=""/>
</p>








  

