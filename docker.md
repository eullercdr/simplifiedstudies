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

## Rodando comandos dentro do container  
docker run -it webserver  

## Removendo containers
docker stop $(docker ps -a -q) (para todos os containers ativos)    
docker rm webserver2 -f (para e remove o container)    
docker stop $(docker ps -a -q) (parar todos os containers)  
docker rm $(docker ps -a -q) (remover todos os containers)  

# Removendo images
docker system prune -a (Remove todas as imagens)  
