# FATEC Profº Jessen Vidal - São José dos Campos - 3º Semestre DSM - 2026
<p>Projeto desenvolvido para a API (Aprendizagem por Projeto Integrado) do 3° Semestre do curso Desenvolvimento de Software Multiplataforma (DSM), no projeto de <b>Controle de Apontamento de Horas</b>.</p>

> _A API se trata de um projeto submetido à metodologia de ensino em implantação na Fatec São José dos Campos, do qual os alunos formam equipes baseadas na metodologia ágil SCRUM, tendo um aluno como Scrum Master, um sendo o Product Owner e o restante dos integrantes como Dev Team._

<p align="center">
<a href="#dor-do-cliente">Dor do Cliente</a> |
<a href="#objetivo-do-produto">Objetivo do Produto</a> |
<a href="#backlog-do-produto">Backlog do Produto</a> |
<a href="#sprint">Cronograma de Sprints</a> |
<a href="#dor-e-dod">DoR e DoD</a> |
<a href="#tecnologias">Tecnologias Utilizadas</a> |
<a href="#branch">Estratégia de Branch e Padrão de Commits</a> |
<a href="#estrutura">Estrutura do Projeto</a> |
<a href="#instalacao">Manual de Instalação</a> |
<a href="#usuario">Manual do Usuário</a> |
<a href="#equipe">Equipe</a>
</p>

## Visão Geral

Este projeto tem como objetivo desenvolver uma plataforma de gestão de horas para a <b>GSW Soluções Integradas</b>, visando resolver a falta de padronização no registro de tempo, a baixa visibilidade das atividades e a inconsistência dos dados financeiros.

A solução permitirá que os colaboradores registrem suas horas de forma centralizada e remota, enquanto líderes terão uma visão clara das atividades e gargalos dos projetos. Com isso, será possível gerar dados confiáveis para análise de custos e apoiar a tomada de decisões baseada em fatos, aumentando a eficiência e a lucratividade da empresa.

## 🔍 Dor do Cliente <a id="dor-do-cliente"></a>

**Contextualização:** A GSW Soluções Integradas gerencia múltiplos projetos com equipes distribuídas por todo o Brasil, operando em um ambiente de alta complexidade onde o volume de demandas cresce continuamente.

**Dor do cliente:** A principal dor do cliente é a dispersão dos dados — hoje distribuídos entre planilhas, mensagens e anotações — que gera inconsistências, retrabalho e pouca clareza sobre como o tempo é distribuído entre projetos e atividades. Sem essa base centralizada, profissionais não têm um lugar padronizado para registrar seu trabalho, gestores não têm visibilidade confiável sobre esforço e custos, o administrativo não consegue monitorar alocações e o financeiro não tem dados sólidos para sustentar a cobrança.

**Impactos:** A dispersão dos dados gera diversos impactos na operação da GSW. O grupo considerou três como os mais críticos e os definiu como foco do desenvolvimento:

- **Registro de horas:** profissionais não têm um lugar padronizado para registrar como gastam seu tempo, tornando os lançamentos inconsistentes e difíceis de aprovar.
- **Acompanhamento de projetos:** líderes não conseguem visualizar a alocação do time nem identificar gargalos em tempo hábil para agir.
- **Dados financeiros:** o financeiro não tem base confiável para calcular custos reais por projeto ou sustentar o faturamento.

**Conclusão:** A escolha por desenvolver uma solução própria é direta: cada funcionalidade foi construída a partir de necessidades reais levantadas com Diego Miranda. O sistema do KernelPanic trata os três perfis de forma integrada — o profissional registra, o gestor valida e o financeiro decide — com rastreabilidade em cada etapa e um fluxo completo construído para a realidade da GSW.

## 🎯 Objetivo do Produto <a id="objetivo-do-produto"></a>

O sistema tem como objetivo centralizar o controle de apontamento de horas da GSW Soluções Integradas, oferecendo para cada perfil a visibilidade que precisa:

- Profissionais com um lugar padronizado para registrar horas por projeto e tipo de atividade
- Líderes técnicos com visão clara da alocação do time, status das tarefas e identificação de gargalos
- Gestores e financeiro com dados confiáveis sobre custos reais e base para cobrança por projeto

## 📋 Backlog do Produto <a id="backlog-do-produto"></a>

