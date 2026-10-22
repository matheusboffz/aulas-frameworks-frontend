# Aula 08 — Projeto React

**Disciplina:** Frameworks Front-end  
**Foco:** Revisão de JavaScript, JSX, Componentes, Props, Virtual DOM, Listas e Keys, Renderização Condicional e Atividade Prática com React.  
**Professor:** Prof. Me. Deivison S. Takatu (`deivison.takatu@edu.senai.br`)

---

## 📌 Sumário

1. [Revisão de JavaScript](#1-revisão-de-javascript)
2. [Variáveis, Tipos de Dados e Operadores](#2-variáveis-tipos-de-dados-e-operadores)
3. [Condicionais e Estruturas de Repetição](#3-condicionais-e-estruturas-de-repetição)
4. [Funções, Arrays e Objetos](#4-funções-arrays-e-objetos)
5. [DOM (Document Object Model)](#5-dom-document-object-model)
6. [JSX — JavaScript XML](#6-jsx--javascript-xml)
7. [Componentes React](#7-componentes-react)
8. [Props (Propriedades)](#8-props-propriedades)
9. [Virtual DOM & Reconciliação](#9-virtual-dom--reconciliação)
10. [Listas e Keys](#10-listas-e-keys)
11. [Renderização Condicional](#11-renderização-condicional)
12. [Atividade Prática](#12-atividade-prática)
13. [Resumo da Aula](#13-resumo-da-aula)
14. [Referências](#14-referências)

---

## 1. Revisão de JavaScript

O JavaScript é a linguagem que permite adicionar comportamento dinâmico e interatividade às páginas web. Ele pode ser incluído de três formas:

- **Inline (na tag HTML):** usando a tag `<script>` diretamente no corpo do HTML para executar funções simples.
- **Arquivo Externo (recomendado):** vinculado com o atributo `src` da tag `<script>`, prática indicada em projetos maiores por facilitar organização e manutenção.
- **Atributos de Eventos:** como `onclick` e `onblur`, que tornam a página interativa ao responder às ações do usuário.

> O JavaScript oferece uma ampla variedade de recursos para controlar aspectos dinâmicos de uma página web, incluindo manipulação do DOM, animações, efeitos visuais, consumo de APIs e construção de aplicações web modernas.

**Referência oficial:** [developer.mozilla.org](https://developer.mozilla.org)

---

## 2. Variáveis, Tipos de Dados e Operadores

### 📦 Variáveis

Em JavaScript, variáveis **não precisam ser declaradas no início do código** e os nomes são **case sensitive** (`nome`, `Nome` e `NOME` são identificadores distintos).

| Declaração | Escopo | Descrição |
|---|---|---|
| `var` | Função / Global | Acessível em toda a função onde foi criada, ou global se fora de funções. |
| `let` | Bloco `{ }` | Existe apenas dentro do bloco em que foi declarado — mais seguro e previsível. |
| `const` | Bloco `{ }` | Valor constante que não pode ser reatribuído após a declaração. |

```javascript
console.log("=== 01 — Variáveis e Tipos ===");
const nome = "João";
let idade = 20;
const estudante = true;
console.log(nome);
console.log(idade);
console.log(estudante);
console.log(typeof nome);      // string
console.log(typeof idade);     // number
console.log(typeof estudante); // boolean
console.log(`Olá, ${nome}! Você tem ${idade} anos.`);
```

### 🔢 Tipos de Dados

| Tipo | Exemplo |
|---|---|
| `String` | `"Olá"` |
| `Number` | `10`, `3.14` |
| `Boolean` | `true`, `false` |
| `Undefined` | valor não definido |
| `Null` | ausência intencional de valor |
| `Object` | `{ nome: "Ana", idade: 20 }` |
| `Array` | `[10, 20, 30]` |
| `Symbol` | identificador único |
| `BigInt` | números inteiros muito grandes |

> `typeof` → verifica o tipo de um valor. O JavaScript identifica automaticamente o tipo de dado armazenado.

### ➕ Operadores

**Aritméticos:**

| Operador | Descrição |
|---|---|
| `+` | Soma dois valores |
| `-` | Subtrai um valor de outro |
| `*` | Multiplica valores |
| `/` | Divide um valor por outro |
| `%` | Retorna o resto da divisão |
| `**` | Realiza uma exponenciação |
| `++` | Incrementa o valor em 1 |
| `--` | Decrementa o valor em 1 |

**Comparação:**

| Operador | Descrição |
|---|---|
| `==` | Compara os valores, permitindo conversão de tipo |
| `===` | Compara valor **e tipo** (estritamente igual) |
| `!=` | Verifica se os valores são diferentes |
| `!==` | Verifica se valor ou tipo são diferentes |
| `>` | Maior que |
| `<` | Menor que |
| `>=` | Maior ou igual a |

**Lógicos:**

| Operador | Descrição |
|---|---|
| `&&` | E: todas as condições devem ser verdadeiras |
| `\|\|` | OU: pelo menos uma condição deve ser verdadeira |
| `!` | NÃO: inverte o resultado lógico |

**Atribuição:**

| Operador | Descrição |
|---|---|
| `=` | Atribui um valor |
| `+=` | Soma e atribui |
| `-=` | Subtrai e atribui |
| `*=` | Multiplica e atribui |
| `/=` | Divide e atribui |
| `%=` | Calcula o resto e atribui |

```javascript
console.log("=== 02 — Operadores ===");
const nota1 = 8;
const nota2 = 7;
const media = (nota1 + nota2) / 2;
console.log("Média:", media);
console.log("Aprovado:", media >= 7);
console.log("Nota1 === Nota2:", nota1 === nota2);
```

---

## 3. Condicionais e Estruturas de Repetição

### 🔀 Condicionais

Em JavaScript, **condicionais** são estruturas de controle que permitem executar diferentes blocos de código dependendo de uma condição booleana:

- **`if`:** avalia uma expressão e executa o bloco se a condição for verdadeira.
- **`else if`:** testa múltiplas condições em sequência.
- **`else`:** executa outro bloco caso nenhuma condição anterior seja verdadeira.
- **Operador Ternário (`? :`):** forma compacta para condicionais simples.

```javascript
console.log("=== 03 — Condicionais ===");
const nota = 8;
if (nota >= 9) {
    console.log("Excelente");
} else if (nota >= 7) {
    console.log("Aprovado");
} else {
    console.log("Reprovado");
}
// Operador ternário
const resultado = nota >= 7 ? "Aprovado" : "Reprovado";
console.log(resultado);
```

### 🔁 Estruturas de Repetição

Permitem executar um bloco de código várias vezes enquanto uma condição for atendida:

| Estrutura | Descrição |
|---|---|
| `for` | Usado quando sabemos ou controlamos a quantidade de repetições. |
| `while` | Repete enquanto uma condição for verdadeira. |
| `do...while` | Executa o bloco pelo menos uma vez e depois verifica a condição. |
| `break` | Interrompe a repetição imediatamente. |
| `continue` | Interrompe a iteração atual e passa para a próxima. |

```javascript
console.log("=== 04 — Repetições ===");
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
console.log("Pares:");
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log(i);
    }
}
```

---

## 4. Funções, Arrays e Objetos

### 🔧 Funções

Funções são blocos de código que executam uma tarefa específica e podem retornar um valor. Permitem organizar o código e evitar repetição.

**Declarações:**
- **Função Tradicional:** `function nome() {}`
- **Arrow Function:** `const nome = () => {}`

```javascript
console.log("=== 05 — Funções ===");
function somar(a, b) {
    return a + b;
}
const resultado = somar(10, 20);
console.log("Resultado:", resultado);

const multiplicar = (a, b) => a * b;
console.log("Multiplicação:", multiplicar(5, 4));
```

**Funções nativas importantes:**

| Função | Descrição |
|---|---|
| `console.log()` | Mostra mensagens no console (útil para depuração) |
| `alert()` / `prompt()` / `confirm()` | Interação básica com o usuário |
| `document.getElementById()` / `document.querySelector()` | Seleciona elementos do HTML |
| `.addEventListener()` | Adiciona eventos (cliques, scroll, input, etc.) |
| `.innerHTML` / `.textContent` | Altera o conteúdo de elementos HTML |

### 📋 Arrays

Arrays são estruturas utilizadas para armazenar vários valores em uma única variável. Os elementos são organizados em sequência e acessados pelo índice.

```javascript
console.log("=== 06 — Arrays ===");
const notas = [7, 8, 5, 9, 10];
console.log("Notas:", notas);
console.log("Quantidade:", notas.length);
notas.forEach((nota, indice) => {
    console.log(indice, nota);
});
const aprovados = notas.filter(nota => nota >= 7);
console.log("Aprovados:", aprovados);
```

### 🧩 Objetos

Objetos são estruturas para armazenar informações relacionadas em propriedades e comportamentos em métodos.

- **Propriedades →** armazenam dados do objeto.
