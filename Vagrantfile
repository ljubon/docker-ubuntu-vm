# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/trusty64"
    config.vm.provision "shell", path: "provision/node.sh", privileged: true

    config.vm.provider "virtualbox" do |v|
        v.memory = 1048
        v.cpus = 1
        v.name = 'docker_ubuntu'
    end
    
    
    # Nodes 1-5 
    # Example: 
    # vagrant up node1 OR vagrant up node1 node3 
    # ONLY mentioned node will be installed
    
    (1..5).each do |number|
        config.vm.define "node#{number}" do |node|
            node.vm.network "private_network", ip: "192.168.10.1#{number}"
            node.vm.hostname = "m#{number}"
        end  
    end
    
end
