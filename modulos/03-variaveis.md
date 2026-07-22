# Módulo 3 — Variáveis

> Até agora você aprendeu a pensar em passos (algoritmos) e a representá-los de formas diferentes (fluxograma, pseudocódigo, Portugol). Chegou a hora de entender **onde a informação fica guardada** enquanto o algoritmo está sendo executado. É aqui que entram as **variáveis**.

---

## 3.1 — O que é uma variável?

> **Variável** é um espaço nomeado na memória do computador, usado para guardar um valor que pode mudar ao longo da execução do programa.

### Analogia: a caixinha com etiqueta

Imagine uma caixa de sapato com uma etiqueta colada na frente, escrito "idade". Dentro dessa caixa, você pode colocar um número: hoje pode ser 25, e daqui a um ano você troca o papel de dentro da caixa e coloca 26. **A caixa continua a mesma, com a mesma etiqueta, só o que está dentro dela muda.**

Isso é exatamente uma variável: um espaço com um **nome** (a etiqueta), que guarda um **valor** que pode ser alterado ao longo do tempo.

```
┌─────────────┐
│   idade     │  ← nome da variável (etiqueta)
├─────────────┤
│     25      │  ← valor guardado dentro
└─────────────┘
```

### Por que variáveis existem?

Porque um programa quase nunca trabalha só com valores fixos, "chapados" no código. Ele precisa **lembrar** de coisas: o que o usuário digitou, um resultado de um cálculo anterior, quantas vezes um loop já rodou, etc. Sem variáveis, seria impossível guardar qualquer informação entre um passo e o outro do algoritmo.

### Exemplo prático

```
INÍCIO
  LEIA idade
  ESCREVA "Você tem ", idade, " anos."
FIM
```

Aqui, `idade` é uma variável. Quando o algoritmo executa `LEIA idade`, o valor digitado pelo usuário é **guardado** dentro dessa variável, para ser usado depois — nesse caso, no `ESCREVA`.

---

## 3.2 — Memória: onde as variáveis realmente "moram"

Todo computador tem um componente chamado **memória RAM** (Random Access Memory), que funciona como um imenso conjunto de "gavetinhas" numeradas, cada uma capaz de guardar um pequeno pedaço de informação.

### Analogia: o prédio de apartamentos

Pense na memória RAM como um prédio gigante com milhares de apartamentos numerados (os **endereços de memória**). Quando você cria uma variável chamada `idade`, o programa reserva um desses "apartamentos" e cola a etiqueta "idade" na porta dele. Sempre que o programa precisa usar o valor de `idade`, ele vai até aquele apartamento específico e pega o que está guardado lá.

```
Prédio da Memória RAM

 Apto 1001        Apto 1002        Apto 1003
┌──────────┐     ┌──────────┐     ┌──────────┐
│  idade   │     │   nome   │     │  salario │
│    25    │     │ "Maria"  │     │  3500.0  │
└──────────┘     └──────────┘     └──────────┘
```

Você (como programador) não precisa saber o número exato do "apartamento", o computador cuida disso sozinho. Você só usa o **nome** da variável, e o computador sabe onde procurar.

### Por que isso importa para lógica de programação?

Porque entender que uma variável **ocupa espaço na memória** ajuda a entender comportamentos importantes:

- Uma variável só existe **depois** de ser criada/declarada, antes disso, o "apartamento" nem existe ainda.
- Guardar um novo valor em uma variável **substitui** o valor anterior (a informação antiga se perde, a não ser que você tenha guardado ela em outra variável antes).
- Cada variável ocupa um espaço, então programas que criam uma quantidade absurda de variáveis desnecessárias desperdiçam memória, mais pra frente, quando você estudar estruturas de dados (Módulo 17) e complexidade (Módulo 18), essa noção de "espaço usado" vai ficar ainda mais importante.

---

## 3.3 — Tipos de dados

Nem toda informação é do mesmo "tipo". A idade de uma pessoa é um número inteiro; o nome dela é um texto; se ela é maior de idade ou não é uma resposta de verdadeiro/falso. Por isso, as linguagens de programação (e o Portugol) organizam a informação em **tipos de dados**.

### Por que os tipos existem?

