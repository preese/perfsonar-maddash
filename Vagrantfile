# -*- mode: ruby -*-
# vi: set ft=ruby :

nodes = [
  {:hostname => 'ps1', :mac => "525400836f41" },
  {:hostname => 'ps2', :mac => "525400836f42" },
  {:hostname => 'ps3', :mac => "525400836f43" },
  {:hostname => 'md', :mac => "525400836f44" },
]

Vagrant.configure("2") do |config|
   nodes.each do |node|
    config.vm.define node[:hostname] do |config|
	  config.vm.box = "centos/7"
	  config.vm.network :public_network, :mac => node[:mac]
    config.vm.provision "file", source: "/home/vagrant/.ssh/id_ed25519.pub", destination: "/home/vagrant/.ssh/authorized_keys"
    config.vm.hostname = node[:hostname]
	  config.vm.provider :virtualbox do |domain|
		  domain.memory = 2048
		  domain.cpus = 1
         end
       end
    end
end
