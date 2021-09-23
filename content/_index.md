+++
title = "Git"
outputs = ["Reveal"]
[reveal_hugo]
custom_theme = "theme.scss"
custom_theme_compile = true
+++

# Git
#### A ferramenta indispensável

---

{{% section %}}

## O que é Git?

---

O Git é uma **um sistema open-source de controle de versão distribuído** mais popular.

---

O Git é usado principalmente para o **desenvolvimento de software**, porém pode ser usado para **registrar o histórico de edições de qualquer tipo de arquivo**.

---

Ser **open-source** significa que qualquer pessoa **utilizá-lo** e **contribuir com o projeto**.

---

Ser um **controle de versão** significa que você pode **controlar e ver o histórico de edições** de um arquivo.

---

Ser um **sistema distribuído** neste caso, significa que todos os que utilizarem em um projeto terão seu **próprio repositório local** com todo o **histórico de versões**.

---

{{< img src="/img/01.svg" >}}

{{% /section %}}

---

{{% section %}}

## História do Git

---

Em **2002** a comunidade do desenvolvimento do kernel Linux começou a utilizar a ferramenta BitKeeper para o controle de versão.

---

Em **2005** a ferramenta BitKeeper começou a ser paga. Então Linux Torvalds (o criador do Linux), criou o Git baseado em lições aprendidas ao usar o BitKeeper.

{{% /section %}}

---

{{% section %}}

## Git é apenas para desenvolvedores?

---

Na verdade não, o Git é **uma ferramenta comum para qualquer pessoa** que deseja trabalhar com versões de documentos e em equipe.

---

O Git permite que grupos de pessoas **trabalhem nos mesmos documentos** (geralmente em código) ao mesmo tempo **sem que um atrapalhe o outro**.

{{% /section %}}

---

{{% section %}}

## Git não é um editor de documento colaborativo

---

Devido as descrições anteriores, sobre o Git permitir que pessoas trabalhem nos mesmos documentos ao mesmo tempo, **pode ter ocasionado um mal entendido**.

---

Se você imaginou o Git sendo um software como com Google Docs...

{{< img src="/img/02.jpg" link="https://blog.softexpert.com/en/edit-and-revise-se-suite-documents-using-google-docs/" >}}

---

Houve um equívoco, a aparência do Git é algo neste estilo, um terminal.

{{% shell %}}
  {{< shell-in c=`# Aqui iremos usar o Git a partir do terminal` >}}
{{% /shell %}}

---

