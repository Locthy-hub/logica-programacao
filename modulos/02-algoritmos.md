# Módulo 2 — Algoritmos

> No Módulo 1 você entendeu **o que é** um algoritmo. Agora vamos aprender a **representá-lo formalmente** — de um jeito organizado, que qualquer pessoa (ou você mesmo, dias depois) consiga entender e seguir.

---

## 2.1 — Sequência: a espinha dorsal de todo algoritmo

Todo algoritmo, por mais complexo que seja, é construído em cima de uma ideia simples: **passos executados em ordem, um depois do outro**. Isso se chama **sequência**.

### Analogia: a fila do banco

Imagine uma fila de banco com uma senha. Ninguém é atendido fora de ordem (pelo menos não deveria!). O guichê 3 só atende a senha 46 depois de atender a 45. Essa é a ideia de sequência: **uma coisa de cada vez, na ordem certa**.

### Por que a ordem importa tanto?

Veja esse "algoritmo" com a ordem errada:

```
1. Coloque a roupa no varal
2. Lave a roupa
3. Coloque a roupa na máquina
```

Está tecnicamente com os mesmos passos de lavar roupa, mas a **ordem** transformou algo sensato em um absurdo. Um computador executaria isso exatamente como está escrito — sem perceber o erro, porque ele não "entende" o sentido, só **obedece a ordem**.

A versão correta:

```
1. Coloque a roupa na máquina
2. Lave a roupa
3. Coloque a roupa no varal
```

> 💡 **Regra de ouro:** cada passo de um algoritmo sequencial depende do(s) anterior(es) terem sido concluídos. Mude a ordem, mude (ou quebre) o resultado.

Até aqui, todos os algoritmos que vimos no Módulo 1 eram **sequenciais**: passo 1, depois passo 2, depois passo 3, sem desvios. Nos módulos 6 e 7 vamos aprender a "quebrar" essa sequência com decisões (`se`) e repetições (`enquanto`) — mas antes disso, precisamos dominar bem a base: escrever e representar sequências.

---

## 2.2 — Fluxogramas: desenhando o raciocínio

Um **fluxograma** é uma representação **visual** de um algoritmo, usando formas geométricas padronizadas conectadas por setas que indicam a ordem de execução.

### Por que usar fluxogramas?

Porque o cérebro humano processa muito bem informação visual. Antes de escrever qualquer código, "desenhar" o problema ajuda a enxergar a lógica de um jeito diferente, revelando furos no raciocínio que passariam despercebidos só no texto.

### Os símbolos principais

```
   ┌─────────┐
   │ Início  │   ← Óvalo/elipse: indica o INÍCIO ou FIM do algoritmo
   └────┬────┘
        │
        ▼
   ┌─────────┐
   │ Leia X  │   ← Paralelogramo: ENTRADA ou SAÍDA de dados
   └────┬────┘
        │
        ▼
   ┌─────────┐
   │ X ← X+1 │   ← Retângulo: PROCESSAMENTO (cálculo, atribuição)
   └────┬────┘
        │
        ▼
      ╱   ╲
     ╱  X>0 ╲    ← Losango: DECISÃO (verdadeiro ou falso)
     ╲       ╱
      ╲     ╱
        │
        ▼
   ┌─────────┐
   │   Fim   │
   └─────────┘
```

| Símbolo | Formato | Significado |
|---|---|---|
| Início / Fim | Óvalo (elipse) | Marca onde o algoritmo começa e termina |
| Entrada / Saída | Paralelogramo | Ler um dado ou mostrar um resultado |
| Processamento | Retângulo | Um cálculo, uma atribuição de valor |
| Decisão | Losango | Uma pergunta com resposta Sim/Não (Verdadeiro/Falso) |
| Setas | Linhas com ponta | Indicam a ordem/direção do fluxo |

### Exemplo: fluxograma para calcular a média de duas notas

```
        ┌───────────┐
        │  Início   │
        └─────┬─────┘
              ▼
      ┌────────────────┐
      │  Leia nota1    │
      └───────┬────────┘
              ▼
      ┌───────────────┐
      │  Leia nota2    │
      └───────┬────────┘
              ▼
   ┌────────────────────────┐
   │ media ← (nota1+nota2)/2│
   └───────────┬────────────┘
               ▼
      ┌───────────────────────────┐
      │ Escreva "Média:", media   │
      └───────────┬───────────────┘
                  ▼
        ┌───────────┐
        │    Fim    │
        └───────────┘
```

