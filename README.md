This todo app is copied from https://github.com/engineyard/todo. It contains chef recipes that will set up the app in Vagrant. It uses a Debian Wheezy box that contains ruby 1.9 and chef but nothing else.

Chef will install nginx, monit, postgresql and create the config files. The app server is unicorn.

The Vagrantfile will create two virtual machines.

- Install Virtualbox from https://www.virtualbox.org/wiki/Downloads
- Install Vagrant 1.2.2 from http://downloads.vagrantup.com
- Run the following commands

        vagrant box add vagrant-debian-wheezy http://crigor.com/reddot/vagrant-debian-wheezy.box
        git clone git://github.com/crigor/todo-reddot-multivm.git
        cd todo-reddot-multivm
        vagrant up

Sample output of the vagrant up command that creates two VMs can be found at https://gist.github.com/crigor/5671882.