A título de curiosidade, também existe ferramentas externas com interface gráfica, como o [**GitKraken**](https://www.gitkraken.com/).

{{< img height="300" src="/img/03.gif" link="https://www.gitkraken.com/compare/gitkraken-vs-tower" >}}

{{% /section %}}

---

{{% section %}}

## Git no mercado de trabalho

---

{{< img height=" " src="/img/04.png" >}}

{{% fragment %}}Conhecimento de Git muitas vezes acaba sendo implícito nos requisitos das vagas de emprego.{{% /fragment %}}

{{% /section %}}

---

{{% section %}}

## Como funciona o trabalho sem o Git?

---

Para ilustrar este cenário será utilizado um exemplo, que talvez tenha passado alguma vez na vida.

---

{{< img height="600" src="/img/05.gif" link="http://www.phdcomics.com/comics/archive.php?comicid=1531" >}}

---

O Git será **útil para diversos setores**, no caso anterior foi demonstrado o problema que a falta de uma ferramenta de controle de versão pode causar.

---

Foi mostrado um caso de um aluno que estava enviando seu trabalho para um professor, e para cada revisão realizada, ele gerava uma versão nova do documento, porém percebemos que a **metodologia adotada pelo aluno não foi adequada**.

---

O exemplo anterior mostrou um caso acadêmico, no qual quem mantinha o documento era apenas o aluno, posteriormente será abordado **casos no mercado de trabalho**, no qual **o trabalho será realizado em equipe**, mas antes disso é necessário entender a estrutura do Git.

{{% /section %}}

---

{{% section %}}

## Estrutura do Git

---

Utilizando adaptações das definições da [documentação da Microsoft](https://docs.microsoft.com/pt-br/contribute/git-github-fundamentals).

---

### Repositório

Também é conhecido como repo, é a **maior unidade de armazenamento**. Um repositório contém uma ou mais branches.

---

### Branch (Ramificação)

Uma unidade de armazenamento que **contém os arquivos e as pastas** que compõem o conjunto de conteúdo de um projeto.

---

As branches **separam fluxos de trabalho** (normalmente conhecidos como versões). As contribuições sempre são feitas para uma branch específica e estará naquele escopo.

---

Todos os repositórios contêm uma **ramificação padrão** (normalmente chamada "**master**") e uma ou mais ramificações que serão mescladas novamente na ramificação padrão.


---

A ramificação padrão funciona como a versão atual e é "**única fonte de verdade**" para o projeto. Ela é a mãe e todos as outras branches no repositório são criados a partir dela.

---

A aparência das ramificações é a seguinte:

{{< graph key="graph1" orientation="horizontal" code=`
const master = graph.branch("master");
master.commit();

const develop = graph.branch("develop");
develop.commit();

const feature = graph.branch("feature/my-feature");
feature.commit().commit().commit();

develop.merge(feature);
develop.commit();

master.merge(develop)
` >}}

{{% /section %}}

---

{{% section %}}

## Git em diversos setores de trabalho

---

Utilizando adaptações do material da Atlassian "[Why Git for your organization](https://www.atlassian.com/br/git/tutorials/why-git)".

---

### Git para desenvolvedores

---

#### **Fluxo de trabalho**

{{< img src="/img/06.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

#### **Desenvolvimento distribuído**

{{< img src="/img/07.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

#### **Solicitações de inserção**

{{< img src="/img/08.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

#### **Ciclo de lançamento mais rápido**

{{< img src="/img/09.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

### Git para marketing

{{< img src="/img/10.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

### Git para gerenciamento de produto

{{< img src="/img/11.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

### Git para designers

{{< img src="/img/12.svg" link="https://www.atlassian.com/br/git/tutorials/why-git" >}}

---

#### Um extra...

#### {{% fragment %}}**Git para administradores de infraestrutura**{{% /fragment %}}

{{< img src="/img/13.svg" class="fragment" >}}

{{% /section %}}

---

{{% section %}}

## Instalando o Git

---

Se estiver em um ambiente Windows, recomendo utilizar o [Chocolatey](https://chocolatey.org/) para instalar o Git:

{{% shell %}}
  {{< shell-in c=`choco install git` >}}
{{% /shell %}}

---

Se estiver em um ambiente Mac, recomendo utilizar o [Homebrew](https://brew.sh/) para instalar o Git:

{{% shell %}}
  {{< shell-in c=`brew install git` >}}
{{% /shell %}}

---

Se estiver em um ambiente baseado Linux baseado no Debian:

{{% shell %}}
  {{< shell-in c=`sudo apt install git` >}}
{{% /shell %}}

---

Para verificar se o Git foi instalado:

{{% small %}}**A versão ser diferente não é um problema**{{% /small %}}

{{% shell %}}
  {{< shell-in c=`git --version` >}}
  {{< shell-out c=`git version 2.25.1` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Configuração inicial

---

Se estiver usando um ambiente **Windows**, utilize o **Git Bash** que foi instalado em conjunto com o Git.

---

Configurando usuário

{{% shell %}}
  {{< shell-in c=`git config --global user.name "Seu Nome"` >}}
  {{< shell-in c=`git config --global user.email "seu-email@email.com"` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Primeiros passos

---

#### Criação do repositório

{{% shell %}}
  {{< shell-in p="repo" c=`git init repo` >}}
  {{< shell-in c=`cd repo` >}}
{{% /shell %}}

---

#### Verificação da criação do repositório

{{% shell %}}
  {{< shell-in p="repo" c=`ls -A` >}}
  {{< shell-out c=`.git` >}}
{{% /shell %}}

---

#### Criando um arquivo

{{% shell %}}
  {{< shell-in p="repo" c=`echo "Olá Mundo" > arquivo.txt` >}}
{{% /shell %}}

---

#### Verificação da criação do arquivo

{{% shell %}}
  {{< shell-in p="repo" c=`cat arquivo.txt` >}}
  {{< shell-out c=`Olá Mundo` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Ciclo de vida dos arquivos

---

#### Untracked

O Git não está controlando o ciclo de vida deste arquivo

{{% shell %}}
  {{< shell-in p="repo" c=`git status -s` >}}
  {{< shell-out c=`?? arquivo.txt` >}}
{{% /shell %}}

---

#### Staged

O arquivo fará parte parte do próximo commit

{{% shell %}}
  {{< shell-in p="repo" c=`git add arquivo.txt` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`A  arquivo.txt` >}}
{{% /shell %}}

---

#### Unmodified

O arquivo já foi "commitado" e não foi modificado

{{% shell %}}
  {{< shell-in p="repo" c=`git commit -m "Primeiro commit"` >}}
  {{< shell-in c=`git status -s` >}}
{{% /shell %}}

---

#### Modified

O arquivo já foi "commitado" e foi modificado

{{% shell %}}
  {{< shell-in p="repo" c=`echo "Nova Linha" >> arquivo.txt` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=` M arquivo.txt` >}}
{{% /shell %}}

---

Para visualizar as modificações podemos usar o `git diff`:

{{% shell %}}
  {{< shell-in p="repo" c=`git diff arquivo.txt` >}}
  {{< shell-out c=`
 Olá Mundo
+Nova Linha
` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Realizando um commit

---

Adicionando outro arquivo

{{% shell %}}
  {{< shell-in p="repo" c=`touch outro-arquivo.txt` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`
 M arquivo.txt
?? outro-arquivo.txt
` >}}
{{% /shell %}}

---

### `git add`

- {{% small %}}**git add -u**: Apenas arquivos monitorados{{% /small %}}
- {{% small %}}**git add .**: Todos os arquivos (diretório e subdiretórios){{% /small %}}
- {{% small %}}**git add -A**: Todos os arquivos (toda a árvore de trabalho){{% /small %}}

---

{{% shell %}}
  {{< shell-in p="repo" c=`git add -A` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`
M  arquivo.txt
A  outro-arquivo.txt
` >}}
{{% /shell %}}

---

### `git commit`

- {{% small %}}**git commit -m "descrição"**: Descrições menos detalhadas{{% /small %}}
- {{% small %}}**git commit**: Descrições mais detalhadas{{% /small %}}

---

{{% shell %}}
  {{< shell-in p="repo" c=`git commit -m "Segundo Commit"` >}}
{{% /shell %}}

---

Se quisermos alterar o ultimo commit:

{{% shell %}}
  {{< shell-in p="repo" c=`git commit --amend -m "Segundo commit"` >}}
{{% /shell %}}

---

#### `git log`

{{% shell %}}
  {{< shell-in p="repo" c=`git log --oneline` >}}
  {{< shell-out c=`
as1209d (HEAD -> master) Segundo commit
qw3487e Primeiro commit
` >}}

  {{< shell-in c=`git log --pretty=format:"%h | %an - %ar: %s"` >}}
  {{< shell-out c=`
as1209d | Seu Nome - 2 minutes ago: Segundo commit
qw3487e | Seu Nome - 7 minutes ago: Primeiro commit
` >}}

  {{< shell-in c=`git log --oneline --since=5.minutes` >}}
  {{< shell-out c=`
as1209d (HEAD -> master) Segundo commit
` >}}

  {{< shell-in c=`git log --oneline --stat` >}}
  {{< shell-out c=`
as1209d (HEAD -> master) Segundo commit
 arquivo.txt       | 1 +
 outro-arquivo.txt | 0
 2 files changed, 1 insertion(+)
qw3487e Primeiro commit
 arquivo.txt | 1 +
 1 file changed, 1 insertion(+)
` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Ignorando arquivos

---

Criando o `.gitignore`

{{% shell %}}
  {{< shell-in p="repo" c=`touch file.log` >}}

  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`?? file.log` >}}

  {{< shell-in c=`echo '*.log' > .gitignore` >}}

  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`?? .gitignore` >}}

  {{< shell-in c=`git add .gitignore` >}}
  {{< shell-in c=`git commit -m "Ignorando *.log"` >}}
{{% /shell %}}

---

Ignorando arquivos já "commitados"

{{% shell %}}
  {{< shell-in p="repo" c=`git rm --cached outro-arquivo.txt` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`
D  outro-arquivo.txt
?? outro-arquivo.txt
` >}}

  {{< shell-in c=`echo outro-arquivo.txt >> .gitignore` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=`
 M .gitignore
D  outro-arquivo.txt
` >}}

  {{< shell-in c=`git commit -am "Ignorando outro-arquivo.txt"` >}}
{{% /shell %}}

---

Depurar o `.gitignore`

{{% shell %}}
  {{< shell-in p="repo" c=`git check-ignore -v file.log` >}}
  {{< shell-out c=`.gitignore:1:*.log	file.log` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Desfazendo alterações

---

Restaurar arquivos da árvore de trabalho

{{% shell %}}
  {{< shell-in p="repo" c=`echo "Outra linha" >> arquivo.txt` >}}
  {{< shell-in c=`cat arquivo.txt` >}}
  {{< shell-out c=`
Olá Mundo
Nova Linha
Outra linha
` >}}

  {{< shell-in c=`git restore arquivo.txt` >}}
  {{< shell-in c=`cat arquivo.txt` >}}
  {{< shell-out c=`
Olá Mundo
Nova Linha
` >}}
{{% /shell %}}

---

Mudando para um commit específico

{{% shell %}}
  {{< shell-in p="repo" c=`git log --oneline` >}}
  {{< shell-out c=`
lk1209j (HEAD -> master) Ignorando outro-arquivo.txt
po3487i Ignorando secret.txt
as1209d Segundo commit
qw3487e Primeiro commit
` >}}

  {{< shell-in c=`git checkout qw3487e` >}}
  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`qw3487e (HEAD) Primeiro commit` >}}

  {{< shell-in c=`git checkout master` >}}
  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`
lk1209j (HEAD -> master) Ignorando outro-arquivo.txt
po3487i Ignorando secret.txt
as1209d Segundo commit
qw3487e Primeiro commit
` >}}
{{% /shell %}}

---

`git reset`

- {{% small %}}**git reset --soft**: Desfaz Commit. Mantem Stage e modificações{{% /small %}}
- {{% small %}}**git reset --mixed**: Desfaz Commit e Stage. Mantém modificações [**Padrão**]{{% /small %}}
- {{% small %}}**git reset --hard**: Desfaz Commit, Stage e modificações{{% /small %}}

---

{{% shell %}}
  {{< shell-in p="repo" c=`git reset HEAD~2 --hard` >}}
  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`
as1209d (HEAD -> master) Segundo commit
qw3487e Primeiro commit
` >}}
{{% /shell %}}

---

`git revert`

{{% shell %}}
  {{< shell-in p="repo" c=`git revert --no-commit HEAD` >}}
  {{< shell-in p="repo" c=`git commit -m "Revertendo para o primeiro commit"` >}}
  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`
mn2356b (HEAD -> master) Revertendo para o primeiro commit
as1209d Segundo commit
qw3487e Primeiro commit
` >}}
{{% /shell %}}

---

`git reflog`

Reflogs **rastreiam** quando refs Git foram atualizados no repositório local.

{{% /section %}}

---

{{% section %}}

## Utilizando branches

---

Criando uma branch

{{% shell %}}
  {{< shell-in p="repo" c=`git branch outra-branch` >}}
  {{< shell-in c=`git branch` >}}
  {{< shell-out c=`
* master
  outra-branch
` >}}
{{% /shell %}}

---

Deletando uma branch

{{% shell %}}
  {{< shell-in p="repo" c=`git branch -d outra-branch` >}}
  {{< shell-in c=`git branch` >}}
  {{< shell-out c=`
* master
` >}}
{{% /shell %}}

---

Alterar branch

{{% small %}}Para criar uma branch, utilizar a flag **`-c`**.{{% /small %}}

{{% shell %}}
  {{< shell-in p="repo" c=`git switch -c outra-branch` >}}
  {{< shell-in c=`git branch` >}}
  {{< shell-out c=`
  master
* outra-branch
` >}}

  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`
mn2356b (HEAD -> outra-branch, master) Revertendo para o primeiro commit
as1209d Segundo commit
qw3487e Primeiro commit
` >}}
{{% /shell %}}

---

Realizando commits na branch

{{% shell %}}
  {{< shell-in p="repo" c=`echo "Modificação 1" >> arquivo.txt` >}}
  {{< shell-in c=`git commit -am "Modificação 1"` >}}
  {{< shell-in p="repo" c=`echo "Modificação 2" >> arquivo.txt` >}}
  {{< shell-in c=`git commit -am "Modificação 2"` >}}
  {{< shell-in p="repo" c=`echo "Modificação 3" >> arquivo.txt` >}}
  {{< shell-in c=`git commit -am "Modificação 3"` >}}

  {{< shell-in c=`cat arquivo.txt` >}}
  {{< shell-out c=`
Olá Mundo
Modificação 1
Modificação 2
Modificação 3
` >}}

  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`
mnb2468 (HEAD -> outra-branch) Modificação 3
asd1357 Modificação 2
qwe4680 Modificação 1
mn2356b (master) Revertendo para o primeiro commit
as1209d Segundo commit
qw3487e Primeiro commit
` >}}
{{% /shell %}}

---

### `git merge`

---

Fast-forward

{{% shell %}}
  {{< shell-in p="repo" c=`git switch master` >}}
  {{< shell-in c=`git merge outra-branch` >}}
  {{< shell-out c=`
Fast-forward
 arquivo.txt | 3 +++
 1 file changed, 3 insertions(+)
` >}}

  {{< shell-in c=`git log --oneline` >}}
  {{< shell-out c=`
mnb2468 (HEAD -> master, outra-branch) Modificação 3
asd1357 Modificação 2
qwe4680 Modificação 1
mn2356b Revertendo para o primeiro commit
as1209d Segundo commit
qw3487e Primeiro commit
` >}}
{{% /shell %}}


---

No Fast-forward

{{% shell %}}
  {{< shell-in p="repo" c=`git reset --hard HEAD~3` >}}
  {{< shell-in c=`echo "Modificação master" >> arquivo.txt` >}}
  {{< shell-in c=`git commit -am "Modificação master"` >}}

  {{< shell-in c=`git merge outra-branch` >}}
  {{< shell-out c=`CONFLICT (content): Merge conflict in arquivo.txt` >}}

  {{< shell-in c=`sed -i '/^<<<<<<</d' arquivo.txt` >}}
  {{< shell-in c=`sed -i '/^=======/d' arquivo.txt` >}}
  {{< shell-in c=`sed -i '/^>>>>>>>/d' arquivo.txt` >}}

  {{< shell-in c=`git commit -am "Merge da branch outra-branch"` >}}

  {{< shell-in c=`git log --oneline --graph` >}}
  {{< shell-out c=`
*   05d44f5 (HEAD -> master) Merge da branch outra-branch
|\
| * mnb2468 (outra-branch) Modificação 3
| * asd1357 Modificação 2
| * qwe4680 Modificação 1
* | pu1234o Modificação master
|/
* mn2356b Revertendo para o primeiro commit
* as1209d Segundo commit
* qw3487e Primeiro commit
` >}}
{{% /shell %}}

---

#### `git rebase`

{{% shell %}}
  {{< shell-in p="repo" c=`git reset --hard HEAD~1` >}}

  {{< shell-in c=`git rebase outra-branch` >}}
  {{< shell-out c=`CONFLICT (content): Merge conflict in arquivo.txt` >}}

  {{< shell-in c=`sed -i '/^<<<<<<</d' arquivo.txt` >}}
  {{< shell-in c=`sed -i '/^=======/d' arquivo.txt` >}}
  {{< shell-in c=`sed -i '/^>>>>>>>/d' arquivo.txt` >}}

  {{< shell-in c=`git add arquivo.txt` >}}
  {{< shell-in c=`git rebase --continue` >}}

  {{< shell-in c=`git log --oneline --graph` >}}
  {{< shell-out c=`
* pu1234o (HEAD -> master) Modificação master
* mnb2468 (outra-branch) Modificação 3
* asd1357 Modificação 2
* qwe4680 Modificação 1
* mn2356b Revertendo para o primeiro commit
* as1209d Segundo commit
* qw3487e Primeiro commit
` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Tags

---

Adicionando uma tag

{{% small %}}Para adicionar uma mensagem, utilizar a flag **`-m`**{{% /small %}}

{{% shell %}}
  {{< shell-in p="repo" c=`git tag 1.0.0` >}}
{{% /shell %}}

---

Deletando uma tag

{{% shell %}}
  {{< shell-in p="repo" c=`git tag -d 1.0.0` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Armazenando mudanças

---

### `git stash`

- {{% small %}}**git stash:** Apenas os arquivos monitorados{{% /small %}}
- {{% small %}}**git stash -u:**: Inclui também os arquivos não monitorados{{% /small %}}
- {{% small %}}**git stash -a:**: Inclui também os arquivos não monitorados e ignorados{{% /small %}}

---

Primeiro armazenamento

{{% shell %}}
  {{< shell-in p="repo" c=`echo "Olá Mundo" > arquivo.txt` >}}
  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=` M arquivo.txt` >}}

  {{< shell-in c=`git stash` >}}
  {{< shell-in c=`git status -s` >}}

  {{< shell-in c=`git stash list` >}}
  {{< shell-out c=`stash@{0}: WIP on master: mnb2468 Modificação 3` >}}
{{% /shell %}}

---

`git stash apply`

{{% shell %}}
  {{< shell-in p="repo" c=`git switch outra-branch` >}}
  {{< shell-in c=`git stash apply` >}}

  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=` M arquivo.txt` >}}

  {{< shell-in c=`cat arquivo.txt` >}}
  {{< shell-out c=`Olá Mundo` >}}

  {{< shell-in c=`git stash list` >}}
  {{< shell-out c=`stash@{0}: WIP on master: mnb2468 Modificação 3` >}}
{{% /shell %}}

---

`git stash pop`

{{% shell %}}
  {{< shell-in p="repo" c=`git restore arquivo.txt` >}}
  {{< shell-in c=`git switch master` >}}

  {{< shell-in c=`git stash pop` >}}
  {{< shell-in c=`git stash list` >}}

  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=` M arquivo.txt` >}}
{{% /shell %}}

---

`git stash save`

{{% shell %}}
  {{< shell-in p="repo" c=`git stash save "Modificação arquivo.txt"` >}}
  {{< shell-in c=`git stash list` >}}
  {{< shell-out c=`stash@{0}: On master: Modificação arquivo.txt` >}}
{{% /shell %}}

---

`git stash show`

{{% shell %}}
  {{< shell-in p="repo" c=`git stash show` >}}
  {{< shell-out c=`
 arquivo.txt | 3 ---
 1 file changed, 3 deletions(-)
` >}}
{{% /shell %}}

---

`git stash -p`

{{% shell %}}
  {{< shell-in p="repo" c=`git stash pop stash@{0}` >}}
  {{< shell-in c=`git stash -p` >}}
{{% /shell %}}

---

`git stash branch`

{{% shell %}}
  {{< shell-in p="repo" c=`git stash branch stash-branch stash@{0}` >}}
  {{< shell-in c=`git branch` >}}
  {{< shell-out c=`
  master
  outra-branch
* stash-branch
` >}}

  {{< shell-in c=`git switch master` >}}
  {{< shell-in c=`git branch -d stash-branch` >}}

  {{< shell-in c=`git status -s` >}}
  {{< shell-out c=` M arquivo.txt` >}}
{{% /shell %}}

---

`git stash drop`

{{% shell %}}
  {{< shell-in p="repo" c=`git stash save "Modificação 1"` >}}
  {{< shell-in c=`echo "Olá Mundo 2" > arquivo.txt` >}}
  {{< shell-in c=`git stash save "Modificação 2"` >}}

  {{< shell-in c=`git stash list` >}}
  {{< shell-out c=`
stash@{0}: On master: Modificação 2
stash@{1}: On master: Modificação 1
` >}}

  {{< shell-in c=`git stash drop stash@{0}` >}}
  {{< shell-in c=`git stash list` >}}
  {{< shell-out c=`stash@{0}: On master: Modificação 1` >}}
{{% /shell %}}

---

`git stash clear`

{{% shell %}}
  {{< shell-in p="repo" c=`git stash clear` >}}
  {{< shell-in c=`git stash list` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Git bare

---

{{% shell %}}
  {{< shell-in p="repo" c=`mkdir ../repo.git` >}}
  {{< shell-in c=`git init --bare ../repo.git` >}}
  {{< shell-in c=`git remote add local full/path/to/repo.git` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Git hook

---

{{% shell %}}
  {{< shell-in p="repo" c=`cat > ../repo.git/hooks/post-receive << EOF
#!/bin/sh
git --work-tree=/var/www/html checkout -f
EOF
` >}}
  {{< shell-in c=`chmod +x ../repo.git/hooks/post-receive` >}}

  {{< shell-in c=`git mv arquivo.txt index.html` >}}
  {{< shell-in c=`echo "<h1>Git</h1>" > index.html` >}}
  {{< shell-in c=`git commit -am "Página html"` >}}

  {{< shell-in c=`git push local master` >}}

  {{< shell-in c=`curl localhost` >}}
  {{< shell-out c=`<h1>Git</h1>` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Chaves SSH

---

#### Algoritmo **`ed25519`**

{{% shell %}}
  {{< shell-in c=`ssh-keygen -t ed25519 -a 128 -C "Comentário"` >}}
{{% /shell %}}

---

#### Algoritmo **`rsa`**

{{% small %}}Usar se o algoritmo `ed25519` não for suportado{{% /small %}}

{{% shell %}}
  {{< shell-in c=`ssh-keygen -t rsa -b 4096 -o -a 128 -C "Comentário"` >}}
{{% /shell %}}

---

O objetivo dessa seção foi mostrar como gerar chaves SSH seguras, para mais informações veja o artigo do GitHub [About SSH](https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh/about-ssh).

{{% /section %}}

---

{{% section %}}

## Instalando o Git Flow

---

Se estiver em um ambiente Windows, o Git Flow já estará instalado, ele foi incluído na versão [`2.5.3`](https://github.com/git-for-windows/git/releases/tag/v2.5.3.windows.1) do Git for Windows.

---

Se estiver em um ambiente Mac, recomendo utilizar o [Homebrew](https://brew.sh/) para instalar o Git Flow:

{{% shell %}}
  {{< shell-in c=`brew install git-flow` >}}
{{% /shell %}}

---

Se estiver em um ambiente baseado Linux baseado no Debian:

{{% shell %}}
  {{< shell-in c=`sudo apt install git-flow` >}}
{{% /shell %}}

---

Para verificar se o Git Flow foi instalado:

{{% small %}}**A versão ser diferente não é um problema**{{% /small %}}

{{% shell %}}
  {{< shell-in c=`git flow version` >}}
  {{< shell-out c=`1.12.3 (AVH Edition)` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Entendendo o Git Flow

---

O Git Flow é um fluxo de trabalho para o Git, criado por Vincent Driessen, a partir da sua publicação [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/) no ano de 2010.

---

{{< img height="600" src="/img/14.png" >}}

{{% /section %}}

---

{{% section %}}

## Utilizando o Git Flow

---

#### Inicializar um repositório

{{% shell %}}
  {{< shell-in c=`mkdir flow` >}}
  {{< shell-in c=`cd flow` >}}
  {{< shell-in p="flow" c=`git flow init` >}}
{{% /shell %}}

---

### Features (Funcionalidades)

---

#### Começar uma funcionalidade

{{% shell %}}
  {{< shell-in p="flow" c=`git flow feature start minha-feature` >}}
{{% /shell %}}

---

#### Finalizar uma funcionalidade

{{% shell %}}
  {{< shell-in p="flow" c=`git flow feature finish minha-feature` >}}
{{% /shell %}}

---

#### Publicar uma funcionalidade

{{% shell %}}
  {{< shell-in p="flow" c=`git flow feature publish minha-feature` >}}
{{% /shell %}}

---

#### Obter uma funcionalidade publicada

{{% shell %}}
  {{< shell-in p="flow" c=`git flow feature pull minha-feature` >}}
{{% /shell %}}

---

### Releases (Versões)

---

#### Começar uma versão

{{% shell %}}
  {{< shell-in p="flow" c=`git flow release start minha-versao` >}}
{{% /shell %}}

---

#### Publicar um versão

{{% shell %}}
  {{< shell-in p="flow" c=`git flow release publish minha-versao` >}}
{{% /shell %}}

---

#### Finalizar uma versão

{{% shell %}}
  {{< shell-in p="flow" c=`git flow release finish minha-versao` >}}
{{% /shell %}}

---

### Hotfixes

---

#### Começar uma hotfix

{{% shell %}}
  {{< shell-in p="flow" c=`git flow hotfix start minha-hotfix` >}}
{{% /shell %}}

---

#### Finalizar uma hotfix

{{% shell %}}
  {{< shell-in p="flow" c=`git flow hotfix finish minha-hotfix` >}}
{{% /shell %}}

{{% /section %}}

---

{{% section %}}

## Contatos

<i class="fab fa-github"></i> [https://github.com/GaMoCh](https://github.com/GaMoCh)

<i class="fab fa-linkedin"></i> [https://linkedin.com/in/gabrielmchaves](https://linkedin.com/in/gabrielmchaves)

{{% /section %}}
