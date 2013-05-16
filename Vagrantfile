# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "precise64"
  config.ssh.forward_x11 = true

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe "apt"
    chef.add_recipe "build-essential"
    chef.add_recipe "git"
    chef.add_recipe "ogs"
  end
end
