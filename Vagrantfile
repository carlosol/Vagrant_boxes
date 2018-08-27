# -*- mode: ruby -*-
# vi: set ft=ruby :

$setupscript = <<END
yum -y install vim yum-utils.noarch  nmap tcpdump net-tools htop
yum -y update
yum clean all
END

Vagrant.configure("2") do |config|
  config.vm.box = "centos7"
#foreman
	config.vm.define "foreman", primary: true do |foreman|
			config.vm.provider :virtualbox do |v|
			v.customize ["modifyvm", :id, "--memory", 4096]
			end
		foreman.vm.hostname = "foreman.local.lo"
		foreman.vm.network :private_network, ip: "10.0.0.2"
		foreman.vm.provision "shell", inline: $setupscript
		#test
		
	    
	end
#puppet-master
	config.vm.define "puppetmaster", primary: true do |puppetmaster|
		puppetmaster.vm.hostname = "puppetmaster.local.lo"
		puppetmaster.vm.network :private_network, ip: "10.0.0.3"
		puppetmaster.vm.provision "shell", inline: $setupscript
	end
#client
	config.vm.define "client", primary: true do |client|
		client.vm.hostname = "client.local.lo"
		client.vm.network :private_network, ip: "10.0.0.4"
		client.vm.provision "shell", inline: $setupscript
	end
end
