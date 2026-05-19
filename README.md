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
<a href="#entrega">Modelo de Entrega</a> |
<a href="#equipe">Equipe</a>
</p>

## Visão Geral

Este projeto tem como objetivo desenvolver uma plataforma de gestão de horas para a <b>GSW Soluções Integradas</b>, visando resolver a falta de padronização no registro de tempo, a baixa visibilidade das atividades e a inconsistência dos dados financeiros.

A solução permitirá que os colaboradores registrem suas horas de forma centralizada e remota, enquanto líderes terão uma visão clara das atividades e gargalos dos projetos. Com isso, será possível gerar dados confiáveis para análise de custos e apoiar a tomada de decisões baseada em fatos, aumentando a eficiência e a lucratividade da empresa.

## Dor do Cliente <a id="dor-do-cliente"></a>

**Contextualização:** A GSW Soluções Integradas gerencia múltiplos projetos com equipes distribuídas por todo o Brasil, operando em um ambiente de alta complexidade onde o volume de demandas cresce continuamente.

**Dor do cliente:** A principal dor do cliente é a dispersão dos dados — hoje distribuídos entre planilhas, mensagens e anotações — que gera inconsistências, retrabalho e pouca clareza sobre como o tempo é distribuído entre projetos e atividades. Sem essa base centralizada, profissionais não têm um lugar padronizado para registrar seu trabalho, gestores não têm visibilidade confiável sobre esforço e custos, o administrativo não consegue monitorar alocações e o financeiro não tem dados sólidos para sustentar a cobrança.

**Impactos:** A dispersão dos dados gera diversos impactos na operação da GSW. O grupo considerou três como os mais críticos e os definiu como foco do desenvolvimento:

- **Registro de horas:** profissionais não têm um lugar padronizado para registrar como gastam seu tempo e gestores não têm controle sobre a estrutura de projetos e equipes, tornando os lançamentos inconsistentes e sem rastreabilidade para a empresa.
- **Acompanhamento de projetos:** gestores não conseguem visualizar a alocação do time, o status das tarefas nem identificar gargalos em tempo hábil para agir.
- **Dados financeiros:** o financeiro não tem base confiável para calcular custos reais por projeto ou sustentar o faturamento.

**Conclusão:** A escolha por desenvolver uma solução própria é direta: cada funcionalidade foi construída a partir de necessidades reais levantadas com Diego Miranda. O sistema do KernelPanic trata os três perfis de forma integrada — o profissional registra, o gestor valida e o financeiro decide — com rastreabilidade em cada etapa e um fluxo completo construído para a realidade da GSW.

## Objetivo do Produto <a id="objetivo-do-produto"></a>

O sistema tem como objetivo centralizar o controle de apontamento de horas da GSW Soluções Integradas, resolvendo a cada sprint um dos pontos críticos identificados a partir da dor do cliente:

- Profissionais com um lugar padronizado para registrar, editar e acompanhar seus apontamentos de horas por projeto e tipo de atividade, e Gestores com controle sobre a estrutura de usuários e projetos cadastrados
- Gestores com visibilidade clara da alocação do time, status das tarefas e identificação de gargalos em tempo real
- Financeiro/Administrador com dados confiáveis sobre custos reais por projeto e base para auditoria e faturamento

## Backlog do Produto <a id="backlog-do-produto"></a>

