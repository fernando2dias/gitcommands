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
git add nomearquivo.txt (Para adicionar um arquivo especifico)
git add --all / git add -A / git add . (essas três maneiras adiciona o dieretório inteiro)
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

### 3.1- Adiciona os arquivos e commita
```sh
git commit -a -m "mensagem do commit"
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
git checkout 6581760a6d3484a2860f814c6816fb439a9061b4 
```

### 5.1- Caso tenha sido apenas para consulta, basta voltar para a branch principal com o comando, ou para acessar uma branch especifica:
```sh
git checkout nomedabranch
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

## 9- Listar as branchs locais
```sh
git branch
```

## 10- Criar uma branch nova
```sh
git branch nomeDaBranch
```

### 10.1- Criar e ja trocar de branch
```sh
git checkout -b nomeDaBranch
```

### 10.2- Subir a branch no servidor
```sh
git push --set-upstream origin nomeDaBranch
ou
git push -u origin nomeDaBranch
```

### 10.3- Como remover uma branch local
```sh
git branch -d nomeDaBranch

em caso de problema, e queira forçar a remoção use -D
git branch -D nomeDaBranch
```

### 10.4- Como remover uma branch servidor
```sh
git push --delete origin nomeDaBranch
```

## 11- Atualização de branch, sempre antes de fazer um gitpush é interessante fazer um git pull para verificar se não tem nenhuma atualização.
```sh
git pull
```

### 11.1- Caso deseje apenas trazer as informações da branch, sem atualizar o conteudo.
```sh
git fetch
```

## 12- Renomear uma branch (estando nela própria)
```sh
git branch -m NovoNomeBranch
```
* OBS: No servidor não é possível renomear, caso seja necessário: Renomear local e subir ela renomeada e excluir a antiga. 


### 12.1 - Renomeando uma branch (sem estar nela)
```sh
git branch -m nomeBranchAntiga nomeBranchNova
```

## 13- Mesclando uma branch
Por exemplo se tiver que mesclar o conteudo da branch develop na master, primeiro eu devo entrar na master.

```sh
git checkout master
```
Sempre é interessante verificar se há atualizações
```sh
git pull
```
Depois finalmente digitar o comando:
```sh
git merge develop
```
Assim você adiciona a branch master tudo que foi criado em develop

### 13.1- Mesclar uma branch aplicando uma na outra
Caso eu esteja na branch master e queira trazer features de uma branch que tenha uma linha temporal diferente da master
```sh
git rebase nomeDaBranch
```

## 14- Criando tags
```sh
git tag -a v1.0 -m "Versão Inicial"
```

### 14.1- Listagem de tags no projeto
```sh
git tag
```

### 14.2- Enviar tag para o servidor
```sh
git push origin nomeDaTag
```

### 14.3- Navegar até uma tag especifica
```sh
git checkout nomeDaTag
```
Lembrando que tudo que você pode modificar a partir desse ponto e commitar fica fora da linha do tempo (HEAD). Este tipo de abordagem é mais recomendado para testes e validações.<br>
Mas caso seja necessário incluir na HEAD, Você pode criar uma branch nova a partir desta branch alterada:
```sh
git checkout -b nomeDaBranchNova idDaBranchGerada
```
Usar somente de último caso.

### 14.4- Remover Tag (Local)
```sh
git tag -d nomeDaTag
```

### 14.5- Remover Tag (Servidor) 
```sh
git push --delete origin nomeDaTag
```

### 14.6- Criar uma tag a partir de um commit especifico
Para ficar mais facil liste os commits

```sh
git log --oneline
```

Depois vá para commit

```sh
git checout idDoCommit
```
Depois adicione a tag
```sh
git tag -a NomaDaTag -m "mensagem"
```
Se for desejo subir no servidor
```sh
git push origin NomeDaTag
```


## 15- Como sair da branch atual sem commitar e salvar para posteriormente continuar
Você salva na memória do git
```sh
git stash
ou 
git stash save "mesnagem"
```

### 15.1- Listar stashs
```sh
git stash list
```

### 15.2- Aplicar o primeiro stash
Suponhamos que voce tenha vários stash, ele sempre vai pegar do mais recente para o ultimo
```sh
git stash apply
(continua com o stash na lista)

git stash pop
(adiciona e ja remove da lista)

```

### 15.2.1- Aplicar uma stash especifica
```sh
git stash pop codigoStash
```

### 15.3- Caso queira remover uma stash da sua lista
```sh
git stash drop codigoStrash
```

## 16- Reverter um commit(Local)
```sh
git reset --hard HEAD~1
```
O número depois do HEAD é a quantidade de commits que desejamos reverter
ATENÇÃO: CASO SEJA REVERTIDO UM COMITT VOCÊ PERDE AS ALTERAÇÕES DO COMMIT


## 17- Adicionar mudanças em um commit já existente (Local)
```sh
git commit --amend
```
Ele abre o VIM Editor de texto, voce pode alterar a mensagem do commit, você aperta ESQ e depois aperte ":"  o cursor para o final da pagina e ele espera um comando. Basta digitar:
```sh
wq
```
w = write
q = quit













