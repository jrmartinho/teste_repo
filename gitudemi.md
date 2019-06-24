# Curso Udemi
# ===========

## Git e contribuicoes para projetos Open Source
## ---------------------------------------------

sudo apt-get install git

Interface Grafica (Recomendado giteye):
https://git-scm.com/downloads/guis

## Gerando chave ssh:

root@slax:~/teste_repo# ssh-keygen
----
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): 
Created directory '/root/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:puAGUY08cdxygrfQSBoUpZD4DFoGF4JFYSXJeUFyuBc root@slax
The key's randomart image is:
+---[RSA 2048]----+
|*B&&XX..         |
|==BOE.B o        |
|.*+o = =         |
|. +.. .          |
|  ...   S        |
|   o . o         |
|    o .          |
|   .             |
|                 |
+----[SHA256]-----+
----


## Add SSH key na conta do Github. 
Colar conteúdo do arquivo ~/.ssh/id_rsa.pub 
ssh -T git@github.com (teste) 

git help <comando> 
HTTPS://www.git-scm.com (documentação) 

Criar diretório, mudar pra o dir e digitar "git init"  <<ou>> 
git init repo_teste 

ls -al (ver dir .git de configuração do git) 

Criar arquivo README.md (mark down) e digitar "git add arquivo" 
[#] - Titulo H1 do html

git commit 
git config --global user.email "jrmartinho66@gmail.com" 
git config --global user.name "jrmartinho" 
git commit <<ou>>
git commit -m "mensagem do commit"
Editar o título da alteração e salvar 

git status 
git log 

git remote add remote URL 

Entre no Github inclua repo - nome e descrição, publico,  

## Quick setup — if you’ve done this kind of thing before
## ------------------------------------------------------
ref https: https://github.com/jrmartinho/teste1_repo.git
ref ssh: git@github.com:jrmartinho/teste1_repo.git

Get started by creating a new file or uploading an existing file.
We recommend every repository include a README, LICENSE, and .gitignore.

…or create a new repository on the command line
 echo "# teste1_repo" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:jrmartinho/teste1_repo.git
git push -u origin master

…or push an existing repository from the command line
 git remote add origin git@github.com:jrmartinho/teste1_repo.git
git push -u origin master

…or import code from another repository
You can initialize this repository with code from a Subversion,
 Mercurial, or TFS project.

Criando um clone total do repositorio remoto
git clone https://github.com/jrmartinho/teste1_repo.git




