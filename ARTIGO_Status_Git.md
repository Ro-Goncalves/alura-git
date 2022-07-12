# Estados dos arquivos no Git

O Git possui uma série de estados para os arquivos em um diretório, no fundo dois; um desses dois; três.
Confuso? Relaxa, todos ficamos no começo; eu ainda estou. 

Nesse breve artigo, comentarei um pouco sobre esse assunto.

O Git pode ou não conhecer um arquivo, por isso são definidos os estados *tracked*, *Untracked* (rastreado, não rastreado respectivamente).
Inicialmente o arquivo é não rastreado; ao "dizer" ao Git para restreá-los temos três estados possíveis *unmodified*, *modified* e *staged* (não modificado, modificado e preparados respectivamente).

## UNTRACKED
Imagina que você possui um diretório, e cria um arquivo dentro dele. Como essa é a primeira vez que o Git vê o arquivo, ele informará que não o conhece.
Para verificar esse fato, basta utilizar `git status`.

```bash
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ARTIGO_Status_Git.md

nothing added to commit but untracked files present (use "git add" to track)
```
Note que temos um arquivo seção *Untracked files*. O Git nos da algumas dicas, logo abaixo da seção lemos: *use "git add <file>..."*, e no final *(...) but untracked files present (use "git add" to track)*.

## TRACKED

### STAGED
Vamos seguir o que foi informado pelo Git e usar `git add`. Ao verificar o estado de nosso diretório novamente, temos:
```bash
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   ARTIGO_Status_Git.md
```

Veja que interessate, surgiu uma nova secão *Changes to be committed*; nosso arquivos é indicado como novo, *new file:   ARTIGO_Status_Git.md*, isso indica que ele está no estado *staged*.

### UNMODIFIED
Ao realizar o *commit* e verificar o estado do diretório, o Git indica que nossa *working tree* está limpa, *nothing to commit, working tree clean*.
É fácil concluir que não existem arquivos novos e nem modificados nesse momento.
```bash
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

### MODIFIED
E se fizermos alguma alteração em um arquivo rastreado, qual o seu estado? Bem; acontece o esperado; modificado; tão simple
quanto parece, *modified:   ARTIGO_Status_Git.md*. 
```bash
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   ARTIGO_Status_Git.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## Eu gosto de ver
Dizem que uma imagem vale mais do que mil palavras.

![Ciclo de vida dos estados dos arquivos](img/lifecycle.png?raw=true).

A fonte dessa imagem pode ser vista na referência [2]


## Referências:
1. [STACKOVERFLOW: Quais as diferenças entre os estados dos arquivos do git untracked unmodified](https://pt.stackoverflow.com/questions/326086/quais-as-diferenças-entre-os-estados-dos-arquivos-do-git-untracked-unmodified).
2. [GIT: Fundamentos de Git gravando alterações em seu repostório](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Gravando-Altera%C3%A7%C3%B5es-em-Seu-Reposit%C3%B3rio).