Porque o computador precisa saber **como interpretar** os bits guardados em cada "apartamento" de memória. Os mesmos bits podem significar coisas completamente diferentes dependendo do tipo: um determinado padrão de 0s e 1s pode ser o número 65, ou pode ser a letra "A", depende de qual tipo de dado o programa está tratando aquele espaço de memória.

### Os tipos primitivos mais comuns

| Tipo | Nome em Portugol | O que representa | Exemplos |
|---|---|---|---|
| Inteiro | `inteiro` | Números sem casas decimais (positivos, negativos ou zero) | `5`, `-3`, `0`, `1000` |
| Real (ponto flutuante) | `real` | Números com casas decimais | `3.14`, `-0.5`, `100.0` |
| Caractere / Texto | `caractere` / `string` | Um único caractere ou uma sequência de caracteres (texto) | `'A'`, `"Maria"`, `"1234"` |
| Lógico / Booleano | `logico` | Apenas dois valores possíveis: verdadeiro ou falso | `verdadeiro`, `falso` |

### Analogia: gavetas de formatos diferentes

Pense em uma cômoda com gavetas de tamanhos e formatos diferentes: uma gaveta para meias (pequena e estreita), uma para casacos (grande e larga). Você não guardaria um casaco na gaveta de meias, não cabe, ou fica prejudicado. Da mesma forma, cada tipo de dado tem seu "formato" de armazenamento mais adequado: números inteiros não precisam de espaço para casas decimais, texto precisa de espaço para vários caracteres, etc.

### Exemplo em Portugol usando os quatro tipos

```portugol
algoritmo "ExemploTipos"
var
   idade: inteiro
   altura: real
   nome: caractere
   aprovado: logico

inicio
   idade <- 25
   altura <- 1.75
   nome <- "Ana"
   aprovado <- verdadeiro

   escreva("Nome: ", nome)
   escreva("Idade: ", idade)
   escreva("Altura: ", altura)
   escreva("Aprovado: ", aprovado)
fimalgoritmo
```

> 💡 Repare que, no Portugol (e na maioria das linguagens), você **declara o tipo** de cada variável antes de usá-la. Isso é diferente de algumas linguagens mais modernas (como Python), que descobrem o tipo automaticamente pelo valor atribuído, mas o **conceito de tipo continua existindo por trás**, mesmo quando você não precisa escrevê-lo explicitamente.

---

## 3.4 — Conversão de tipos

Às vezes você precisa transformar um dado de um tipo para outro. Isso se chama **conversão de tipos** (ou, em inglês, *type casting*).

### Quando isso é necessário?

Exemplo clássico: o usuário digita a idade em um campo de texto (então, tecnicamente, o computador recebe isso como texto/caractere: `"25"`), mas para fazer cálculos com essa idade (somar, comparar, etc.), o programa precisa **convertê-la** para um número inteiro de verdade.

### Analogia: trocar moeda em uma viagem

Imagine que você está viajando e só tem reais na carteira, mas o país que você visitou só aceita dólares. Antes de poder gastar o dinheiro, você precisa ir a uma casa de câmbio e **converter** reais em dólares. O valor "equivalente" existe nos dois formatos, mas cada um só é aceito/utilizável em contextos diferentes. É basicamente isso que a conversão de tipos faz com os dados.

### Tipos comuns de conversão

```
"25"  (texto)         →  25      (inteiro)     conversão texto → número
25    (inteiro)        →  "25"    (texto)       conversão número → texto
3.9   (real)            →  3       (inteiro)      conversão real → inteiro (perde a parte decimal!)
5     (inteiro)         →  5.0     (real)         conversão inteiro → real (não perde nada)
```

### Um erro comum: perda de informação na conversão

Quando você converte um número real para inteiro, a parte decimal **é descartada** (não é arredondada, na maioria das linguagens, é simplesmente cortada). Por exemplo, convertendo `9.9` para inteiro, você normalmente obtém `9`, não `10`. Isso é uma fonte clássica de bugs para quem está começando, então preste atenção sempre que fizer esse tipo de conversão.

### Exemplo em pseudocódigo

```
INÍCIO
  LEIA idadeTexto        // o que o usuário digitou, como texto
  idadeNumero ← CONVERTER_PARA_INTEIRO(idadeTexto)
  proximoAniversario ← idadeNumero + 1
  ESCREVA "No próximo aniversário você terá: ", proximoAniversario
FIM
```

---

## 3.5 — Constantes: valores que nunca mudam

