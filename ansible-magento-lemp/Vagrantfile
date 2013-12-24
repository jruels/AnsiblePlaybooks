# Vagrantfile
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "Centos6.4"
 # config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  # config.vm.network :private_network, ip: "192.168.111.222"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
   ansible.verbose = "vvvv"
  end

  config.vm.network :forwarded_port, guest: 8080, host: 3751
  config.vm.network :forwarded_port, guest: 80, host: 3750
  # config.vm.network :private_network, ip: "192.168.33.10"
  # config.vm.network :public_network

  # config.ssh.forward_agent = true

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024", "--name", "ansible-plaything"]
  end
end
