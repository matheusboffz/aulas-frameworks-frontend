# Aula 06 — Projetos Front-End

**Disciplina:** Frameworks Front-end  
**Foco:** Gestão de Projetos Front-End, Gestão de Requisitos, User Stories e Tarefas, Gestão do Backlog, Priorização e Estimativas, Definition of Done (DoD), Metodologia Ágil (Scrum/Kanban) e Atividade Prática do Projeto Integrador.  
**Professor:** Prof. Me. Deivison S. Takatu (`deivison.takatu@edu.senai.br`)  

---

## 📌 Sumário

1. [Por que Gerenciar um Projeto Front-End?](#1-por-que-gerenciar-um-projeto-front-end)
2. [Gestão de Projetos Front-End](#2-gestão-de-projetos-front-end)
3. [Gestão de Requisitos: Requisito, História e Tarefa](#3-gestão-de-requisitos-requisito-história-e-tarefa)
4. [Gestão do Backlog](#4-gestão-do-backlog)
5. [Gestão de Prioridade e Estimativa](#5-gestão-de-prioridade-e-estimativa)
6. [Definition of Done (DoD)](#6-definition-of-done-dod)
7. [Metodologias Ágeis: Scrum e Kanban no Front-End](#7-metodologias-ágeis-scrum-e-kanban-no-front-end)
8. [Repositórios Complementares](#8-repositórios-complementares)
9. [Atividade Prática (Projeto Integrador Interdisciplinar)](#9-atividade-prática-projeto-integrador-interdisciplinar)
10. [Resumo da Aula](#10-resumo-da-aula)
11. [Referências](#11-referências)

---

## 1. Por que Gerenciar um Projeto Front-End?

Projetos Front-End modernos envolvem alta complexidade, integração de APIs, bibliotecas dinâmicas, gerenciamento de estado e múltiplos dispositivos/resoluções. Sem um planejamento e processos de gestão adequados, os projetos tendem a crescer desordenadamente.

### ⚠️ Problemas causados pela falta de gestão:
- **Tarefas esquecidas:** Funcionalidades essenciais deixadas de lado ou incompletas.
- **Requisitos confusos:** Falta de clareza no que realmente deve ser desenvolvido.
- **Retrabalho:** Necessidade de reescrever componentes por falha de comunicação ou design incorreto.
- **Conflitos no Git:** Múltiplos desenvolvedores alterando o mesmo código sem alinhamento de *branches* e responsabilidades.
- **Atrasos:** Perda de controle sobre os prazos de entrega.
- **Problemas de integração:** Incompatibilidades entre o Front-End e as APIs do Back-End.
- **Dificuldade para acompanhar o progresso:** Falta de visibilidade sobre o estado atual do desenvolvimento.

### ✅ Benefícios ao aplicar processos de gestão:
- **Responsabilidades claras:** Cada membro da equipe sabe exatamente qual parte do sistema deve construir.
- **Prioridades definidas:** Foco primário no que entrega maior valor ao produto/usuário.
- **Entregas incrementais:** Liberação contínua de partes funcionais do software.
- **Acompanhamento transparente:** Visibilidade em tempo real do progresso da equipe.
- **Redução significativa de retrabalho:** Padronização de requisitos e validações prévias.

---

## 2. Gestão de Projetos Front-End

Gerenciar um projeto Front-End significa **organizar pessoas, tarefas, tecnologias e prazos** para transformar uma ideia inicial em uma aplicação funcional, performática e utilizável.

```text
Ideia Inicial ➔ Levantamento de Requisitos ➔ Organização do Backlog ➔ Priorização & Estimativa ➔ Desenvolvimento Incremental ➔ Testes & DoD ➔ Entrega ao Usuário
```

Durante todo o ciclo de vida do desenvolvimento:
1. **Decisões precisam ser planejadas:** Escolha de arquitetura, ferramentas e estruturação dos componentes.
2. **Decisões precisam ser acompanhadas:** Monitoramento contínuo através de quadros (Kanban/Scrum) e reuniões de alinhamento.
3. **Decisões precisam ser ajustadas:** Adaptação rápida a mudanças de requisitos ou impedimentos técnicos.

---

## 3. Gestão de Requisitos: Requisito, História e Tarefa

Para organizar o trabalho de forma eficiente, dividimos o escopo do projeto em diferentes níveis de abstração: **Requisito**, **User Story (História de Usuário)** e **Tarefas Técnicas**.

### Níveis de Desdobramento

| Nível | Conceito | Exemplo Prático |
|---|---|---|
| **Requisito** | Uma funcionalidade macro ou regra de negócio que o sistema deve atender. | *Sistema deve permitir o gerenciamento de tarefas.* |
| **User Story** | Descrição simples da funcionalidade sob a perspectiva do usuário final. | *Como usuário, quero criar uma tarefa para organizar minhas pendências diárias.* |
| **Tarefas (Tasks)** | Passos técnicos específicos e mensuráveis necessários para implementar a história. | *Ver lista abaixo.* |

### 🛠️ Desdobramento de Tarefas Técnicas no Front-End:
Para a User Story *"Como usuário, quero criar uma tarefa"*, as tarefas técnicas incluem:
1. **Criar formulário:** Interface HTML/JSX para entrada de dados.
2. **Criar componente:** Componentização visual em React/Vue/HTML reutilizável.
3. **Validar campos:** Garantir preenchimento dos dados obrigatórios antes do envio.
4. **Integrar API:** Fazer requisição HTTP (`POST /api/tasks`) enviando os dados do formulário.
5. **Criar testes:** Desenvolver testes unitários/de integração para o fluxo de criação.

---

## 4. Gestão do Backlog

O **Backlog do Produto (Product Backlog)** é uma lista dinâmica e priorizada de tudo o que pode ser necessário no produto.

### O que compõe o Backlog?
- **Novas Funcionalidades (Features):** Telas, formulários, componentes interativos.
- **Melhorias (Enhancements):** Otimização de performance, acessibilidade, responsividade.
- **Correções de Bugs (Fixes):** Ajustes de layout, correção de chamadas de API quebradas.
- **Refatorações e Débito Técnico:** Organização de arquivos, atualização de dependências, melhoria de padrões de código.

> 💡 **Importante:** Os itens do backlog recebem prioridades distintas. Isso permite que a equipe de desenvolvimento concentre seus esforços primariamente nas funcionalidades vitais para o negócio ou MVP (*Minimum Viable Product*).

---

## 5. Gestão de Prioridade e Estimativa

### Priorização
Determina a ordem em que os itens do backlog devem ser desenvolvidos, levando em consideração:
- **Valor de Negócio:** O impacto direto para o usuário final ou para a empresa.
- **Dependências Técnicas:** Telas que dependem de componentes de UI base ou autenticação prévia.
- **Restrições e Prazos:** Prazos de entrega da Sprint ou marcos de lançamento (*milestones*).

### Estimativas
Ajudam a equipe a compreender a **complexidade relativa** e o esforço necessário de cada atividade antes de se comprometer com sua execução na Sprint.
- Permite evitar sobrecarga da equipe.
- Facilita o planejamento de capacidades (Velocity).
- Técnicas comuns: *Planning Poker*, *T-Shirt Sizing* (P, M, G), *Story Points*.

---

## 6. Definition of Done (DoD)

A **Definition of Done (Definição de Concluído)** é um conjunto claro e acordado de critérios que uma tarefa ou história de usuário deve atender para ser considerada 100% pronta para produção.

### 📋 Checklist de DoD típico em projetos Front-End:

- [x] **Código Implementado:** Funcionalidade desenvolvida segundo os requisitos e padrões do projeto.
- [x] **Responsividade Verificada:** Interface testada em diferentes tamanhos de tela (Mobile, Tablet, Desktop).
- [x] **Integração Realizada:** Comunicação com as APIs do Back-End validada e sem erros no console.
- [x] **Testes Realizados:** Testes unitários e manuais executados com sucesso.
- [x] **Revisão Concluída (Code Review / Pull Request):** Código aprovado por outro desenvolvedor da equipe.
- [x] **Sem Débito Técnico Adicional:** Sem avisos (warnings) críticos ou código morto acumulado.

---

## 7. Metodologias Ágeis: Scrum e Kanban no Front-End

### 🔄 Scrum no Front-End
O **Scrum** é um framework ágil para desenvolvimento incremental de produtos complexos.
- **Sprints:** Ciclos curtos e fixos de trabalho (geralmente de 1 a 2 semanas).
- **Aplicações no Front-End:**
  - Organização e fatiamento dos requisitos em entregas visíveis ao final de cada Sprint.
  - Planejamento de Sprints alinhado ao consumo de APIs já disponíveis no Back-End.
  - Reuniões diárias (*Dailies*) para identificar bloqueios (ex: falta de endpoint da API ou dúvidas de layout).

### 📋 Kanban no Front-End
O **Kanban** foca na visualização do fluxo de trabalho através de quadros com colunas bem definidas:

```text
[ Backlog ] ➔ [ To Do ] ➔ [ In Progress ] ➔ [ Code Review / PR ] ➔ [ Testing ] ➔ [ Done ]
```

- **WIP Limit (Limit de Trabalho em Progresso):** Evita que os desenvolvedores iniciem muitas tarefas ao mesmo tempo sem concluir as anteriores.

### 🌿 Git & Fluxo de Trabalho (Branches)
Para garantir que o fluxo de trabalho ágil funcione no repositório:
- **`main` / `master`:** Código estável e pronto para produção.
- **`develop`:** Branch de integração do desenvolvimento.
- **`feature/nome-da-tarefa`:** Branches isoladas para criação de componentes/funcionalidades específicas.

---

## 8. Repositórios Complementares

Para aprofundar os conhecimentos em gestão e metodologias ágeis aplicadas ao desenvolvimento de software, consulte os repositórios oficiais disponibilizados pelo professor:

- 🔗 [aula-gestao](https://github.com/deivisontakatu/aula-gestao) — Conceitos gerais de gestão de projetos de software.
- 🔗 [aula-gestao-produto](https://github.com/deivisontakatu/aula-gestao-produto) — Práticas e estratégias para gestão de produtos de software.
- 🔗 [aula-scrum](https://github.com/deivisontakatu/aula-scrum) — Guia prático sobre a aplicação do framework Scrum.

---

## 9. Atividade Prática (Projeto Integrador Interdisciplinar)

Com base nos conceitos apresentados na aula, os grupos devem estruturar o gerenciamento do seu **Projeto Integrador Interdisciplinar**.

### Roteiro da Atividade:

1. **Planejamento da Gestão:**
   - Definir como o grupo irá gerenciar as tarefas do projeto utilizando os conceitos da Aula 06.
2. **Criação dos Artefatos de Gestão:**
   - **Product Backlog:** Listar todas as funcionalidades do Projeto Integrador.
   - **User Stories & Tarefas:** Mapear os requisitos em histórias de usuário e desdobrar em tarefas técnicas de Front-End e Back-End.
   - **Priorização & Estimativas:** Atribuir prioridades (ex: Alta, Média, Baixa) e estimativas de esforço para cada item.
   - **Sprint & Kanban:** Estruturar o quadro de acompanhamento (ex: GitHub Projects, Trello ou Jira).
   - **Estratégia de Branches:** Definir o padrão de nomes para as *branches* do Git (ex: `feature/login-screen`, `fix/header-layout`).
   - **Definition of Done (DoD):** Estabelecer os critérios mínimos para considerarem uma tarefa concluída.
3. **Documentação & Execução:**
   - Documentar todo o processo em um arquivo `Markdown` (no repositório do grupo).
   - Utilizar ativamente o board Kanban criado para gerenciar e acompanhar a evolução do projeto durante as Sprints.

---

## 10. Resumo da Aula

```text
Ideia ➔ Requisito ➔ User Story ➔ Tarefas Técnicas ➔ Backlog Priorizado ➔ Sprint/Kanban ➔ DoD ➔ Entrega
```

Nesta aula aprendemos a importância da **gestão estruturada de projetos Front-End**. Vimos que gerenciar não é apenas distribuir tarefas, mas garantir que a equipe trabalhe com clareza de requisitos, prioridades bem definidas, acompanhamento visual via Kanban/Scrum e padrões claros de conclusão (Definition of Done), reduzindo retrabalho e aumentando a qualidade das entregas.

---

## 11. Referências

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