Repare como o fluxograma "traduz" visualmente o mesmo algoritmo que já vimos no Módulo 1 em pseudocódigo. Ambas as formas representam a **mesma lógica** — só mudam a forma de expressar.

### Exemplo com decisão: verificar se um número é par ou ímpar

```
             ┌───────────┐
             │  Início   │
             └─────┬─────┘
                   ▼
            ┌────────────────┐
            │  Leia número   │
            └───────┬────────┘
                    ▼
                  ╱      ╲
                ╱ número  ╲
               ╱ % 2 == 0? ╲
                ╲          ╱
                 ╲        ╱
               Sim │    │ Não
                    ▼    ▼
          ┌──────────┐ ┌──────────┐
          │Escreva   │ │Escreva   │
          │"É par"   │ │"É ímpar" │
          └────┬─────┘ └────┬─────┘
               └──────┬──────┘
                      ▼
                 ┌───────────┐
                 │    Fim    │
                 └───────────┘
```

Note que, a partir do losango (decisão), o fluxo **se divide em dois caminhos possíveis**, e depois os dois caminhos voltam a se unir antes do fim. Essa é a primeira vez que vemos um algoritmo **não puramente sequencial** — ele tem um "desvio" dependendo de uma condição. Vamos aprofundar isso a fundo no Módulo 6.

---

## 2.3 — Pseudocódigo: escrevendo algoritmos em "quase-português"

**Pseudocódigo** é uma forma de escrever algoritmos usando uma linguagem parecida com o português (ou inglês), só que de forma **estruturada**, sem se prender à sintaxe rígida de uma linguagem de programação real.

### Por que não escrever só em português comum?

Porque o português do dia a dia é **ambíguo**. Veja a frase:

> "Some os números e mostre se for maior que 10."

Que números? Quantos? "Mostre o quê" exatamente? O pseudocódigo existe para eliminar essa ambiguidade, adotando um pequeno conjunto de **palavras-chave padronizadas** e uma estrutura fixa, sem exigir que você aprenda toda a sintaxe complicada de uma linguagem real (como chaves `{}`, ponto e vírgula `;`, etc.).

### Estrutura básica de um pseudocódigo

```
INÍCIO
  <declarações de variáveis, se necessário>
  <passo 1>
  <passo 2>
  <passo 3>
  ...
FIM
```

### Palavras-chave mais comuns (vamos usar durante todo o curso)

| Palavra-chave | Para que serve |
|---|---|
| `INÍCIO` / `FIM` | Marca o começo e o fim do algoritmo |
| `LEIA` | Recebe um valor digitado pelo usuário (entrada) |
| `ESCREVA` | Mostra um valor/mensagem na tela (saída) |
| `←` (ou `=`) | Atribui um valor a uma variável |
| `SE ... ENTÃO ... SENÃO` | Estrutura condicional (Módulo 6) |
| `ENQUANTO ... FAÇA` | Estrutura de repetição (Módulo 7) |
| `PARA ... FAÇA` | Estrutura de repetição com contador (Módulo 7) |

Não se preocupe em decorar tudo agora — vamos usar essas palavras à exaustão nos próximos módulos, e elas vão se tornar naturais com a prática.

### Exemplo: calcular a área de um retângulo

```
INÍCIO
  LEIA base
  LEIA altura
  area ← base * altura
  ESCREVA "A área do retângulo é: ", area
FIM
```

Repare que isso é exatamente o mesmo algoritmo que poderíamos desenhar como fluxograma. **Pseudocódigo e fluxograma são duas representações diferentes da mesma lógica** — algumas pessoas preferem visualizar em fluxograma, outras preferem escrever direto em pseudocódigo. Ambas as habilidades são úteis, e vamos treinar as duas ao longo do curso.

---

## 2.4 — Portugol: o "pseudocódigo padronizado" brasileiro

**Portugol** é uma linguagem de programação didática, criada especificamente para ensinar lógica de programação para falantes de português. É basicamente um pseudocódigo com regras mais fixas — tem uma sintaxe mais parecida com uma linguagem de programação de verdade, mas usando palavras em português.

### Por que aprender Portugol?

