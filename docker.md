## Comandos DOCKER
docker ps (Verifica cointainers ativos)  
docker ps -a (Verifica containers não ativos)  

## Rodando comandos dentro do container  
docker run -it webserver  

## Removendo containers
docker stop $(docker ps -a -q) (para todos os containers ativos)    
docker rm webserver2 -f (para e remove o container)    
docker stop $(docker ps -a -q) (parar todos os containers)  
docker rm $(docker ps -a -q) (remover todos os containers)  

# Removendo images
docker system prune -a (Remove todas as imagens)  
