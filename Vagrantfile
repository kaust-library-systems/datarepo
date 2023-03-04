# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"

  config.vm.define "datarepo" do |datarepo|
    datarepo.vm.hostname = "datarepo"
    datarepo.vm.provider :virtualbox do |vb|
      vb.memory = 4096
      vb.cpus = 4
    end
    datarepo.vm.provision :ansible_local do |ansible|
      ansible.verbose = true
      ansible.install = true
      ansible.limit = "all"
      ansible.inventory_path = "inventory"
      ansible.playbook = "datarepo.yml"
    end
  end
end
