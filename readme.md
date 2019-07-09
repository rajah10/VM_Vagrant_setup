# Setup a vagrant workstation 

### What is vagrant?
Vagrant is open source and allow to use virtual machines via command-line. The workstation can be defined in code, easy to back up, modify and share.

### Install Virtual Box
First need to install Virtual Box, download 
<a href="https://www.virtualbox.org/wiki/Linux_Downloads"> here </a>


### Install Vagrant

Download <a href="https://www.vagrantup.com/downloads.html"> here  </a>

### Run box
#### Create and direct to the folder

Run `mkdir mybox` to create directory and direct to the folder `cd mybox` 

Then run `vagrant init bento/ubuntu-16.04` to initailize vagrant.

### Open the Vagrantfile and make the configuration. Uncomment bellow line and make the appropriate changes

```
config.vm.network "forwarded_port", guest: 80, host: 8081, host_ip: "127.0.0.1"

config.vm.network "private_network", type: "dhcp"
  
config.vm.synced_folder "files", "/files_data"

 
config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
     vb.memory = "512"
     vb.cpus = 2
     vb.customize ["modifyvm", :id, "--vram", "16"]
end
  

#config.vm.provision "shell", path: "provisioners/node_install.sh"
```

Run `vagrant up` to start vagrant, and run `vagrant ssh` to enter to guest mechine.


### Useful vagrant commands  
```
 vagrant up
 vagrant provision
 vagrant reload/restart
 vagrant status
 vagrant halt
 vagrant destroy 

 vagrant ssh

 ```

To setup Apache server, click <a href="https://github.com/rajah10/Vagrant_Apache2_PHP_MySql_env"> here </a>

To setup multiple vhost, click <a href="https://github.com/rajah10/Vagrant_vhost"> here </a>

To setup Ngnix server, click <a href="https://github.com/rajah10/Vagrant_Nginx_MySql_PHP_env"> here </a>