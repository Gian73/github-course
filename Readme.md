# Github
https://help.github.com/pt/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

Utilizando controle de versão:
Configurando o Git para usuario:$ git config --global user.name "giancarloc"
Configurando o email: $ git config --global user.email "gincarloc@ciandt.com"
Configurando editor de texto: $ git config --global core.editor  MingW
Para saber o user name: $ git config user.name
Para saber o user email:$ git config user.email
Para mostra tudo no git: $ git config --list

Inicializando um repositorio:
Criar pasta:$ mkdir ( nome do projeto) git-course
Entrar na pasta: $ cd git-course/( git-nome do projeto )
inicializando: git init
Para voltar um diretorio: cd ..
Para mostrar o que tem na pasta e o arquivo .git: la -la
Para alterar um arquivo: $ Vi ( nome do arquivo a ser editado)
Obs. usei Vi, mas pode ser outro de sua preferencia, nesse caso como estou usando o windows, ficou mais facil.
Já dentro do vi( Vim ), para poder começar a inserir algo digite: i( entra no modo de inserção).
Depois de inserido as informações que vc quiser clique em: Esc ( vai sair do modo de inserção).
Para indicar que vai começar algum comando digite: (:)
Para sair e salvar digite: WQ
Para listar tds seus arquivos digite: lsgit
Para ver como esta esta seu repositorio, ver os commits digite:git status
Para criar uma pasta pelo VIM: digite VIM e o nome da pasta que vc quer criar.
Para adicionar a pasta no respositorio para da um commit: Exemplo:git add Readme.md
Exemplo de um commit: $ git commit -m "ADD Readme.md", entre aspas vc coloca aquilo que vc quer passar.
Para ver os commits(quem fez, data de modificação)digite: git log
Para ver mais detalhes podemos usar o: git log --decorate
Para encontrar tudo que esta no seu nome ou de quaquer pessoa digite: git log --author= "nome do author"
Para ver quantos commits, em ordem de quem fez e quais foram digite: git shortlog
para saber só os nomes e quantidade de commits: git shortlog -sn
Para ver em forma grafica o que esta acontecendo com as versões com:git log --graph
Para ver o que foi add a rash: git show + a rash
Para ver as mudanças antes de fazer um commit: $ git diff
Para ver só o NOME DO ARQUIVO QUE FOI MODIFICADO: $ git diff --name-only
Depois de alterar algo no seu arquivo e salvar, caso não queira mais esta alteração digite: $ git checkout Readme.md
Tirar aquivo da fila de stade: $ git reset HEAD Readme.md
Para fazer um commit: $ git commit -am "Aula top"
git reset -- soft: Mata o commit, mas não altera no arquivo
git reset -- mixed: volta para o estado modifield
git reset -- hard: ignora o commit e tudo que foi feito nele

