
## Instalação DOCKER
sudo apt-get update  
sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D  
sudo apt-add-repository 'deb https://apt.dockerproject.org/repo ubuntu-xenial main'  
sudo apt-get update  
apt-cache policy docker-engine  
sudo apt-get install -y docker-engine  
sudo systemctl status docker  

## Instalação DOCKER COMPOSE

sudo su curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose   
sudo chmod +x /usr/local/bin/docker-compose    
docker-compose --version    

## Criando um container e expondo a porta do vm
docker run -d -p 8080:80 --name name nginx

## Rodando comandos dentro do container
docker exec webserver uname -a    
docker exec -it webserver bash  

## Criando um volume apontando para dados locais
docker run --name webserver2 -p 8081:80 -v /d/projeto/html:/usr/share/nginx/html nginx

## Removendo containers
docker stop $(docker ps -a -q) (para todos os containers ativos)    
docker rm webserver2 -f (para e remove o container)    
docker stop $(docker ps -a -q) (parar todos os containers)  
docker rm $(docker ps -a -q) (remover todos os containers)  

