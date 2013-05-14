# Guide for setting up Vagrant and Rails on Windows or Linux/MAC

Click windows.md or linux_and_mac.md above for instructions.

Configuration of box at http://files.gravygrip.com/package.box includes Ubuntu 12.04, Ruby 2.0 and Rails 3.2.13

To set up synced folders edit setting in Vagrantfile to look like...

      config.vm.synced_folder "C:\\Users\\joe\\myFolder", "\/vagrant"

To forward ports edit settings in Vagrantfile to look like...
        config.vm.network :forwarded_port, guest: 3000, host: 3000
