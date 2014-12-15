# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.synced_folder "pipeweb/target", "/usr/share/tomcat7/webapps"

  ## For masterless, mount your salt file root
  config.vm.synced_folder "salt/roots/", "/srv"

  ## Use all the defaults:
  config.vm.provision :salt do |salt|
    salt.run_highstate = true
    salt.minion_config = "salt/minion.conf"
  end
end
