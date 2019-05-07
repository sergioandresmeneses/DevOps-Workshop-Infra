# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  #config.vm.box = "devops-workshop"
  config.vm.provider :virtualbox do |vb|
        vb.name = "jenkins-vagrant"
        vb.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
  end
# Jenkin's Ports
  config.vm.network "forwarded_port", guest: 8080, host: 8080
# App QA
  config.vm.network "forwarded_port", guest: 8220, host: 8220
# App Prod
  config.vm.network "forwarded_port", guest: 8320, host: 8320
  config.vm.provision :shell, path: "bootstrap.sh", args: "2>&1 >> /vagrant/log-file.txt"
end

