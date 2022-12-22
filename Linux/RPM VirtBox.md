 <h1></h1>

<h1 align=center> RPM - Fedora </h1>
<p>

This guide assumes that you have Fedora already installed, this guide will walk you through the steps to install virtual box and create an ubuntu virtual machine on a Fedora (RPM) host.
</p><br>

> <h2>Download Ubuntu 22.04 LTS </h2>
---

<p>
The next thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.

- [Ubuntu Download 22.04 LTS](https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64)

**Or** go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS" The download will begin automagically!
</p><br>


Once the download is complete you can move on

----| From Package Manager
Open the Ubuntu Software catalogue, and search for "virtual", it will be the first one, click install, and go through the installer.

If for whatever reason this is not available, you can see it from the distributor
----| From Distributor
Follow this link: "https://www.virtualbox.org/wiki/Downloads"
or head to virtualbox.org, click download

If by the time this guide is not updated, Fedora 37 is not listed, we must use the other installation till it is supported.

and then select linux distributions. Since this is arch, we will have to click on "Fedora 36 (if you have 37 you will likely need to perform the following"
After this is installed reboot and when back in, open a terminal and run "sudo /sbin/vboxconfig"

--| Issue #1 Driver cannot start
  This is either because secure boot is on, or you do not have developement headers to actually install a kernel module.
  This can be fixed by installing the headers for your device ex. with "sudo dnf install kernel-devel kernel-devel-6.0.13-300.fc37.x86_64"

If all goes well you will be able to proceed.

--| Ubuntu VM Creation
Now to the fun part, the Virtual Machine. 
run Virtual Box, if it is not already open, and click the "New *" button in the middle of the application.

Click on the bottom "Expert Mode", cause youll be an expert at this after following this guide.

If your Ubuntu ISO is not downloaded yet, youll need to wait untill it has completed before continuing :/
Once you click New, a window appears with a bunch of boxes. 
Name this whatever you like, i prefer to name it "UbUntU for Class", that way I know what its for.
Next youll need to select the ISO Image, this is the ubuntu you just downloaded, youll click the drop down, and the other
 navigate to downloads and it should be there.

After you do this some thing will update, and it will auto detect the version. 
For the Folder, feel free to put it anywhere you feel comfortable, I typically leave it as-is.
Check the box that says "Skip Unattended Install", and click on "Hardware"

------| VM Hardware
This is where we set how much power to give the VM, in our case we need 4Gb of ram, this is measured in Mega bytes,
so youll need to set it to 4096 MB.
Next we need 4 cores, now this says "CPU's" it means cores, set this to 4 and click on Hard Disk.

------| VM Storage
Now this is where we give the VM storage, we need 80 GB so either type or drag this to where it says 80GB.
Make sure that you actually have more than 80Gb, otherwise youll have performance issues, among other headaches. 
You can safely ignore the "Active Directoy" box, and click continue.

If you selected minimal install yours will likely take longer as it needs remove all the extra software prior to the install
In the next section we will fix the resolution and setup Ubuntu quickly.

Once Ubuntu is installed it will request you to restart, after which it will ask you to remove the install media and hit enter.
You can safely ignore this and hit enter.

Once it restarts youll be brought to the login screen.

At this point it will begin the installation period, provided theres no errors and you get a desktop environment,
you have successfully installed Ubuntu 22.04 to virtualbox on your computer! Yay!

--| Optimization & Fixing Resolution
At this point if youve messed around with the display at all youll notice that it is flixkering and glitchy,
we need to install drivers for the virtual display that ubuntu is using.

To do this go to the top left of the screen, click devices, and then "Insert Guest Additions CD".
After this is "inserted" it will "mount" automatically, an then will ask you to run it, run it and this will install
the required device drivers.

If this does not happen, on the left side of the screen will be a CD, click it, and it will open a folder, right click in the folder 
select "Open in terminal", this will open an terminal instance, and then run the following "./autorun.sh" 
This will run the installer for the utils needed for the VM.

After you do this and it installs, restart your VM and when it boots back up you will be able to resize the VM.

----| Settings

At this point we're only missing updates, which we can fix with the following command:
sudo apt update && sudo apt upgrade 

We need internet at this point, so make sure that in the top right you either have wifi, or see the 3 node looking icon. (Ethernet)

Then press the windows key and then type "Terminal", open terminal and run the command above.
You can also click the 9 dots on the bottom left, and click on terminal in the middle of the screen. Then run the command
above.

It will propmt for your password, and then download and install any required update

And just like that you have a working and up-to-date virtual machine running Ubuntu 22.04 LTS
