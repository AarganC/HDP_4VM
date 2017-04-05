# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|
  
	config.vm.define :master do |config|
	  config.vm.box = "centos/6"
	  config.vm.hostname = "master.ryba"
	  config.vm.network "forwarded_port", guest: 22, host: 24011
	  config.vm.network "private_network", ip: "10.11.10.2"
	  	config.vm.provider "virtualbox" do |vb|
	  	vb.memory = "6144"
	  	vb.name = config.vm.hostname
		end
		config.vm.provider "libvirt" do |vb|
      	vb.memory = 2048
      	vb.graphics_port = 5915
    	end
	end
	config.vm.define :datanode1 do |config|
	  config.vm.box = "centos/6"
	  config.vm.hostname = "datanode1.ryba"
	  config.vm.network "forwarded_port", guest: 22, host: 24012
	  config.vm.network "private_network", ip: "10.11.10.3"
	  	config.vm.provider "virtualbox" do |vb|
  		vb.memory = "1024"
  		vb.name = config.vm.hostname
		end
		config.vm.provider "libvirt" do |vb|
      	vb.memory = 1536
      	vb.graphics_port = 5916
    	end
	end
	config.vm.define :datanode2 do |config|
	  config.vm.box = "centos/6"
	  config.vm.hostname = "datanode2.ryba"
	  config.vm.network "forwarded_port", guest: 22, host: 24013
	  config.vm.network "private_network", ip: "10.11.10.4"
	  	config.vm.provider "virtualbox" do |vb|
	  	vb.memory = "1024"
	  	vb.name = config.vm.hostname
		end
		config.vm.provider "libvirt" do |vb|
      	vb.memory = 1536
      	vb.graphics_port = 5917
    	end
	end
	config.vm.define :datanode3 do |config|
	  config.vm.box = "centos/6"
	  config.vm.hostname = "datanode3.ryba"
	  config.vm.network "private_network", ip: "10.11.10.5"
	  config.vm.network "forwarded_port", guest: 22, host: 24014
	  	config.vm.provider "virtualbox" do |vb|
	  	vb.memory = "1024"
	  	vb.name = config.vm.hostname
		end
		config.vm.provider "libvirt" do |vb|
      	vb.memory = 1536
      	vb.graphics_port = 5918
    	end
	end 
end
