
---

<h1 align=center>Windows 10/11</h1>
<p>

This guide assumes that you have Windows 10 or 11 already installed, this guide will walk you through the steps to install Windows Subsystem for Linux and create an ubuntu virtual machine on a Windows host.
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


> <h2> Installing Ubuntu
---

Open Powershell or Command Prompt as admin.

Then type <code>wsl --install -d kali-linux</code>

And this will install Kali Linux Rolling


</p>

