# Vagrant setup for Linux and MAC users

## Introduction
This is a simple step-by-step guide to setting up Ruby on Rails in a Virtualbox and Vagrant environment on Linux or MAC.

## Step 1 - Install Virtualbox
Go to https://www.virtualbox.org/wiki/Downloads and install VirtualBox 4.2.12.

## Step 2 - Install Vagrant
Go to http://downloads.vagrantup.com/tags/v1.2.2 and install Vagrant-1.2.2.msi. After the install open a command prompt and type:

		host$ vagrant -v
		Vagrant version 1.0.7

## Step 3 - Project Setup
Open a command window and type:

		host$ vagrant init
		A `Vagrantfile` has been placed in this directory. You are now
		ready to `vagrant up` your first virtual environment! Please read
		the comments in the Vagrantfile as well as documentation on
		`vagrantup.com` for more information on using Vagrant.

## Step 4 - Add a box
In your command window run:

		vagrant box add rails_box http://files.gravygrip.com/package.box

This will take a few seconds to download.

##Step 5 - Spin up your box and SSH into it
In your commend windows type:

		vagrant up

This may take up to one minute to configure and start. Now type:

		host$ vagrant ssh

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
