# Estados Git - Onde vivem o que comem

O Git possui uma série de estados para os arquivos em um diretório, no fundo dois, e um desses dois mais 3.
Confuso? Relaxa, todos ficamos no começo; eu ainda estou. Nesse breve artigo comentárei um pouco sobre esse 
assunto.

O Git pode o não conhecer o arquivo, por isso são definidos os estados *tracked*, *Untracked* (rastreado, não rastreado respectivamente).
Inicialmente o arquivo é não rastreado e ao "dizer" ao Git para restreá-los temos três estados possivéis *unmodified*, *modified* e *staged* (não modificado, modificado e preparados respectivamente).

**UNTRACKED**
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


## Referências:
[STACKOVERFLOW - Quais as diferenças entre os estados dos arquivos do git untracked unmodified](https://pt.stackoverflow.com/questions/326086/quais-as-diferenças-entre-os-estados-dos-arquivos-do-git-untracked-unmodified).
[GIT - Fundamentos de Git gravando alterações em seu repostório](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Gravando-Altera%C3%A7%C3%B5es-em-Seu-Reposit%C3%B3rio).
