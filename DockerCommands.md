# Docker Commands

## 1 - Gerenciamento de Imagens

### 1.1 - Baixar uma imagem do Docker Hub ou de outro registro de imagens
```
docker pull <imagem>
```
* Exemplo:
```
docker pull nginx
```

### 1.2 - Listar todas as imagens disponíveis localmente
```
docker images
```

### 1.3 - Remover uma imagem do sistema
```
docker rmi <imagem>
```
* Exemplo:
```
docker rmi nginx
docker rm nginx
```

### 1.4 - Criar Imagem
```
docker build -t <nome-imagem>
```

### 1.5 - Criar container
```
docker run --name <nome-container> -d <nome-imagem>
 ```

