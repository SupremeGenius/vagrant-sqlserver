# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant virtual environments for SQL Server 2017 on Ubuntu Linux

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  
  config.vm.network "private_network", ip: "192.168.50.4"
  config.vm.network :forwarded_port, host: 1433, guest: 1433
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.cpus = 4
    vb.name = "ubuntu-sqlserver"
  end

  scripts = [ "bootstrap.sh" ]
  scripts.each { |script|
    config.vm.provision :shell, privileged: false, :path => "./" << script
  }

end
