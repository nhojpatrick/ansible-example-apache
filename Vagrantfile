# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "centos/7"

  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false

    vb.cpus = "1"
    vb.memory = "1024"

    vb.customize ["modifyvm", :id, "--audio", "none"]
  end

  config.vm.define "webhost0", autostart: true do |inst|

    inst.vm.hostname = "webhost0"

  end

end
