### INSTALAÇÃO CENTOOS ###
yum install vim wget  
yum docker install -y  
yum install docker -y  
systemctl start docker  
systemctl enable docker  
systemctl disable firewalld  

## COMANDOS DOCKER ##
docker ps (containers em execução)    
docker ps -a (todos os containers)    
docker images (lista todas as images)    
docker run -it centos bash (Entrar dentro do container)  