| Rank | Prioridade | User Story | Estimativa | Sprint |
| :--: | :--------: | :--------- | :--------: | :----: |
| 1 | 🔴 Alta | US1: Como Gestor, quero cadastrar usuários com seus respectivos dados e custos por hora, cadastrar projetos com informações de identificação, responsável, equipe e prazo, e acompanhar o andamento dos projetos cadastrados, para que a empresa tenha controle sobre a estrutura das equipes e o progresso dos projetos. | 8 | 1 |
| 2 | 🔴 Alta | US2: Como Gestor, quero criar e gerenciar tarefas dentro de cada projeto, podendo atribuí-las a profissionais alocados e acompanhar seu status, para que o time saiba exatamente o que precisa ser feito e eu tenha visibilidade do andamento. | 8 | 1 |
| 3 | 🔴 Alta | US3: Como Gestor, quero acessar um painel de aprovação de horas lançadas pelos profissionais, podendo filtrar por profissional, projeto ou período, aprovar ou reprovar lançamentos individualmente ou em lote, e ao reprovar informar obrigatoriamente o motivo, para que apenas horas aprovadas sejam contabilizadas no custo real do projeto. | 5 | 2 |
| 4 | 🔴 Alta | US4: Como Profissional, quero registrar, editar e excluir apontamentos de horas com informações de projeto, atividade e período, e acompanhar meus lançamentos por status (aguardando aprovação, aprovados e rejeitados) com filtros por projeto e data, para que a empresa tenha rastreabilidade sobre o esforço da equipe e o Gestor possa validar os lançamentos. | 13 | 2 |
| 5 | 🔴 Alta | US5: Como Profissional, quero alterar o status de uma tarefa para bloqueada, informando obrigatoriamente a categoria do impedimento (Erro de Analista, Aguardando Cliente, Problema Técnico, Dúvida de Negócio ou Outro), para que o Gestor seja alertado e o tempo de bloqueio fique registrado. | 5 | 2 |
| 6 | 🔴 Alta | US6: Como Gestor, quero visualizar em tempo real o status de todas as tarefas e a ocupação do time por projeto, para identificar gargalos no fluxo de trabalho e garantir que as entregas sigam o cronograma. | 5 | 2 |
| 7 | 🟠 Média | US7: Como Gestor, quero acessar um painel de rastreabilidade que exiba o consolidado de bloqueios do projeto por categoria e tempo parado, e o histórico cronológico detalhado de cada tarefa, para identificar padrões recorrentes e ter visibilidade total do esforço e impedimentos por tarefa. | 3 | 3 |
| 8 | 🟠 Média | US8: Como Financeiro, quero acessar o histórico de alterações feitas em lançamentos de horas aprovadas, visualizando quem alterou, quando e o que mudou, para garantir rastreabilidade e base confiável para faturamento. | 3 | 3 |
| 9 | 🟠 Média | US9: Como Financeiro, quero visualizar o custo real acumulado de cada projeto comparado ao valor contratado e o detalhamento de custo por profissional, para ter base confiável para análise e faturamento. | 8 | 3 |
| 10 | 🟡 Baixa | US10: Como usuário do sistema, quero acessar um dashboard personalizado de acordo com o meu perfil, para visualizar de forma consolidada as informações mais relevantes para a minha função e tomar decisões com base em dados. | 13 | 3 |

## Cronograma de Sprints <a id="sprint"></a>

Cada sprint foi planejada para atacar um dos três impactos mais críticos identificados pelo grupo:

| Sprint | Período | Entrega | Documentação |
| --------------- | :-----------: | :--------- | ------------------------------------------------ |
| **SPRINT 1** | 16/03 - 05/04 | Cadastro de projetos e usuários, lançamento de horas por atividade e acompanhamento de lançamentos por status. | [Sprint 1 Docs](Material%20Academico/Sprint%20Um) |
| **SPRINT 2** | 13/04 - 03/05 | Gestão e atribuição de tarefas, aprovação de lançamentos pelo Gestor, sinalização de bloqueios com categoria do impedimento e visibilidade em tempo real do time. | [Sprint 2 Docs](Material%20Academico/Sprint%20Dois) |
| **SPRINT 3** | 11/05 - 31/05 | Histórico de tarefas e auditoria de lançamentos, painel financeiro com custo real por projeto e dashboard personalizado por perfil. | [Sprint 3 Docs](Material%20Academico/Sprint%20Tr%C3%AAs) |

## DoR e DoD <a id="dor-e-dod"></a>

### DoR - Definition of Ready

| Critério | Descrição |
| :--- | :--- |
| **Clareza na Descrição** | A User Story deve estar escrita de forma clara e objetiva no padrão: "Como [usuário], quero [ação], para [benefício]" tendo que estar alinhada às regras de negócio. |
| **Critérios de Aceitação Definidos** | A história possui critérios objetivos que indicam o que é necessário para considerá-la concluída. |
| **Dependências Verificadas** | As dependências com outras User Stories ou tarefas estão identificadas e registradas, e não há bloqueios para o início da implementação. |
| **Documentos de Apoio** | Critérios de aceitação, cenários, regras de negócio e dicionário de dados estão documentados e anexados na pasta de documentos (docs). |

### DoD - Definition of Done

| Critério | Descrição |
| :--- | :--- |
| **Critérios de Aceitação Atendidos** | Todos os cenários de testes foram executados e aprovados. |
| **Código Revisado** | O código foi revisado por pelo menos um membro do Dev Team e validado pelo Product Owner. |
| **Estabilidade do Sistema** | A funcionalidade implementada não quebra funcionalidades já existentes no sistema. |
| **Padrão de Commits e Branch Seguido** | O código segue o padrão de mensagens de commit e estratégia de branch definidos pelo time. |
| **Documentação Atualizada** | Documentação da API atualizada ao longo de cada sprint e conferida no final de cada uma (quando aplicável). |
| **Pronto para Deploy** | O código está em uma branch principal, versionado, e pode ser integrado ao produto final sem esforço adicional. |

