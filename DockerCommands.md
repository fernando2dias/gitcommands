# Docker Commands

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