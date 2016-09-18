Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  # configure virtualbox resources
  config.vm.provider "virtualbox" do |v|
    v.memory = 4000
    v.cpus = 1
  end

  # configure vb guest plugin
  config.vbguest.auto_update = true
  config.vbguest.no_install = false

  # private network 
  config.vm.network "private_network", ip: "192.168.10.90"

  # sync folder
  config.vm.synced_folder "app", "/app", type: "nfs", create: true

  # provisioner
  config.vm.provision :ansible do |ansible| 
    #ansible.limit = 'play_vagrant'
    ansible.verbose="-vvv"
    ansible.playbook = "ansible/playbook.yml"
  end
end