## Tecnologias Utilizadas <a id="tecnologias"></a>

<div align="center">
<img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Spring Cloud-6DB33F?style=for-the-badge&logo=spring&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white&color=043873">
<img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white&color=043873">
</div>

## Estratégia de Branch e Padrão de Commits <a id="branch"></a>

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

## Estrutura do Projeto <a id="estrutura"></a>

<details>
<summary>Clique para expandir</summary>

<pre>
KernelPanic-3DSM-API/
├── Backend/
│   ├── api-gateway/
│   ├── auth-service/
│   ├── apontamentohoras-service/
│   ├── projeto-service/
│   ├── task-service/
│   └── usuario-service/
│
├── Documentação/
│   └── Manual do Usuario GSW.pdf
│
├── Frontend/
│   └── frontend/
│       ├── app/
│       │   ├── cadastro_usuario/
│       │   ├── controleHoras/
│       │   │   ├── aguardando-aprovacao/
│       │   │   ├── aprovados/
│       │   │   ├── entrada-saida/
│       │   │   ├── historico/
│       │   │   └── rejeitados/
│       │   ├── login/
│       │   ├── projetos/
│       │   └── services/
│       ├── components/
│       │   └── layout/
│       │       └── navegationBar/
│       └── public/
│
└── Material Academico/
    ├── Sprint Um/
    ├── Sprint Dois/
    ├── Sprint Três/
    ├── Guia de Contribuição.md
    └── Manual de Instalação.pdf
</pre>

</details>

## Manual de Instalação <a id="instalacao"></a>

O Manual de Instalação está disponível na pasta de material acadêmico do projeto.

[📄 Acessar Manual de Instalação](Material%20Academico/Manual%20de%20Instala%C3%A7%C3%A3o%20.pdf)

## Manual do Usuário <a id="usuario"></a>

O Manual do Usuário está disponível em PDF na pasta de documentação do projeto.

[📄 Acessar Manual do Usuário](Documenta%C3%A7%C3%A3o/Manual%20do%20Usuario%20GSW.pdf)

## Modelo de Entrega <a id="entrega"></a>

O sistema é entregue como serviço hospedado, com a equipe desenvolvedora responsável pela operação e manutenção contínua. A GSW Soluções Integradas recebe acesso ao sistema e ao Manual do Usuário. Qualquer solicitação de ajuste, correção ou evolução deve ser encaminhada à equipe responsável pelo produto.

## Equipe <a id="equipe"></a>

| Foto | Função | Nome | LinkedIn | GitHub |
| :----: | :-----------: | :-----------------------: | :------------------------------------------------------------: | :-----------------------------------------------: |
| <img src="https://avatars.githubusercontent.com/u/144951743?v=4" width="75px"> | Scrum Master | Miguel Tomio Toledo Nonaka | [Linkedin](https://www.linkedin.com/in/miguel-nonaka) | [GitHub](https://github.com/miguelnonaka) |
| <img src="https://avatars.githubusercontent.com/u/119637682?v=4" width="75px"> | Product Owner | Heloisa Cardillo | [Linkedin](https://www.linkedin.com/in/heloisa-cardillo-lima/) | [GitHub](https://github.com/heloisa-cardillo) |
| <img src="https://avatars.githubusercontent.com/u/155785922?v=4" width="75px"> | Dev Team | Gabriel Henrique Lázaro | [Linkedin](https://www.linkedin.com/in/gabriel-henrique-a1330a26a/) | [GitHub](https://github.com/gabsact4) |
| <img src="https://avatars.githubusercontent.com/u/140865436?v=4" width="75px"> | Dev Team | Henry Vilela Silva Tito | [Linkedin](https://www.linkedin.com/in/henry-tito-989b4b354/) | [GitHub](https://github.com/HenryTito) |
| <img src="https://avatars.githubusercontent.com/u/102493225?v=4" width="75px"> | Dev Team | Paula Emy Tamay | [Linkedin](https://www.linkedin.com/in/paula-tamay-7a168228a/) | [GitHub](https://github.com/PaulaEmy) |
| <img src="https://avatars.githubusercontent.com/u/163305926?v=4" width="75px"> | Dev Team | Vinícius da Silva Leite | [Linkedin](https://www.linkedin.com/in/vinícius-leite-4792b02ba/) | [GitHub](https://github.com/vinislvleite) |
| <img src="https://avatars.githubusercontent.com/u/106409918?v=4" width="75px"> | Dev Team | Vitor Serpa da Silva | [Linkedin](https://www.linkedin.com/in/vitor-serpa-925b46322/) | [GitHub](https://github.com/VitorSerpa) |
