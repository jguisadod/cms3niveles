# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|



#################################################################################
#################################################################################
####################     BALANCEADOR NFS   ######################################


config.vm.define "balanceadorJesus" do |balanceadorJesus|
balanceadorJesus.vm.box = "ubuntu/xenial64"
balanceadorJesus.vm.hostname = "balanceadorJesus"


balanceadorJesus.vm.network "private_network", ip:"172.16.10.2",
				virtualbox__itnet: "red1"

balanceadorJesus.vm.network "public_network"

balanceadorJesus.vm.provision "shell", path: "scriptbal.sh"



end


#################################################################################
#################################################################################
############################     NGINX 1    #####################################


config.vm.define "nginx1Jesus" do |nginx1Jesus|
nginx1Jesus.vm.box = "ubuntu/xenial64"
nginx1Jesus.vm.hostname = "nginx1Jesus"


nginx1Jesus.vm.network "private_network", ip:"172.16.10.3",
				virtualbox__itnet: "red1"

nginx1Jesus.vm.network "private_network", ip:"192.168.10.3",
				virtualbox__itnet: "red2"


nginx1Jesus.vm.network "public_network"

nginx1Jesus.vm.provision "shell", path: "scriptnginx.sh"



end

#################################################################################
#################################################################################
############################     NGINX 2    #####################################


config.vm.define "nginx2Jesus" do |nginx2Jesus|
nginx2Jesus.vm.box = "ubuntu/xenial64"
nginx2Jesus.vm.hostname = "nginx2Jesus"


nginx2Jesus.vm.network "private_network", ip:"172.16.10.4",
				virtualbox__itnet: "red1"

nginx2Jesus.vm.network "private_network", ip:"192.168.10.4",
				virtualbox__itnet: "red2"


nginx2Jesus.vm.network "public_network"

nginx2Jesus.vm.provision "shell", path: "scriptnginx.sh"



end


#################################################################################
#################################################################################
#######################     SERVIDOR NFS   ######################################


config.vm.define "servidorJesus" do |servidorJesus|
servidorJesus.vm.box = "ubuntu/xenial64"
servidorJesus.vm.hostname = "servidorJesus"


servidorJesus.vm.network "private_network", ip:"172.16.10.5",
				virtualbox__itnet: "red1"

servidorJesus.vm.network "private_network", ip:"192.168.10.5",
				virtualbox__itnet: "red2"

servidorJesus.vm.network "public_network"

servidorJesus.vm.provision "shell", path: "scriptserver.sh"



end


#################################################################################
#################################################################################
####################     BASE DE DATOS MYSQL   ##################################


config.vm.define "mysqlJesus" do |mysqlJesus|
mysqlJesus.vm.box = "ubuntu/xenial64"
mysqlJesus.vm.hostname = "mysqlJesus"


mysqlJesus.vm.network "private_network", ip:"192.168.10.6",
				virtualbox__itnet: "red2"

mysqlJesus.vm.network "public_network"

mysqlJesus.vm.provision "shell", path: "scriptmysql.sh"



end



#################################################################################
#################################################################################






  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "base"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