Gerar uma nova chave SSH
Open Git Bash.
Cole o texto abaixo, substituindo o endereço de e-mail pelo seu do GitHub.
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
O comando criará uma nova chave SSH, usando o e-mail fornecido como uma etiqueta.
> Gerar par de chaves rsa pública/privada.
Quando aparecer a solicitação "Enter a file in which to save the key" (Insira um arquivo no qual salvar a chave), presssione Enter. O local padrão do arquivo será aceito.
> Insira um arquivo no qual salvar a chave (/c/Users/you/.ssh/id_rsa):[Press ENTER
$ cd ~/.ssh/  para entrar na raiz da pasta
$ ls vai mostrar a pasta com os arquivos criados no SSH.
$ cat id_rsa.pub para mostrar a chave.
Copie e cole essa chave e coloque no Gitgub:em settings>SSH and GPG Keys>New SSH Key> cole a chave e de um nome> só clicar em criar.
Ligando o repopsitorio local com o do remoto (github)
Para criar o caminho remoto digite: $ git remote add origin  git@github.com:Gian73/github-course.git
Para mostrar a origem remota: $ git remote ou git remote -v para mostrar todo o caminho.
Para enviar tds arquivos para o repositorio remoto: $ git push -u origin master
Depois de alterar seu aquivo e quiser subir as alterações basta digitar gitpush origin master
Para criar um clone do repositorio, sair da raiz e digitar:$ g clone git@github.com:Gian73/github-course.git(só um exemplo)
Para criar um Branch: $ git checkout -b testing( testing é o nome que eu escolhi para meu Branch)
$ git branch:  mostra as brachs que vc tem e com um Asterisco mostra em qual vc esta no momento.
Para voltar para brach Master por exemplo: $ git checkout master
Apagando uma Branch: $ git branch -D testing

Merge:
Criar uma pasta:$ mkdir rebase-merge
para ver se foi criada: $ cd rebase-merge/
inicializando o repositorio: $ git init
Criar um arquivo foo: $ vim foo
Escreva no arquivo, depois digite esc,:,wq
Depois para adicionar: $ git add foo
Depois um commit:$ git commit -m "Ada foo"
OBS. pode criar varias Brachs
Para unir as branchs digite: $ git merge(o nome da branch) test

Rebase:
Criar um arquivo buzz: $ vim buzz
Escreva no arquivo, depois digite esc,:,wq
Depois para adicionar: $ git add buzz
Depois um commit:$ git commit -m "Ada buzz"
Criar novo branch: $ git checkout -b 'rebase-branch'
OBS. pode criar varias Brachs
Para chamar a Branch e jogar para o topo dalista: $ git reabse rebase-branch

Criando o gitignore:
Criando arquivo ignore: $ vi .gitignore
Dentro dele posso passar o que eu quero que ignore na hora de subir por exemplo tudo que for .jason.
Só digita dentro do vim(nome caso)* .jason e salvar.
Nesse link podemos encontrar varios padrões prontos: https://github.com/github/gitignore

Git stash:Guardar informações que ainda não foram comitadas.Como?
Entra pelo Vim( meu caso )faça as alterações e salve.E no git, digite: $ git stash.
Voce esta dizendo que ainda esta trabalhando naquela branch.
Para aplicar as mudanças que ficaram guardadas digite: $ git stash apply.
Mostrar a lista de tds stash que voce tem: $ git stash list
Se não quer mais usar, digite: $ gir stash clear

Comando alias para que server?
Exemplo se voce não quer toda hora digitar status, voce pode abreviar da seguinte forma.
$ git config --global alias.s status, prontoagora voce digita só o s( para status)
Serve para tds comandos.

Versionando Tags:
$ git tag -a 1.0.0( versão) -m( para colocar uma mensagem) "Readme finalizado"
Subindo a tag: $ git push origin master --tags

Git Revert:
EX: altere o arquivo, salve e comita.
De um $git log e pega o commit e colca da seguinte forma: $ git revert 5b6e8d8s7s7s7s7s7s7sxhb
Pronto foi revertido.
Depois de salvar, digite: $ git show 5b6e8d8s7s7s7s7s7s7sxhb.
Vai mostra o que foi apagado.

Apagar tags e brachs do repositorio local e remoto:
Local: $ git tag -d 1.0.1( exemplo )
Remota: git push origin :1.0.1( exemplo)
O mesmo se aplica para branch

Comandos do VIM:
O vim possui três formas de trabalho: modo de linha, modo de edição e modo de comandos
-r : recupera a última versão do arquivo (o arquivo estava sendo editado quando o vim foi encerrado de forma não normal, por exemplo, devido a falta de energia elétrica).
-R : abre arquivo apenas para leitura.
a : inserir texto após a posição atual do cursor.
A : inserir texto no final da linha atual.
dd : deletar linha atual.
[n]+dd : deletar n linhas a partir da linha atual.
G : ir para o fim do arquivo.
h : voltar um caractere.
H : ir para a primeira linha exibida na tela atual.
i : inserir texto a partir da posição atual do cursor.
I : inserir texto no início da linha atual.
j : descer uma linha.
J : juntar a linha atual com a linha seguinte.
k : subir uma linha.
n : procurar, a partir da posição atual do cursor, a próxima ocorrência do texto definido no último comando /.
N : procurar, a partir da posição atual do cursor e indo em direção ao início do arquivo, a próxima ocorrência do texto definido no último comando /.
o : inserir uma linha em branco após a linha atual.
O : inserir uma linha em branco acima da linha atual.
p : inserir linhas copiadas após a linha atual.
P : inserir linhas copiadas antes da linha atual.
r : substituir o caractere atual.
R : substituir um conjunto de caracteres.
s : deletar o caractere atual e inserir texto.
S : apagar linha e inserir novo texto na linha.
u : desfazer a última alteração feita no texto e ainda não desfeita.
U : desfazer a última alteração feita no texto.
x : apagar caractere onde o cursor está posicionado.
F1 : exibir tela de ajuda.
:q+ENTER : sair da tela de ajuda.
:q! : sair do vim sem salvar as alterações.
:w arquivo : salvar arquivo com o nome especificado.
:wq : sair do vim salvando as alterações.
dd: limpa a linha

Treinamento de logica:
Vetores
Matriz
Condicional encadeada, composta e simples
Estrutura de repetição Faça, Para, Passo e Repita
a <-8+4      //soma
b <- 5-4      //subtrção
c <- 4.5 * 4  // multiplicação
z <- 2^10     // Pontenciação
t <-a+b+c*z  // expressão aritimetica
Operadores Logico E, Não, Ou
Relacionais
= igual
> maior
< menor
>= maior ou igual
<= menor ou igual
Raiz quadrada
# github-course
