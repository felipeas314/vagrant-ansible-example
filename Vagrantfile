Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/bionic64"
  
  config.vm.network "forwarded_port", guest: 80, host: 8089, protocol: "tcp"
  # config.vm.network "private_network", ip: "192.168.50.4"
  config.vm.network "private_network", type: "dhcp"
  # config.vm.network "public_network"
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
  end
  
  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end

end