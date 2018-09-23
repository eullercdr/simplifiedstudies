## Comandos DOCKER
docker ps (Verifica cointainers ativos)    
docker ps -a (Verifica containers não ativos)    
docker start id-container (Starta o container)   
docker stop id-container (Para o container)   
docker start -a -i id-container (Startar e entrar no modo bash)    
docker container prune (Remove todos os containers inativos)  
docker rmi nomeimagem (Remove a imagem do container)  
docker run -d -P nomeimagem (Atrela as portas do container as portas do computador local)  
docker run -d -P --name [nome] imagedocker (Atribuir um nome ao container e atrelar as portas)    
docker run -d -p portlocal:portacontainer --name [nome] imagedocker   
docker run -d -P -e AUTHOR="BLABLA" imagedocker (Seta uma variavel de ambiente no docker)      
docker port id-container (Lista as portas utilizadas pelo container)  
docker ps -q (Retorna o hash dos containers)  
docker stop -t 0 $(docker ps -q) (Para todos os containers)    

## Volumes
docker run -v "pathlocal:pathcontainer" image (Criando um volume)  
docker run -v -p portalocal:portacontainer "pathlocal:pathcontainer" image (Criando um volume) 
docker inspect id-container (mostra as informações do container)  

## Docker File
docker build -f Dockerfile -t eullercristian/node . (Buildando através de docker file)  

## Docker Hub
docker push eullercristian/node (subindo a imagem)    
docker pull eullercristian/node (baixando a imagem)  

## Criando redes
 docker network create --driver bridge minha-rede (criando uma rede no docker)
