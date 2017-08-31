# Comandos Vagrant

### Comandos Básicos

`vagrant init` - iniciar maquina   
`vagrand up` - subir a maquina   
`vagrant halt` - desligar a maquina   
`vagrant destroy` - destroi maquina virtual   

### Configurando multiplos servidores - Vagrant File

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"

   #SERVER 1
   config.vm.define :ser1 do |a_config|
      a_config.vm.network "forwarded_port", guest: 80, host: 8080
      a_config.vm.network "private_network", ip: "192.168.33.10"
      a_config.vm.synced_folder "./www", "/var/www/html"
      a_config.vm.provision "shell", inline: <<-SHELL
             apt-get update
             apt-get install -y apache2 php5
             echo "PROVISIONAMENTO TERMINADO, SERVER 1"
       SHELL
   end

   #SERVER 2
   config.vm.define :ser2 do |b_config|
         b_config.vm.network "forwarded_port", guest: 80, host: 8081
         b_config.vm.network "private_network", ip: "192.168.33.11"
         b_config.vm.synced_folder "./www2", "/var/www/html"
         b_config.vm.provision "shell", inline: <<-SHELL
                add-apt-repository ppa:ondrej/php
                apt-get update
                apt-get install -y apache2 php7.0
                echo "PROVISIONAMENTO TERMINADO, SERVER 2"
          SHELL
    end

    #SERVER 3
    config.vm.define :ser3 do | c_config|
             c_config.vm.network "forwarded_port", guest: 80, host: 8083
             c_config.vm.network "private_network", ip: "192.168.33.12"
             c_config.vm.synced_folder "./www3", "/var/www/html"
             c_config.vm.provision "shell", inline: <<-SHELL
                  echo "PROVISIONAMENTO TERMINADO, SERVER 3"
              SHELL
    end

end`
