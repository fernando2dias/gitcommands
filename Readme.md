# Git Commands

## Comandos básicos
Para conferir a versão do git instalado:<br>
git --version<br><br>

Para ver o status do arquivo<br>
git status


## Configuracoes de usuario
git config --global user.name "Fernando Dias" <br>
git config --global user.email "email@gmail.com" <br>

## Para visualizar as configuracoes 
git config --list

## 1- Iniciar um repositório
git init

## 2- Adicionar arquivos
git add nomearquivo.txt (Para adicionar um arquivo especifico) <br>
git add --all / git add -A / git add . (essas três maneiras adiciona o dieretório inteiro)<br>

## 2.1- Ver diferenças ou modificações antes de comittar
git diff (se não foram adicionadas) 
git cached (se os arquivos já foram adicionados)

## 3- Salvar versionamento - COMMIT
git commit -m "mensagem do que foi alterado"

