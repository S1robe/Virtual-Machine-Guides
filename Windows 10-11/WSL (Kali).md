
---

<h1 align=center>Windows 10/11</h1>
<p>

This guide assumes that you have Windows 10 or 11 already installed, this guide will walk you through the steps to install Windows Subsystem for Linux and create a Kali virtual machine on a Windows host.
</p><br>

> <h2> Enabling Intel or AMD Virtualization Support </h2>
---

<p>
For this you will need to enable virtualization support.

You can check this by opening Task Manager, and switching to the performance tab, it should say "Virtualization: Enabled"

If not,

 The settings for it can be found in your bios, typically by restarting and hitting the "F2" key during startup.  

- <h3>Intel: VT-d, VT-x, SR-IOV, Hyper-V</h3>

- <h3>AMD: AMD-V
<br>

> <h2> Installing WSL </h2>
---

<p>
First youll need to enable WSL, you can do this from features.
  Search for <code>Features</code>, click on "Turn Windows features on or off"
  Then Click again on "Turn Windows features on or off"
<br>
This will bring up a list of features, we will need to enable the following

<b>

- Hyper-V (Can be omitted if running Windows 10 Home)
- Virtual Machine Platform
- Windows Hypervisor Platform
- Windows Subsystem for Linux

</b>

Make sure these are checked, and click okay. It will request an update.
<br><br>



> <h3> Microsoft Store Installation Method
---

Open the Microsoft Store App, and search for <code>Subsystem</code>. <br>

You are looking for the Penguin icon, install it.
<br><br>



> <h3> Commandline Installation Method (Fastest)
---
Open Powershell or Command Prompt in Administrator mode (Ctrl + Shift + Enter) or "Run as Administrator"

Type the command <code>wsl --set-default-version 2</code>


This will set the default verison for all installed Linux Kernels to WSL2 (updated)

Then you will want to run <code>wsl --update</code>

This will update to include Microsoft's most recent WSLg update that will enable most if not all GUI-enabeld apps from linux to run on windows natively. Amazing!
<br><br>


> <h2> Installing Kali Linux
---

Open Powershell or Command Prompt as admin.

Then type <code>wsl --install -d kali-linux</code>

And this will install Kali Linux Rolling

After you get it installed, make sure you update:

<code>sudo apt update && sudo apt full-upgrade</code>

After this completes, youll want to install the following packages:

NOTE: if you dont need graphical support you can omit the "kali-win-kex freeglut3-dev mesa-utils" packages
 
<code>sudo apt install yasm gcc make ddd mesa-utils freeglut3-dev kali-win-kex</code>

> <h2> Setting up Win-Kex
---

Win-Kex, is Kali-linux's response to wslg. This lets you run graphical applications on Linux, on Windows.

To start run:

<code>kex start</code>

This starts the server and allows it to auto-start when kali is run

It will ask for a password, you are setting up a VNC server, so this will be the login password, and I choose to not set a view-only password

It will prompt for some Windows firewall permissions, youll need to allow these, its so that the VNC server that this talks over can talk back and forth on your computer.

Next to actually run it in my suggested mode (Seamless --sl & Sound -s)
Run: 

<code>kex --sl -s</code>

This will take a second, but after it completes you can close the terminal window and use it like a normal desktop.

Thats it!

</p>

