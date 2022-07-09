# Antes de entrar de trabalhar, mais uma entrevista

## Personagens
```
Joãozinho: Estudante de analise e desenvolvimento de sistemas, tentando uma vaga de estágio
na área.

Pedrinho: Responsável pelo setor de desenvolvimento da N.C.M.N.B.

Marquinho: Um desenvolvedor do time.
```

## Cenário
```
Uma sala de reuniões da N.C.M.N.B., Pedrinho está sentado à frente de Joãozinho, entre eles existe uma mesa retangular.
```
---

**Pedrinho:**
Boa tarde.

**Joãozinho:**
Boa tarde.

**Pedrinho:**
Vejo que você foi bem na primeira parte da avaliação, suas notas sobre fundamentos de java foram
boas.

**Joãozinho:**
Muito obrigado. Estou estudando a algum tempo, quero muito comseguir essa vaga.

**Pedrinho:**
Como você sabe, não iremos trabalhar sozinho. Atualmente o setor conta com cinco colaboradores.
Com você iremos expandir o nosso time. Em casa você deve desenvolver sem grandes procupações com 
o versionamento do seu código. Para que o desenvolvimento não vire um caos, nós usamos o Git. Já
ouviu falar?

**Joãozinho:**
Sim, eu já estudei um pouco sobre isso. Até uso em casa, mas como não desenvolvo com outras pessoas,
não passei por alguns problemas que vocês podem tem infrentado.

**Pedrinho:**
Saber o que é e como funciona já ajuda bastante. Você poderia me explicar, sem muitos detalhes, como 
funciona o controle de versão?

**Joãozinho:**
Humm, deixa eu ver: No cenário de vocês, com várias pessoas trabalhando no mesmo código, é interessante 
exirtir uma ferramenta que compare a versão do código que está no servidor com o que o desenvolvedor está
enviando. Basicamente, existe um servidor com o código atual do projeto, ao submetermos uma nova versão,
ele irá comparar se a versão enviada é a mesma que está no servidor, se não for a mesmo, ele obriga quem está enviado atualizar sua versão, e somente após isso, enviar o que ele queria.

**Pedrinho:**
Muito bem. Esse é o caminho. Se eu trouxesse um *notebook*, você conseguiria criar um repositório e trabalhar um pouco com ele.

**Joãozinho:**
Creio que sim, vamos tentar.

```
Pedrinho sai da sala, assim que volta, além do notebook trás consigo o Marquinho
```

**Pedrinho:**
Aqui está, eu aproveitei e trouxe o Marquinho, ele é um de nossos desenvolvedores.

**Marquinho:**
Prazer.

**Joãozinho:**
O prazer é todo meu.

*Marquinho senta-se ao lado de Joãozinho, e Pedinho do outro*

**Pedrinho:**
Bem vamos lá. Pode iniciar o projeto e nós falar o que está fazendo.

**Joãozinho:**
Primeiro eu criarei um pasta, para fazer isso pelo git eu posso utilizar o comando
```
git init
```
Creiarei um arquivo chamado index.html, vou colocar qualquer coisa aqui dentro. 
Agora eu consigo ver as minhas alterações.
```
git status
```

**Marquinho:**
Antes de você continuar, eu gostaria de fazer uma pergunta. Olha aqui, quando você utilizou o
git status, esse arquivo que você acabou de criar apareceu na seção 
```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
```
Sabe o que isso quer dizer?

**Joãozinho:**
Que eu preciso adicioná-lo antes de fazer um commit.

**Marquinho:**
Também. Mas esse status *untracked*. Sabe me explica-lo?

**Joãozinho:**
Creio que não.

**Marquinho:**
Nesse caso o git está falando para você que não conhece esse arquivo. Ele é não rastreado. Ainda veremos 
alguns outros status. Vou lhe explicando quando aparecerem. 

**Joãozinho:**
Certo. Agora eu posso adicionar esse arquivo na fila para ser *"comitado"* utilizando
```
git add .
```
ou
```
git add nome-do-arquivo
```
ou ainda
```
git add nome-da-pasta/
```
Agora o arquivo está preparado para o *commit*, conforme pode ser visto aqui
```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
```  

**Marquinho:**
Isso, quando você faz isso falamos que enviou o arquivo para o *stage*.

**Joãozinho**
Certo. Antes de continuar, eu acabei me esquecendo de fazer algo muito importante,
informar quem é o autor do código. Gosto de fazer essa definição somente no repositório
do projeto, por isso defino o nome com
```
git config --local user.name "Meu nome"
```
e meu e-mail com:
```
git config --local user.email "meu@email.aqui"
```
Desculpe estou meio nervoso.

**Pedrinho**
Não se preocupe você está indo bem.

**Joãozinho**
Obrigado. Então vamos continuar. Se por algum motivo eu colocar algum arquivo errado no 
*stage*, posso utiliza
```
git rm "nome do arquivo/pasta"
````Com isso ele volta a ser *untracked*,faço o que for necessário e o volto para o *stage*.
Agora basta utilizar
```
git commit -m"Mensagem"
```
E pronto, terminei as minhas alterações. É só fazer todo esse ciclo toda vez que algo 
mudar no meu repositório local.

**Pedrinho**
Perfeito, eu gostei do que vi até aqui, e você Marquinho?

**Marquinho**
Eu gostei muito também. Ao menos para trabalhar em um diretório local, esse conhecimento
seria quase que o suficiente.

**Pedrinho**
Legal Joãozinho, gostei muito mesmo do que vi até agora. Você saberia mais alguma coisa 
sobre Git?

**Joãozinho**
Sei mais algumas coisinhas sim, se você estiverem com tempo, posso mostrar.

**Pedrinho**
Temos sim, só vamos ali fora pegar um café e esticar as pernas.

```
Todo se levantam, pegam um café na máquina. Conversam sobre coisas aleatórias e voltam à 
sala
```

**Marquinho**
Agora pode continuar. 

**Pedrinho**
Muito bem. Algo que eu gosto bastente de fazer é verificar como estão as minhas publicações. 
Para isso eu utilizo o 
```
git log
```
essa funcionalidade possui várias opções, a que eu mais uso é a --oneline. Nos dois casos temos
informações parecidas. Gostaria de me atendar a duas.

```
commit e3ee8d8f75e89f84acf660676210cc1d1768bf82 (HEAD -> main)
Author: Rodrigo Gonçalves <ro.go.calves@gmail.com>
Date:   Fri Jul 8 21:32:50 2022 -0300

    Minha mensagem.

```
Aqui em cima tem esse *hash* que funciona como um identificador único. Logo após vemos a 
palavra *HEAD*, ela indica o estado atual do código, e *main* é o *branch* em que estamos 
trabalhando







*