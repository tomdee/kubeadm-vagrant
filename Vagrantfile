Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false

  config.vm.provision :shell, :path => "install.sh"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 4
    vb.memory = "2048"
  end

  config.vm.define "n1" do |c|
      c.vm.hostname = "n1"
      c.vm.network "private_network", ip: "192.168.77.10"
  end

  config.vm.define "n2" do |c|
      c.vm.hostname = "n2"
      c.vm.network "private_network", ip: "192.168.77.11"
  end

  config.vm.define "n3" do |c|
      c.vm.hostname = "n3"
      c.vm.network "private_network", ip: "192.168.77.12"
  end

end
