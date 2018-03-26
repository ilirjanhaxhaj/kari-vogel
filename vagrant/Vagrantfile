Vagrant.configure("2") do |config|
  config.vm.define "ilirjan" do |subconfig|
    subconfig.vm.box = "bento/ubuntu-16.04"
	subconfig.vm.hostname = "ilirjan"
	subconfig.vm.network :private_network, ip: "172.20.10.15"
	subconfig.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.provision "shell", inline: <<-SHELL
	sudo apt-get update
	sudo apt-get -y install apache2
  SHELL
  end

  config.vm.define "node1" do |subconfig|
    subconfig.vm.box = "bento/ubuntu-16.04"
    subconfig.vm.network :private_network, ip: "172.20.10.16"
  end

  config.vm.define "node2" do |subconfig|
    subconfig.vm.box = "bento/ubuntu-16.04"
    subconfig.vm.network :private_network, ip: "172.20.10.17"
  end
  config.vm.provision "shell", inline: <<-SHELL
  apt-get install -y avahi-daemon libnss-mdns
SHELL
end