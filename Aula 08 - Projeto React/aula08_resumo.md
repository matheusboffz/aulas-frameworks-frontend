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
- **Acesso →** permite consultar ou alterar suas propriedades.
- **Métodos →** funções associadas ao objeto.
- **`this` →** referencia o próprio objeto dentro de seus métodos.

```javascript
console.log("=== 07 — Objetos ===");
const aluno = {
    nome: "Carlos",
    idade: 20,
    curso: "ADS",
    apresentar() {
        console.log(`Meu nome é ${this.nome} e curso ${this.curso}.`);
    }
};
console.log(aluno.nome);
console.log(aluno.curso);
aluno.apresentar();
```

---

## 5. DOM (Document Object Model)

O **DOM** é uma representação em árvore da estrutura de uma página web, permitindo que o JavaScript altere seu conteúdo, estilos e estrutura.

### 🔍 Selecionando Elementos do DOM

| Método | Descrição |
|---|---|
| `getElementById()` | Seleciona um elemento pelo `id` |
| `querySelector()` | Seleciona o **primeiro** elemento que corresponde a um seletor CSS |
| `querySelectorAll()` | Seleciona **todos** os elementos que correspondem ao seletor CSS |

### ✏️ Alterando o DOM com JavaScript

| Propriedade / Método | Descrição |
|---|---|
| `textContent` | Altera o texto de um elemento |
| `value` | Altera o valor de campos de formulário |
| `classList` | Adiciona, remove ou alterna classes CSS |
| `createElement()` | Cria novos elementos HTML |
| `appendChild()` | Adiciona elementos ao documento |

```javascript
// Seleciona o botão pelo ID
const botao = document.querySelector("#botao");
// Seleciona o elemento que exibirá a mensagem
const texto = document.querySelector("#mensagem");
// Adiciona um evento de clique ao botão
botao.addEventListener("click", () => {
    // Altera o texto do elemento
    texto.textContent = "Olá! O conteúdo foi alterado.";
});
```

