# Módulo 1 — O que é programação

> "Programar não é decorar comandos. É aprender a pensar de um jeito novo." 

Bem-vindo ao primeiro módulo do curso! Antes de escrever qualquer linha de código, você precisa entender **o que realmente significa programar**. Esse é o módulo mais importante de todos — não porque é o mais difícil, mas porque tudo o que vem depois se apoia nele.

Vá com calma. Leia devagar. Não pule nada.

---

## 1.1 — O que é um algoritmo?

Imagine que você vai ensinar alguém que nunca cozinhou a fazer um bolo. Você não diria só "faça um bolo". Você diria algo assim:

```
1. Pegue uma tigela
2. Coloque 2 xícaras de farinha
3. Adicione 1 xícara de açúcar
4. Quebre 2 ovos e adicione
5. Misture tudo
6. Coloque em uma forma
7. Leve ao forno por 40 minutos
8. Retire e deixe esfriar
```

Isso, meus caros, **é um algoritmo**.

> **Algoritmo** é uma sequência finita de passos, bem definidos e ordenados, que resolve um problema ou realiza uma tarefa.

Repare nas palavras-chave dessa definição:

- **Finita**: tem começo, meio e fim. Não é infinita.
- **Bem definidos**: cada passo é claro, sem ambiguidade. "Coloque farinha" é vago; "coloque 2 xícaras de farinha" é preciso.
- **Ordenados**: a ordem importa! Não dá pra assar o bolo antes de misturar os ingredientes.

### Algoritmos no seu dia a dia

Você já executa (e cria) algoritmos o tempo todo, mesmo sem perceber:

- A receita do bolo acima.
- O trajeto que você faz de casa até o mercado.
- O passo a passo para trocar o pneu de um carro.
- As instruções de montagem de um móvel.
- Um manual de "como resetar a senha do Wi-Fi".

Programar é, essencialmente, **escrever algoritmos que um computador consegue entender e executar**.

---

## 1.2 — O que é lógica?

Lógica é a ciência do raciocínio correto. É a capacidade de conectar ideias, tirar conclusões válidas e resolver problemas passo a passo, de forma coerente.

Quando dizemos "lógica de programação", estamos falando da capacidade de **quebrar um problema grande em pequenos passos que fazem sentido, em uma ordem que leva à solução**.

### Analogia: o GPS

Pense em um GPS. Quando você pede uma rota, ele não te dá o destino de uma vez — ele te dá uma sequência de instruções:

```
1. Siga em frente por 300 metros
2. Vire à direita na Rua das Flores
3. Siga por 1,2 km
4. Vire à esquerda na Avenida Central
5. Seu destino está à direita
```

Cada instrução depende da anterior ter sido cumprida corretamente. Se você errar o passo 2, todos os passos seguintes ficam errados. **Isso é lógica aplicada.**

A boa notícia: você já tem lógica. Todo ser humano usa lógica para tomar decisões (se está chovendo, eu levo o guarda-chuva). O que este curso vai fazer é **treinar** essa habilidade para que você consiga aplicá-la a problemas computacionais.

---

## 1.3 — Como computadores "pensam"?

Aqui está uma verdade importante, e talvez um pouco desconfortável:

> **Computadores não pensam. Computadores obedecem.**

Um computador não tem bom senso, não "entende" o que você quis dizer, não deduz intenções. Ele faz **exatamente** o que você mandou — nem mais, nem menos.

### Analogia: o gênio da lâmpada literal

Imagine um gênio da lâmpada que realiza qualquer desejo, mas de forma **extremamente literal**. Se você disser "quero ficar milionário", ele pode reduzir todo o dinheiro do mundo a um dólar, para que o pouco que você tem já te torne, tecnicamente, "o mais rico". Ele não fez nada de errado — ele fez exatamente o que você pediu, só que você não foi específico o suficiente.

Computadores são assim. Por isso, um dos maiores desafios de quem está aprendendo a programar não é a sintaxe (os comandos), e sim **aprender a ser extremamente específico e claro** ao descrever os passos de um problema.

### Por baixo dos panos

Nos bastidores, tudo que um computador processa vira, no final das contas, uma sequência de **0s e 1s** (bits), que representam sinais elétricos ligados ou desligados. Programar em uma linguagem como Python, Java ou JavaScript é uma forma de escrever instruções de um jeito legível para humanos, que depois é **traduzido** (compilado ou interpretado) para essa linguagem de máquina.

Você não precisa entender tudo isso agora — só precisa saber que existe uma "tradução" acontecendo, e que por isso o computador exige **precisão absoluta**: um erro de digitação pode fazer tudo parar de funcionar.

---

## 1.4 — O ciclo Entrada → Processamento → Saída

