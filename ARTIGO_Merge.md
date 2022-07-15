# Merge, o fim, ou não, do caos
Filmes são interessantes, normalmente começam calmo, ficam agitados, e calmos novamente. 
O estudo de algo novo pode ser assim também, começamos empolgados com a novidade, 
conforme adquirimos conhecimento tudo fica confuso, um monte de coisas soltas que não 
sabemos onde ligar, por fim, depois de muito esforço e tempo as coisas se ligam e chegamos 
ao conhecimento do que estávamos estudando.  

A natureza também é assim, o mesmo mar que é calmo, pode ficar violento e agitado, depois calmo 
e lindo novamente; a temperatura vai do quente insuportável, para o frio ameno e aconchegante, 
para o frio congelante, depois para o calor que nos abraça. Enfim para tudo existe um ciclo, 
calmaria-agitação-calmaria, ou algo desse tipo.

*Merge* é a nossa calmaria após a agitação, estávamos aconchegantes em nossa *branch* principal; 
água fresca, coco gelado. Chega uma onda criando uma bagunça; criamos um, duas, três novas *braches*; 
organizamos a casa. Depois, assim como o banhista, que teve de mudar de lugar por causa da onda, 
colocamos tudo na *branch* principal e voltamos a apreciar a praia, nesse novo local, o mesmo, porém 
um pouco diferente. 

## E o desenvolvedor, como vê
Agora sem alusões à praia. Você está trabalhando, faz alguns *commits*, cria uma nova *branch* faz um 
*commit* nela. Seu log é parecido com isso:

![basic-branching-3](img/basic-branching-3)

Agora você precisa fazer uma correção, volta à *master*, `git checkout master`, e cria um outro *branch* 
para trabalhar nessa correção, `git checkout -b hotfix`.

![basic-branching-4](img/basic-branching-4)

Estando pronta a correção, faz um merging com a master.

## Primeiro merging, eu estou ao lado dele
Como pode ser visto na imagem acima, os *commits* realizados na *branch hotfix* estão imediatamente após o 
último *commit* da *master*. O Git, cara esperto como é, percebe isso e só move o ponteiro da *master* para o 
ponteiro da *hotfix*, ele faz isso sempre que pode alcançar o branch que iremos mesclar na principal através 
de um histórico, vulgo, ele só vai para frente, em tecniques: “*master* sofre um ‘*fast-forward*’ até *hotfix*”.

![basic-branching-5](img/basic-branching-5)

Feito isso, basta deletar o *branch* utilizado para fazer a correção: `git branch -d hotfix`. 

## Segundo merging, e agora José?
Tento corrigido o problema, voltamos ao que estávamos fazendo, codificamos e fazemos mais um *commit*. 
Um ponto importante aqui, nesse momento o que foi feito no *branch hotfix* não está presente no iss53, só estará quando fizermos um *merge*.

![basic-branching-6](img/basic-branching-6)

Terminando, vamos fazer um novo *merging*, porém o Git trabalhará um pouco diferente do anterior. Agora ele fará 
algo chamado *three-way merge*. Isso é meio que simples: O Git pega o último *snapshot* da *branch* que você está, 
compara com o último da que você está tentando mesclar, juntamente com o ancestral comum, essas são as três vias, 
depois ele gerará um novo *snapshot* que é a composição dos 3.

![basic-merging-2](img/basic-merging-2.png)
 
## Alguém mexeu em meu arquivo
Se você está trabalhando sozinho, tudo pode acontecer de forma mais linda e harmoniosa, mas, se trabalha com alguém, 
tudo é caos e desordem. 

É obvio que alguém editará um arquivo que não deveria, e é mais obvio ainda que será o seu, lógico, “se algo pode dar errado, 
ele vai dar errado”.

Você tenta fazer o *merging* e recebe uma mensagem do Git dizendo que alguém fez alterações no mesmo arquivo que você, 
**NA MESMA LINHA, NA SEXTA-FEIRA ÀS 17:50**. E aquilo que era para trazer ordem ao caos, trouxe caos.
Lembra-se do ciclo dito no começo? Não existe noite longa que o dia não possa iluminar, e nesse caso o Sol também existe.
Você abre o arquivo indicado pelo Git, o Visual Studio pode ajudar bastante nessa hora, vê o que tem nas linhas conflitantes, 
escolhe qual a melhor solução, terminando coloca tudo no *stage*, faz o *commit*, e tudo é finalizado como esperado.

## Referência
1. [GITBOOK: Branches no Git - O básico de Ramificação (Branch) e Mesclagem (Merge)](https://git-scm.com/book/pt-br/v2/Branches-no-Git-O-b%C3%A1sico-de-Ramifica%C3%A7%C3%A3o-Branch-e-Mesclagem-Merge)