Porque ele funciona como uma "ponte" entre o pseudocódigo livre (que temos usado até aqui) e uma linguagem de programação real. No Portugol, você já pratica conceitos como declaração de tipos de variáveis, blocos de código bem delimitados, etc. — sem a barreira do inglês técnico das linguagens comerciais.

Existe até uma ferramenta gratuita e muito usada em cursos técnicos e faculdades chamada **VisuAlg**, que interpreta e executa código em Portugol, mostrando o resultado passo a passo — ótima para quem está começando.

### Estrutura básica de um programa em Portugol (estilo VisuAlg)

```portugol
algoritmo "NomeDoAlgoritmo"
var
   nota1, nota2, media: real

inicio
   escreva("Digite a primeira nota: ")
   leia(nota1)

   escreva("Digite a segunda nota: ")
   leia(nota2)

   media <- (nota1 + nota2) / 2

   escreva("A média é: ", media)
fimalgoritmo
```

Repare nas diferenças em relação ao pseudocódigo mais "livre" que usamos antes:

1. Existe uma seção `var` onde você **declara** as variáveis antes de usá-las, junto com o **tipo** de cada uma (`real`, `inteiro`, `caractere`, etc. — veremos tipos de dados a fundo no Módulo 3).
2. O algoritmo tem um nome, entre aspas.
3. `inicio` e `fimalgoritmo` delimitam claramente onde o código "roda" de fato.

Isso é **exatamente** a estrutura que você vai encontrar em linguagens reais como C, Java ou Python (cada uma com sua própria sintaxe) — então praticar Portugol já é um treino direto para o que vem depois.

> 📌 **Neste curso**, vamos alternar entre pseudocódigo livre (mais didático para explicar conceitos novos) e blocos em estilo Portugol (para você já se acostumar com uma sintaxe mais próxima de código real). Os exercícios podem ser resolvidos em qualquer um dos dois formatos.

---

## 2.5 — Sequência, fluxograma, pseudocódigo e Portugol: tudo é a mesma coisa

Isso é fundamental de entender: **as quatro formas que vimos representam exatamente a mesma lógica**, só que de jeitos diferentes. Veja o mesmo algoritmo (par ou ímpar) nas quatro formas:

**Em palavras (sequência descrita):**
```
1. Leia um número
2. Calcule o resto da divisão desse número por 2
3. Se o resto for 0, é par
4. Senão, é ímpar
5. Mostre o resultado
```

**Em fluxograma:** (já vimos a versão completa na seção 2.2)

**Em pseudocódigo:**
```
INÍCIO
  LEIA numero
  SE numero % 2 == 0 ENTÃO
    ESCREVA "É par"
  SENÃO
    ESCREVA "É ímpar"
  FIM SE
FIM
```

**Em Portugol (VisuAlg):**
```portugol
algoritmo "ParOuImpar"
var
   numero: inteiro

inicio
   escreva("Digite um número: ")
   leia(numero)

   se (numero % 2 = 0) entao
      escreva("É par")
   senao
      escreva("É ímpar")
   fimse
fimalgoritmo
```

Perceba: a **lógica** é idêntica nas quatro formas. O que muda é só a "roupagem". Quando você entender isso de verdade, vai perceber que aprender uma nova linguagem de programação no futuro é, na maior parte das vezes, **só aprender uma nova roupagem para a mesma lógica que você já sabe.**

---

## 📊 Diagrama resumo do módulo

```
                    ALGORITMO (a lógica em si)
                            │
        ┌───────────────────┼───────────────────┐
        ▼                    ▼                    ▼
   SEQUÊNCIA           FLUXOGRAMA           PSEUDOCÓDIGO / PORTUGOL
 (passos em ordem,   (representação        (escrita estruturada,
  um após o outro)    visual com formas      parecida com código real)
                       e setas)
        │                    │                    │
        └────────────────────┴─────────────────────┘
                             │
                        TODAS REPRESENTAM
                         A MESMA LÓGICA
```

---

## 💡 Erros comuns de quem está começando

