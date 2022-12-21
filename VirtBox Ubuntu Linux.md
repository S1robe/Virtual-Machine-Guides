<h3>It is important to note before we begin that results will vary between flavours or distributions of linux.</h3>
<h4>This guide will cater to 3 types, Debian (Ubuntu), Arch (Manjaro), RPM (Fedora): 
You should match your distro to one of these three types (Debian, Arch, RPM), not necessarily one of the 3 flavours (Ubuntu, Manjaro, Fedora)</h4>

<h5>If you are not using one of these types or distributions, your package manager may include virtual box, this is generally up to date
and stable. However, if it is not listed then you will have to check on the creator's page for either source or an installation.

The installation is typically the same across any distribution with maybe Gentoo based being the odd one out, however the general form:
Package Manager, Source, Original Creator, should have a supported version.

Like mentioned before we will go through the main 3, beginning with Debian, Ubuntu

You should follow and only need to follow one.
</h5>

## (Debian) -> Ubuntu
For this gudie we feature only from the package manager as the source from the distributor is 
buggy to install, and requires far more understanding than what this guide will expect you to know

This guide assumes that you have Ubuntu already installed, this guide will walk you through the steps to install virtual box and create an ubuntu virtual machine.

### Download Ubuntu 22.04 LTS
The next thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.
You can either follow this link: https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64
or go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS"
The download will begin automagically!

Once the download is complete you can move on

### From Package Manager
Open the Ubuntu Software catalogue, and search for "virtual", it will be the first one, click install, and go through the installer.

### Ubuntu VM Creation
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

### VM Hardware
This is where we set how much power to give the VM, in our case we need 4Gb of ram, this is measured in Mega bytes,
so youll need to set it to 4096 MB.
Next we need 4 cores, now this says "CPU's" it means cores, set this to 4 and click on Hard Disk.

### VM Storage
Now this is where we give the VM storage, we need 80 GB so either type or drag this to where it says 80GB.
Make sure that you actually have more than 80Gb, otherwise youll have performance issues, among other headaches. 
For the "File type and Variant" select VMDK (Virtual Machine Disk), This is the fastest of the three formats currently.
I choose to preallocate full size, but it can be resized at any time provided theres free space. This guide will not cover this.

### Install
Once you've done that click finish, now youll see something like this: <insert image here>
Youll be back on the first screen we started at. Click on Ubuntu, if not already selected, and click "Start".
Now just give it some time, some words and phrases will come onto screen, they can be ignored unless you dont 
see the Orange Ubuntu logo on screen.

Youll have a message on the right side of the screen, feel free to close that one to gain the full screen.
The screen will be black for a while, just let it load untill there is text on screen, at which point youll want to select 
"Try or Install Ubuntu"

Once the Install screen shows up, which will be a purplish background with a window that showes up.

Select Install Ubuntu
Were, going to use a Minimal install. If you are okay with all the extra bloat feel free to
install the normal installation. Then click continue, and make sure erase disk and install Ubuntu. Then click install now.
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

### Optimization & Fixing Resolution
At this point if youve messed around with the display at all youll notice that it is flixkering and glitchy,
we need to install drivers for the virtual display that ubuntu is using.

To do this go to the top left of the screen, click devices, and then "Insert Guest Additions CD".
After this is "inserted" it will "mount" automatically, an then will ask you to run it, run it and this will install
the required device drivers.

If this does not happen, on the left side of the screen will be a CD, click it, and it will open a folder, right click in the folder 
select "Open in terminal", this will open an terminal instance, and then run the following "./autorun.sh" 
This will run the installer for the utils needed for the VM.

After you do this and it installs, restart your VM and when it boots back up you will be able to resize the VM.

### Settings
At this point we're only missing updates, which we can fix with the following command:
sudo apt update && sudo apt upgrade 

We need internet at this point, so make sure that in the top right you either have wifi, or see the 3 node looking icon. (Ethernet)

Then press the windows key and then type "Terminal", open terminal and run the command above.
You can also click the 9 dots on the bottom left, and click on terminal in the middle of the screen. Then run the command
above.

It will propmt for your password, and then download and install any required update

And just like that you have a working and up-to-date virtual machine running Ubuntu 22.04 LTS
 
## (Arch) -> Manjaro

----| Download Ubuntu 22.04 LTS
The next thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.
You can either follow this link: https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64
or go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS"
The download will begin automagically!

Once the download is complete you can move on

----| From Package Manager
Open the Ubuntu Software catalogue, and search for "virtual", it will be the first one, click install, and go through the installer.

If for whatever reason this is not available, you can see it from the distributor
----| From Distributor
Follow this link: "https://www.virtualbox.org/wiki/Downloads"
or head to virtualbox.org, click download
and then select linux distributions. Since this is arch, we will have to click on "Other Installation"
This will redirect, now find "All Distributions", right click and copy this link,
then open a terminal and type "curl -o install.run "https://download.virtualbox.org/virtualbox/7.0.4/VirtualBox-7.0.4-154605-Linux_amd64.run""
the link in this command is the same as what is listed on the site at the time of publishing.

This will download the installer file, once its downloaded, make it executable "sudo chmod +x install.rn", and run it as super user "sudo ./install.run"
After this has completed, youll need to open a terminal again and install the drivers for virtualbox
you can do this with "sudo pacman -S virtualbox-host-dkms" 
After this is installed reboot and when back in, open a terminal and run "sudo /sbin/vboxconfig"
--| Issue #1 Driver cannot start
  This is either because secure boot is on, or you do not have developement headers to actually install a kernel module.
  This can be fixed by installing the headers for your device ex. on kernel version 5.15 install linux515-headers with "sudo pacman -S linux515-headers"

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


--| (RPM) -> Fedora -------------------------------------------------------------------------------------------------------------------

----| Download Ubuntu 22.04 LTS
The next thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.
You can either follow this link: https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64
or go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS"
The download will begin automagically!

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

||||-------End Linux------||||