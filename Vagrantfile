
Vagrant.configure(2) do |config|
  #Generic provision setup for all vm
  config.vm.box = "generic/ubuntu2004"
  config.vm.boot_timeout = 1800 # 30 minutes
  #Definition of mine ansible node manager
  config.vm.define "ansible.core" do |ansible_core|
    ansible_core.vm.hostname = "ansible.core"
    ansible_core.vm.network "private_network", ip: "192.168.135.10"
    ansible_core.vm.provision "shell", inline: "sudo apt-get update"
    ansible_core.vm.provision "shell", inline: "sudo apt-get install --yes ansible"
    #ansible_core.vm.provision "shell", inline: "sudo apt-get install git --yes" not necesary with generic/ubuntu2004
  end
  #Definition of my machines who will be the targets of my ansible playbook
  config.vm.define "target01" do |target01|
    target01.vm.network "private_network", ip: "192.168.135.11"
    target01.vm.hostname = "target01"
  end

  config.vm.define "target02" do |target02|
    target02.vm.network "private_network", ip: "192.168.135.12"
    target02.vm.hostname = "target02"
  end
end
