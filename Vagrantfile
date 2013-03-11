# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = 'precise64'
  config.vm.box_url = 'http://files.vagrantup.com/precise64.box'

  config.vm.customize ['modifyvm', :id, '--memory', 2048]
  config.vm.host_name = 'openam.vagrant.dev'

  config.vm.network :hostonly, '192.168.33.10'
  config.vm.forward_port 80, 8080

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet"
    puppet.manifest_file = "site.pp"
    puppet.module_path = "puppet/modules"
  end
end
