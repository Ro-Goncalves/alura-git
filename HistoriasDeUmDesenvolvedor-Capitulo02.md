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
```git
git init
```
Creiarei um arquivo chamado index.html, vou colocar qualquer coisa aqui dentro. 
Agora eu consigo ver as minhas alterações.
```git
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

