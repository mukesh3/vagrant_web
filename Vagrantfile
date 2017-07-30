# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "web", primary: true do |web|
  	web.vm.box ="puppetlabs/ubuntu-14.04-32-nocm"
        web.vm.network "forwarded_port", guest:80, host:8888
        web.vm.synced_folder "vagrantsite/", "/opt/vagrantsite"
        web.vm.provision "shell", inline: "apt-get install -y  nginx; ln -s /opt/vagrantsite /usr/share/nginx/html/vagrantsite"
  end
end

