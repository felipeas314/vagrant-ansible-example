Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/bionic64"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  
  config.vm.define "vm_test" do |vmteste|
    
    vmteste.vm.network "forwarded_port", guest: 80, host: 8089, protocol: "tcp"
    # config.vm.network "private_network", ip: "192.168.50.4"
    vmteste.vm.network "private_network", type: "dhcp"
    # config.vm.network "public_network"

    vmteste.vm.provision "ansible" do |ansible|
      ansible.playbook = "main.yml"
    end
    
    vmteste.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
    end

  end

end