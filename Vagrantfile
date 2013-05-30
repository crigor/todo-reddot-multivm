Vagrant.configure("2") do |config|
  config.vm.define :db do |db|
    db.vm.box = "vagrant-debian-wheezy"
    db.vm.network :private_network, :ip => "192.168.44.11"
    db.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "apt"
      chef.add_recipe "database"
    end
  end
  config.vm.define :app do |app|
    app.vm.box = "vagrant-debian-wheezy"
    app.vm.network :private_network, :ip => "192.168.44.10"
    app.vm.network :forwarded_port, :guest => 80, :host => 8091
    app.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "apt"
      chef.add_recipe "app"
      chef.json = {:db_host => "192.168.44.11"}
    end
  end
end
