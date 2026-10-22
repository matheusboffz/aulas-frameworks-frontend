# Aula 07 — Frameworks CSS

**Disciplina:** Frameworks Front-end  
**Foco:** Fundamentos de CSS, Formas de Aplicação, Propriedades Essenciais, Box Model, Flexbox, Layouts Responsivos, Introdução aos Frameworks CSS, Tailwind CSS (Abordagem Utility-First), Instalação e Atividades Práticas.  
**Professor:** Prof. Me. Deivison S. Takatu (`deivison.takatu@edu.senai.br`)  

---

## 📌 Sumário

1. [Introdução ao CSS (Cascading Style Sheets)](#1-introdução-ao-css-cascading-style-sheets)
2. [Formas de Aplicação do CSS](#2-formas-de-aplicação-do-css)
3. [Propriedades Essenciais e Seletores (Class e ID)](#3-propriedades-essenciais-e-seletores-class-e-id)
4. [CSS Box Model (Modelo de Caixas)](#4-css-box-model-modelo-de-caixas)
5. [Flexbox (Flexible Box Layout) & Responsividade](#5-flexbox-flexible-box-layout--responsividade)
6. [Atividade Prática 01 — Box Model & Flexbox](#6-atividade-prática-01--box-model--flexbox)
7. [O que é um Framework CSS?](#7-o-que-é-um-framework-css)
8. [Tailwind CSS & Abordagem Utility-First](#8-tailwind-css--abordagem-utility-first)
9. [Formas de Importação e Ferramentas do Tailwind](#9-formas-de-importação-e-ferramentas-do-tailwind)
10. [Atividade Prática 02 — Projeto com Tailwind CSS](#10-atividade-prática-02--projeto-com-tailwind-css)
11. [Resumo da Aula](#11-resumo-da-aula)
12. [Referências](#12-referências)

---

## 1. Introdução ao CSS (Cascading Style Sheets)

O **CSS (Cascading Style Sheets)** é a linguagem responsável por estilizar e organizar visualmente documentos HTML. Ele controla cores, fontes, margens, alinhamentos, dimensões e posicionamento, garantindo a criação de interfaces modernas, organizadas e responsivas.

### 📐 Sintaxe Básica do CSS
O CSS funciona definindo regras estilísticas no formato:
```css
seletor {
  propriedade: valor;
}
```
- **Seletor:** Indica qual tag, classe ou ID HTML receberá a estilização.
- **Propriedade:** O atributo visual a ser modificado (ex: `background-color`, `color`, `font-size`).
- **Valor:** A configuração específica atribuída à propriedade (ex: `#FF0000`, `16px`).

### 🔄 Comparativo: HTML Legado vs. CSS Moderno
Antigamente, estilos eram aplicados via atributos diretos nas tags HTML. O CSS trouxe separação de responsabilidades e reutilização:

| Tipo | Exemplo HTML | Exemplo CSS |
|---|---|---|
| **Cor de Fundo** | `<body bgcolor="#FF0000">` | `body { background-color: #FF0000; }` |
| **Tamanho / Cor de Fonte** | `<font size="4" color="blue">` | `p { font-size: 18px; color: blue; }` |

---

## 2. Formas de Aplicação do CSS

Existem três formas de incluir estilos CSS em uma aplicação web:

### 1. CSS In-line
Estilos aplicados diretamente no elemento HTML através do atributo `style`.
- **Uso:** Testes rápidos ou ajustes pontuais.
- **Desvantagem:** Dificulta a manutenção e não permite reutilização.
```html
<p style="color: red; font-size: 20px;">Texto em vermelho e maior</p>
```

### 2. CSS Interno
Definido dentro da tag `<style>` no cabeçalho (`<head>`) do arquivo HTML.
- **Uso:** Estilos exclusivos para uma única página ou prototipagem rápida.
```html
<head>
  <style>
    p {
      color: blue;
      font-size: 18px;
    }
  </style>
</head>
```

### 3. CSS Externo (Recomendado)
Estilos escritos em um arquivo separado com extensão `.css` e vinculados no HTML através da tag `<link>`.
- **Vantagens:** Centraliza o estilo do projeto, permite reutilização em múltiplas páginas e melhora a organização do código.
```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

---

## 3. Propriedades Essenciais e Seletores (Class e ID)

### 🎨 Propriedades Visuais e de Texto
- `color`: Define a cor do texto (ex: `color: #ff0000;` ou `color: red;`).
- `background-color`: Define a cor de fundo do elemento (ex: `background-color: #0000ff;`).
- `font-family`: Especifica a família da fonte (ex: `font-family: Arial, sans-serif;`).
- `font-size`: Controla o tamanho do texto em `px`, `rem`, `em` ou `%` (ex: `font-size: 16px;`).
- `text-align`: Alinha o texto horizontalmente (`left`, `center`, `right`, `justify`).

### 📐 Dimensões e Posicionamento
- `width` e `height`: Controlam largura e altura (ex: `width: 300px; height: 200px;`).
- `display`: Define como o elemento é renderizado (`block`, `inline`, `inline-block`, `flex`, `grid`, `none`).
- `position`: Define o método de posicionamento (`static`, `relative`, `absolute`, `fixed`, `sticky`).
- `top`, `right`, `bottom`, `left`: Auxiliam no deslocamento de elementos com `position`.

### 🏷️ Seletores de Classe (`.`) e ID (`#`)
- **Classes (`.nome-classe`):** Aplicadas a múltiplos elementos HTML. Permitem reuso e consistência visual.
  ```css
  .botao-primario {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    border-radius: 5px;
  }
  ```
- **IDs (`#nome-id`):** Identificadores únicos na página. Usados para estilização exclusiva, navegação por âncoras e manipulação via JavaScript.
  ```css
  #cabecalho-principal {
    height: 80px;
    background-color: #333;
  }
  ```

---

## 4. CSS Box Model (Modelo de Caixas)

O **Box Model** é o conceito fundamental do CSS que descreve como todo elemento HTML é representado como uma caixa retangular.

```text
+-----------------------------------+
|              MARGIN               |
|  +-----------------------------+  |
|  |           BORDER            |  |
|  |  +-----------------------+  |  |
|  |  |        PADDING        |  |  |
|  |  |  +-----------------+  |  |  |
|  |  |  |     CONTENT     |  |  |  |
|  |  |  +-----------------+  |  |  |
|  |  +-----------------------+  |  |
|  +-----------------------------+  |
+-----------------------------------+
```

### Componentes do Box Model:
1. **Content (Conteúdo):** Onde aparecem textos, imagens ou outros elementos filhos.
2. **Padding (Preenchimento Interno):** Espaço entre o conteúdo e a borda da caixa.
3. **Border (Borda):** Linha que envolve o padding e o conteúdo.
4. **Margin (Margem Externa):** Espaço fora da borda, criando distância em relação a outros elementos.

### 💡 Por que aplicar o Box Model corretamente?
- Controlar com precisão o tamanho dos elementos.
- Garantir espaçamento e hierarquia visual.
- Evitar sobreposição desordenada de elementos.
- Construir layouts previsíveis e adaptáveis a telas responsivas.

---

## 5. Flexbox (Flexible Box Layout) & Responsividade

O **Flexbox** é um módulo de layout unidimensional (em linha ou coluna) projetado para distribuição proporcional de espaço e alinhamento de elementos dentro de um container flexível.

### ⚙️ Propriedades Principais do Flexbox:
- `display: flex;`: Ativa o contexto flexível no container.
- `flex-direction`: Define o eixo principal (`row`, `row-reverse`, `column`, `column-reverse`).
- `justify-content`: Alinha itens no eixo principal (`flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly`).
- `align-items`: Alinha itens no eixo transversal (`flex-start`, `center`, `flex-end`, `stretch`, `baseline`).
- `flex-wrap`: Define se os itens podem quebrar para a próxima linha (`nowrap`, `wrap`, `wrap-reverse`).
- `gap`: Define o espaçamento entre itens flexíveis sem precisar de margens individuais.

### 📱 Layouts Responsivos
A responsividade adapta a interface para diferentes tamanhos de tela (smartphones, tablets e desktops), melhorando a usabilidade e a experiência do usuário sem a necessidade de criar sites separados.

---

## 6. Atividade Prática 01 — Box Model & Flexbox

Projeto prático focado na fixação de manipulação de caixas e posicionamento flexível em CSS.

### 🎯 Requisitos da Atividade 01:
1. Criar um projeto com estrutura separada em `index.html` e `style.css` (CSS Externo).
2. Adicionar **20 elementos HTML** configurando todas as propriedades do Box Model (*Content*, *Padding*, *Border* e *Margin*).
3. Aplicar **20 propriedades de Flexbox** para organizar os elementos de forma responsiva.

---

## 7. O que é um Framework CSS?

Um **Framework CSS** é um conjunto de ferramentas, estilos pré-definidos, componentes e padronizações desenvolvidos para acelerar e facilitar a criação de interfaces web responsivas.

### 🧩 Componentes de um Framework CSS:
- **Layout:** Grid system, Flexbox, utilitários de responsividade.
- **Estilos:** Paleta de cores, tipografia, espaçamentos padronizados.
- **Componentes:** Botões, cards, barras de navegação (navbars), modais, formulários.

### 🛑 O Problema do CSS Manual (Vanilla CSS)
Escrever CSS puramente manual em projetos grandes exige estilizar individualmente cada elemento, mantendo classes personalizadas, tratando breakpoints e lidando com repetições extensas de código (*boilerplate*).

---

## 8. Tailwind CSS & Abordagem Utility-First

O **Tailwind CSS** é um framework CSS baseado no conceito **Utility-First** (Primeiro Utilitários).

### 💡 Conceito Utility-First
Em vez de oferecer componentes prontos com classes compostas (como `.btn-primary`), o Tailwind fornece **pequenas classes utilitárias** onde cada classe é responsável por uma única regra CSS.

> **Regra de Ouro:** *Uma utility = uma responsabilidade. Várias utilities = um componente.*

### 🛠️ Exemplo de Comparativo:

#### CSS Tradicional:
```html
<button class="botao">Enviar</button>
```
```css
.botao {
  background-color: #2563eb;
  color: white;
  padding: 12px 24px;
  border-radius: 8px;
}
```

#### Tailwind CSS:
```html
<button class="bg-blue-600 text-white px-6 py-3 rounded-lg">
  Enviar
</button>
```

### 🚀 Principais Vantagens do Tailwind CSS:
- **Redução do tempo de desenvolvimento:** Estilização ágil direto no HTML.
- **Flexibilidade total:** Criação de interfaces exclusivas sem o "visual padronizado" de outros frameworks.
- **Consistência:** Sistema baseado em tokens de design (cores, margens, fontes padronizadas).
- **Mobile-First nativo:** Prefixos de responsividade como `sm:`, `md:`, `lg:`, `xl:` aplicados diretamente nas classes.

---

## 9. Formas de Importação e Ferramentas do Tailwind

### 1. Importação via Play CDN (Uso em Protótipos/Testes)
Inclusão via tag `<script>` no `<head>` do arquivo `index.html`:
```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
```

### 2. Instalação via Tailwind CLI / PostCSS (Projetos em Produção)
Para projetos profissionais utilizando empacotadores ou build tools:
```bash
# Passo 1: Instalar o CLI do Tailwind
npm install tailwindcss @tailwindcss/cli

# Passo 2: Importar no arquivo CSS principal
@import "tailwindcss";

# Passo 3: Integração com PostCSS (se necessário)
npm install tailwindcss @tailwindcss/postcss postcss
```

### 3. Integração com Frameworks
O Tailwind possui suporte oficial e procedimentos dedicados de instalação para frameworks como **Next.js**, **React (Vite)**, **Vue**, **Angular**, **Laravel**, entre outros.

### 🔌 Tailwind IntelliSense (Extensão para Editores)
Extensão essencial para VS Code e outros editores que oferece:
- Autocompletar inteligente de classes utilitárias.
- Dicas flutuantes (*tooltips*) mostrando o CSS gerado por cada classe.
- Destaque de sintaxe e prevenção de erros de digitação.

---

## 10. Atividade Prática 02 — Projeto com Tailwind CSS

Atividade prática para consolidação de estilização utilitária e desenvolvimento responsivo.

### 🎯 Requisitos da Atividade 02:
1. Criar um projeto utilizando no mínimo **30 classes utilitárias diferentes do Tailwind CSS**.
2. Utilizar classes que contemplem:
   - Cores de fundo e texto (`bg-*`, `text-*`).
   - Tipografia e peso de fonte (`font-*`, `text-*`).
   - Espaçamentos internos e externos (`p-*`, `m-*`, `gap-*`).
   - Dimensões (`w-*`, `h-*`).
   - Bordas e sombras (`border`, `rounded-*`, `shadow-*`).
   - Posicionamento, Flexbox, Grid e Responsividade (`flex`, `grid`, `items-center`, `md:flex-row`).
3. **Documentação:** Criar um arquivo `README.md` contendo:
   - Prints do código e da aplicação em funcionamento.
   - Lista das 30 classes utilizadas com suas respectivas explicações.
   - Links para o repositório no GitHub e o deploy online.

---

## 11. Resumo da Aula

```text
HTML/CSS Tradicional ➔ Box Model & Flexbox ➔ Frameworks CSS ➔ Tailwind CSS (Utility-First) ➔ Responsividade & Deploy
```

Nesta aula exploramos desde os fundamentos de estilização com **CSS Vanilla** (Box Model e Flexbox) até a evolução com **Frameworks CSS**, focando na abordagem **Utility-First do Tailwind CSS**. Compreendemos como as classes utilitárias aumentam a produtividade, garantem responsividade nativa e evitam a proliferação de arquivos CSS extensos e difíceis de manter.

---

## 12. Referências

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
