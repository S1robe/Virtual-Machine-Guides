<h1></h1>

<h1 align=center> Vmware (Fusion) - Mac </h1>
<p>
For this guide we feature only from the distributor.

NOTE: this guide may be out of date
</p>


> <h2>Download Ubuntu 22.04 LTS </h2>

---

<p>
The next thing we need to download is the latest version of Ubuntu. This guide will use the 22.04 LTS version, that is
long term support. This type of version generally is more stable, and, well, supported.

- [Ubuntu Download 22.04 LTS](https://ubuntu.com/download/desktop/thank-you?version=22.04.1&architecture=amd64)

**Or** go to ubuntu.com, at the top middle of the page clicking download, then the one that says "22.04 LTS" The download will begin automagically!
</p><br>

> <h2>Download VM Fusion</h2>
---

You can download it here: 

- [VMware Fusion Download]("https://customerconnect.vmware.com/en/downloads/details?downloadGroup=FUS-1225&productId=1040")

or 

1. head to vmware.com
2. go to resources in the top right
3. then head to product download.
4. Now search for vmware fusion
5. download the latest version. 

This will run on either arm or intel based Mac's

> <h2>Install VM Fusion</h2>
---

Once you have the installer downloaded, double click it to begin the installation.
It will propt you for administrative access, allow it. Make sure that youve given your mac permissions to install, otherwise this might not install properly.

> <h2>Ubuntu VM Creation</h2>
---

<p>
Now to the fun part, the Virtual Machine. 

Click the "Create New Virtual Machine" button in the middle of the application.a

Select the Installer Disc, it will tell you its using <code>Easy Install</code>

Thats just a sped up version of the install, this doesnt affect the machine

Enter the user account information, and click next.
</p><br>

> <h2>VM Storage (80GB)</h2>
---

<p>
Make sure that you actually have more than 80Gb, otherwise youll have performance issues, among other headaches. 

Whether you choose to leave it as multiple files or single file is up to you, I choose single file, mostly for performance.

After clicking next, make sure to click "Customize Hardware"
</p><br>

> <h2>VM Hardware (4GB RAM + 4 CPUS)</h2>
---

<p>
Now to change the hardware section of the virutal machine. There will be a few options in here we need to change.

Fist make sure Memory says "4 GB" or something more, if you need to give your machine less, see the "Minimization" section

Next click "Processors" and set it to 4. Leave the other things unchecked.

Click Close, and click "Finish"
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

