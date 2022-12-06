# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|


# Nginx 1


config.vm.define "adringinx" do |adringinx|
  adringinx.vm.box = "debian/bullseye64"
  adringinx.vm.hostname = "adringinx"
  adringinx.vm.network "private_network", ip: "192.168.11.11",
				virtualbox__intnet: "red1"
  adringinx.vm.network "private_network", ip: "192.168.20.11",
				virtualbox__intnet: "red2"
  adringinx.vm.provision "shell", path: "nginx.sh"

end

# Nginx 2


config.vm.define "adringinx2" do |adringinx2|
  adringinx2.vm.box = "debian/bullseye64"
  adringinx2.vm.hostname = "adringinx2"
  adringinx2.vm.network "private_network", ip: "192.168.11.12",
				virtualbox__intnet: "red1"
  adringinx2.vm.network "private_network", ip: "192.168.20.12",
				virtualbox__intnet: "red2"
  adringinx2.vm.provision "shell", path: "nginx.sh"
end

# Balanceador


config.vm.define "balanceador" do |balanceador|
  balanceador.vm.box = "ubuntu/xenial64"
  balanceador.vm.hostname = "adribalanceador"
  balanceador.vm.network "public_network"
  balanceador.vm.network "private_network", ip: "192.168.11.10",
				virtualbox__intnet: "red1"
  balanceador.vm.provision "shell", path: "bal.sh"

end

# NFS


config.vm.define "adrinfs" do |adrinfs|
  adrinfs.vm.box = "debian/bullseye64"
  adrinfs.vm.hostname = "adriadrinfs"
  adrinfs.vm.network "private_network", ip: "192.168.11.100",
				virtualbox__intnet: "red1"
  adrinfs.vm.provision "shell", path: "nfs.sh"
end


# BD

config.vm.define "adrianMysql" do |adrianMysql|
  adrianMysql.vm.box = "debian/bullseye64"
  adrianMysql.vm.hostname = "adrianMysql"
  adrianMysql.vm.network "private_network", ip: "192.168.20.10",
				virtualbox__intnet: "red2"
  adrianMysql.vm.provision "shell", path: "mysql.sh"
end



  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.


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