| Rank | Prioridade | User Story | Estimativa | Sprint |
| :--: | :--------: | :--------- | :--------: | :----: |
| 1 | 🔴 Alta | US1: Como Gerente, quero registrar usuários com seus custos por hora e criar projetos com orçamento previsto, associando profissionais a cada projeto, para que eu tenha controle sobre a viabilidade financeira e seja alertado quando o custo acumulado se aproximar ou ultrapassar o orçamento definido. | 8 | 1 |
| 2 | 🔴 Alta | US2: Como Líder Técnico, quero administrar as tarefas e alocar os profissionais certos, para garantir que o time não fique parado e os bugs sejam resolvidos com agilidade. | ? | ? |
| 3 | 🔴 Alta | US3: Como Analista, quero detalhar os requisitos, estimar prazos e propor testes, para que o desenvolvimento ocorra com o mínimo de dúvidas de negócio possível. | ? | ? |
| 4 | 🔴 Alta | US4: Como Desenvolvedor, quero lançar minhas horas trabalhadas informando o projeto, a task, o período (início e fim) e o tipo de atividade realizada (Feature, Correção de Bug, Reunião ou Documentação), para que a empresa tenha rastreabilidade sobre como o tempo está sendo distribuído entre inovação e correção de falhas, e gestores possam aprovar ou rejeitar lançamentos retroativos com justificativa. | 13 | 1 |
| 5 | 🔴 Alta | US5: Como Desenvolvedor, quero alterar o status de uma tarefa para "Bloqueada", selecionando obrigatoriamente a categoria do impedimento (Erro de Analista, Aguardando Cliente, Problema Técnico ou Dúvida de Negócio), para que o sistema registre automaticamente o tempo de parada, calcule o custo do atraso com base no meu valor/hora e alerte o gestor no dashboard quando o bloqueio ultrapassar 24 horas, permitindo identificar e resolver gargalos com precisão financeira. | 5 | 1 |
| 6 | 🔴 Alta | US6: Como Líder Técnico, quero visualizar em tempo real o status de todas as tarefas e a ocupação do time, para identificar gargalos no fluxo de trabalho e garantir que as entregas sigam o cronograma planejado. | ? | ? |
| 7 | 🟠 Média | US7: Como Gerente, quero acessar um painel de aprovação de horas lançadas pelos funcionários, podendo filtrar por profissional, projeto ou período, aprovar ou reprovar lançamentos individualmente ou em lote, e ao reprovar informar obrigatoriamente o motivo, para que apenas horas aprovadas sejam contabilizadas no custo real do projeto e no relatório financeiro. | 3 | 1 |
| 8 | 🟠 Média | US8: Como Líder Técnico, quero ter um histórico cronológico de quem trabalhou em cada task e quais impedimentos encontrou. | ? | ? |
| 9 | 🟡 Baixa | US9: Como Gerente, quero um relatório consolidado de falhas e atrasos, para identificar padrões e treinar a equipe onde for necessário. | ? | ? |
| 10 | 🟡 Baixa | US10: Como Gestor, quero ter o controle de quanto tempo uma tarefa ficou parada, quanto custou para a empresa e o porquê ela ficou parada. | ? | ? |

## 📅 Cronograma de Sprints <a id="sprint"></a>

Cada sprint foi planejada para atacar um dos três impactos mais críticos identificados pelo grupo:

| Sprint | Período | Entrega | Documentação |
| --------------- | :-----------: | :--------- | ------------------------------------------------ |
| **SPRINT 1** | 16/03 - 05/04 | Cadastro de projetos e usuários, lançamento de horas por atividade, sinalização de bloqueios com custo automático e aprovação de lançamentos pelo Gerente. | [Sprint 1 Docs](Documenta%C3%A7%C3%A3o/Sprint%20Um) |
| **SPRINT 2** | 13/04 - 03/05 | Gestão de tarefas, alocação do time, visibilidade em tempo real dos projetos e suporte a diferentes tipos e regras de cobrança por projeto. | [Sprint 2 Docs](Documenta%C3%A7%C3%A3o/Sprint%20Dois) |
| **SPRINT 3** | 11/05 - 31/05 | Histórico completo de tarefas, relatórios financeiros por projeto, controle de custos por bloqueio e base confiável para faturamento. | [Sprint 3 Docs](Documenta%C3%A7%C3%A3o/Sprint%20Tres) |

## ✅ DoR e DoD <a id="dor-e-dod"></a>

### DoR - Definition of Ready

| Critério | Descrição |
| :--- | :--- |
| **Clareza na Descrição** | A User Story deve estar escrita de forma clara e objetiva no padrão: "Como [usuário], quero [ação], para [benefício]" tendo que estar alinhados na regra de negocio. |
| **Critérios de Aceitação Definidos** | A história possui critérios objetivos que indicam o que é necessário para considerá-la concluída. |
| **Independente** | A história pode ser implementada sem depender de outra tarefa da mesma Sprint. |
| **Documentos de Apoio** | Estar realizado mockups, fluxos ou modelos de dados estão anexados na pasta de documentos (docs) |
| **Dicionário de dados** | Possuir um dicionário dos dados a ser utilizado para a produção da User Story |

### DoD - Definition of Done

