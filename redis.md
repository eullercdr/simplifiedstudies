## Comandos Redis
redis-cli -h 127.0.0.1 -p 6379 (Conectando ao client docker)  
set "key" value  
get "key"  
delete "key"
keys * (retorna todas as chaves)
"key:id:id:id" value (organizando chaves)  
mset "key" value "key" value (Armazenando multiplos valores)  
keys "resultado*" (retorna todas os indices que contenham resultados)  
