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

`cat arquivo` = Exibe o conteúdo de um arquivo  
`cd` = Mudar de diretório  
`chmod` = Mudar proteção de um arquivo  
`chown` =  Mudar o DONO e o GRUPO dono de um arquivo ou diretório  
`cp` = Copia arquivos  
`file` = Mostra o tipo de um arquivo  
`find . -name arquivo` = Buscar um arquivo  
`find . -name "oi*"` = Buscar um arquivo  
`ln` =  Cria um link entre diretórios e arquivos  
`ln -s framework framework2` = Cria um link simbólico de framework pra framework2  
`ls` = Listar arquivos  
`ls -l` = Ver tipos de arquivo  
`ls -la` = Lista todos os arquivos, até ocultos  
`ls -la | grep oi` = Busca arquivos com um filtro  
`mkdir` =  Criar diretório    
`mv` = Move arquivos  
`mv arquivo nomenovo` = Renomear arquivo  
`pwd` = Exibe o diretório  
`rm` = Remover arquivo  
`rm arquivo`  = Remove um único arquivo  
`rm -rf diretorio` = Remover um diretorio  
`rm -rf *` = Remove tudo dentro de um contexto  
`rmdir` = Remove um diretório vazio  
`sudo chown euller diretorio`= Muda o dono do arquivo  
`tar` = Armazena ou extrair arquivos .tar  
`top` = Tempo real de tudo que está acontecendo na máquina  
`touch` = Criar arquivo vazio  
`touch .qualquernome` = Criação de arquivo oculto  
`whoami` = Mostra o usuário logado  

d = diretorio , a = arquivo, s = socket  

### Permissões de Arquivo

USUARIO  |GRUPO  | OUTROS (USUARIO ANONIMO)  
rwx        rwx     rwx  
r=read w=write x=execute  

### Permissões CHMOD

`chmod u+x arquivo.txt` - Adicionar permissão de usuario para executar  
`chmod g+r arquivo.txt` - Adicionar permissão de leitura para o grupo  
`chmod g=rwx arquivo.txt`  
Para retirar uma permissão basta usar o comando - (menos)    

0 - permissão negada  
1 - permissão de execução  
2 - permissão de gravação  
3 - permissão de gravação e execução  
4 - permissão de leitura  
5 - permissão de leitura e execução  
6 - permissão de leitura e gravação  
7 - soma de todas as permissões  

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

### Instalando PHP 7 no Ubuntu
Rode os comandos abaixo em sequencia. 
```
sudo apt-get install -y language-pack-en-base
sudo LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt-get install zip unzip
sudo apt-get install -y php7.0 php7.0-fpm php7.0-mysql php7.0-zip php7.0-gd
sudo apt-get install nginx git
```

Pacotes Importantes
```
sudo apt-get install mcrypt php7.0-mcrypt
sudo apt-get install -y php7.0-mbstring php7.0-xml --force-yes
```

Pacotes Opcionais
```
sudo apt-get install php7.0-curl php7.0-json
```

**NOTE:** Você pode usar o comando abaixo para visualizar os pacotes disponiveis para o PHP 7.0: 
```
sudo apt-cache search php7-*
```
### Alterando a configuraçao do PHP.ini
```
sudo nano /etc/php/7.0/fpm/php.ini
```
Descomente e corrija `cgi.fix_pathinfo` para 
```
cgi.fix_pathinfo=0
```
Reinicie PHP 7.0 FPM 
```
sudo service php7.0-fpm restart
```
