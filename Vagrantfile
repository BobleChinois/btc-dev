# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # Virtualbox specific config

  config.vm.provider "virtualbox" do |vb, override|
    override.vm.box = "ubuntu/bionic64"
    # A bit more RAM
    vb.memory = "4000"

    # Network config

    # No port forwarding
    # config.vm.network "forwarded_port", guest: 80, host: 8080

    # No private network
    # config.vm.network "private_network", ip: "192.168.33.10"

    # Public bridged network
    override.vm.network "public_network"

    # provisioning script
    override.vm.provision :shell, path: "bootstrap.sh", args: "-u vagrant"

    # Shared storage for bitcoin source code
    override.vm.synced_folder "../bitcoin", "/bitcoin"
  end

end

