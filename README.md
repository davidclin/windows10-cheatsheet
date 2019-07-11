# Windows 10 Tips and Tricks
This is my short list of Windows 10 tips and tricks to speed performance.

# Things I do periodically
- Clean system disk space 
  <pre>
  This is especialy applicable after a Windows update
	Start --> Disk Cleanup
  Check Windows Defender action recommendations from the taskbar pulldown menu
	This includes virus scanning
  </pre>
- Run CCleaner

# Cool tricks
- Add Desktop and URL Address field to taskbar
  <pre>
  Right click --> Toolbars --> Desktop & Address
  </pre>
  
# Fix blurry text
<pre>
Start --> Type 'Performance' --> Adjust the appearance and performance of windows --> Visual Effects --> Disable everything except "Smooth edges of screen fonts
</pre>

# Speedup Chrome
Disable Chrome extensions you're not using

# Check for Harmful Software in Chrome Settings
Chrome --> Settings --> Advanced --> Reset and Cleanup --> Cleanup computer --> Find (This may take awhile)

# Speedup Taskbar
<pre>
Right click taskbar
Select Taskbar settings
Select Color
Disable Transparency effects
</pre>

# Speedup Start Menu 
<pre>
Disable Cortana from GUI and registry<br>
Regedit --> HKEY_CURRENT_USER --> Desktop --> MenuShowDelay 20  (400 is default)<br>
Task Manager --> Startup tab --> Disable all apps (especially `Windows Defender notification icon in startup`)<br>
Rebuild your index (last resort)<br>
</pre>

# Speedup Windows 10
<pre>
- Upgrade memory
- Update outdated drivers (especially the video driver)
- Run indexing troubleshooter
	Start --> Troubleshoot
	(or Settings --> Troubleshoot --> Select 'Search and Indexing' and run the troubleshooter for 'search 	
	for indexing is slowing down the computer)
- Disable remote desktop access
- Restart your computer instead of powering down (powering down uses a snapshot when powered back on)
- Disable Windows tips
	Settings --> Notifications --> Disable "Get tips, tricks, and suggestions as you use Windows
- Optimize paging
	Start --> Type 'Performance' 
	Adjust the appearance and performance of windows --> Advanced 
  	Virtual memory --> change the paging file size 
	(Select Custom size and set Initial size (MB) and Maximum size (MB) to the Recommended 
	total paging file size for all drives.
- Disable apps that launch during startup
	But keep the "Windows Defender notification icon"
- Delete programs you don't use
- Use a high performance power plan
- Disable Startup apps using CCleaner. CCleaner shows more apps, services, and scheduled tasks that get started during startup In my case, Adobe was slowing things down significantly. Your situation your differ but the idea is to disable apps and services you don't need running during Startup.
</pre>

# Command Prompt
<pre>
- Issue `prompt` to change the prompt
- Issue `title` to change the title bar
- Change the registry to autorun commnands in the command prompt window all the time; 
  this allows things like prompt and title settings to persist after closing the command prompt window
  
  Open Regedit 
  --> Computer 
  --> HKEY_CURRENT_USER 
  --> SOFTWARE
  --> Microsoft 
  --> Command Processor 
  --> [Create New String Value: Autorun] 
  --> Right-click `Autorun`
  --> Modify 
  --> [Value Data: prompt $D $B $T $B $P$G && cd desktop && title David Lin's Command Prompt]
  
- F7 will display history of commands you've entered
- [command] | clip will send output to the Clipboard
- [command 1] && [command 2] where && will run [command 2] if [command 1] succeeds
- [command 1] &  [command 2] where  & will always run [command 2]
- [command 1] || [command 2] where || will run [command 2] if [command 1] fails
- You can drag and drop files/folders into the command prompt and it will automatically type the path for you
- From file explorer, you can type `cmd` in the path field and a command prompt will open in the specified path
- You can right-click and `Mark` text then paste what was marked
- If you click the upper left corner image and select `Default`, you can change the command prompt window's default settings (e.g. font size)
- If you click the upper left corner image and select `Properties`, you can change the command prompt window's present settings
- [command] /? provides context help on command issued
</pre>

# Package Management 
Installing and Using Chocolatey (with PowerShell)
- Blog: https://jcutrer.com/windows/install-chocolatey-choco-windows10

<pre>
Start 
--> Type `powershell`
--> Right-click Windows Powershell 
--> Choose "Run as Administrator"

Paste the following:
===================================================================
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
===================================================================

--> Answer Yes if prompted
--> Close and reopen an elevated PowerShell window to start using choco

Choco is now installed and can be used from a PowerShell prompt or a regular command prompt windows to install many different software packages. Whichever one you use, just make sure you run choco from an elevated powershell/command prompt window.
</pre>

## Useful Choco commands
<pre>
choco upgrade   chocolatey
choco search    [keyword] -v
choco install   [packagename]
choco upgrade   [packagename]
choco uninstall [packagename]
choco info      [packagename]
choco list      --local-only
</pre>

## Advanced Choco commands
<pre>
choco install [packagename] --yes
choco seaerch [packagename] --exact --verbose
choco search  [packagename] --order-by-popularity
</pre>

## Other Useful Software to Install with Choco
<pre>
choco install python3 --pre     	- Python 3
choco upgrade python3 --pre     	- Python 3 upgrade
choco install -y vim            	- Vim
choco install -y chrome 		- Google Chrome Browser
choco install -y git 			– Git cli Client for Windows
choco install -y github 		– Official GUI-Based Git Client
choco install -y 7zip 			– Archive utility to compress/uncompress zip, tar, gz, bzip and other formats.
choco install -y SublimeText3 		– An execellent markdown & source code editor.
choco install -y vlc 			– An open-source media player
choco install -y putty 			– An open-source SSH client
choco install -y keepass 		– An open-source Password Manager
choco install -y greenshot 		– My favorite screenshot utility for Windows
choco install -y imagemagick.app	– A suite of cli tools for working with and converting images
</pre>

# Chocolatey Packages
[Packages](https://chocolatey.org/packages)
