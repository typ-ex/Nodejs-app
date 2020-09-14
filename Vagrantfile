# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/centos7"
  config.vm.network :private_network, ip: "10.19.0.56"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  
  config.vm.provider :virtualbox do |v|
    v.memory = 512
  end

  # Ansible provisioner
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become=true
  end
end
