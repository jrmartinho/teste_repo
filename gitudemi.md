## Curso Udemi 
#### (Git e contribuicoes para projetos Open Source)
-----
#### Instalando:
* `sudo apt-get install git`

#### Interface Grafica (Recomendado giteye): https://git-scm.com/downloads/guis
#### Documentacao: https://www.git-scm.com

#### Conectando por chave ssh no Github: (anexo A)
* `ssh-keygen -t rsa -b 4096 -C "email_do_github"`
* Adicionando chave SSH na conta do Github.
  * Colar conteúdo do arquivo ~/.ssh/id_rsa.pub no campo Key em "Add SSH key" no servidor Github.
* Testando `ssh -T git@github.com`
* Trocando a referencia de https por ssh:
  * `git remote set-url origin git@github.com:jrmartinho/teste_repo.git` 
  
#### Utilizando a interface Git
* `git help <comando>`
* Criar diretório, mudar para o diretorio e digitar `git init`  [ou]  
   `git init repo_teste` estando na raiz do diretorio local do Git
* Definindo usuario e Email do Git
  * `git config --global user.email "jrmartinho66@gmail.com"`  
  * `git config --global user.name "jrmartinho"`  
  * `git config -l`  
* `ls -al` (ver diretorio .git de configuração do git) 
* Criando um clone total do repositorio remoto  
  * `git clone https://github.com/jrmartinho/teste_repo.git`  
[ou]
* Criar arquivos iniciais:
  * Mudar para o diretorio e criar arquivo README.md (markdown - anexo C)
  * `git add README.md` [ou] `git add .`
  * `git commit` e editar mensagem do commit [ou] `git commit -m "mensagem do commit"`  
  * `git push`  
-----
* Comandos para verificacao: `git status` e `git log`  
-----

git remote add remote URL  
Entre no Github inclua repo - nome e descrição, publico,  






### Anexo A: Utilizando chave ssh para se conectar ao Github

>ref https: https://github.com/jrmartinho/teste_repo.git  
>ref ssh: git@github.com:jrmartinho/teste_repo.git  

[\[Git+GitHub\] Evitando Informar Usuário e Senha a cada Push para o GitHub]
(https://medium.com/@andgomes/git-github-evitando-informar-usu%C3%A1rio-e-senha-a-cada-push-para-o-github-d8edbb5c6de4)

* ssh-keygen -t rsa -b 4096 -C "email_do_github"  
 Se apenas pressionarmos Enter, o nome e a localização padrão
 serão utilizados(/home/usuário/.ssh/id_rsa).
 Após isso, também será solicitada uma senha para a chave,
 que não precisa ser a mesma senha da conta do GitHub.  
* ssh-add ~/.ssh/id_rsa  
 Copie todo o conteúdo do arquivo id_rsa.pub e cole no campo Key em "Add SSH key".  
 Para utilizar a chave SSH automaticamente, é necessário alterar a
 URL HTTPS para uma URL SSH.  
* git remote -v  
 origin https://github.com/andgomes/my-repo.git (fetch)  
 origin https://github.com/andgomes/my-repo.git (push)  
* git remote set-url origin git@github.com:andgomes/my-repo.git  


### Anexo B: Quick setup — if you’ve done this kind of thing before  
Get started by creating a new file or uploading an existing file.  
We recommend every repository include a README, LICENSE, and .gitignore.  

…or create a new repository on the command line  
 echo "# teste_repo" >> README.md  
 git init  
 git add README.md  
 git commit -m "first commit"  
 git remote add origin git@github.com:jrmartinho/teste_repo.git  
 git push -u origin master  

…or push an existing repository from the command line  
 git remote add origin git@github.com:jrmartinho/teste1_repo.git  
 git push -u origin master  

…or import code from another repository  
 You can initialize this repository with code from a Subversion,  
 Mercurial, or TFS project.  

#### Anexo C: Markdown dicas:
[Ref: https://www.markdowntutorial.com](https://www.markdowntutorial.com)

* Titulo H1 a H6 - \#, \##, ..., \######
* **Bold**, _Italico_ - `**Bold**, _Italico_` 
* Blockquotes - > Paragrafo
* Lista e Lista Numerada - `* I1`
```
                            * I2
                            * I3
```
* Lista e Lista Numerada - `1. I1`
```
                         2. I2  
                           2.1. I2a  
```
* Imagem - `![Texto alternativo](Arquivo.png)`  
* Tag - `Texto[Tag][nome do tag]`  
        `[nome do tag]: [link/endereco do tag]`  
* Paragrafo `- Hard code (digitar um enter a mais)`  
            `- Soft code (digitar dois espacos ao fim da linha)`  
