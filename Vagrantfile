# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.network :private_network, ip: "192.168.33.99"
  config.vm.network :forwarded_port, guest: 22, host: 2299

  config.vbguest.no_remote = true
  config.vbguest.auto_update = false

  config.vm.define 'ubuntu1404-amd64' do |instance|

    # Every Vagrant virtual environment requires a box to build off of.
    instance.vm.box = 'ubuntu/trusty64'

    # View the documentation for the provider you're using for more
    # information on available options.
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "test.yml"
      ansible.verbose = 'vvvv'
      ansible.sudo = true
    end
  end
end
