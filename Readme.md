# Git Commands

## Comandos básicos
Para conferir a versão do git instalado:<br>
```sh
git --version
```

<br>

Para ver o status do arquivo<br>
```sh
git status
```

## Configuracoes de usuario
```sh
git config --global user.name "Fernando Dias" 
git config --global user.email "email@gmail.com" 
```

## Para visualizar as configuracoes 
```sh
git config --list
```

## 1- Iniciar um repositório
```sh
git init
```

## 2- Adicionar arquivos
```sh
git add nomearquivo.txt (Para adicionar um arquivo especifico) <br>
git add --all / git add -A / git add . (essas três maneiras adiciona o dieretório inteiro)<br>
```

### 2.1- Ver diferenças ou modificações antes de comittar
```sh
git diff (se não foram adicionadas) 
git cached (se os arquivos já foram adicionados)
```

## 3- Salvar versionamento - COMMIT
```sh
git commit -m "mensagem do que foi alterado"
```

## 4- Para ver o histórico de commits
```sh
git log // git log --oneline
```

## 5- Para voltar um commit especifico
Quando é necessário voltar um commit, basta voce pegar o id do commit obtido no git log<br>
E utilizar com o seguinte comando:<br><br>

(exemplo de id, não precisa digitar o número inteiro.. basta 5..6.. primeiros caracters que o sistema ja entende, mas por via das dúvidas vale a pena colar)<br><br>
```sh
git checkout 6581760a6d3484a2860f814c6816fb439a9061b4 <br> 
```

### 5.1- Caso tenha sido apenas para consulta, basta voltar para a branch principal com o comando:
```sh
git checkout nomedabranch<br>
```

### 5.2- Caso queira voltar um arquivo especifico antes de commitar basta:
```sh
git checkout nomearquivo.txt
```

### 5.3- Caso queira voltar todos os arquivos modificados
```sh
git reset --hard
```

### 5.4 Caso queira remover arquivos não trackeados
```sh
git clean -f
```

## 6- .gitignore
nomearquivo.txt -> para um arquivo especifico<br>
(asterisco).txt -> para uma extensão<br>
pasta/  -> para uma pasta especifica<br>
pasta/(asterisco).txt -> para uma pasta especifica com um extensão especifica<br>
Default gitignore de varias linguagens ou tipos de projetos -> https://github.com/github/gitignore

## 7- Clonar um projeto
```sh
git clone url-ou-pasta-proejto
```

## 8- Baixar ultima versão da branch
```sh
git pull
```