Praticamente **todo programa de computador**, do mais simples ao mais complexo, segue este ciclo básico:

```
┌───────────┐      ┌────────────────┐      ┌───────────┐
│  ENTRADA  │ ───► │  PROCESSAMENTO │ ───► │   SAÍDA   │
└───────────┘      └────────────────┘      └───────────┘
```

### Entrada (Input)

É a informação que o programa recebe do mundo exterior. Pode vir de:

- O que o usuário digita no teclado.
- Um clique do mouse.
- Um arquivo lido do disco.
- Dados vindos da internet.
- Uma leitura de sensor (temperatura, por exemplo).

### Processamento

É a parte em que o programa **faz algo** com os dados recebidos: calcula, compara, organiza, transforma, decide.

### Saída (Output)

É o resultado que o programa devolve para o mundo exterior:

- Um texto exibido na tela.
- Um som.
- Um arquivo salvo.
- Uma mensagem enviada.

### Exemplo prático

Vamos analisar um programa simples: **calcular a média de duas notas de um aluno**.

```
ENTRADA:
  - Nota 1
  - Nota 2

PROCESSAMENTO:
  - Somar Nota 1 + Nota 2
  - Dividir o resultado por 2

SAÍDA:
  - Mostrar a média calculada
```

Em pseudocódigo (uma forma de escrever algoritmos parecida com português, que vamos estudar a fundo no Módulo 2), ficaria assim:

```
INÍCIO
  LEIA nota1
  LEIA nota2
  media ← (nota1 + nota2) / 2
  ESCREVA "A média é: ", media
FIM
```

Não se preocupe em entender cada símbolo agora — o importante é que você **enxergue o padrão**: primeiro entra informação, depois ela é processada, depois sai um resultado. Esse padrão vai se repetir em praticamente tudo que você programar dali pra frente, seja um joguinho, um sistema bancário ou um site.

---

## 1.5 — Por que aprender lógica antes de uma linguagem?

Muita gente comete o erro de tentar aprender Python, Java ou C++ direto, sem entender lógica antes. É como tentar aprender a compor músicas complexas sem antes saber o que são notas musicais.

A lógica de programação é **independente de linguagem**. Uma vez que você entende como estruturar um algoritmo — como fazer o computador repetir uma tarefa, tomar uma decisão, guardar um valor — você consegue aplicar isso em **qualquer linguagem**, porque a estrutura de pensamento é a mesma. Só muda a "sotaque" (a sintaxe).

É por isso que, neste curso, vamos usar **pseudocódigo/Portugol**: uma forma de escrever algoritmos em português estruturado, sem nos prendermos às regras específicas de uma linguagem de programação real. Assim, quando você for aprender Python ou Java depois, vai perceber que já sabe 80% do caminho — só falta aprender a "sintaxe" daquela linguagem específica.

---

## 📊 Diagrama resumo do módulo

```
                     PROGRAMAÇÃO
                          │
          ┌───────────────┼───────────────┐
          │                                │
      ALGORITMO                        LÓGICA
  (sequência de passos             (raciocínio para
   para resolver um problema)       chegar à solução)
          │                                │
          └───────────────┬───────────────┘
                          │
                 COMPUTADOR OBEDECE
              (não pensa, executa exatamente
                    o que foi escrito)
                          │
          ┌───────────────┼───────────────┐
          ▼                ▼               ▼
      ENTRADA      PROCESSAMENTO         SAÍDA
   (dados que        (o que é feito    (resultado
   entram)             com os dados)    devolvido)
```

---

## 💡 Erros comuns de quem está começando

1. **Achar que o computador "entende" a intenção.** Ele não entende — ele executa exatamente o que foi escrito, então a precisão é essencial.
2. **Tentar aprender uma linguagem antes de entender lógica.** Isso costuma gerar frustração, porque a pessoa decora comandos sem entender o raciocínio por trás.
3. **Pular etapas dos algoritmos.** Achar que um passo é "óbvio" e não escrevê-lo — para você pode ser óbvio, para o computador nunca é.
4. **Confundir "não saber programar" com "não ter lógica".** Todo mundo tem lógica (você usa isso o tempo todo na vida real); o que falta é **treino** para aplicá-la a problemas computacionais.

---

## ✅ Boas práticas desde o primeiro dia

- Sempre que for resolver um problema, **escreva os passos em português antes de pensar em código**.
- Seja específico. Troque frases vagas ("processar os dados") por passos concretos ("somar o valor de A com B").
- Treine a habilidade de **explicar o passo a passo de tarefas simples do seu dia a dia** (escovar os dentes, fazer café) como se estivesse ensinando um robô muito literal. Esse exercício sozinho já desenvolve lógica.