1. **Trocar a ordem dos passos "porque parece mais natural falar assim".** Sempre valide se a ordem escrita realmente resolve o problema, passo a passo, como se você fosse o computador executando.
2. **Desenhar fluxogramas sem seta de direção clara.** Todo fluxograma precisa deixar óbvio "o que vem depois do quê" — sem isso, ele perde a utilidade.
3. **Esquecer de fechar as estruturas no pseudocódigo/Portugol** (por exemplo, esquecer o `FIM SE` ou `fimse`) — isso é como abrir um parêntese e não fechar.
4. **Confundir "declarar uma variável" com "usar uma variável"** — no Portugol, você primeiro *declara* (`var numero: inteiro`) e só depois *usa* (`leia(numero)`). Vamos entender variáveis a fundo no Módulo 3.

---

## ✅ Boas práticas desde já

- Ao resolver um exercício, **desenhe o fluxograma ou escreva o pseudocódigo antes de "codar de verdade"** em qualquer linguagem — isso vira um hábito valiosíssimo mesmo quando você já for experiente.
- Nomeie os passos e variáveis de forma **clara e descritiva** (`media`, `notaFinal`) em vez de nomes genéricos (`x`, `coisa`).
- Sempre teste seu algoritmo "na mão", com números de exemplo, antes de considerá-lo pronto — como se você mesmo fosse o computador executando o passo a passo.

---

## 🎲 Curiosidades

- Os símbolos padronizados de fluxograma que usamos hoje (retângulo, losango, óvalo) foram formalizados pela indústria em meados do século XX, através de normas como a ANSI (American National Standards Institute), para que qualquer engenheiro no mundo entendesse o mesmo desenho da mesma forma.
- O **Portugol** e ferramentas como o **VisuAlg** são amplamente usados em cursos técnicos e vestibulares/concursos brasileiros de tecnologia justamente por eliminar a barreira do inglês no início do aprendizado.
- Grandes empresas de tecnologia frequentemente pedem, em entrevistas técnicas, que o candidato **desenhe o fluxo do algoritmo no quadro branco antes de escrever qualquer código** — ou seja, a habilidade que você está treinando aqui é usada profissionalmente, e não é "só para iniciante".

---

## 📝 Exercícios

### Fáceis

1. Escreva, em pseudocódigo, um algoritmo que leia o nome de uma pessoa e mostre "Olá, [nome]!" na tela.
2. Desenhe (em texto/ASCII, como fizemos no módulo) o fluxograma de um algoritmo que leia um número e mostre o dobro dele.
3. Escreva em pseudocódigo um algoritmo que leia três números e mostre a soma deles.
4. Explique, com suas palavras, a diferença entre um fluxograma e um pseudocódigo.
5. Reescreva o seguinte algoritmo, corrigindo a ordem dos passos: "1. Seque o cabelo. 2. Lave o cabelo. 3. Passe xampu."

### Médios

6. Escreva em Portugol (estilo VisuAlg) um algoritmo que leia o preço de um produto e mostre o valor com 10% de desconto aplicado.
7. Desenhe o fluxograma de um algoritmo que leia a idade de uma pessoa e mostre se ela é maior ou menor de idade (considere maior de idade a partir de 18 anos).
8. Escreva em pseudocódigo um algoritmo que leia dois números e mostre qual é o maior entre eles.
9. Converta o pseudocódigo abaixo para Portugol (estilo VisuAlg):
```
INÍCIO
  LEIA salario
  bonus ← salario * 0.1
  ESCREVA "O bônus é: ", bonus
FIM
```
10. Explique por que dizemos que fluxograma, pseudocódigo e Portugol "representam a mesma lógica". Dê um exemplo próprio.

### Difíceis

11. Escreva em pseudocódigo um algoritmo que leia três notas de um aluno, calcule a média e mostre se o aluno foi aprovado (média maior ou igual a 6) ou reprovado.
12. Desenhe o fluxograma completo (incluindo o losango de decisão) do exercício anterior.
13. Escreva em Portugol um algoritmo que leia a temperatura em graus Celsius e mostre o valor convertido para Fahrenheit (fórmula: F = C * 9/5 + 32).
14. Reescreva, em pseudocódigo, o seguinte problema mal formulado (deixe-o específico e sem ambiguidade): "Verifique o desconto do cliente e mostre o valor final."
15. Escreva um algoritmo (em pseudocódigo) que leia o valor de uma compra e a forma de pagamento (à vista ou parcelado) e, se for à vista, aplique 5% de desconto; se for parcelado, não aplique desconto algum. Mostre o valor final.

### Desafios

