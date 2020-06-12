Vagrant.configure("2") do |config|

  config.vm.define "hadoop-pseudo" do |hdfs|
    hdfs.vm.box = "hashicorp/precise64"
    hdfs.vm.hostname = "hadoop-pseudo"
    hdfs.vm.network "private_network", ip: "10.0.0.1/24"
    hdfs.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "setup.yml"
      ansible.host_key_checking = "false"
      ansible.limit = "all"
    end

    hdfs.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "1500"]
    end

  end
  
  config.vm.synced_folder "sync", "/vagrant", create: true
end
