# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "web01" do |web|
  web.vm.network "private_network", ip:"192.168.200.3"
  web.vm.provision "shell", path: "web.sh"
  web.vm.network "forwarded_port", guest: 80 , host: 8080
  web.vm.synced_folder ".", "/var/www/html"
  config.vm.provider :virtualbox do |vb|
          vb.customize ['modifyvm', :id, '--name', 'web_11']
          end
  end		
end
