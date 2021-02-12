Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.define "org0" do |org0|
    org0.vm.hostname = "org0"
    org0.vm.box = "bento/ubuntu-20.04"
    org0.vm.network "public_network", ip: "192.168.0.200", bridge: "enx00e04c680559" # Remove bridge attribute if not working

  end
  config.vm.define "org1" do |org1|
    org1.vm.hostname = "org1"
    org1.vm.box = "bento/ubuntu-20.04"
    org1.vm.network "public_network", ip: "192.168.0.201", bridge: "enx00e04c680559" # Remove bridge attribute if not working
  end
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "1"
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end  
end
