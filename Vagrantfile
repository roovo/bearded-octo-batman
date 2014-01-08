# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_NAME  = ENV.fetch("BOX_NAME", "ubuntu")
BOX_URI   = ENV.fetch("BOX_URI",  "http://files.vagrantup.com/precise64.box")

Vagrant.configure("2") do |config|
  config.vm.box     = BOX_NAME
  config.vm.box_url = BOX_URI

  config.ssh.forward_agent = true

  # uncomment to skip the auto-update of guest additions
  # config.vbguest.auto_update = false

  confirmation = [
    %{if [[ ! -z $(type -p docker) ]]; then},
      %{echo -e "\nVM ready - on first log in:"},
      %{echo    "  * add yourself to the docker group \\`sudo usermod -a -G docker <user>\\`"},
      %{echo    "  * set up dotfiles \\`bash <(curl -sSL https://raw.github.com/roovo/dotfiles/master/scripts/bootstrap)\\`"},
      %{echo -e "  * and log out and in again to pick up the new permissions and dotfile stuff\n"},
    %{fi},
  ]

  config.vm.provision :shell, :path   => 'provision_dev_essentials'
  config.vm.provision :shell, :path   => 'provision_dockerize'
  # config.vm.provision :shell, :path   => 'provision_dockerize', :args => '--skip-backport'

  config.vm.provision :shell, :inline => confirmation.join("\n")
end

# GuestAdds Backport  Provision Time
#     Y        Y      10 mins
#     Y        N       5 mins
#     N        Y       ERROR on shared folders
#     N        N       3 mins