> **Atividade de Revisão:** [wayground.com](https://wayground.com/) | **Material:** [github.com/deivisontakatu/aula-javascript](https://github.com/deivisontakatu/aula-javascript)

---

## 6. JSX — JavaScript XML

### 📖 O que é JSX?

**JSX** é uma extensão de sintaxe para JavaScript que permite escrever estruturas semelhantes a HTML dentro do JavaScript. É utilizado para descrever interfaces de componentes React, combinando a estrutura da interface com a lógica que produz seu conteúdo.

```jsx
const titulo = <h1>Olá, React!</h1>;
```

**Principal vantagem:** simplificar a leitura e a manutenção das interfaces.

### 🔗 Expressões JavaScript no JSX

É possível utilizar as chaves `{ }` para inserir expressões JavaScript no JSX:

```jsx
const nome = "João";
const saudacao = <h1>Olá, {nome}!</h1>;

const a = 10;
const b = 5;
const resultado = <p>Soma: {a + b}</p>;
```

### ⚠️ Diferenças entre JSX e HTML

| Característica | HTML | JSX |
|---|---|---|
| Atributo de classe | `class` | `className` |
| Atributo de rótulo | `for` | `htmlFor` |
| Elementos sem conteúdo | `<img>` | `<img />` (deve ser fechado) |
| Raiz de componente | Múltiplos elementos | Um elemento raiz ou `Fragment` |
| Expressões JavaScript | Não suportado diretamente | Entre chaves `{}` |

```jsx
function LinkDocumentacao() {
  return (
    <a href="https://react.dev" className="link">
      Documentação do React
    </a>
  );
}
```

### ✅ Resumo do JSX

- Facilita a descrição das interfaces React.
- Permite inserir expressões JavaScript entre chaves `{}`.
- Possui convenções diferentes do HTML.
- Organiza interfaces em componentes reutilizáveis.
- **É transformado em JavaScript antes da execução** (transpilado pelo Babel/Vite/etc.).

---

## 7. Componentes React

### 🧱 O que é um Componente?

**Componentes** são unidades independentes e reutilizáveis da interface. Em React, são normalmente **funções JavaScript** que retornam elementos React, geralmente descritos com JSX, permitindo dividir uma aplicação em partes menores e organizadas.

```jsx
function Cabecalho() {
  return (
    <header>
      <h1>React Lab</h1>
    </header>
  );
}
```

> Na prática: uma loja virtual pode ter componentes como `Cabecalho`, `Busca`, `Produto` e `Rodape`.

### 📐 Por que dividir uma interface?

- Uma página pode ter várias partes: menu, busca, cartões, rodapé.
- Colocar tudo em um único componente dificulta a leitura.
- Dividir em partes menores facilita a organização do código.
- **Cada parte pode ser reutilizada em outras páginas.**

### 🛠️ Como utilizar componentes no JSX?

1. **Crie uma função** com nome iniciado em **letra maiúscula**.
2. **Use `return`** para definir o que será exibido.
3. **Utilize `<NomeDoComponente />`** para exibir o componente.
4. **Combine componentes** para montar uma página completa.

```jsx
function Cabecalho() {
  return <h1>Catálogo React</h1>;
}
function App() {
  return (
    <main>
      <Cabecalho />
      <p>Explore os principais conceitos.</p>
    </main>
  );
}
```

### 🌳 Árvore de Componentes

Uma aplicação pode ser representada como uma árvore hierárquica, onde o componente principal contém componentes filhos, que por sua vez podem conter outros componentes:

```
App
├── Cabecalho
├── BarraDePesquisa
├── ListaDeConceitos
│   ├── CardConceito
│   └── CardConceito
└── Rodape
```

### ♻️ Componentes e Reutilização

- Um componente pode ser reutilizado em diferentes partes da aplicação.
- A reutilização evita repetir estruturas semelhantes.
- Componentes ajudam a manter a consistência visual.
- Os dados específicos de cada utilização podem ser recebidos por meio de **props**.

---

## 8. Props (Propriedades)

### 📬 O que são Props?

**Props** é a abreviação de *properties* (propriedades). São dados recebidos por um componente React que permitem:
- Enviar informações de um **componente pai** para um **filho**.
- **Reutilizar componentes** com conteúdos diferentes.

```jsx
function CardConceito({ titulo, descricao }) {
  return (
    <article>
      <h2>{titulo}</h2>
      <p>{descricao}</p>
    </article>
  );
}
```

> **Conceito-chave:** a estrutura do componente permanece igual, enquanto os dados exibidos podem mudar.

### 💡 Por que utilizar Props?

- Permitem **personalizar componentes reutilizáveis**.
- Evitam duplicar estruturas de interface.
- Facilitam a passagem de informações entre componentes.
- Tornam explícitos os dados utilizados por cada componente.

```jsx
<CardConceito
  titulo="JSX"
  descricao="Sintaxe para descrever interfaces."
/>
<CardConceito
  titulo="Props"
  descricao="Entradas recebidas por componentes."
/>
```

```jsx
function Saudacao({ nome }) {
  return <h1>Olá, {nome}!</h1>;
}
// Utilização
<Saudacao nome="Joao" />
<Saudacao nome="Maria" />
// Resultado: cada utilização apresenta uma mensagem diferente com o mesmo componente.
```

### 🔄 Fluxo de Dados entre Componentes

- Os dados fluem do **componente pai** para o **filho** (unidirecional).
- O componente pai organiza e fornece as informações.
- O componente filho recebe as props e apresenta os dados.
- Esse fluxo explícito facilita compreender de onde vêm as informações.

```jsx
function Card({ titulo }) {
  return <h2>{titulo}</h2>;
}
function App() {
  return (
    <main>
      <Card titulo="Componentes" />
      <Card titulo="Props" />
    </main>
  );
}
```

### 📊 Tipos de Valores em Props

| Tipo | Descrição |
|---|---|
| **Strings** | Textos informados entre aspas |
| **Números** | Valores numéricos passados entre chaves `{}` |
| **Booleanos** | Valores `true` ou `false` |
| **Arrays e Objetos** | Estruturas de dados enviadas ao componente |
| **Funções** | Referências a funções (ex: callbacks de eventos) |
| **Elementos React** | Conteúdo que pode ser renderizado pelo componente |

---

## 9. Virtual DOM & Reconciliação

### 🌐 O que é o DOM?

O **DOM (Document Object Model)** é a representação estruturada do documento HTML disponibilizada pelo navegador. Permite que o JavaScript consulte e modifique elementos da página (textos, atributos, estilos). Em interfaces complexas, gerenciar manualmente todas as alterações pode tornar o código difícil de manter.

```javascript
document.querySelector("h1").textContent = "Olá!";
```

### ⚡ O que é o Virtual DOM?

O **Virtual DOM** é um termo utilizado para descrever uma **representação da interface em memória**. O React utiliza descrições de elementos para determinar como a interface deve se apresentar. O desenvolvedor **descreve o resultado esperado** em vez de indicar manualmente cada alteração visual — e o React coordena o processo de atualização.

> O Virtual DOM (usado no React) é uma cópia mais rápida do DOM real. Quando algo muda, o React primeiro atualiza essa cópia, compara com o DOM real e só aplica as diferenças, tornando tudo mais rápido e eficiente.

### ⚖️ DOM vs. Virtual DOM

| DOM | Virtual DOM |
|---|---|
| Representa a estrutura do documento no navegador. | É um modelo conceitual para compreender as descrições da interface usadas pelo React. |
| Pode ser consultado e modificado por JavaScript. | É utilizado pelo React para coordenar a atualização da interface. |
| Reflete a estrutura do documento renderizado. | Ajuda a representar como a interface deve se apresentar. |

### 🔄 Como funciona a atualização da interface?

```text
Mudança → Renderização → Reconciliação → Atualização
```

1. **Mudança:** ocorre uma interação ou atualização de dados.
2. **Renderização:** o React executa novamente os componentes relevantes para calcular a nova descrição da interface.
3. **Reconciliação:** o React compara a nova descrição com a anterior.
4. **Atualização:** as alterações necessárias são aplicadas ao DOM do navegador.

> **Exemplo — Contador:** Um contador começa exibindo o valor zero. Ao clicar em "Incrementar", o estado passa a representar o valor um. A interface é descrita com base no valor atual do estado. O React coordena a atualização necessária — **não é necessário localizar manualmente o elemento e substituir seu texto no DOM.**

### 🔍 Reconciliação e Identidade dos Elementos

- **Reconciliação** é o processo pelo qual o React determina as mudanças necessárias entre descrições sucessivas da interface.
- O React considera a **estrutura dos elementos** e sua **identidade**.
- Nem toda nova renderização exige alterações no DOM.
- O objetivo é coordenar a atualização da interface de acordo com as mudanças identificadas.
- Em listas, as propriedades `key` ajudam a identificar cada item.
- **Chaves estáveis** facilitam a associação entre itens quando a lista é alterada.

---

## 10. Listas e Keys

### 📋 Por que renderizar listas no React?

Aplicações frequentemente exibem listas de alunos, produtos, tarefas e conceitos — dados normalmente armazenados em arrays. O React permite transformar coleções de dados em elementos de interface usando o método `map()`.

> **Conceito-chave:** `map()` transforma cada item de um array em um elemento da interface.

```jsx
const nomes = ["Joao", "Maria", "Ana"];
const itens = nomes.map((nome) => (
  <li>{nome}</li>
));
```

```javascript
// map() percorre os elementos de um array
// Uma função é executada para cada item
// O resultado é um novo array com os valores retornados
```

### 🔑 O que é `key`?

- `key` é uma **propriedade especial** utilizada pelo React para identificar elementos entre irmãos em uma lista.
- Ajuda o React a reconhecer quais itens foram **mantidos, adicionados, removidos ou reordenados**.
- **Deve ser informada** ao renderizar listas de elementos.
- Normalmente, utiliza-se um **identificador** associado a cada item dos dados.

```jsx
const alunos = [
  { id: 101, nome: "Ana" },
  { id: 102, nome: "Bruno" },
  { id: 103, nome: "Caio" }
];

{alunos.map((aluno) => (
  <li key={aluno.id}>{aluno.nome}</li>
))}
```

### 🔍 Listas, Filtros e Atualização de Dados

- Listas podem ser combinadas com `filter()` e `map()`.
- `filter()` seleciona os itens que atendem a uma condição.
- `map()` transforma os itens selecionados em elementos JSX.
- As chaves devem continuar associadas aos mesmos itens após a filtragem.
- Quando uma lista está em estado, prefira **produzir novos arrays** em vez de modificar diretamente o array existente.

```jsx
const conceitos = ["JSX", "Props", "State", "Hooks"];

function ConceitosBasicos() {
  const basicos = conceitos.filter(
    (item) => item !== "Hooks"
  );
  return (
    <ul>
      {basicos.map((item) => (
        <li key={item}>{item}</li>
      ))}
    </ul>
  );
}
```

---

## 11. Renderização Condicional

### ❓ O que é Renderização Condicional?

Permite **mostrar, ocultar ou alterar** partes da interface conforme uma condição. Utiliza expressões e operadores JavaScript dentro do JSX para adaptar a interface aos dados e ao estado da aplicação.

> **Exemplo:** uma tela pode apresentar mensagens diferentes para usuários autenticados e não autenticados.

### 🔀 Utilizando `if` e `return`

A instrução `if` é indicada quando as partes da interface são substancialmente diferentes. O `return` pode encerrar a execução do componente antecipadamente, mantendo o código organizado.

```jsx
function MensagemAcesso({ autenticado }) {
  if (autenticado) {
    return <p>Bem-vindo de volta!</p>;
  }
  return <p>Entre para continuar.</p>;
}
```

> **Quando utilizar?** Quando cada condição exige uma resposta ou interface diferente.

### 📊 Renderização Condicional com Dados e Estado

- As condições podem depender de props, estado ou dados recebidos pela aplicação.
- Listas podem apresentar resultados ou uma mensagem quando estiverem vazias.
- Interfaces também podem representar **estados de carregamento e erro**.
- A condição deve refletir o estado real dos dados.

```jsx
function ListaResultados({ resultados }) {
  if (resultados.length === 0) {
    return <p>Nenhum resultado encontrado.</p>;
  }
  return (
    <ul>
      {resultados.map((resultado) => (
        <li key={resultado.id}>
          {resultado.nome}
        </li>
      ))}
    </ul>
  );
}
```

### ⚡ Operador Ternário — Alternando Mensagens

O **operador ternário** pode apresentar diferentes mensagens conforme o estado:

```text
condicao ? valorSeVerdadeiro : valorSeFalso
```

- É útil para alternar entre carregamento e resultado.
- A condição deve indicar claramente qual estado está ativo.
- Em aplicações maiores, carregamento, erro e sucesso podem precisar de tratamentos distintos.

```jsx
function ResultadoBusca({ carregando }) {
  return (
    <div>
      {carregando
        ? <p>Buscando...</p>
        : <p>Busca finalizada.</p>}
    </div>
  );
}
```

> **Aplicações:** catálogos, resultados de busca, listas de produtos e painéis administrativos.

---

## 12. Atividade Prática

### 🎯 Requisitos da Atividade

Desenvolver uma **aplicação React** que utilize **todos os conceitos estudados nesta aula**:

- ✅ **JSX** — sintaxe e expressões JavaScript
- ✅ **Componentes** — criação, composição e reutilização
- ✅ **Props** — passagem de dados entre componentes
- ✅ **Virtual DOM** — renderização e reconciliação
- ✅ **Listas e Keys** — renderização de coleções de dados
- ✅ **Renderização Condicional** — controle de exibição da interface

### 📦 Entregáveis

- Criar um **repositório público no GitHub**.
- Incluir um **README** contendo:
  - Descrição da aplicação.
  - Funcionalidades implementadas.
  - Conceitos do React utilizados.

### 🔗 Links Complementares

| Recurso | Link |
|---|---|
| Conceitos React (aula) | [github.com/deivisontakatu/aula-react](https://github.com/deivisontakatu/aula-react) |
| Exemplo Completo | [github.com/deivisontakatu/projeto-react](https://github.com/deivisontakatu/projeto-react) |
| Aplicação Online | [projeto-react-five-swart.vercel.app](https://projeto-react-five-swart.vercel.app/) |

---

## 13. Resumo da Aula

```text
Revisão JS (Variáveis, Funções, Arrays, Objetos, DOM)
       ↓
JSX (Sintaxe, Expressões, Diferenças do HTML)
       ↓
Componentes (Criação, Composição, Árvore, Reutilização)
       ↓
Props (Passagem de Dados Pai → Filho, Tipos de Valores)
       ↓
Virtual DOM & Reconciliação (Renderização Eficiente)
       ↓
Listas e Keys (map(), filter(), key única)
       ↓
Renderização Condicional (if/return, Ternário, Estados)
       ↓
Atividade: Aplicação React integrada no GitHub
```

Nesta aula exploramos os fundamentos essenciais do **React**, partindo de uma revisão sólida de **JavaScript** (variáveis, operadores, condicionais, repetições, funções, arrays, objetos e manipulação do DOM). Em seguida, aprofundamos os conceitos centrais do React: **JSX** como extensão de sintaxe para descrever interfaces, **Componentes** como unidades independentes e reutilizáveis, **Props** para o fluxo de dados unidirecional entre componentes, **Virtual DOM** e o processo de **Reconciliação** para atualizações eficientes, **Listas e Keys** para renderização de coleções e **Renderização Condicional** para controlar dinamicamente a exibição de partes da interface.

---

## 14. Referências

1. SOUZA, Natan. **Bootstrap 4: conheça a biblioteca front-end mais utilizada no mundo.** São Paulo: Casa do Código, 2018. E-book. Disponível em: https://plataforma.bvirtual.com.br.
2. MACHADO, Kheronn Khennedy. **Angular 11 e Firebase: construindo uma aplicação integrada com a plataforma do Google.** São Paulo: Casa do Código, 2021. E-book. Disponível em: https://plataforma.bvirtual.com.br. Acesso em: 13 maio 2025.
3. EIS, Diego. **Guia Front-end: o caminho das pedras para ser um dev front-end.** São Paulo: Casa do Código, 2015. E-book. Disponível em: https://plataforma.bvirtual.com.br.
4. GONÇALVES, Edson. **Desenvolvendo aplicações Web com JSP, Servlets, JavaServer Faces, Hibernate, EJB 3 Persistence e Ajax.** Rio de Janeiro: Ciência Moderna, c2007.
5. HARTCOPP, Patrícia Ferreira. **Métrica Web.** São Paulo: Contentus, 2020. E-book (94 p.). Disponível em: https://plataforma.bvirtual.com.br/Acervo/Publicacao/185191. Acesso em: 30 abr. 2024.
6. NIEDERAUER, Juliano. **Desenvolvendo Websites com PHP: aprenda a criar Websites dinâmicos e interativos com PHP e banco de dados.** 3. ed. São Paulo: Novatec, 2017.
7. PREECE, J.; ROGERS, Y.; SHARP, H. **Design de Interação: além da interação Homem-Computador.** 3. ed. Porto Alegre: Bookman, 2013.
8. SOUSA, Roque Fernando Marcos. **Canvas HTML 5: composição gráfica e interatividade na Web.** Rio de Janeiro: Brasport, 2014. E-book (194 p.). Disponível em: https://plataforma.bvirtual.com.br/Acervo/Publicacao/160686. Acesso em: 22 jun. 2024.

---
**Material de Apoio:** Disciplina de Frameworks Front-end — Prof. Me. Deivison S. Takatu (SENAI).
