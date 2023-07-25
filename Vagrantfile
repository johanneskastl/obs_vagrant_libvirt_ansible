# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # name the VMs
  config.vm.define "obs-server-153" do |node|

    # which image to use
    node.vm.box = "opensuse/Leap-15.3.x86_64"

    # disable synced folders
    node.vm.synced_folder ".", "/vagrant", disabled: true

    # sizing of the VMs
    node.vm.provider "libvirt" do |lv|
      lv.random_hostname = false
      lv.memory = 8196
      lv.cpus = 2
    end

    # set the hostname
    node.vm.hostname = "obs-server-153"

    # disable shared folders
    node.vm.synced_folder ".", "/vagrant", disabled: true

    # Ansible provisioning
    node.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "ansible/playbook-vagrant.yml"
    end # node.vm.provision
  end # config.vm.define nodes
end
