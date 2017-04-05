# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/zesty64"

  # Barbican Ports
  config.vm.network "forwarded_port", guest: 9311, host: 9311

  # Keystone Ports
  config.vm.network "forwarded_port", guest: 35357, host: 35357
  config.vm.network "forwarded_port", guest: 5000,  host: 5000
  config.vm.network "forwarded_port", guest: 21000,  host: 21000
  config.vm.network "private_network", ip: "192.168.50.4"

  config.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "8192"
      vb.cpus = "3"
  end
  config.vm.provision "shell", path: "install.sh", privileged: false
end
