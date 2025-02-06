# Docker Commands

## Obtendo informações docker 
```
docker info
```

## 1 - Gerenciamento de Imagens

### Baixar uma imagem do Docker Hub ou de outro registro de imagens
```
docker pull <imagem>
```
* Exemplo:
```
docker pull nginx
```

### Listar todas as imagens disponíveis localmente
```
docker images
```

### Rodar uma imagem
```
docker run <nome-da-imagem>
```

### Rodar uma imagem por um determinado tempo
```
docker run <nome-da-imagem> sleep 10
```

### Visualizar os processos que estão rodando dentro do container
```
docker top <container> 
```

### Remover uma imagem do sistema
```
docker rmi <imagem>
```
* Exemplo:
```
docker rmi nginx
docker rm nginx
```

### Criar Imagem
```
docker build -t <nome-imagem>
```

### Criar container
```
docker run --name <nome-container> -d <nome-imagem>
```

### Criar container e rodar de forma iterativa
```
docker run -it <nome-container>
 ```

### Verificar se o docker está rodando
```
systemctl status docker
```

### Verificar os containers em execução
```
docker ps
```

### Verificar os containers que estão em execução ou foram executados recentemente
```
docker ps -a
```

### Parar um container
```
docker stop <id-container>
docker stop <name-container>
```

### Remover um container
```
docker rm <id-container>
```

### Listar arquivos dentro de um container
```
docker exec <container> ls
```

### Copiar uma arquivo para dentro de um container
```
docker cp <meu-arquivo> <container>:/<pasta-destino>
```

### Para exibir ionformações de um container
```
docker inspect <container>
```

### Limitar o uso de memória e CPU de um container
Pensando em um container já criado
Ex. Limitando o container a 128MB de memória
Ex. Limitando o cpu em 20%.
```
docker update <container> -m 128M --cpus 0.2
```
Para checkar

```
docker stats <container>
```

### Container com MySQL
-e : variavel de ambiente
-p : porta
```
docker run -e MYSQL_ROOT_PASSWORD=Senha123 --name mysql-A -d -p 3306:3306 mysql
```

* Criando um banco de dados

```
docker exec -it mysql-A bash
```

```
mysql -u root -p --protocol=tcp
```

```
CREATE DATABASE fernandoDB;
```

* Criando um banco de dados e persistindo dados na maquina
-v para indicar o volume
```
docker run -e MYSQL_ROOT_PASSWORD=Senha123 --name mysql-A -d -p 3306:3306 --volume=/data/mysql-A:/var/lib/mysql mysql
```

* Criar um volume
```
docker volume create mysql_data
```

```
docker run -e MYSQL_ROOT_PASSWORD=Senha123 --name mysql-A -d -p 3306:3306 --volume=mysql_data:/var/lib/mysql mysql
```

### Criando uma rede
```
docker network create minha-rede
```

### Criando um container com uma rede
```
docker network create minha-rede
```


### Criando um arquivo tar
Estando dentro do diretorio que deseja compactar

```
tar -czf <nome-arquivo>.tar
```

### Criando um arquivo Dockerfile

```
nano Dockerfile
```


### Exemplo Dockerfile

```
FROM debian

RUN apt-get update && apt-get install -y apache2 && apt-get clean

ENV APACHE_LOCK_DIR="var/lock"
ENV APACHE_PID_FILE="var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

ADD arquivo.tar /var/www/html

LABEL description = "Apache webserver 1.0"

VOLUME /var/www/html
 

```


### Colocando um arquivo tar dentro de um container
Estando dentro do diretorio que deseja compactar

```
tar -czf <nome-arquivo>.tar
```