| Critério | Descrição |
| :--- | :--- |
| **Critérios de Aceitação atendidos** | Todos os cenários de testes foram executados e aprovados. |
| **Código revisado** | O código foi revisado por pelo menos um membro. |
| **Documentação atualizada** | Documentação da API atualizados ao longo de cada sprint e conferidos no final de cada uma (quando aplicável). |
| **Pronto para deploy** | O código está em uma branch principal, versionado, e pode ser integrado ao produto final sem esforço adicional. |

## 🛠️ Tecnologias Utilizadas <a id="tecnologias"></a>

<div align="center">
<img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white&color=043873">
</div>

## 🌿 Estratégia de Branch e Padrão de Commits <a id="branch"></a>

<details>
<summary>Clique para expandir</summary>

## 🔹 Estrutura de Branches
Adotamos uma variação do GitFlow, com regras específicas para nossa equipe.

**Fluxo Principal**
- `main` → Código estável em produção.
- `desenvolvimento` → Integração da sprint.

**Fluxo de Desenvolvimento**
- `feature/US-<id>-<nome>` → Cada User Story tem sua branch.
- `task/US-<id>-<descrição>` → Subtasks técnicas (opcional).
- `db/sprint-<número>` → Alterações de banco de dados da sprint.

## 🔹 Padrão de Commits

Padrão de Mensagem dos Commits: `(Tipo de commit)(ID da task): Descrição detalhada do que foi feito`

Exemplo: `feat(US-01): adiciona cadastro de usuário`

**Tipos de Commit Aceitos**

| Tipo | Descrição |
| :--- | :--- |
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `chore` | Manutenção, configuração ou build |
| `docs` | Alterações na documentação |
| `style` | Formatação de código (sem alterar lógica) |
| `refactor` | Refatoração de código |
| `test` | Adição ou refatoração de testes |

</details>

## 📁 Estrutura do Projeto <a id="estrutura"></a>
Em andamento 

## 📖 Manual de Instalação <a id="instalacao"></a>
 Em andamento

## 👤 Manual do Usuário <a id="usuario"></a>
Em andamento

## 👥 Equipe <a id="equipe"></a>

| Foto | Função | Nome | LinkedIn | GitHub |
| :----: | :-----------: | :-----------------------: | :------------------------------------------------------------: | :-----------------------------------------------: |
| <img src="https://avatars.githubusercontent.com/u/144951743?v=4" width="75px"> | Scrum Master | Miguel Tomio Toledo Nonaka | [Linkedin](https://www.linkedin.com/in/miguel-nonaka) | [GitHub](https://github.com/miguelnonaka) |
| <img src="https://avatars.githubusercontent.com/u/119637682?v=4" width="75px"> | Product Owner | Heloisa Cardillo | [Linkedin](https://www.linkedin.com/in/heloisa-cardillo-lima/) | [GitHub](https://github.com/heloisa-cardillo) |
| <img src="https://avatars.githubusercontent.com/u/162122368?v=4" width="75px"> | Dev Team | Daniel Porto Renó Sás Piloto | [Linkedin](https://www.linkedin.com/in/daniel-piloto-98b717226/) | [GitHub](https://github.com/danprsp) |
| <img src="https://avatars.githubusercontent.com/u/140865436?v=4" width="75px"> | Dev Team | Henry Vilela Silva Tito | [Linkedin](https://www.linkedin.com/in/henry-tito-989b4b354/) | [GitHub](https://github.com/HenryTito) |
| <img src="https://avatars.githubusercontent.com/u/163298566?v=4" width="75px"> | Dev Team | João Victor Dos Reis Santos | [Linkedin](https://www.linkedin.com/in/joão-victor-dos-reis-santos-1823532b4) | [GitHub](https://github.com/Templasan) |
| <img src="https://avatars.githubusercontent.com/u/102493225?v=4" width="75px"> | Dev Team | Paula Emy Tamay | [Linkedin](https://www.linkedin.com/in/paula-tamay-7a168228a/) | [GitHub](https://github.com/PaulaEmy) |
| <img src="https://avatars.githubusercontent.com/u/202960831?v=4" width="75px"> | Dev Team | Pedro Miguel Nascimento | [Linkedin](https://www.linkedin.com/in/) | [GitHub](https://github.com/P3dr0213) |
| <img src="https://avatars.githubusercontent.com/u/163305926?v=4" width="75px"> | Dev Team | Vinícius da Silva Leite | [Linkedin](https://www.linkedin.com/in/vinícius-leite-4792b02ba/) | [GitHub](https://github.com/vinislvleite) |
| <img src="https://avatars.githubusercontent.com/u/106409918?v=4" width="75px"> | Dev Team | Vitor Serpa da Silva | [Linkedin](https://www.linkedin.com/in/vitor-serpa-925b46322/) | [GitHub](https://github.com/VitorSerpa) |

