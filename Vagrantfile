Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
   config.vm.network "public_network"
  # config.vm.network "private_network", ip: "192.168.0.131"
   config.vm.synced_folder "./ansible", "/ansible"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "Lab_06_Devops"
    vb.memory = "4096"
    vb.cpus = 4
  end
  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install ansible -y 
    ansible-playbook --connection=local /ansible/playbook.yml
  SHELL
end