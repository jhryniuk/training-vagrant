# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "hp01" do |v|
    v.vm.hostname = "hp01"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.200"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 256]
      p.customize ["modifyvm", :id, "--name", "hp-hp01"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 1
    end
  end

  config.vm.define "db01", primary: true do |v|
    v.vm.hostname = "db01"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.201"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "hp-db01"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 2
    end
  end

  config.vm.define "db02" do |v|
    v.vm.hostname = "db02"
    v.vm.box = "ubuntu/trusty64"
    v.vm.box_check_update = true

    v.vm.network "private_network", ip: "10.0.0.202"

    v.ssh.forward_agent = true
    v.vm.provider :virtualbox do |p|
      p.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      p.customize ["modifyvm", :id, "--memory", 512]
      p.customize ["modifyvm", :id, "--name", "hp-db02"]
      p.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
      p.cpus = 2
    end
  end
end