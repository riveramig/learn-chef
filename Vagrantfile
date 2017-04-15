# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "node", primary:true do|node|
  	node.vm.box = "ubuntu/trusty32"
  	node.vm.network "forwarded_port", guest:8080, host:7777, host_ip:"127.0.0.1"
  	node.omnibus.chef_version = :latest
  	node.vm.provision :chef_client do |chef|
  		chef.provisioning_path = "/etc/chef"
  		chef.chef_server_url = "https://manage.chef.io/organizations/coffeex"
  		chef.validation_key_path = ".chef/miguelriv7.pem"
  		chef.validation_client_name = "miguelriv7"
  		chef.node_name = "server"
  	end
  end
end
