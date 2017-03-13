# Comandos Linux

### Estrutura de pastas linux

/home = pasta de usuarios  
/dev = devices  
/media = driver de cd  
/root = estrutura de pasta do root/superusuario  
/tmp = logs etc  
/etc=arquivos de configuracao  
/var=conteudo de arquivos logs, mysql  
/bin=executavel  
/user/bin=executaveis  
/lib=bibliotecas  

### Comandos Básicos

`mkdir` = criar diretorio  
`touch` = criar arquivo  
`ls -l` = ver tipos de arquivo  
`touch .qualquernome` = criação de arquivo oculto  
`ls -la` = lista todos os arquivos, até ocultos  
`rm` = remover arquivo   
`rm arquivo`  = remove um unico arquivo  
`rm -rf diretorio` = remover um diretorio  
`rm -rf *` = remove tudo dentro de um contexto  
`mv arquivo nomenovo` = renomear arquivo  
`sudo chown euller diretorio`= muda o dono do arquivo  
`find . -name arquivo` = buscar um arquivo  
`find . -name "oi*"` = buscar um arquivo  
`ls -la | grep oi` = busca arquivos com um filtro  
`ln -s framework framework2` = cria um link simbolico de framework pra framework2  
`cat arquivo` = exibe o conteudo de uma arquivo  
`top` = tempo real de tudo que está acontecendo na máquina  
`whoami` = mostra o usuário logado  
d=diretorio , a = arquivo, s=socket  

### Permissões de Arquivo

USUARIO  |GRUPO  | OUTROS (USUARIO ANONIMO)  
rwx        rwx     rwx  
r=read w=write x=execute  

### Permissões CHMOD

`chmod u+x arquivo.txt` - Adicionar permissão de usuario para executar  
`chmod g+r arquivo.txt` - Adicionar permissão de leitura para o grupo  
`chmod g=rwx arquivo.txt`  
Para retirar uma permissão basta usar o comando - (menos)                       
`chmod 644` = UGO  
`chmod -R 777` = Todos os arquivos e subpastas terão a permissão  

### Atenção 

Cuidado com permissões CHMOD 777 - Ultimo 7, deixa até o usuário anonimo ler executar e escrever no arquivo (MUITO SÉRIO)  

### Instalando Pacotes

#### Distribuições baseadas no debian (ubuntu, mint, etc)

`su` ou `sudo su` - = logar como root    

### Instalando PHP, Apache e Mysql  
`php -i | grep pdo`  
`sudo apt-get install php5`  
`sudo apt-get install apache2`  
`sudo apt-get install mysql-server libapache2-mod-auth-mysql php5-mysql`  
`sudo apt-get install php5-mysql`  
`sudo apt-get install phpmyadmin`  
`sudo vim /etc/apache2/apache2.conf`  
e adiciona no final do arquivo:  
`Include /etc/phpmyadmin/apache.conf`  

### Instalando PHPStorm

`sudo apt-get purge openjdk*`  
`sudo add-apt-repository ppa:webupd8team/java`  
`sudo apt-get update`  
`sudo apt-get install oracle-java7-installer`  
`sudo apt-get install oracle-java7-set-default`  
`wget http://download-cf.jetbrains.com/webide/PhpStorm-10.0.2.tar.gz`  
`tar -xvf PhpStorm-10.0.2.tar.gz`  
`cd PhpStorm-143.1184.87/bin/ ` 
`./phpstorm.sh`  

#### Distribuições baseadas no Arch (antergos, manjaro, etc)

yaourt {pacote} (pesquisar um pacote)  
yaourt -S {pacote} (instalar um pacote diretamente)  
yaourt -R {pacote} (remover um pacote)  
yaourt -Syu (atualizar o sistema)

### Resolvendo issue IBUS PHPSTORM 

http://serverfault.com/questions/735189/ibus-1-5-11-on-ubuntu/735381#735381

### Comandos Mysql/Apache

Acessar mysql via terminal  
mysql -h localhost -u root -p  
Reiniciar/Parar/Iniciar o apache  
sudo service apache2 restart  
sudo service apache2 stop  
sudo service apache2 start  
