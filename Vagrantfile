# -*- mode: ruby -*-
# vi: set ft=ruby :

servers=[
  {
    :hostname => "controller-0",
    :ip => "10.240.0.10",
  },
  {
    :hostname => "controller-1",
    :ip => "10.240.0.11",
  },
  {
    :hostname => "controller-2",
    :ip => "10.240.0.12",
  }
]

Vagrant.configure("2") do |config|
  servers.each do |machine|
    config.vm.define machine[:hostname] do |node|
      node.vm.box = "debian/buster64"
      node.vm.hostname = machine[:hostname]
      node.vm.network "private_network", ip: machine[:ip]

      node.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.memory = "512"
      end
    end
  end
end
