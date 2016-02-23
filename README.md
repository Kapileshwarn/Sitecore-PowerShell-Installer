Sitecore-PowerShell-Installer
=============================
The Sitecore-PowerShell-Installer script enables you to install Production-ready Sitecore instances from the command-line. This script supports installing Sitecore 8.0 and 8.1. If there is enough interest shown, I will consider retro-fitting it to earlier versions of Sitecore.

### Features of the Project
- Install Sitecore with or without the databases.
- Supports installing a CD, CM, or Publishing server
- Script sanity checks SQL connection, input validation, and module dependencies prior to making any changes
- Write output to the screen and to a log file.
- Fine-grained control of the application pool identity (built-in or domain account)
- Assign recommended file system permissions on web server.
- Add application pool identity to recommended local groups on web server.
- Create user mappings for login in SQL and grant execute permission.
- Install database files on any valid filesystem path or UNC share
- SQL Login used during install doesn't have to be the same account executing the script.
- Full supports MongoDB's connection string specification
- May supply a Solr base address
- Choose to use SQL as a session state server
- Many CD-hardening options

### Software Dependencies
- Web Server (IIS) Administration: https://technet.microsoft.com/en-us/library/ee790599.aspx
- SQL Server PowerShell: https://msdn.microsoft.com/en-us/library/hh245198.aspx

### Requirements
- SQL logins must exist prior to running script
- SQL login used for install must either have the sysadmin role
- The path used to install SQL files must exist and the targetted SQL instance must have FullControl
- Must have a valid Sitecore .zip file

### How To Use
1. Download script, config file, and .zip for desired Sitecore version
2. Edit config file
3. Run Powershell as Administrator and invoke ```.\install.ps1```

### Troubleshooting
- If you see an error in PowerShell complaining that "the execution of scripts is disabled on this system." then you need to invoke ```Set-ExecutionPolicy -ExecutionPolicy unrestricted -Force```
- If you receive a security warning after invoking ```.\install.ps1``` and want to make it go away permanently, then right-click on the install.ps1 file and "Unblock" it.

This script was inspired by Alex Shyba's script: https://github.com/Sitecore/PowerShell-Script-Library
