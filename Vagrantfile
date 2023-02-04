Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64" 
  config.vm.network "private_network", ip: "192.168.56.101"  
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 22, host: 2222
  config.vm.synced_folder ".", "/vagrant", disabled: false
  config.vm.disk :disk, size: "50GB", primary: true
  config.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
     vb.cpus = "2"
  
  end

  config.vm.provision "shell", inline: <<-SHELL
      apt-get update -y
      apt-get install wget curl git vim make tree ca-certificates gnupg lsb-release -y 
      apt-get install -y apache2 ssh git make tree nano net-tools wget curl
  SHELL
  
end