Uma **constante** é parecida com uma variável, mas com uma diferença fundamental: **seu valor é definido uma vez e nunca pode ser alterado durante a execução do programa.**

### Analogia: a placa gravada em metal

Uma variável é como um quadro-negro, onde você pode apagar e reescrever o valor quantas vezes quiser. Uma constante é como uma placa gravada em metal: uma vez feita, o valor ali **não muda nunca mais**.

### Por que usar constantes?

1. **Clareza:** ao ler `PI` no código, fica claro que é o valor de π, em vez de um número "mágico" solto como `3.14159` sem explicação nenhuma.
2. **Segurança:** evita que, por engano, alguém (ou você mesmo, no futuro) mude acidentalmente um valor que nunca deveria mudar.
3. **Manutenção:** se um valor precisar ser atualizado no futuro (por exemplo, uma alíquota de imposto que mudou por lei), basta mudar em **um único lugar** — a declaração da constante, em vez de procurar o valor espalhado pelo código inteiro.

### Exemplo em Portugol

```portugol
algoritmo "AreaCirculo"
const
   PI = 3.14159

var
   raio, area: real

inicio
   escreva("Digite o raio do círculo: ")
   leia(raio)

   area <- PI * raio * raio

   escreva("A área do círculo é: ", area)
fimalgoritmo
```

Note que, mesmo que alguém tentasse escrever `PI <- 4` em algum lugar do código, isso geraria um **erro**, porque uma constante, por definição, não pode ser reatribuída.

---

## 3.6 — Regras e boas práticas para nomear variáveis

Nomear bem uma variável é uma das habilidades mais subestimadas por quem está começando, e uma das que mais faz diferença na hora de reler ou corrigir o próprio código depois.

### Regras técnicas (variam um pouco entre linguagens, mas em geral):

- Não pode começar com número (`1idade` é inválido, `idade1` é válido).
- Não pode ter espaços (`nota final` é inválido; use `notaFinal` ou `nota_final`).
- Não pode usar palavras reservadas da linguagem (como `SE`, `ENQUANTO`, `INICIO`).
- Pode usar letras, números e underline (`_`), mas geralmente deve começar com letra.

### Boas práticas (isso não é "regra obrigatória", mas faz toda a diferença):

- **Use nomes descritivos.** `idade` é melhor que `x`. `notaFinal` é melhor que `nf`.
- **Seja consistente com o estilo de escrita.** Dois estilos comuns:
  - `camelCase`: `notaFinal`, `precoTotal` (primeira palavra minúscula, as seguintes com inicial maiúscula)
  - `snake_case`: `nota_final`, `preco_total` (tudo minúsculo, separado por underline)
- **Evite abreviações obscuras.** `qtdProdEstoq` é confuso; `quantidadeProdutoEstoque` é claro (mesmo sendo mais longo).

### Exemplo: nome ruim vs. nome bom

```
❌ Ruim:                          ✅ Bom:
INÍCIO                            INÍCIO
  LEIA x                            LEIA precoProduto
  LEIA y                            LEIA quantidade
  z ← x * y                        valorTotal ← precoProduto * quantidade
  ESCREVA z                         ESCREVA "Total: ", valorTotal
FIM                               FIM
```

Repare como a segunda versão é **compreensível só de olhar**, sem precisar "decifrar" o que cada letra representa. Isso vira ouro quando seu algoritmo cresce e tem dezenas de variáveis.

---

## 📊 Diagrama resumo do módulo

```
                        VARIÁVEL
                           │
        ┌──────────────────┼────────────────────┐
        ▼                  ▼                    ▼
      NOME                TIPO                VALOR
 (a "etiqueta"      (inteiro, real,      (o que está guardado,
  que a identifica)   caractere, lógico)   pode mudar com o tempo)
        │
        ▼
   Vive num espaço da MEMÓRIA RAM
        │
        ▼
  Pode ser CONVERTIDA para outro tipo
        │
        ▼
  Se o valor NUNCA deve mudar → use uma CONSTANTE
```

---

## 💡 Erros comuns de quem está começando

