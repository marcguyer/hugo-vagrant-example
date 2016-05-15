# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 1313, host: 1313
  config.vm.provision "shell", inline: <<-SHELL
    sudo add-apt-repository ppa:ubuntu-lxc/lxd-stable
    sudo apt-get update
    sudo apt-get autoremove -y
    sudo apt-get install -y golang git
    wget -q https://github.com/spf13/hugo/releases/download/v0.15/hugo_0.15_amd64.deb
    sudo dpkg -i hugo_0.15_amd64.deb && sudo rm hugo_0.15_amd64.deb
  SHELL
end
