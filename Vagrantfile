# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.cpus = 2
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.define "elkstack" do |elkstack|
    elkstack.vm.hostname = "elkstack"
    elkstack.vm.network :private_network, ip: "172.28.128.30"

    elkstack.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/elk/playbook.yml"
      ansible.inventory_path = "provisioning/elk/inventory"
      ansible.sudo = true
    end
  end

  config.vm.define "app" do |app|
    app.vm.hostname = "app"
    app.vm.network :private_network, ip: "172.28.128.31"

    app.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/web/playbook.yml"
      ansible.inventory_path = "provisioning/web/inventory"
      ansible.sudo = true
    end
  end

end