1. **Usar uma variável antes de declará-la.** Em muitas linguagens (e no Portugol), isso gera erro, a "gaveta" precisa existir antes de você tentar guardar algo nela.
2. **Misturar tipos sem conversão.** Tentar somar um texto com um número diretamente costuma gerar erro ou um resultado inesperado, dependendo da linguagem.
3. **Esquecer que converter real para inteiro corta a parte decimal**, achando (erroneamente) que o valor será arredondado.
4. **Tentar alterar o valor de uma constante.** Lembre-se: constante é gravada, não é reescrita.
5. **Usar nomes de variáveis genéricos demais** (`var1`, `temp`, `dado`), dificultando a leitura do próprio código depois.

---

## ✅ Boas práticas desde já

- Declare suas variáveis com o **tipo certo** para o dado que elas vão guardar (não declare "idade" como texto, por exemplo).
- Use **constantes** para qualquer valor fixo que se repete no algoritmo (como taxas, limites, valores de referência).
- Adote um padrão de nomenclatura (camelCase ou snake_case) e **seja consistente** durante todo o algoritmo/projeto.
- Sempre que for necessário converter tipos, **pense no que pode ser perdido** na conversão (como casas decimais).

---

## 🎲 Curiosidades

- O termo **"bug"** (erro de programação) tem uma origem curiosa: em 1947, um mau funcionamento em um computador da Marinha americana foi causado literalmente por uma **mariposa** (bug, em inglês) presa em um relé. A engenheira Grace Hopper documentou o inseto colado no registro, com a frase "first actual case of bug being found", e o termo "debugar" (tirar o bug) pegou.
- Em algumas linguagens de programação (como Python), você não precisa declarar o tipo explicitamente, o interpretador "adivinha" o tipo pelo valor atribuído. Isso se chama **tipagem dinâmica**, em oposição à **tipagem estática** (como em Java ou C, e como fazemos no Portugol), onde o tipo é fixado no momento da declaração.
- Grace Hopper também é famosa por ter ajudado a criar um dos primeiros compiladores da história, que traduziam instruções escritas de forma mais próxima do inglês para linguagem de máquina, uma ideia parecida com o que fazemos aqui indo do pseudocódigo para uma linguagem real.

---

## 📝 Exercícios

### Fáceis

1. Explique com suas próprias palavras a diferença entre uma variável e uma constante.
2. Diga qual seria o tipo de dado mais adequado para armazenar: (a) o CEP de uma casa, (b) o preço de um produto, (c) se uma pessoa é maior de idade, (d) o nome de um aluno.
3. Aponte o erro de nomenclatura em cada variável abaixo e corrija: `1nome`, `nota final`, `SE`.
4. Escreva em pseudocódigo um algoritmo que declare uma variável `nome` (texto) e uma variável `idade` (inteiro), leia os dois valores e mostre "Nome: [nome], Idade: [idade]".
5. Explique, com uma analogia própria (diferente da usada no módulo), o que é a memória RAM.

### Médios

6. Escreva em Portugol um algoritmo com uma constante `TAXA_ENTREGA = 5.0` que leia o valor de uma compra e mostre o valor final somando a taxa de entrega.
7. Dado o valor real `7.8`, explique o que aconteceria se ele fosse convertido para inteiro sem arredondamento, qual seria o valor resultante?
8. Escreva em pseudocódigo um algoritmo que converta uma temperatura digitada como texto (ex: "36.5") para um valor numérico e mostre se está acima de 37.5 (indicando possível febre).
9. Reescreva as variáveis abaixo seguindo boas práticas de nomenclatura (escolha um padrão, camelCase ou snake_case, e seja consistente): `x`, `nf`, `qtdprod`, `vlTotal`.
10. Explique por que, em geral, é considerado mais seguro usar uma constante em vez de uma variável comum para representar um valor como uma alíquota de imposto.

### Difíceis

11. Escreva em Portugol um algoritmo completo que: declare uma constante `SALARIO_MINIMO = 1518.00`, leia o salário de um funcionário, e mostre quantos salários mínimos aquele valor representa (o resultado pode ser um número com casas decimais).
12. Um programador escreveu o seguinte código com um erro proposital. Encontre o erro e explique por que ele é um problema:
```portugol
algoritmo "Erro"
const
   LIMITE = 100

var
   valor: inteiro

inicio
   valor <- 50
   LIMITE <- valor + 10
   escreva(LIMITE)
fimalgoritmo
```
13. Escreva em pseudocódigo um algoritmo que leia o preço de um produto em reais (como número real) e o converta para uma exibição em texto formatado como "R$ [valor]" (você pode descrever a lógica da conversão sem se preocupar com a sintaxe exata de formatação).
14. Explique, com um exemplo próprio, uma situação da vida real em que usar o tipo errado de dado (por exemplo, guardar um número de telefone como um `inteiro` em vez de texto) pode causar um problema.
15. Escreva um algoritmo (em pseudocódigo) que leia três notas de um aluno (como valores reais), calcule a média e converta o resultado final para inteiro antes de exibi-lo (mostrando ao usuário que a parte decimal será perdida).

