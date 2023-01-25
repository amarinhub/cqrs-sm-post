Url : https://www.udemy.com/course/net-microservices-cqrs-event-sourcing-with-kafka

#Docker

How to install WSL2:
https://cloudbytes.dev/snippets/how-to-install-wsl2-on-windows-1011

Installing WSL2 on Windows 10/11 (The hard way)
If you're running Windows 10 version 1903 or lower (Build 18362 and below), you will need to install WSL2 manually.

Step 1: Enable Windows Subsystem for Linux (WSL)
Open the Windows Terminal or Powershell, and type the following command to enable WSL:

	dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Step 2: Enable Windows Virtual Machine Platform
In the Windows Terminal or Powershell, type the following command to enable Windows Virtual Machine Platform:

	dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

Step 3: Update the Linux kernel to the latest version
This requires you to download the WSL2 Linux kernel update MSI package, 
choose the appropriate version from below, and install it. 
	WSL2 Linux kernel update MSI package for x64 systems 2 
	("https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi") 


Step 4: Set WSL2 as the default version
Installing WSL2 in Step #3 doesn't change the default version of WSL from 1 to 2. To change the default version of WSL, you must run the following command in terminal or powershell:

	wsl --set-default-version 2

#Projects docker commands
	PS C:\Users\adria> docker network create --attachable -d bridge mydockernetwork
	7a1670dc5aac1dbe42440966ef5e1821d34d5122cf2136704b15cbdd12176b01
	PS C:\Users\adria> docker network ls
	NETWORK ID     NAME              DRIVER    SCOPE
	85e3a9917f7d   bridge            bridge    local
	885cc7e58a45   host              host      local
	7a1670dc5aac   mydockernetwork   bridge    local
	9c04234603ee   none              null      local
	PS C:\Users\adria>