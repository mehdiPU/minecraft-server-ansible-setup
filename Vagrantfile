# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "generic/fedora35"

  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  # I use Qemu as a provider so if you use it as well, you have to install
  # libvirt pluging for Vagrant (vagrant plugin install vagrant-libvirt).
  # If you want to use virtual box (or another provider), you have to
  # change this part and use a Vagrant box that is made for Virtualbox
  # (or the provider you use)
  config.vm.provider :libvirt do |v|
    v.memory = 4096
    v.qemu_use_session = false
  end

  config.vm.define "testServer" do |ts|
    ts.vm.hostname = "mfserver.test"
    ts.vm.network :private_network, ip: "192.168.60.4"
  end
end