16. **Desafio do tradutor:** pegue qualquer um dos algoritmos que você escreveu nos exercícios anteriores e represente-o nas **quatro formas** que aprendemos neste módulo (sequência em palavras, fluxograma, pseudocódigo e Portugol).
17. **Desafio do fluxograma complexo:** desenhe o fluxograma de um algoritmo que leia um número e diga se ele é positivo, negativo ou zero (isso envolve duas decisões em sequência — pense com calma).

---

## 📖 Gabarito explicado

**1.**
```
INÍCIO
  LEIA nome
  ESCREVA "Olá, ", nome, "!"
FIM
```

**2.**
```
     ┌───────────┐
     │  Início   │
     └─────┬─────┘
           ▼
   ┌────────────────┐
   │  Leia número   │
   └───────┬────────┘
           ▼
   ┌───────────────────┐
   │ dobro ← número*2  │
   └───────┬───────────┘
           ▼
   ┌────────────────────────┐
   │ Escreva "Dobro:", dobro│
   └───────┬────────────────┘
           ▼
     ┌───────────┐
     │    Fim    │
     └───────────┘
```

**3.**
```
INÍCIO
  LEIA n1
  LEIA n2
  LEIA n3
  soma ← n1 + n2 + n3
  ESCREVA "A soma é: ", soma
FIM
```

**4.** O fluxograma é uma representação **visual**, feita com formas geométricas e setas, ótima para enxergar rapidamente o caminho que o algoritmo percorre (inclusive desvios e decisões). O pseudocódigo é uma representação em **texto estruturado**, mais parecida com uma "escrita de código", útil para detalhar melhor cálculos e passos específicos. Ambos descrevem a mesma lógica.

**5.** Ordem correta: "1. Passe xampu. 2. Lave o cabelo. 3. Seque o cabelo." — repare que a ordem original tinha o passo de secar antes mesmo de lavar, o que não faz sentido físico algum.

**6.**
```portugol
algoritmo "DescontoProduto"
var
   preco, precoComDesconto: real

inicio
   escreva("Digite o preço do produto: ")
   leia(preco)

   precoComDesconto <- preco - (preco * 0.1)

   escreva("O preço com desconto é: ", precoComDesconto)
fimalgoritmo
```

**7.**
```
          ┌───────────┐
          │  Início   │
          └─────┬─────┘
                ▼
        ┌───────────────┐
        │  Leia idade    │
        └───────┬────────┘
                ▼
             ╱     ╲
            ╱ idade  ╲
           ╱  >= 18?   ╲
            ╲          ╱
             ╲        ╱
          Sim │      │ Não
              ▼      ▼
      ┌──────────┐ ┌──────────┐
      │Escreva   │ │Escreva   │
      │"Maior de │ │"Menor de │
      │idade"    │ │idade"    │
      └────┬─────┘ └────┬─────┘
           └──────┬──────┘
                  ▼
            ┌───────────┐
            │    Fim    │
            └───────────┘
```

**8.**
```
INÍCIO
  LEIA a
  LEIA b
  SE a > b ENTÃO
    ESCREVA "O maior é: ", a
  SENÃO
    ESCREVA "O maior é: ", b
  FIM SE
FIM
```
*Observação:* esse pseudocódigo assume que a e b não são iguais. No Módulo 6 vamos aprender a tratar também o caso de empate (a == b) com mais precisão.

**9.**
```portugol
algoritmo "CalculoBonus"
var
   salario, bonus: real

inicio
   escreva("Digite o salário: ")
   leia(salario)

   bonus <- salario * 0.1

   escreva("O bônus é: ", bonus)
fimalgoritmo
```

**10.** Resposta livre, mas o exemplo deve mostrar que, independentemente da forma escolhida (desenho, texto estruturado, ou "código" em Portugol), os **passos e decisões continuam sendo exatamente os mesmos** — só a "roupagem" muda.

**11.**
```
INÍCIO
  LEIA nota1
  LEIA nota2
  LEIA nota3
  media ← (nota1 + nota2 + nota3) / 3
  SE media >= 6 ENTÃO
    ESCREVA "Aprovado. Média: ", media
  SENÃO
    ESCREVA "Reprovado. Média: ", media
  FIM SE
FIM
```

