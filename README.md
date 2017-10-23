# Docker

## Comandos úteis
Em algumas situações, o Docker pode conter processos que oca


Parar todos os containers:
```
docker kill $(docker ps -q)
```
Remover todos os containers
```
docker rm $(docker ps -a -q)
```

Remover todas as docker images
```
docker rmi $(docker images -q)
```

## Cuidados

Nunca se esqueça de desativar os logs dos containers Docker em produção. Você não vai querer ter todas as suas instâncias de armazenamento ocupadas com arquivos de logs dantescos. Para desativar os logs, basta adicionar as seguintes linhas no seu docker-compose.yml:
```
logging:
    driver: none
```


