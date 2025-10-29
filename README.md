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

 <h2>🔡Printer Printing Garbled or Scrambled Text🔡</h2>

Possible Causes or Root Issues: Driver issues, incorrect printer model selection, or corrupted data


<ins>Fixes:</ins> 

**1.)** Ensure you have the right printer drivers installed.

**2.)** Reinstall or update the printer drivers from the manufacturer's website.

**3.)** Verify you're sending print jobs to the correct printer in the print dialog.

**4.)** Restart the printer and the PC.

**5.)** Try printing from a different app or file to isolate the issue. 

 <h2>📄Printer paper Jams📄</h2>

Possible Causes or Root Issues: Obstructed rollers, misaligned paper, paper scraps, or poor paper quality

<ins>Fixes:</ins> 

**1.)** Power the printer off and gently remove the jammed paper from the feeder.

**2.)** Open access panels to ensure there aren't any paper scraps inside.

**3.)** Gently reseat and reload the paper properly into the tray.

**4.)** Check the rollers for dust buildup or debris and clean with a clean cloth.

**5.)** Avoid overload or overfilling the paper tray and always use the recommended paper sizing. 
