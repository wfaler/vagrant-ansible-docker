# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!


Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
#  config.vm.box = "ubuntu/trusty64"

  config.vm.define "docker" do |jenkins|
    jenkins.vm.box = "ubuntu/trusty64"
    jenkins.vm.network "private_network", ip: "192.168.93.135"
    jenkins.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 1
    end
  end

  # can this be by box? eg jenkins.vm.provider instead of config.vm.provider?
#  config.vm.provider "virtualbox" do |v|
#    v.memory = 1024
#    v.cpus = 1
#  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision-vagrant.yml"
  end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:


end
