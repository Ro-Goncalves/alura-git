# Branches, que venha o caos
Um belo dia, qualquer desenvolvedor perceberá que é necessário estudar alguma ferramenta de versionamento de código.
Descobrirá que a mais famosa, ou falada, ao menos para quem está começando, é o Git. O começo é empolgante, as 
possibilidades quase ilimitadas. Pode trabalhar em equipe e sincronizar os códigos, "maravilhindo". Eis que chega o fatídico dia, aula de *Branches*. Sabe quando você entra na faculdade, ao até mesmo na escola, passa quatro horas tento a mesma aula; maçante; chata; sem graça; àquela onde você se perde nos quinze primeiros minutos. Quando saímos de tal aula, parece que o nosso cérebro foi batido em um liquidificador, vamos a caminho do RU, restaurante universitário, no automático, ou por força divina.  
Bem, isso é a aula de *branches*, 15 minutos que são capazes de lhe fazer se sentir um burro, e se perguntar: Por quê?

## Esclarecendo o que foi obscurecido
No fundo não é tão difícil de entender como funciona e para que servem os *branches*, é que a princípio parece um bicho-de-sete-cabeças, mas não é, talvez duas, vamos extirpar algumas delas.

**Primeira:** Imagine que você está trabalhando em um site, código para aqui, código para lá, *commit*, mais código, mais *commit*, mais trabalho. Até que seu celular vibra, você dá aquela olhada, meio que de “rabo de zoi”, notificação do Whats, quando a vê é uma mensagem do “The Boss”. Primeiro pensamento: “Deu ruim”. Quando lê: “É, muito ruim, e logo na sexta”, SEXTA.

A página está com um problema em produção, e você precisa atuar o mais rápido possível, “The Boss” ainda coloca um “ASAP” no final. O grupo de vendedores, parece mais um vespeiro em que foi atirado uma pedra. 
Então você deve parar o que está fazendo e trabalhar nessa correção. 

### Para que serve
Você pode criar uma nova *branch*, `git branch SextaNao`, e trabalhar nessa correção, dessa forma você não irá interferir naquilo que estava fazendo antes, no *branch master* provavelmente. 

**Segunda:** Uma outra utilidade seria para testes. Você precisa testar uma solução, cria uma *branch*, escreve, escreve código, cria um Frankenstein, não resolve o problema, basta excluir o *branch*, e tudo volta a ser como antes.

## Era uma hidra
Para que serve é facíl de explicar, e o como funciona? Será que o bicho era uma Hidra ou um Dragão?

**Terceira:** Já comentei sobre *snapshots*, [Um pouco sobre Snapshots](ARTIGO_ExplicandoSnapshot.md), em resumo, o Git grava nossos *commits*
como uma foto do projeto, cada foto tem as informações necessárias para podermos voltar a ela quando quisermos. 
Algo como:
![commit-and-tree](/img/commit-and-tree.png)

De tal forma que cada *snapshot* é uma coleção desses arquivos onde um *commit* aponta para outro. Agora podemos dar uma definição mais tecnica para *branch*, ele é um pontei que aponta para algum desses *snapshots*. No inicio do projeto, normalmente temos o *branch master*.
![branch-and-history](/img/branch-and-history.png)

**Quarta:** Para o Git saber em qual desses *branches* você está trabalhando ele utiliza um ponteiro especial *HEAD*. Para verificar onde 
você está é fácil, basta usar `git log --oneline --decorate`, em imagem:
![head-to-testing](/img/head-to-testing.png)

no *log*:
```bash
40d85dc (HEAD -> master, origin/master, origin/HEAD) ARTIGO: Finalizando 'Um pouco sobre Snapshots'
e95ec11 ARTIGO: Snapshot - Iniciando o desenvolvimento
0ff5255 ARTIGO: Finalizando o desenvolvimento de 'Estados dos arquivos no git'
```
Para alterar entre *branches* basta utilizar `git checkout SextaNao`

**Quinta, mais duas:** Voltemos ao nosso exemplo, correção na sexta-feira, você cria seu novo *branch*, faz um pouco de correção.
Enquanto o pessoal está homologando, você volta ao *branch* principal, trabalha mais um pouco, até que fica com algo parecido com 
isso:
![advance-master](img/advance-master.png)

Algora você tem duas linhas de desenvolvimento, como juntar tudo? Como publicar a correção sexta-feira em produção? Esse é um outro
assunto: **MERGING**

A fonte de toas as imagens é a referência [1]


## Referências
1. [GITBOOK: Branches no Git em poucas palavras](https://git-scm.com/book/pt-br/v2/Branches-no-Git-Branches-em-poucas-palavras)
2. [YOUTUBE: Professor José de Assis -  Curso GIT e GITHUB - Criando ramificações do projeto (branch e merge) e resolução de conflitos](https://www.youtube.com/watch?v=iRs6sQOPcvg)