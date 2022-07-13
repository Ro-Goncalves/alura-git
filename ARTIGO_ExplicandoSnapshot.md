# Um pouco sobre Snapshots
Começar algo novo é sempre difícil, ainda mais quando muita coisa escrita sobre é em uma lingua
que não estamos tão familiarizados. Porém, para quem é desenvolvedor, esse é só mais um desafio no nosso
dia-a-dia.

Em um desses dias, tentando entender como funciona o Git, eis que me deparo com a palavra *snapshots*.
Primeira coisa que vem a cabeça "*WTF* que p... é essa?". E qual a solução que dei? "Deixa para lá,
consigo entender sem saber o que isso quer dizer".

Conseguir..., consegue, mas, fica uma pulga, ou elefantes, atrás da orelha: "O que quer dizer isso?"

Esse artigo é para matar a pulga e o elefante, ou melhor, matar somente a pulga, o elefante eu o coloco
em seu lugar.

## Começando pelo fim
 Em resumo, um *snapshot* é uma foto que o Git tira do repositório, isso acontece toda faz que fazemos
 um *commit*. 

 ## Começando pelo início
Existem alguns objetos no Git, *blob*, *tree*, *commit*, cada um com o seu *hash* que o identifica nesse
emaranhado de alterações que vamos fazendo no decorrer do desenvolvimento. 

Por hora, não irei descrever muito a fundo o que são esses objetos; como diria o Jack: "Vamos por partes".

A grosso modo, podemos dizer que um *commit* é um conjunto de *hashs* dos *blobs* e *trees* presentes em
nosso repositório. No *Blob* encontramos o conteudo de um arquivo e no *tree* o caminho para chegar àquele arquivo,
e alguns outros metadados em ambos.

Imagine que temos um pasta com três arquivos em nosso diretório. Logo, em teoria, lembre-se que é somente uma 
aproximação para explicar o conceito de *snapshot*, temos um *hash* para a *tree* e três para os *blobs*, um
para cada arquivo.

Ao alterarmos um arquivo, o Git calculará um novo *hash* para ele, e o comparará com o de seu *blob*, lembre-se
uma coisa é o arquivo que você está escrevendo, outra é o *blob* que o Git gera, você termina a alteração, faz o *commit*,
isso cria um novo *snapshot*. 

## O que acontece agora
O Git é um "cara" esperto. Ele sabe que o arquivo-b, vamos supor que foi esse o arquivo que sofreu alteração, foi alterado e
o demais não. Logo nesse novo *snapshot* ele terá um *blob* com esse arquivo alterado e para os demais somente uma referência
que aponta para o arquivo anterior, gênial.

## Em resumo
**Começando pelo fim (...)**

## Eu gosto de imagens
Dado o que você leu até agora, interprete esse imagem.

![Snapshots](img/snapshots.png?raw=true).

A fonte dessa imagem encontra-se na referêcia [2].


## Referências:
1. [GITHUB: Commits Are Snapshots not diffs](https://github.blog/2020-12-17-commits-are-snapshots-not-diffs/).
2. [GIT BOOK: Começando - O Básico do Git](https://git-scm.com/book/pt-br/v2/Começando-O-Básico-do-Git).
3. [STACKOVERFLOW: What is a git "Snapshot"](https://stackoverflow.com/questions/4964099/what-is-a-git-snapshot#:~:text=The%20term%20snapshot%20is%20used,snapshot%20to%20denote%20the%20difference.).