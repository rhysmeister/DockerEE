Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  # Add 4GB RAM
  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "DockerEE",
      "--memory", "4096"
    ]
  end

  config.vm.hostname = "DockerEE"
  config.vm.network "private_network", ip: "192.168.4.111"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provision :ansible do |ansible|
    ansible.raw_arguments = "--ask-vault-pass"
    ansible.playbook = "DockerEE.yml"
  end

end
