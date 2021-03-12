$useraddscript = <<SCRIPT
useradd -s /bin/bash -c "Ansible testuser" -m student
echo 'student:Welcome01' | chpasswd
groupadd operators
usermod -aG operators student
usermod -aG sudo student
mkdir /operators
chown student /operators
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

    config.vm.define :lb1 do |machine1|
        machine1.vm.host_name = "lb1.local"
        machine1.vm.network "private_network", ip: "192.168.10.200"
        machine1.vm.provision "shell", inline: $useraddscript
		machine1.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    end
	
	config.vm.define :lb2 do |machine6|
        machine6.vm.host_name = "lb2.local"
        machine6.vm.network "private_network", ip: "192.168.10.201"
        machine6.vm.provision "shell", inline: $useraddscript
		machine6.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    end

    config.vm.define :web1 do |machine2|
        machine2.vm.host_name = "web1.local"
        machine2.vm.network "private_network", ip: "192.168.10.210"
        machine2.vm.provision "shell", inline: $useraddscript
		machine2.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    end

    config.vm.define :web2 do |machine3|
        machine3.vm.host_name = "web2.local"
        machine3.vm.network "private_network", ip: "192.168.10.211"
        machine3.vm.provision "shell", inline: $useraddscript
		machine3.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
	end
	
	config.vm.define :db1 do |machine4|
        machine4.vm.host_name = "db1.local"
        machine4.vm.network "private_network", ip: "192.168.10.220"
        machine4.vm.provision "shell", inline: $useraddscript
		machine4.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
	end
	
	config.vm.define :db2 do |machine5|
        machine5.vm.host_name = "db2.local"
        machine5.vm.network "private_network", ip: "192.168.10.221"
        machine5.vm.provision "shell", inline: $useraddscript
		machine5.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
    end
	
end