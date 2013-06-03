# -*- mode: ruby -*-
# vi: set ft=ruby :
#^syntax detection

Vagrant::Config.run do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  config.vm.forward_port 80, 8080
  config.vm.forward_port 8125, 8125, :protocol => 'udp'

  config.vm.provision :chef_solo do |chef|

    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
    chef.add_recipe 'nodejs'
    chef.add_recipe 'statsd'

  end

end

