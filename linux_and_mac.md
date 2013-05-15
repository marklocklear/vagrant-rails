# Vagrant setup for Linux and MAC users

## Introduction
This is a simple step-by-step guide to setting up Ruby on Rails in a Virtualbox and Vagrant environment on Linux or MAC.

## Step 1 - Install Virtualbox
Go to https://www.virtualbox.org/wiki/Downloads and install VirtualBox 4.2.12.

## Step 2 - Install Vagrant
Go to http://downloads.vagrantup.com/tags/v1.2.2 and install Vagrant. After the install open a command prompt and type:

		host$ vagrant -v
		Vagrant version 1.2.2

## Step 3 - Project Setup
Open a command window and type:

		host$ vagrant init
		A `Vagrantfile` has been placed in this directory. You are now
		ready to `vagrant up` your first virtual environment! Please read
		the comments in the Vagrantfile as well as documentation on
		`vagrantup.com` for more information on using Vagrant.

## Step 4 - Add a box
In your command window run:

		vagrant box add base http://files.gravygrip.com/package.box

This will take a few seconds/minutes/hours to download depending on your internet speed.


##Step 5 - Spin up your box and SSH into it
In your commend windows type:

		vagrant up

This will take a minute or two configure and start. Now type:

		host$ vagrant ssh

This should take you do a login prompt. Login with the user 'vagrant', and no password.

## Verify it works

In your console type...

		vagrant@precise32:~$ ruby -v
		ruby 2.0.0p0 (2013-02-24 revision 39474) [i686-linux]
		vagrant@precise32:~$ rails -v
		Rails 3.2.13


Thats it. You are done! When you are ready to exit the VM just type 'exit' in the VM console. Then type 'vagrant halt' in your locahost's console.