### Desafios

16. **Desafio da calculadora de troco:** escreva em Portugol um algoritmo que declare uma constante para o valor de uma nota fixa (por exemplo, `VALOR_NOTA_50 = 50.0`), leia o valor de uma compra, calcule o troco e diga quantas notas de 50 seriam necessárias para pagar aquele troco (considerando apenas a parte inteira da divisão, já que não existe "meia nota").
17. **Desafio da conversão em cadeia:** pesquise (ou raciocine) sobre a ordem correta de conversão nesta situação: o usuário digita a idade como texto, você precisa somar 5 anos a essa idade, e depois mostrar o resultado novamente como texto formatado dentro de uma frase. Descreva, passo a passo, todas as conversões de tipo necessárias nesse processo.

---

## 📖 Gabarito explicado

**1.** Uma variável guarda um valor que **pode mudar** durante a execução do programa (como a idade de uma pessoa em um cadastro que é atualizado anualmente). Uma constante guarda um valor que é definido uma única vez e **nunca muda** durante a execução (como o valor de π ou uma taxa fixa).

**2.**
- (a) CEP → caractere/texto (mesmo sendo só números, o CEP não é usado para cálculos matemáticos, e pode ter zeros à esquerda que seriam perdidos se fosse tratado como número).
- (b) Preço → real.
- (c) Maior de idade → lógico.
- (d) Nome → caractere/texto.

*Atenção especial ao item (a):* esse é um erro clássico! Muita gente guarda CEP, telefone ou CPF como número, mas como esses dados não são usados em contas matemáticas (você nunca vai "somar" dois CEPs) e podem ter zeros à esquerda importantes, o correto é tratá-los como texto.

**3.**
- `1nome` → inválido, não pode começar com número → correção: `nome1`
- `nota final` → inválido, tem espaço → correção: `notaFinal` ou `nota_final`
- `SE` → inválido, é palavra reservada → correção: `situacaoAluno` ou similar

**4.**
```
INÍCIO
  LEIA nome
  LEIA idade
  ESCREVA "Nome: ", nome, ", Idade: ", idade
FIM
```

**5.** Resposta livre — o importante é que a analogia transmita a ideia de "espaços numerados que guardam informação, cada um com seu próprio conteúdo".

**6.**
```portugol
algoritmo "ValorComEntrega"
const
   TAXA_ENTREGA = 5.0

var
   valorCompra, valorFinal: real

inicio
   escreva("Digite o valor da compra: ")
   leia(valorCompra)

   valorFinal <- valorCompra + TAXA_ENTREGA

   escreva("O valor final é: ", valorFinal)
fimalgoritmo
```

**7.** O valor resultante seria `7` — a conversão de real para inteiro, na maioria das linguagens e no Portugol, **corta** a parte decimal em vez de arredondar. É um erro muito comum achar que 7.8 viraria 8.

**8.**
```
INÍCIO
  LEIA temperaturaTexto
  temperaturaNumero ← CONVERTER_PARA_REAL(temperaturaTexto)
  SE temperaturaNumero > 37.5 ENTÃO
    ESCREVA "Possível febre"
  SENÃO
    ESCREVA "Temperatura normal"
  FIM SE
FIM
```

**9.** Exemplo em camelCase: `x` → `valor`, `nf` → `notaFinal`, `qtdprod` → `quantidadeProdutos`, `vlTotal` → `valorTotal` (o importante aqui é a consistência — todas seguindo o mesmo padrão).

**10.** Porque uma constante **impede alterações acidentais**, se um valor tão sensível quanto uma alíquota de imposto fosse guardado em uma variável comum, bastaria um erro de digitação em qualquer parte do código para alterá-la sem querer, e esse tipo de erro pode ser difícil de detectar depois.

