Vagrant.configure("2") do |config|
	# Base VM OS configuration.
	config.vm.box = "ubuntu/focal64"
	config.vm.provider :virtualbox do |v|
		v.memory = 2048
		v.cpus = 1
	end
	# Define two VMs with static private IP addresses.
	boxes = [
	  { :name => "dc1",
            :ip => "192.168.56.10",
	  },
	  { :name => "dc2",
            :ip => "192.168.56.15",
          }
         ]
	# Provision each of the VMs.
	boxes.each do |opts|
	  config.vm.define opts[:name] do |config|
   	    config.vm.hostname = opts[:name]
	    config.vm.network "private_network", ip: opts[:ip]
		
 	 	end
	end
end
