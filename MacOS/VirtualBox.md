

<h1></h1>

<h1 align=center> VirtualBox - Mac </h1>
<p>
For this guide we feature only from the distributor.
</p>


> <h2>Download Ubuntu 22.04 LTS </h2>

---

<p>
The next thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.

- [Ubuntu Download 22.04 LTS](https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64)

**Or** go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS" The download will begin automagically!
</p><br>


> <h2>Download Virtual Box</h2>
---

You can download it here:
- [Virtual Box Download](https://download.virtualbox.org/virtualbox/7.0.4/VirtualBox-7.0.4-154605-OSX.dmg)

or 
1. Go to virtualbox.org 
2. Go to download page, selecting "macOS /Intel hosts"

This will download a .dmg file for installation.

> <h2>Install Virtual Box</h2>
---

Once you have the installer downloaded, double click it to begin the installation.

It will propt you for administrative access, allow it. Make sure that youve given your mac permissions to install, otherwise this might not install properly.

To grant permission
1. Click the magnifying glass at the top right
2. Type “Security”

Alternatively

1. you can click Applications > System Preferences > Security and Privacy. 
2. Near the bottom of the General tab, from Oracle America, Inc.
3. Click “Allow,” and then reinstall.

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



