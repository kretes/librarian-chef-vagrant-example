# encoding: utf-8
# This file originally created at http://rove.io/2c381a146ee3e7d9dd1a0bfcf2c3a7a1

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "opscode-ubuntu-12.04_chef-11.4.0"
  config.vm.box_url = "https://opscode-vm-bento.s3.amazonaws.com/vagrant/opscode_ubuntu-12.04_chef-11.4.0.box"
  config.ssh.forward_agent = true

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe :apt
    chef.add_recipe 'nodejs'
    chef.add_recipe 'vim'
    chef.add_recipe 'git'
    chef.add_recipe 'mongodb::10gen_repo'
    chef.add_recipe 'mongodb::default'
    chef.add_recipe 'tmux'
    chef.json = {
      :git     => {
        :prefix => "/usr/local"
      },
      :mongodb => {
        :dbpath  => "/var/lib/mongodb",
        :logpath => "/var/log/mongodb",
        :port    => "27017"
      }
    }
  end
end
