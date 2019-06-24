## Curso Udemi #### (Git e contribuicoes para projetos Open Source)
-----
#### Instalando:

sudo apt-get install git

#### Interface Grafica (Recomendado giteye): https://git-scm.com/downloads/guis

#### Gerando chave ssh:

ssh-keygen

> Generating public/private rsa key pair.

> Enter file in which to save the key (/root/.ssh/id_rsa): 

> Created directory '/root/.ssh'.

> Enter passphrase (empty for no passphrase): 

> Enter same passphrase again:

> Your identification has been saved in /root/.ssh/id_rsa.

> Your public key has been saved in /root/.ssh/id_rsa.pub.

> The key fingerprint is:

> SHA256:puAGUY08cdxygrfQSBoUpZD4DFoGF4JFYSXJeUFyuBc root@slax

> The key's randomart image is:

> +---[RSA 2048]----+

> |*B&&XX..         |

> |==BOE.B o        |

> |.*+o = =         |

> |. +.. .          |

> |  ...   S        |

> |   o . o         |

> |    o .          |

> |   .             |

> |                 |

> +----[SHA256]-----+

> ----


#### Add SSH key na conta do Github. 

Colar conteúdo do arquivo ~/.ssh/id_rsa.pub
 
ssh -T git@github.com (teste) 

git help <comando>
 
HTTPS://www.git-scm.com (documentação) 

Criar diretório, mudar pra o dir e digitar "git init"  [ou]
 
git init repo_teste 

ls -al (ver dir .git de configuração do git) 

Criar arquivo README.md (mark down) e digitar "git add arquivo" 


#### MarkupDown dicas:
#### Titulo H1 do html [#### Titulo H1 do html]
*Bold* [*Bold*] **Italico** [**Italico**]
[> BlockQuotes]
> Blockquotes
> Blockquotes1

[* List]
* Item1
* Item2
   * Item2a
   * Item2b

[1. List Ordered    ]
[    1. List Ordered]
1. Item1
1. Item2
   1. Item2a
   1. Item2b
  

git commit
git config --global user.email "jrmartinho66@gmail.com"
git config --global user.name "jrmartinho"
git config -l
git commit [ou]
git commit -m "mensagem do commit"
Editar o título da alteração e salvar 

git status 
git log 

git remote add remote URL 

Entre no Github inclua repo - nome e descrição, publico,  

Quick setup — if you’ve done this kind of thing before
------------------------------------------------------
ref https: https://github.com/jrmartinho/teste_repo.git
ref ssh: git@github.com:jrmartinho/teste_repo.git

[Git+GitHub] Evitando Informar Usuário e Senha a cada Push para o GitHub
https://medium.com/@andgomes/git-github-evitando-informar-usu%C3%A1rio-e-senha-a-cada-push-para-o-github-d8edbb5c6de4

ssh-keygen -t rsa -b 4096 -C "email_do_github"
 Se apenas pressionarmos Enter, o nome e a localização padrão serão
 utilizados(/home/usuário/.ssh/id_rsa). Após isso, também será solicitada
 uma senha para a chave, que não precisa ser a mesma senha da conta do GitHub.
ssh-add ~/.ssh/id_rsa
 copie todo o conteúdo do arquivo id_rsa.pub e cole no campo Key em "Add SSH key".
 Para utilizar a chave SSH automaticamente, é necessário alterar a
 URL HTTPS para uma URL SSH.
git remote -v
 origin https://github.com/andgomes/my-repo.git (fetch)
 origin https://github.com/andgomes/my-repo.git (push)
git remote set-url origin git@github.com:andgomes/my-repo.git

-
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

-
-

