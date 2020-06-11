Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/precise64"
  config.vm.network "private_network", ip: "10.0.0.1/24"
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "setup.yml"
    ansible.host_key_checking = "false"
    ansible.limit = "all"
  end
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1500"]
  end
  # config.vm.synced_folder ".", "/vagrant", owner:"www-data", group:"www-data", mount_options:["dmode=775", "fmode=775"]
  config.vm.synced_folder ".", "/vagrant"

end
