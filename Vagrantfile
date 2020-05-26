# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.host_name = "Vagrant"
  # config.disksize.size = "20GB"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end

  #config.vm.provision :hosts do |provisioner|
  #  provisioner.add_host '10.1.42.240' ['vault1.local', 'vault1']
  #end
  config.vm.provision 'ansible' do |ansible|
  
    ansible.playbook = 'playbook.yml'
    ansible.verbose = 'vv'
  end

  config.vm.network "forwarded_port", guest: 8000, host: 8001
  config.vm.network "private_network", ip: "192.168.50.4"

end
