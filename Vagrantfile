# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure(2) do |config|

  config.vm.provision "shell", path:"install_docker.sh"

  config.vm.define "calicoserver" do |calicoserver|
    calicoserver.vm.hostname = 'calicoserver'
    calicoserver.vm.box= "ubuntu/trusty64"
    calicoserver.vm.box_url = "ubuntu/trusty64"

    calicoserver.vm.network :private_network, ip: "172.22.101.9",
      nic_type: "82545EM"

    calicoserver.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "calicoserver"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
    end
  end

  config.vm.define "calicoh1" do |calicoh1|
    calicoh1.vm.hostname = 'calicoh1'
    calicoh1.vm.box= "ubuntu/trusty64"
    calicoh1.vm.box_url = "ubuntu/trusty64"

    calicoh1.vm.network :private_network, ip: "172.22.101.10",
      nic_type: "82545EM"

    calicoh1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "calicoh1"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
    end
  end

  config.vm.define "calicoh2" do |calicoh2|
    calicoh2.vm.hostname = 'calicoh2'
    calicoh2.vm.box= "ubuntu/trusty64"
    calicoh2.vm.box_url = "ubuntu/trusty64"

    calicoh2.vm.network :private_network, ip: "172.22.101.11",
      nic_type: "82545EM"

    calicoh2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "calicoh2"]
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
    end
  end

end
