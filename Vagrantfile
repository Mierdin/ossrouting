# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
 
  config.vm.box = "trusty64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
 
  config.vm.define "r1" do |r1|
    r1.vm.host_name = "r1"
    r1.vm.network "private_network",
                         ip: "192.168.12.11",
                         virtualbox__intnet: "01-to-02"
    r1.vm.network "private_network",
                         ip: "192.168.31.11",
                         virtualbox__intnet: "03-to-01"
    r1.vm.network "private_network",
                         ip: "1.1.1.10",
                         virtualbox__intnet: "Network to Advertise"
    r1.vm.provision "ansible" do |ansible|
      ansible.playbook = "r1.yml"
    end
  end

  config.vm.define "r2" do |r2|
    r2.vm.host_name = "r2"
    r2.vm.network "private_network",
                         ip: "192.168.23.12",
                         virtualbox__intnet: "02-to-03"
    r2.vm.network "private_network",
                         ip: "192.168.12.12",
                         virtualbox__intnet: "01-to-02"
    r2.vm.network "private_network",
                         ip: "2.2.2.10",
                         virtualbox__intnet: "Network to Advertise"
    r2.vm.provision "ansible" do |ansible|
      ansible.playbook = "r2.yml"
    end
  end

  config.vm.define "r3" do |r3|
    r3.vm.host_name = "r3"
    r3.vm.network "private_network",
                         ip: "192.168.31.13",
                         virtualbox__intnet: "03-to-01"
    r3.vm.network "private_network",
                         ip: "192.168.23.13",
                         virtualbox__intnet: "02-to-03"
    r3.vm.network "private_network",
                         ip: "3.3.3.10",
                         virtualbox__intnet: "Network to Advertise"
    r3.vm.provision "ansible" do |ansible|
      ansible.playbook = "r3.yml"
    end                     
  end

        
end
