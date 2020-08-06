# Comandos Docker

```sh
 # Executa uma imagem
 # -d Executa uma imagem em background
 # -p $local_port:$container_port Faz um roteamento da porta
 # --name define um nome para o container
 docker run -d --name $name -p $local_port:$container_port $image_name || $image_name:$version

 # Mostra todas as imagens sendo executadas
 # -a Lista todas as images até as que não estão sendo executadas
 docker ps

 # Remove um containber
 docker rm $name || $id

 # Remove uma imagem
 docker rmi $name || $id

 # Lista as imagens baixadas
 docker images

 # Finaliza a execução do container
 docker stop $name || $id

 # Executa um container
 docker start $name || $id
```