**11.**
```portugol
algoritmo "SalariosMinimos"
const
   SALARIO_MINIMO = 1518.00

var
   salario, quantidade: real

inicio
   escreva("Digite o salário: ")
   leia(salario)

   quantidade <- salario / SALARIO_MINIMO

   escreva("Isso representa ", quantidade, " salários mínimos.")
fimalgoritmo
```

**12.** O erro está na linha `LIMITE <- valor + 10`, o programa está tentando **alterar o valor de uma constante**, o que não é permitido. Constantes só recebem valor uma vez, na sua declaração (`const LIMITE = 100`), e depois disso não podem ser reatribuídas. Esse código geraria um erro de compilação/execução.

**13.**
```
INÍCIO
  LEIA precoNumero            // valor real, ex: 49.9
  precoTexto ← CONVERTER_PARA_TEXTO(precoNumero)
  exibicaoFinal ← "R$ " + precoTexto
  ESCREVA exibicaoFinal
FIM
```

**14.** Exemplo: se um número de telefone como `011987654321` for guardado como `inteiro`, o zero à esquerda (`0`) é **perdido**, porque numericamente `011987654321` é igual a `11987654321`, um número não "lembra" zeros à esquerda como o texto lembra. Isso causaria erro na hora de discar ou exibir o telefone corretamente.

**15.**
```
INÍCIO
  LEIA nota1
  LEIA nota2
  LEIA nota3
  media ← (nota1 + nota2 + nota3) / 3
  mediaInteira ← CONVERTER_PARA_INTEIRO(media)
  ESCREVA "A média (arredondada para baixo) é: ", mediaInteira
FIM
```
*Observação importante:* repare que a conversão aqui **corta** a parte decimal (não arredonda de verdade) — é um detalhe que vale a pena destacar ao usuário final, para não gerar confusão.

**16.**
```portugol
algoritmo "TrocoEmNotas"
const
   VALOR_NOTA_50 = 50.0

var
   valorCompra, valorPago, troco: real
   quantidadeNotas: inteiro

inicio
   escreva("Digite o valor da compra: ")
   leia(valorCompra)

   escreva("Digite o valor pago: ")
   leia(valorPago)

   troco <- valorPago - valorCompra
   quantidadeNotas <- CONVERTER_PARA_INTEIRO(troco / VALOR_NOTA_50)

   escreva("Troco: ", troco)
   escreva("Notas de 50 necessárias (parte inteira): ", quantidadeNotas)
fimalgoritmo
```

**17.** Passo a passo:
```
1. LEIA idadeTexto (tipo texto, ex: "30")
2. idadeNumero ← CONVERTER_PARA_INTEIRO(idadeTexto)   → converte texto para inteiro
3. novaIdade ← idadeNumero + 5                          → soma usando o valor numérico
4. novaIdadeTexto ← CONVERTER_PARA_TEXTO(novaIdade)    → converte de volta para texto
5. ESCREVA "Em 5 anos você terá ", novaIdadeTexto, " anos."
```
*Por que é difícil:* esse exercício mostra que, na prática, muitas vezes você precisa **ir e voltar** entre tipos diferentes (texto → número → texto) dentro do mesmo algoritmo, e cada conversão precisa ser pensada com cuidado para não gerar erros.

---

## 🧾 Resumo do Módulo 3

- **Variável** é um espaço nomeado na memória que guarda um valor que pode mudar durante a execução do algoritmo.
- A **memória RAM** funciona como um prédio de "apartamentos" numerados, cada variável ocupa um desses espaços.
- **Tipos de dados** (inteiro, real, caractere, lógico) dizem ao computador como interpretar a informação guardada.
- **Conversão de tipos** transforma um valor de um tipo para outro, e é importante lembrar que essa conversão pode causar perda de informação (como casas decimais).
- **Constantes** são como variáveis, mas com valor fixo, que nunca pode ser alterado após a declaração, usadas para valores que não devem (ou não podem) mudar.
- **Nomear bem as variáveis** é uma prática essencial para manter o código legível e fácil de manter.

No próximo módulo, vamos aprender a **manipular** esses valores: os **operadores** matemáticos, relacionais e lógicos que permitem fazer cálculos, comparações e combinações de condições.

➡️ **Próximo módulo:** [Módulo 4 — Operadores](04-operadores.md)
