# -*- mode: ruby -*-
# vi: set ft=ruby

Vagrant.configure("2") do |config|
    # ssh settings
    config.ssh.insert_key = false
    config.ssh.extra_args = ["-D", "1080"]

    # base box settings
    config.vm.box = "moatn/kali-minimal"
    config.vm.box_version = "0.2"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
	    vb.cpus = 2
	    vb.gui = false
    end

    # kali machine setttings
    config.vm.define :kali01, primary: true do |machine|
        machine.vm.host_name = "kali01.local"
        machine.vm.network "private_network", ip: "10.13.37.10"
        machine.vm.provider "virtualbox" do |vb|
            vb.cpus = 2
        end

        # extra kali provisioning/synced folders
	    machine.vm.synced_folder "data/", "/home/vagrant/Documents"

    end

    # room for extra machine config here 

end
