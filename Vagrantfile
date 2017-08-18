# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "abh"

  config.vm.define "abh" do |abh|

  end

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = 2048
  end

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network :private_network, ip: "10.0.0.10"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'provisioning/playbook.yaml'
    ansible.limit = "all"
  end
end
