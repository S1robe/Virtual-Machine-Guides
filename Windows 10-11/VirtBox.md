
---

<h1 align=center>Windows 10/11</h1>
<p>

This guide assumes that you have Windows 10 or 11 already installed, this guide will walk you through the steps to install virtual box and create an ubuntu virtual machine on a Windows host.
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


> <h2>Download Ubuntu 22.04 LTS </h2>
---

<p>
The first thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.

- [Ubuntu Download 22.04 LTS](https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64)

**Or** go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS" The download will begin automagically!
</p><br>

> <h2>Download Virtual Box</h2>
---

Start off by visiting this link: 
- [Virtualbox Download](https://download.virtualbox.org/virtualbox/7.0.4/VirtualBox-7.0.4-154605-Win.exe)

Or head to virtualbox.org, following their download page and selecting "Windows Host"

> <h2>Configure & Install Virtual Box</h2>
---

<p>
If you dont know what you are doing just click next, and accept the install.

You can modify the components it includes with the install as you want, but **LEAVE NETWORKING**.

This will be needed to allow the virtual machine access to the internet.
The USB support enables the virtual machine to use USB's you plug into your device.

Python support will include some libraries and potentially Python if you dont have it installed already.

Click finish to complete the install.
</p><br>

><h2> Ubuntu VM Creation</h2>

---

<p>
Now to the fun part, the Virtual Machine. <br>
Click the <code>New *</code> button in the middle of the application.

Click <code>"Expert Mode"</code>, cause youll be an expert at this after following this guide.
 
Next youll need to select the ISO Image, this is the ubuntu you just downloaded.
Check the box that says <code>Skip Unattended Install</code>, and click on <code>Hardware</code>
</p><br>

> <h2>VM Hardware (4GB Ram + 4 Cores)
---

<p>
This is where we set how much power to give the VM, in our case we need <code>4GB RAM</code>, this is measured in Mega Bytes, so youll need to set it to <code>4096 MB</code>.
Set <code>"CPU"</code> to 4 and click on Hard Disk.
</p><br>

> <h2> VM Storage (80GB + .vmdk)
---

<p>
We need 80 GB for this Virtual Machine.

<u>Make sure that you actually have more than 80Gb</u>, otherwise youll have performance issues, among other headaches. 

For the <code>"File type and Variant"</code> select <u>VMDK (Virtual Machine Disk)</u>, This is the fastest of the three formats currently. You can either pre-allocate, or allocate as you use the disk, either is acceptable.

Click finish.
</p><br>

> <h2> Install
---

<p>
Youll be back on the first screen we started at. Click on Ubuntu, if not already selected, and click "Start".

When there is text on screen select > <code>Try or Install Ubuntu</code>

Select > <code>Install Ubuntu</code> 

I suggest using a Minimal install. Then click install now.

It will ask again to confirm, click continue.

Select your closest time zone, name your user, and the computer whatever you like. 
As a security advocate id suggest you pick a strong password, and require it upon login. 
You can safely ignore the "Active Directoy" box, and click continue.

If you selected minimal install yours will likely take longer as it needs remove all the extra software prior to the install
In the next section we will fix the resolution and setup Ubuntu quickly.

Once Ubuntu is installed it will request you to restart, after which it will ask you to remove the install media and hit enter.
You can safely ignore this and hit enter.

Once it restarts youll be brought to the login screen.

At this point it will begin the installation period, provided theres no errors and you get a desktop environment,
you have successfully installed Ubuntu 22.04 to virtualbox on your computer! Yay!
</p>
<br>


> <h2>Optimization & Fixing Resolution
---

<p>
At this point we need to install drivers for the virtual display that ubuntu is using.

To do this go to the top left of the screen, click devices, and then "Insert Guest Additions CD".
After this is "inserted" it will "mount" automatically, an then will ask you to run it, run it and this will install
the required device drivers.

If this does not happen, on the left side of the screen will be a CD, click it, and it will open a folder, right click in the folder 
select "Open in terminal", this will open an terminal instance, and then run the following "./autorun.sh" 
This will run the installer for the utils needed for the VM.

After you do this and it installs, restart your VM and when it boots back up you will be able to resize the VM.
</p><br>


> <h2>Settings
---

<p>
At this point we're only missing updates, which we can fix with the following command:

```sudo apt update && sudo apt upgrade ```

Make sure that in the top right you either have wifi, or see the 3 node looking icon. (Ethernet)

Then press the windows key and then type "Terminal", open terminal and run the command above.
You can also click the 9 dots on the bottom left, and click on terminal in the middle of the screen. Then run the command
above.

It will propmt for your password, and then download and install any required update

And just like that you have a working and up-to-date virtual machine running Ubuntu 22.04 LTS
</p>