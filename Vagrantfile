# -*- mode: ruby -*-
# vi: set ft=ruby :
system('./export.sh')

Vagrant.configure("2") do |config|

  config.vm.box = 'almalinux/8'
  # config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "playbook.yml"
  # end
  config.vm.define "Client" do |web|
      web.vm.network "private_network", ip: "192.168.56.25"
      web.vm.host_name = 'Client'
      web.vm.provider :virtualbox do |vb|
        vb.memory = "2048"
      end
  end
  config.vm.define "BackUp" do |log|
     log.vm.network "private_network", ip: "192.168.56.24"
     log.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
     end
     log.vm.host_name = 'BackUp'
     (0..2).each do |i|
      log.vm.disk :disk, size: "2GB", name: "disk-#{i}"
     end
  
  
   
  end
end