---

## 🤔 Curiosidades

- A palavra **"algoritmo"** vem do nome do matemático persa **Al-Khwarizmi**, que viveu no século IX e escreveu métodos sistemáticos para resolver problemas matemáticos.
- A primeira pessoa considerada "programadora da história" foi **Ada Lovelace**, no século XIX — ela escreveu instruções para uma máquina de calcular (a Máquina Analítica de Charles Babbage) décadas antes de existir qualquer computador eletrônico.
- Existe uma expressão famosa entre programadores: **"Garbage in, garbage out"** ("lixo entra, lixo sai") — se a entrada de dados for ruim ou errada, a saída também será, não importa o quão bom seja o processamento.

---

## 📝 Exercícios

### Fáceis

1. Escreva, em passos numerados, o algoritmo para "trocar uma lâmpada".
2. Escreva o algoritmo para "atravessar a rua com segurança".
3. Identifique a ENTRADA, o PROCESSAMENTO e a SAÍDA da seguinte situação: "Uma calculadora soma dois números digitados pelo usuário e mostra o resultado na tela."
4. Explique, com suas próprias palavras, a diferença entre "algoritmo" e "lógica".
5. Dê três exemplos de algoritmos que você segue no seu dia a dia, que não foram citados no módulo.

### Médios

6. Escreva um algoritmo (em passos) para determinar se um número digitado pelo usuário é par ou ímpar. (Dica: pense na ideia de "resto da divisão por 2", mesmo que ainda não saiba escrever isso em código.)
7. Escreva um algoritmo para decidir se uma pessoa pode ou não votar, sabendo que a idade mínima é 16 anos.
8. Escreva um algoritmo para calcular o troco de uma compra, dado o valor da compra e o valor pago.
9. Explique por que a ordem dos passos em um algoritmo é importante, usando um exemplo próprio (diferente da receita de bolo).
10. Reescreva a frase "processe os dados do cliente e mostre o resultado" tornando-a específica o suficiente para um "gênio literal" entender exatamente o que fazer.

### Difíceis

11. Escreva um algoritmo para determinar o maior entre três números.
12. Escreva um algoritmo para verificar se uma pessoa pode entrar em um cinema, considerando: classificação indicativa do filme, idade da pessoa, e se está acompanhada de um adulto (quando necessário).
13. Escreva um algoritmo para organizar, em ordem crescente, três números digitados pelo usuário — sem usar nenhuma função pronta, apenas comparações passo a passo.
14. Pense em um erro que um "computador literal" cometeria se você desse a instrução "ligue a luz se estiver escuro" sem detalhar melhor. Reescreva a instrução de forma mais precisa.
15. Descreva, em etapas de Entrada, Processamento e Saída, um sistema simples de cadastro de um produto em uma loja (nome, preço, quantidade).

### Desafios

16. **Desafio do robô doméstico:** Escreva um algoritmo extremamente detalhado para um robô fazer um sanduíche de queijo, assumindo que ele não sabe absolutamente nada (nem que é preciso abrir a embalagem do pão, por exemplo).
17. **Desafio da lógica invertida:** Pegue o algoritmo da receita de bolo do início do módulo e reescreva-o para "desfazer" o bolo — ou seja, pense na lógica inversa dos passos (isso ajuda a treinar o raciocínio sequencial).

---

## 📖 Gabarito explicado

**1.** Exemplo de resposta:
```
1. Desligue o interruptor da luz
2. Pegue uma escada, se necessário
3. Retire a lâmpada queimada girando-a no sentido anti-horário
4. Pegue a lâmpada nova
5. Encaixe a lâmpada nova girando-a no sentido horário
6. Ligue o interruptor para testar
```
*Por que importa:* repare que "desligar o interruptor" vem antes de mexer na lâmpada — a ordem aqui não é só lógica, é uma questão de segurança. Isso mostra como a ordem dos passos pode ter consequências reais.

**2.** Exemplo de resposta:
```
1. Pare na calçada
2. Olhe para a esquerda
3. Olhe para a direita
4. Olhe novamente para a esquerda
5. Se não houver carros vindo, atravesse
6. Se houver carros, aguarde e repita o processo
```
*Por que importa:* note o passo 6 — ele faz o algoritmo "esperar" até que a condição seja satisfeita. Isso é um prenúncio do que vamos estudar no Módulo 7 (estruturas de repetição)!

**3.**
- ENTRADA: os dois números digitados pelo usuário.
- PROCESSAMENTO: a soma dos dois números.
- SAÍDA: o resultado mostrado na tela.

**4.** Algoritmo é a sequência de passos em si (o "roteiro"). Lógica é a capacidade de raciocínio usada para **construir** esse roteiro de forma coerente e eficaz. Uma pessoa com boa lógica consegue criar bons algoritmos.

