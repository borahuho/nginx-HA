$useraddscript = <<SCRIPT
useradd -m henk
groupadd operators
usermod -aG operators henk
mkdir /operators
chown henk /operators
chgrp operators /operators
SCRIPT


Vagrant.configure('2') do |config|

    # Ssh settings
    config.ssh.insert_key = false

    # Default settings
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
        vb.cpus = 1
    end

    config.vm.define :lb01 do |machine1|
        machine1.vm.host_name = "lb01.local"
        machine1.vm.network "private_network", ip: "192.168.10.200"
        machine1.vm.provision "shell", inline: $useraddscript
    end

    config.vm.define :web1 do |machine2|
        machine2.vm.host_name = "web1.local"
        machine2.vm.network "private_network", ip: "192.168.10.210"
        machine2.vm.provision "shell", inline: $useraddscript
    end

    config.vm.define :web2 do |machine3|
        machine3.vm.host_name = "web2.local"
        machine3.vm.network "private_network", ip: "192.168.10.211"
        machine3.vm.provision "shell", inline: $useraddscript
	end
	
	config.vm.define :db1 do |machine4|
        machine3.vm.host_name = "db1.local"
        machine3.vm.network "private_network", ip: "192.168.10.220"
        machine3.vm.provision "shell", inline: $useraddscript
	end
	
	config.vm.define :db2 do |machine5|
        machine3.vm.host_name = "db2.local"
        machine3.vm.network "private_network", ip: "192.168.10.221"
        machine3.vm.provision "shell", inline: $useraddscript
    end
end