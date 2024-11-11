# Vagrantfile
Vagrant.configure("2") do |config|
    # Configuración de la máquina virtual
    config.vm.box = "ubuntu/bionic64"
    config.vm.network "private_network", ip: "192.168.56.10"
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    # Instalación de Apache y configuración del directorio compartido
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      systemctl enable apache2
      systemctl start apache2
    SHELL
  
    # Configuración de la carpeta compartida
    config.vm.synced_folder "./paginas", "/var/www/html"
  end
  