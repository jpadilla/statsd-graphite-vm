# -*- mode: ruby -*-
# vi: set ft=ruby :
#^syntax detection

Vagrant::Config.run do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise32"

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  config.vm.forward_port 80, 8080
  config.vm.forward_port 8125, 8125, :protocol => 'udp'

  # Upgrade Chef automatically
  config.vm.provision :shell, :inline => "gem install --no-ri --no-rdoc chef -v '=11.4.2'"

  config.vm.provision :chef_solo do |chef|

    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
    chef.add_recipe 'nodejs'
    chef.add_recipe 'statsd'

  end

end
