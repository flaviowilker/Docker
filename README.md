# Docker

Cria e executa um continer a partir de uma imagem:
```sh
$ docker run ubuntu
$ docker run ubuntu echo "olá mundo"
$ docker run -it ubuntu
$ docker run -v "/var/www" ubuntu
$ docker run -it -v "C:\Users\flavio\Desktop:/var/www" ubuntu
```

```sh
$ docker run -d dockersamples/static-site
$ docker run -d -P dockersamples/static-site
$ docker run -d -P --name meu-site dockersamples/static-site
$ docker run -d -p 8080:80 dockersamples/static-site
$ docker run -d -P -e AUTHOR="Flavio" dockersamples/static-site
```

```sh
$ docker run -d -p 8080:3000 -v "C:\Users\flavio\Desktop\node:/var/www" -w "/var/www" node npm start
$ docker run -d -p 8080:3000 -v "$(pwd):/var/www" -w "/var/www" node npm start
```

```sh
$ docker exec -it <container_1> ping <container_2>
```


Lista containers:
```sh
$ docker ps
$ docker ps -a
```


Executa um container:
```sh
$ docker start <id_container>
$ docker start -a -i <id_container>
```


Pausa um container:
```sh
$ docker stop <id_container>
$ docker stop -t 0 <id_container>
$ docker stop $(docker ps -q)
```


Apaga um container:
```sh
$ docker rm <id_container>
$ docker rm -f <id_container>
$ docker rm $(docker ps -aq)
```
```sh
$ docker container prune
```


Lista imagens:
```sh
$ docker images
```


Apaga uma imagem:
```sh
$ docker rmi <nome_imagem>
$ docker rmi $(docker images -q)
```


Verifica a porta do container:
```sh
$ docker port <id_container>
```


Verifica o ip da máquina docker:
```sh
$ docker-machine ip
```


Inspeciona um container:
```sh
$ docker inspect <id_container>
```


Criar imagem com Dockerfile:
>Exemplos de nome de arquivo Dockerfile: Dockerfile, node.dockerfile.
```sh
$ docker build -f Dockerfile -t flavio/node:latest .
```
```sh
$ docker run -d -p 8080:3000 flavio/node
```

Logar no DockerHub:
```sh
$ docker login
```


Enviar imagem para o DockerHub:
```sh
$ docker push flavio/node
```


Baixar imagem do DockerHub:
```sh
$ docker pull flavio/node
```


Criar uma rede docker:
```sh
$ docker network create --driver bridge minha-rede
```


Lista redes docker:
```sh
$ docker network ls
```

Inspeciona uma rede docker:
```sh
$ docker network inspect <rede>
```


Criar container em uma rede específica:
>O nome do container que é utilizado para conexão entre os containers da rede docker, no ping por exemplo.
```sh
$ docker run -it --name meu-ubuntu --network minha-rede ubuntu
```


Realiza o build dos containers de acordo com o arquivo docker-compose:
```sh
$ docker-compose build
```


Sobe todos os serviços criados pelo docker-compose:
```sh
$ docker-compose up
$ docker-compose up -d
```


Lista os serviços do docker-compose:
```sh
$ docker-compose ps
```


Derruba os serviços do docker-compose:
```sh
$ docker-compose down
```
