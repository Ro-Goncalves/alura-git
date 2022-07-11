# Estados dos arquivos no Git

O Git possui uma série de estados para os arquivos em um diretório, no fundo dois, e um desses dois mais 3.
Confuso? Relaxa, todos ficamos no começo; eu ainda estou. Nesse breve artigo comentárei um pouco sobre esse 
assunto.

O Git pode o não conhecer o arquivo, por isso são definidos os estados *tracked*, *Untracked* (rastreado, não rastreado respectivamente).
Inicialmente o arquivo é não rastreado e ao "dizer" ao Git para restreá-los temos três estados possivéis *unmodified*, *modified* e *staged* (não modificado, modificado e preparados respectivamente).

## UNTRACKED
Imagina que você possui um diretório, e cria um arquivo dentro dele. Como essa é a primeira vez que o Git vê o arquivo, ele informará que não o conhece.
Para verificar esse fato utilizamos o git status

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
Note que temos um arquivo seção *Untracked files*. O Git nos da algumas dicas, logo abaixo da seção lemos: `use "git add <file>..."`, e no final `(...) but untracked files present (use "git add" to track)`.

## TRACKED

### STAGED
Vamos seguir o que foi informado pelo Git e usar `git add`. 
```bash
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   ARTIGO_Status_Git.md
```

Lembra o que comentamos sobre os arquivos rastreados? Eles pode estar em três estados. Nesse caso o nosso arquivo "pulou" para o terceiro, preparado, isso quer dizer que podemos fazer o *commit* desse arquivo. Ao faze-lo nosso diretório estará sem modificação ou novos arquivos.
Note também que o Git indicou que se trata de um novo arquivo: `new file:   ARTIGO_Status_Git.md`.
(NÂO GOSTEI MUITO DESSA PARTE - REESCREVER)

### UNMODIFIED
E agora que não criamos e nem modificamos nenhum arquivos, o que acontece? Bem o Git entende que não existe nada a fazer no momento, 
indicando: `nothing to commit, working tree clean`.
```bash
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

### MODIFIED
E se fizermos alguma alteração em um arquivo rastreado, qual o seu estado? Bem, acontece o esperado, modificado, tão simple
quanto parece. Agora é possível seguir os mesmos passo anteriores. `add`, `commit`. 
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
Essa imagem pode ajudar a ver o que acabo de escrever.
![Ciclo de vida dos estados dos arquivos](img/lifecycle.png?raw=true).


## Referências:
[STACKOVERFLOW - Quais as diferenças entre os estados dos arquivos do git untracked unmodified](https://pt.stackoverflow.com/questions/326086/quais-as-diferenças-entre-os-estados-dos-arquivos-do-git-untracked-unmodified).
[GIT - Fundamentos de Git gravando alterações em seu repostório](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Gravando-Altera%C3%A7%C3%B5es-em-Seu-Reposit%C3%B3rio).
