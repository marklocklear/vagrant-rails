# Vagrant setup for Windows Users

## Introduction
This is a simple step-by-step guide to setting up Ruby on Rails in a Virtualbox and Vagrant environment. Where you see 'c:\users\joe' replace 'joe' with your windows user name.

## Step 1 - Install Virtualbox
Go to https://www.virtualbox.org/wiki/Downloads and install VirtualBox 4.2.12 for Windows hosts

## Step 2 - Install Vagrant
Go to http://downloads.vagrantup.com/tags/v1.2.2 and install Vagrant-1.2.2.msi. After the install open a command prompt and type:

		c:\Users\joe>vagrant -v
		Vagrant version 1.2.2


## Step 3 - Download putty and create ppk key
Go to http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html and download both putty.exe and puttygen.exe under the 'For Windows on Intel x86' section. Run puttygen.exe and click "Load". Browse to your .vagrant.d directory (probably in  c:\Users\joe). In the lower right hand corner choose "All Files(*.*)" from the drop down box. Now click the insecure_private_key file and choose "Open". Click "OK" at the PuTTYgen Notice. Now choose "Save private key". At the PuTTYgen warning message regarding a passphrase choose "Yes" and save the file as myKey.ppk in your .vagrant.d folder.


## Step 4 - Project Setup
Open a command window and type:

		c:\Users\joe>vagrant init
		A `Vagrantfile` has been placed in this directory. You are now
		ready to `vagrant up` your first virtual environment! Please read
		the comments in the Vagrantfile as well as documentation on
		`vagrantup.com` for more information on using Vagrant.

## Step 5 - Add a box
In your command window run:

		vagrant box add rails http://files.gravygrip.com/package.box

This will take a few seconds to download.

##Step 6 - Spin up your box and SSH into it
In your commend windows type:

		vagrant up

This may take up to one minute to configure and start. Now type:

		C:\Users\mlocklear.ABTECH>vagrant ssh
		`ssh` executable not found in any directories in the %PATH% variable. Is an
		SSH client installed? Try installing Cygwin, MinGW or Git, all of which
		contain an SSH client. Or use the PuTTY SSH client with the following
		authentication information shown below:

		Host: 127.0.0.1
		Port: 2222
		Username: vagrant
		Private key: C:/Users/mlocklear.ABTECH/.vagrant.d/insecure_private_key

Now open putty.exe and go to Connection > SSH > Auth. In "Private key for authentication" browse to mykey.ppk that we created in step 3. Now in putty go to "Session" and enter 127.0.0.1 (localhost) and in port replace 22 with 2222. Now click "Open". If you get a PuTTY Security Alert click "Yes". In your terminal window you should see "login as:". Type in the username "vagrant" and you should be taken to a linux prompt.

## Verify it works

In your Ubuntu console type...

		vagrant@precise32:~$ ruby -v
		ruby 2.0.0p0 (2013-02-24 revision 39474) [i686-linux]
		vagrant@precise32:~$ rails -v
		Rails 3.2.13


## Virtual Machine Management

When done just log out with `^D` and suspend the virtual machine

    host $ vagrant suspend

then, resume to hack again

    host $ vagrant resume

Run

    host $ vagrant halt

to shutdown the virtual machine, and

    host $ vagrant up

to boot it again.

You can find out the state of a virtual machine anytime by invoking

    host $ vagrant status

Finally, to completely wipe the virtual machine from the disk **destroying all its contents**:

    host $ vagrant destroy # DANGER: all is gone

Please check the [Vagrant documentation](http://docs.vagrantup.com/v2/) for more information on Vagrant.