**12.**
```
        ┌───────────┐
        │  Início   │
        └─────┬─────┘
              ▼
      ┌───────────────┐
      │ Leia nota1,2,3 │
      └───────┬────────┘
              ▼
   ┌─────────────────────────┐
   │ media←(nota1+nota2+nota3)/3│
   └────────────┬──────────────┘
              ▼
           ╱      ╲
          ╱ media   ╲
         ╱   >= 6?    ╲
          ╲           ╱
           ╲         ╱
        Sim │       │ Não
            ▼       ▼
    ┌──────────┐ ┌──────────┐
    │"Aprovado"│ │"Reprovado"│
    └────┬─────┘ └────┬──────┘
         └──────┬──────┘
                ▼
          ┌───────────┐
          │    Fim    │
          └───────────┘
```

**13.**
```portugol
algoritmo "ConversorCelsiusFahrenheit"
var
   celsius, fahrenheit: real

inicio
   escreva("Digite a temperatura em Celsius: ")
   leia(celsius)

   fahrenheit <- celsius * 9/5 + 32

   escreva("Em Fahrenheit: ", fahrenheit)
fimalgoritmo
```

**14.** Versão específica:
```
INÍCIO
  LEIA valorCompra
  LEIA percentualDesconto
  valorFinal ← valorCompra - (valorCompra * percentualDesconto / 100)
  ESCREVA "O valor final é: ", valorFinal
FIM
```
*Por que importa:* a frase original não dizia de onde vem o desconto nem como ele é calculado — o pseudocódigo obriga você a decidir e explicitar cada detalhe.

**15.**
```
INÍCIO
  LEIA valorCompra
  LEIA formaPagamento
  SE formaPagamento == "à vista" ENTÃO
    valorFinal ← valorCompra - (valorCompra * 0.05)
  SENÃO
    valorFinal ← valorCompra
  FIM SE
  ESCREVA "Valor final: ", valorFinal
FIM
```

**16.** Resposta livre — o importante é que as quatro versões contem exatamente a mesma história, só com "roupagens" diferentes.

**17.**
```
              ┌───────────┐
              │  Início   │
              └─────┬─────┘
                    ▼
            ┌───────────────┐
            │  Leia número   │
            └───────┬────────┘
                    ▼
                 ╱      ╲
                ╱ número  ╲
               ╱   > 0?    ╲
                ╲          ╱
                 ╲        ╱
              Sim │      │ Não
                  ▼      ▼
          ┌──────────┐    ╱      ╲
          │"Positivo"│   ╱ número  ╲
          └────┬─────┘  ╱   < 0?    ╲
               │         ╲          ╱
               │          ╲        ╱
               │       Sim │      │ Não
               │           ▼      ▼
               │   ┌──────────┐ ┌──────────┐
               │   │"Negativo"│ │  "Zero"  │
               │   └────┬─────┘ └────┬─────┘
               └────────┴─────┬──────┘
                              ▼
                        ┌───────────┐
                        │    Fim    │
                        └───────────┘
```
*Por que é difícil:* esse problema tem **duas decisões encadeadas** (uma dentro do "senão" da outra) — essa estrutura se chama "decisão aninhada" e vamos formalizá-la no Módulo 6.

---

## 🧾 Resumo do Módulo 2

- **Sequência** é a base de todo algoritmo: passos executados em ordem, um após o outro — mudar a ordem pode quebrar o resultado.
- **Fluxograma** é a representação visual de um algoritmo, usando símbolos padronizados (óvalo, retângulo, paralelogramo, losango) conectados por setas.
- **Pseudocódigo** é uma escrita estruturada e "quase-português", com palavras-chave fixas (`INÍCIO`, `LEIA`, `ESCREVA`, `SE`, etc.) que elimina a ambiguidade da linguagem natural.
- **Portugol** é uma linguagem de programação didática em português, mais próxima da sintaxe de linguagens reais — uma ótima ponte antes de aprender uma linguagem comercial.
- Todas essas formas representam **a mesma lógica** — a escolha de qual usar é só uma questão de praticidade, não muda o raciocínio por trás.

No próximo módulo, vamos abrir a "caixa-preta" da memória do computador: o que são **variáveis**, como elas guardam informação, os diferentes **tipos de dados**, e como e por que os valores podem ser convertidos de um tipo para outro.

➡️ **Próximo módulo:** [Módulo 3 — Variáveis](03-variaveis.md)
