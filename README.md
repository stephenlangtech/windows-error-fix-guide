<h1>Common Windows Error Guides</h1>
<p align="center">
<img src="https://www.securedatarecovery.com/Media/blog/2024/blue-screen-of-death-laptop.webp" alt="How To Fix a Blue Screen of Death (BSOD) on Windows PC"/>
</p>

This repository serves as a quick reference point to resolve common Windows errors and performance issues. Each section will outline key symptoms, possible causes, and troubleshooting steps used by IT professionals to resolve them.

<h2>🥾Windows Failing to Boot or Stuck🥾</h2>  

***Symptoms:*** Windows restarts repeatedly, displays a message stating **"Automatic Repair couldn't Repair your PC"**, or it gets stuck at the Windows Logo Screen.    

***Possible Causes or Root Issues:*** Corrupted system files, bad updates, bad drivers, or boot configuration errors.


<ins>Fixes:</ins> 

**1.)** Hold `Shift+Click` **Restart->Troubleshoot->Advanced Startup Options->Startup Repair**.

**2.)** If the previous step fails, open up the **Command Prompt** and run the following commands:

```bash
bootrec /fixmbr  
bootrec /fixboot  
bootrec /scanos  
bootrec /rebuildbcd
```

**3.)** Next, run a **System File Check**: 

```bash
sfc /scannow
```
**4.)** If issues still persists, boot into **Safe Mode** and unistall recent updates, software, or bad drivers and perform a **System Restore** and restore to the lastest **Restore Point**. 

**5.)** As a last resort, backup all of your files and perform a clean install.

<h2>🟦Blue Screen of Death (BSOD)🟦</h2>  

***Symptoms:*** Blue Screen errors with codes such as `MEMORY_MANAGEMENT`, `SYSTEM_SERVICE_EXCEPTION`, or `CRITICAL_PROCESS_DIED`.

***Possible Causes or Root Issues:*** Faulty drivers, hardware failure, or corrupted memory.  

<ins>Fixes:</ins> 

**1.)** Boot into **Safe Mode**.  

**2.)** Run the **Windows Diagnostic Tool**. `Windows+R` and type `mdsched.exe`->**Restart now** and check for problems, and run the test.

**3.)** Update or rollback the drivers in **Device Manager**

**4.)** Check for more malware or run the command in **Command Prompt** 
```bash
chkdsk /r chkdsk /f
```


**5.)** Also, try to run the command to repair corrupted Windows system files.
```bash
sfc /scannow
```

<h2>📉Slow Performance or 100% Disk Usage📉</h2>  

***Symptoms:*** System running extremely slow, taking a long time to boot, fans running loudly, disk usage stays at 100% in **Task Manager** 

***Possible Causes or Root Issues:*** Too many apps and programs up at once, Background services, **Windows Search Indexing**, or disk health issues.


<ins>Fixes:</ins> 

**1.)** Restart the system and check **Task Manager**. `Ctrl+Shift+Esc`->select the **Processes** tab-> single out which apps are using high disk, CPU, or memory and end the tasks. 

**2.)** Disable Unecessary **Startup Apps**. Press `Ctrl+Shift+Esc` -> select the **Startup** tab->right-click and disable apps that are eating up too many resources and that don't need to be automatically running. 

**3.)** Check the **Disk Health** by running the commands in **Command Prompt**
```bash
chkdsk /f
chkdsk /r
```
This scans for and repairs bad sectors on the drive that can cause performance slowdowns.

**4.)** If you're running on **HDD**, upgrade to **SSD** to boost and improve performance. 

 <h2>🖥️Windows Update Failures🖥️</h2>

 ***Symptoms:*** Update fails to install, error codes `0x80070002` or `0x800f081f` 

Possible Causes or Root Issues: Corrupted update cache or broken Windows components.


<ins>Fixes:</ins> 

**1.)** Run **Windows Update Troubleshooter** by going to **Start->Settings->Update & Security->Troubleshoot->Additional Troubleshooters->Windows Update-> Run Troubleshooter**

**2.)** Stop update services by running these two commands:
```bash
net stop wuauserv
net stop bits
```
`net stop wuauserv` - This command stops the **Windows Update Service**, which is responsible for verifying, downloading, and installing Windows updates.  

`net stop bits` - This stops the **Background Intelligent Transfer Service (BITS)**. **BITS** manages background downloads, including Windows updates.

**3.)** Delete the update cache folder: 
```bash
C:\Windows\SoftwareDistribution
```

**4.)** Now restart the services by running the following commands in **Command Prompt**
```bash
net start wuauserv
net start bits
```

**5.)** Lastly, reboot and retry updating Windows. 

 <h2>📶Wi-Fi or Network Connectivity Issues📶</h2>  

***Symptoms:*** **Wi-fi** appears to be connected, but no internet, or **DNS** errors occur.

***Possible Causes or Root Issues:*** **Network adapter** issues or **DNS** misconfigurations.
<ins>Fixes:</ins> 

**1.)** Run the **Network Troubleshooter** by heading to **Settings->Network & internet->Status->Network Troubleshooter**.

**2.)** Reset the networ settings in **Command Prompt**:
```bash
ipconfig /release
ipconfig /renew
ipconfig /flushdns
```

**3.)** Update or reinstall network drivers in **Device Manager**

**4.)** Switch DNS to Google's public DNS
`8.8.8.8` and `8.8.8.4` 

**5.)** **Reset** router or **Power Off** router and wait 30 secondsbefore powering it back on. 
