# Guide for setting up Vagrant and Rails on Windows or Linux/MAC

Click windows.md or linux_and_mac.md above for instructions.

Configuration of box at http://files.gravygrip.com/package.box includes Ubuntu 12.04, Ruby 2.0 and Rails 3.2.13

To set up synced folders edit setting in Vagrantfile to look like...

      config.vm.synced_folder "C:\\Users\\joe\\myFolder", "\/vagrant"

To forward ports edit settings in Vagrantfile to look like...

      config.vm.network :forwarded_port, guest: 3000, host: 3000

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
