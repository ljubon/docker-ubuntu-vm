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
    
    
    # Managers
    (1..2).each do |number|
        config.vm.define "m-#{number}" do |node|
            node.vm.network "private_network", ip: "192.168.10.1#{number}"
            node.vm.hostname = "m#{number}"
        end  
    end

    # Workers
    (1..5).each do |number|
        config.vm.define "w-#{number}" do |node|
            node.vm.network "private_network", ip: "192.168.10.10#{number}"
            node.vm.hostname = "w#{number}"
        end  
    end

end
