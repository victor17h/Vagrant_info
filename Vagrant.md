# Vagrant Dev Environment

## Install Vagrand

- In order to install ruby, vagrant and virtual box follow this link: [here](https://github.com/khanmaster/vb_vagrant_installtion)

## Setting up virtual machine

1. Create folder in which vagrant will be initialized.
2. Run git bash as an administrator and enter the folder created. Then use `vagrant init` to start vagrant and be able to enter key information.
3. Create a file called `vagrantfile` using nano with the following information:

```
Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end

 config.vm.box = "ubuntu/xenial64"
 # creating a virtual machine ubuntu 
 config.vm.network "private_network", ip: "192.168.10.100"
 
end
```
4. Once this file has been saved run the command `vagrant up`. This will boot up your virtual machine.
5. Next enter virtual machine by using `vagrant ssh`.
6. Then update to the current version of linux by using `sudo apt-get update -y`.
7. After this, install nginx with `sudo apt-get install nginx -y`.
8. The process is completed, you should be able to navigate to your locally hosted virtual machine by typing the ip `192.168.10.100` into your browser url.

## Close virtual machine

1. Type `exit` in git bash to exit the virtual machine.
2. Next type `vagrant destroy` to destroy the vagrant created.


## Other commands

- To reload vagrant `vagrant reload`.
- To suspend vagrant `vagrant suspend`.


## More commands

- List of tasks in linux `top`.
- to have root control `sudo su`, to avoid using sudo all the time. Use `exit` to escape root.
- Use `history` to see all commands you have used.
- Check system status using `sudo systemctl status nginx`. `Ctrl C` to exit.
- Use `sudo systemctl stop nginx` to stop nginx service.
- Restart the system by using `sudo systemctl restart nginx`
- To stop the system use `sudo systemctl stop nginx`.
- A file with called provision.sh with all the instructions can be created and then run all the instructions `sudo bash provision.sh`.
- Use `sudo chmod +x provision.sh` to make it executable and then `sudo ./provision.sh`.
- To check if it worked use `ls` or `ll` and the file should appear in other color.

