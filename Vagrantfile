# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "geerlingguy/centos7"
  config.vm.network "private_network", ip: "192.168.33.9"

  # Add the local directory you want to sync to the vagrant box here
  config.vm.synced_folder "LOCAL PATH HERE", "/code", mount_options: ["dmode=777,fmode=666"]
  config.ssh.forward_agent = true

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/playbook.yml"
    # Allow ansible to provision all machines
    ansible.limit = "all"
    # Enable agent forwarding for ansible provisioner
    ansible.extra_vars = { ansible_ssh_user: 'vagrant', 
                           ansible_connection: 'ssh',
                           ansible_ssh_args: '-o ForwardAgent=yes'}
  end
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end
end
