# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # config.vm.provider "virtualbox" do |vb|
  #   vb.memory = "512"
  # end

  %w{trusty xenial}.each do |ubuntu_version|
    config.vm.define ubuntu_version do |m|
      m.vm.box = "ubuntu/#{ubuntu_version}64"
    end
  end

  # config.vm.define "travis" do |t|
  #   t.vm.box = "ubuntu/precise64"
  #   t.vm.provider "virtualbox" do |vb|
  #     vb.memory = "1024"
  #   end
  #
  #   t.vm.provision :shell, inline: "apt-get update && apt-get install linux-image-generic-lts-trusty -y"
  # end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "tests/vagrant.yml"
    ansible.verbose = true
    ansible.extra_vars = {
      docker_users: ["vagrant"],
    }
  end

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end
end
