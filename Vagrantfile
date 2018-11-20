# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  if Vagrant.has_plugin?('vagrant-ca-certificates')
    config.ca_certificates.enabled = true
    config.ca_certificates.certs = Dir.glob('/etc/pki/ca-trust/source/anchors/*.crt')
  end
  config.vm.box = "ubuntu/trusty64"
  config.vm.network :forwarded_port, host: 8000, guest: 80
  config.vm.synced_folder ".", "/vagrant"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "nginxdocker.yml"
  end
  config.vm.provider "virtualbox" do |v|
    v.name = "provisioning-ansible"
    v.memory = 2048
  end
end
