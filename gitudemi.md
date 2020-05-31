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
* Definindo usuario, email do Git e editor padrao
  * `git config --global user.email "jrmartinho66@gmail.com"`  
  * `git config --global user.name "jrmartinho"`  
  * `git config --global core.editor leafpad`  
  * `git config -l`  
* `ls -al` (ver diretorio .git de configuração do git) 
* Criar arquivos iniciais:
  * Mudar para o diretorio e criar arquivo README.md (markdown - anexo C)
  * `git add README.md` [ou] `git add .`
  * `git commit` e editar mensagem do commit [ou] `git commit -m "mensagem do commit"`  
  * `git push`  
---
* Comandos para verificacao:
 * `git status` e `git log`
 * `git diff HEAD~1` - alteracoes do ultimo commit 
---
- Estados dos arquivos:
  * Nao monitorados (untracked)
  * Modifcado (modified)
  * Preparado (staged)
  * Consolidado (commited)
--- 
* Criando um clone total do repositorio remoto no local  
  * `git clone https://github.com/jrmartinho/teste_repo.git`  
  * `git remote -v` 
* Baixando as alteracoes do repositorio remoto para o local  
  * `git pull https://github.com/jrmartinho/teste_repo.git`  
* Baixando as alteracoes do repositorio remoto de um commit especifico para o local
  * `git log`  
  * `git checkout d6a21b3`
* Baixando as alteracoes do repositorio remoto do ultimo commit para o local
  * `git checkout master`
* Desfazer alteracoes correntes no local
  * `git diff` para ver modificacoes
  * `git checkout -- arquivo` ou `git checkout -- .` para todos
---
## nao funcionou
* Desfazer alteracoes do ultimo commit enviado ao remoto
  * `git checkout HEAD -- arquivo` ou `git checkout HEAD -- .` para todos
* Usei `git checkout num.commit arquivo`
* `git add .`,`git commit -m "retornando ao commit num.commit"`,`git push` 
  
--- 
git remote add remote URL  
Entre no Github inclua repo - nome e descrição, publico,

---
**Lição Aprendida**

Se `git remote -v ` aparecerem outros repositorios reveja a variável global e redefina se necessário 
* `git config -l`
* `git config --global remote.origin.url https://github.com/jrmartinho/teste_repo.git` 


### Seção 4: Branching, Merge e Rebase

#### Branching
-----------
git branch (qual branch estou)  
git status

git branch <nova_branch> (cria branch)  
git branch -d <branch>  (apaga branch)

git checkout <branch>  (muda para a branch)

altere o arquivo  
git add .  
git commit -a  
git push (apresenta erro por não existir a nova branch)  

git push -u (--set-upstream origin <branch>  (cria e atualiza novaBranch no remoto)

Os arquivos estão diferentes na master e novaBranch  

git checkout master (muda para a branch master)  
notepad arquivo (altere)  
git add .  
git diff  
git commit  
git push  

Observar em Insights/network com ficam as branchs depois dos push

#### Git Merge
---  

git checkout master  
git merge novaBranch  

editar os arquivos em conflito  
git add .
git commit  
git push  

Observar em Insights/network com ficam as branchs depois dos push


#### Git Rebase
---  
git checkout -b branch2 (cria a branch e muda para branch2)  

git checkout master  
altera arquivos  
git add .  
git commit  
git log  

git checkout branch2  
altera arquivos  
git add .  
git commit  
git log  

git rebase master

notepad (edit) nos conflitos  

git status  
git add .  
git rebase --continue  
git log  
git diff HEAD~1 HEAD  
git diff HEAD~2 HEAD~1 (os commits se unificam)  


#### Git Fetch
---  

Baixa as atualizações do remote porém não aplica elas no repositorio  
pull = fetch + merge

git fetch  
git rebase  

notepad nos conflitos  
git add .  
git rebase --continue (ate acabarem os conflitos)  

git push


#### Git Tag
---  

git tag tagname  
git pull origin tagname  

### Seção 5: Colaboração com Open Source

#### Interfaces graficas 

* Egit - Plugin p/Eclipse  
* GitEye - Linux, W e Mac

#### Estrelas
* Dar estrelas e seguir
 
#### Fork e issues (Questoes/Bug/Tarefas a serem resolvidas)
* Fork copia de outro e depois pode devolver para integrar novamente
* Issues Permite expor bug ou solicitação ao publico e depois das alterações/commit
Fechar a issue com commit Close #Numero da issue

#### Pull request e Workflow
* Pull request - submissão para analise e integraçao a master 
* Fiz o Pull request pelo site do github
* Workflow - https://guides.github.com/introduction/flow/

#### Verificando e aceitando a Pull request
* git fetch origin pull/ID/head:Branching
* git checkout Branching
* git log
* No site aceitar o merge com a master
* git checkout master
* git pull
* _Editar o desejavel_
* git status
* git add .
* git commit
* git push

### Seção 6: Alem do basico

#### Git Ignore
* criar arquivo .gitignore e incluir as exclusões
* Configura os arquivos que devem ser ignorados pelo git, e não serão levados ao repositorio.

#### Commit Amend
Permite adicionar no mesmo commit anterior já feito outras alterações antes do push.
* git commit --amend

#### Stash
Permite pular entre branchs sem efetuar commit e permite salvar as alteraçoes a parte  retornar com as alterações
* altera algo na master e não commit
* muda para a branch e se não divergir incorpora mudança
* na branch sem mesmo alterar da commit
* retorna para a master e a alteração nao aparece (mas foi editado nesta master)
* ainda na master inclui outra linha diferentes
* se tentar mudar para outra branch sem commit antes reclama.
* usar o comando git stash, remove a alteração do arquivo e emplilha no stash
* git stash list - mostra as alteraçoes empilhadas
* mudo de branch, faço alterações e commit e retorno a master
* na master faço o git stash pop tenho as alterações incorporados q estavam no stash

#### Cherrypick e Blame
Cherryplane - Incorpora um commit anterior a versão atualiza  
Blame - Lista a alterações por linha e commits

#### git bissect
Localiza o commit onde ocorreu uma alteração

* git bisect start
* git bisect bad
* git bisect good numcommit
* pula para um commit e testa o arquivo com cat ou outra forma
* git bisect bad
* testa
* git bisect bad
* testa
* se ok 
* git bisect good
* git bisect reset

Exercicio - http://www.git-game

#### GitHub Pages
Cria pagina web para o repositorio

#### GitHub Milestones
Facilita acompanhar atualizacoes bugfix
- https://guides.github.com/features/issues/  

#### WebHooks
Teste de programa/codigo

#### GitKraken GUI
Outra indicação de GUI para o GitHub

https://gitkraken.com

---
---
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

---
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

---
### Anexo C: Markdown dicas:
[Ref: https://www.markdowntutorial.com](https://www.markdowntutorial.com)
[Ref: https://www.markdownguide.org](https://www.markdownguide.org)  
* Titulo H1 a H6 - \#, \##, ..., \######
* **Bold**, _Italico_ - `**Bold**, _Italico_` 
* Blockquotes - > Paragrafo
* Lista e Lista Numerada
```
   * I1
   * I2
   * I3

   1. I1  
   2. I2  
   2.1. I2a  
```
* Imagem - `![Texto alternativo](Arquivo.png)`  
* Tag - `Texto[Tag][nome do tag]`  
        `[nome do tag]: [link/endereco do tag]`  
* Paragrafo `- Hard code (digitar um enter a mais)`  
`            - Soft code (digitar dois espacos ao fim da linha)`  

---
---