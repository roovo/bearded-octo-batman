# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_NAME  = ENV.fetch("BOX_NAME", "ubuntu")
BOX_URI   = ENV.fetch("BOX_URI",  "http://files.vagrantup.com/precise64.box")

Vagrant.configure("2") do |config|
  config.vm.box     = BOX_NAME
  config.vm.box_url = BOX_URI

  # uncomment to skip the auto-update of guest additions
  # config.vbguest.auto_update = false

  config.vm.provision :shell, :path => 'provision_dev.sh'
  # config.vm.provision :shell, :path => 'provision_dev.sh', :args => '--skip-backport'
end

# GuestAdds Backport  Provision Time
#     Y        Y      10 mins
#     Y        N       5 mins
#     N        Y       ERROR on shared folders
#     N        N       3 mins
