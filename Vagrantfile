# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.username="vagrant"
  # - ports for elk - #
  # e #
  config.vm.network "forwarded_port", guest: 9200, host: 8200, host_ip: "127.0.0.1" 
  # l #
  config.vm.network "forwarded_port", guest: 5601, host: 8601, host_ip: "127.0.0.1"
  # k #
  config.vm.network "forwarded_port", guest: 9300, host: 8300, host_ip: "127.0.0.1"
  
  config.vm.provision :ansible do |ansible|
    ansible.verbose="v"
    ansible.playbook = "elk.yml"
  end
end