**5.** Resposta livre — o importante é perceber que algoritmos estão em todo lugar: rotina de academia, montar uma lista de compras, organizar um guarda-roupa, etc.

**6.**
```
1. Peça ao usuário para digitar um número
2. Divida o número por 2
3. Se o resto da divisão for 0, o número é par
4. Caso contrário, o número é ímpar
5. Mostre o resultado
```
*Por que importa:* essa ideia de "resto da divisão por 2" (chamada de operador módulo) vai aparecer formalmente no Módulo 4 (Operadores). Aqui você já praticou o raciocínio antes de aprender o nome técnico — é assim que este curso funciona.

**7.**
```
1. Peça a idade da pessoa
2. Se a idade for maior ou igual a 16, a pessoa pode votar
3. Caso contrário, a pessoa não pode votar
4. Mostre o resultado
```

**8.**
```
1. Peça o valor da compra
2. Peça o valor pago
3. Calcule: troco = valor pago - valor da compra
4. Mostre o troco
```
*Atenção (erro comum):* muitos iniciantes esquecem de verificar se o valor pago é suficiente. Um algoritmo mais completo verificaria isso antes de calcular o troco — vamos formalizar essa ideia no Módulo 6.

**9.** Resposta livre, mas deve deixar claro que trocar a ordem de passos dependentes muda o resultado — por exemplo, "vestir os sapatos" antes de "vestir as meias" resulta em algo fisicamente impossível ou incorreto.

**10.** Exemplo: "Processe os dados do cliente" pode virar "Some o valor total das compras do cliente e aplique 10% de desconto se o total for maior que R$100". Quanto mais específico, melhor.

**11.**
```
1. Peça três números: A, B e C
2. Se A for maior que B e A for maior que C, então A é o maior
3. Senão, se B for maior que A e B for maior que C, então B é o maior
4. Senão, C é o maior
5. Mostre o maior número
```

**12.** Resposta esperada (pode variar):
```
1. Verifique a classificação indicativa do filme
2. Verifique a idade da pessoa
3. Se a idade for igual ou maior que a classificação, permita a entrada
4. Se a idade for menor, verifique se há um adulto acompanhando
5. Se houver adulto acompanhando e a diferença de idade for aceitável, permita a entrada
6. Caso contrário, não permita a entrada
```
*Por que é difícil:* este exercício tem múltiplas condições combinadas — é um ótimo prenúncio dos operadores lógicos (E / OU) que veremos no Módulo 4.

**13.** Envolve comparar A com B, depois o resultado com C, trocando posições até ficar em ordem — essa é a semente da lógica por trás dos algoritmos de ordenação que veremos a fundo no Módulo 14 (Bubble Sort, Selection Sort, etc.).

**14.** "Ligue a luz se estiver escuro" não diz *onde*, *quando* medir se está escuro, nem *qual* luz. Versão melhor: "Meça a luminosidade do ambiente às 18h; se for menor que 30%, ligue a luz da sala."

**15.**
```
ENTRADA: nome do produto, preço, quantidade
PROCESSAMENTO: validar se os dados foram preenchidos corretamente,
               calcular valor total em estoque (preço x quantidade)
SAÍDA: confirmação de cadastro + valor total em estoque
```

**16.** Não existe resposta única — o objetivo é que você perceba o quão "burro" (literal) um computador realmente é. Bons exemplos incluem passos como "abra a embalagem do pão puxando pela lateral perfurada" em vez de apenas "abra o pão".

**17.** Também sem resposta única — o valor está em treinar a mente a pensar em sequências reversas, uma habilidade útil mais adiante (por exemplo, ao estudar pilhas, no Módulo 17).

---

## 🧾 Resumo do Módulo 1

- **Algoritmo** é uma sequência finita, ordenada e bem definida de passos para resolver um problema.
- **Lógica** é a capacidade de raciocinar e estruturar esses passos de forma coerente.
- **Computadores não pensam, obedecem** — por isso a precisão nas instruções é essencial.
- Todo programa segue, em algum nível, o ciclo **Entrada → Processamento → Saída**.
- Aprender **lógica** antes de uma **linguagem específica** é o caminho mais sólido, porque a lógica é reaproveitável em qualquer linguagem.

No próximo módulo, vamos aprofundar como representar algoritmos formalmente: fluxogramas, pseudocódigo e Portugol. Você vai aprender a "desenhar" e "escrever" seus algoritmos de um jeito padronizado, prontos para virarem código de verdade.

➡️ **Próximo módulo:** [Módulo 2 — Algoritmos](02-algoritmos.md)
