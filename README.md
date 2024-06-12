# KAMI N8N Workflows [PT](README.md) | [EN](README-en_us.md)

## Sumário

1. [**Introdução**](#introdução)
2. [**Objetivo e Escopo do Projeto**](#objetivo-e-escopo-do-projeto)
3. [**Metodologia do Roteiro de Desenvolvimento**](#metodologia)
4. [**Primeiros passos com N8N**](#primeiros-passos-com-n8n)
5. **Workflows por Área de Interesse**
    - [**CRM**](./modules/crm/main.md)
    - [**E-Comm**](./modules/ecomm/main.md)
6. [**Referências**](#referências)

## Introdução

Este documento fornece um guia abrangente para que usuários não desenvolvedores possam importar, configurar, testar e ativar várias automações de tarefas em uma instância N8N. Essas automações integram múltiplas plataformas aumentando a produtividade de processos em diferentes setores da empresa.

## Objetivo e Escopo do Projeto

O objetivo principal deste projeto é criar um hub de automação para a empresa, utilizando N8N para agilizar e automatizar tarefas em vários departamentos. Isto aumentará a eficiência, reduzirá tarefas manuais e garantirá uma integração perfeita entre diferentes plataformas.

## Metodologia

### Como as Salsichas São Feitas?

Utilizando conceitos de Domain-Driven Design (DDD), o projeto é estruturado para refletir os domínios de negócios reais. O processo criativo também será documentado para incluir o processo que o tornou possível. Isso será detalhado em documentos específicos conforme listado abaixo:

- **Requisitos Funcionais:** Este documento contém o resumo das reuniões realizadas com especialistas de negócio e usuários finais para extrair os requisitos funcionais que a solução precisa entregar, proporcionando uma visão clara das funcionalidades esperadas. [Saiba mais...](./requirements_análise.md)
- **Geração A.I. Prompts:** Inclui os prompts utilizados no ChatGPT-4 para auxiliar no desenvolvimento do projeto, detalhando as interações e resultados obtidos. [Saiba mais...](./prompts-gpt.md)
- **Diário de Bordo:** Lançamentos resumidos por dia e horário descrevendo a evolução do projeto e os desafios enfrentados. [Saiba mais...](./logbook.md)

### Porque Usar o N8N?

Usar o N8N como servidor de automação RPA oferece diversas vantagens em um ambiente de negócios dinâmico:

- **Flexibilidade:** O N8N permite fácil integração com diversas APIs e serviços, tornando-o adaptável às mudanças nas necessidades de negócios.
- **Interface Amigável:** O construtor visual de workflow no N8N é intuitivo, permitindo que usuários com conhecimento técnico mínimo criem e gerenciem fluxos de trabalho complexos.
- **Escalabilidade:** O N8N pode ser dimensionado horizontalmente, suportando grandes volumes de dados e processos de automação complexos.
- **Código Aberto:** Como plataforma de código aberto, o N8N oferece transparência e a capacidade de personalizar o código-fonte conforme necessário.
- **Suporte da Comunidade:** Uma comunidade robusta oferece amplos recursos, plug-ins e suporte, facilitando a resolução rápida de problemas.

No entanto, os usuários devem estar atentos a:

- **Segurança:** Garanta que todas as credenciais e dados confidenciais sejam tratados com segurança.
- **Desempenho:** Monitore o desempenho do workflow para evitar gargalos e garantir uma execução eficiente.
- **Manutenção:** Atualize regularmente a instância N8N e os fluxos de trabalho para incorporar novos recursos e patches de segurança.

### Primeiros Passos com N8N

N8N é uma ferramenta extensível de automação de fluxo de trabalho (workflow) que permite conectar vários aplicativos e automatizar tarefas repetitivas. Ele permite criar workflows por meio de uma interface amigável, que integra diversos serviços e APIs sem escrever código. O N8N fornece um poderoso mecanismo de automação, tornando-o adequado para uma ampla gama de necessidades de automação comercial.

#### Workflows

No contexto do N8N, um workflow é uma série de tarefas automatizadas que são acionadas por determinados eventos ou condições. Cada workflow pode conter vários nós, onde cada nó representa uma tarefa ou operação específica, como enviar um email, fazer uma solicitação de API ou processar dados. Ao vincular esses nós, você pode criar sequências de automação complexas que agilizam seus processos de negócios. Este conceito está alinhado com as tarefas automatizadas descritas neste documento, onde workflows são utilizados para integrar e automatizar diferentes plataformas e serviços, aumentando a eficiência e reduzindo o esforço manual.

### Acessando N8N

1. **Faça login em sua instância N8N.**

    ![N8N Login](./docs/assets/pictures/main/pic_01_n8n_login.png)
    *Legenda: Tela de login do N8N.*

2. **Tela Inicial do N8N.**

    ![N8N Dashboard](./docs/assets/pictures/main/pic_02_n8n_dashboard.png)
    *Legenda: Painel do N8N.*

### Operações Básicas de Gerenciamento de Workflow

- **Criando um Workflow:**
   1. Clique em 'Add Workflows' para criar um novo workflow.

    ![Criando Workflow](./docs/assets/pictures/main/pic_02_n8n_dashboard.png)
    *Legenda: Criando um novo workflow no N8N.*

   2. Clique no botão com '+' para adicionar um novo nó.

    ![Criando Workflow](./docs/assets/pictures/main/pic_03_n8n_new_workflow.png)
    *Legenda: Criando um novo nó no workflow.*

- **Importando um Workflow de um Arquivo JSON:**
   1. Crie um novo workflow como na seção anterior.
   2. No botão '...' no canto direito selecione 'Import from file...'
   3. Carregue seu arquivo JSON de workflow.

    ![Importar Workflow](./docs/assets/pictures/main/pic_04_n8n_import_workflow.png)
    *Legenda: Importando um workflow no N8N.*

- **Ativando um Workflow:**
   1. Abra o workflow que deseja ativar.
   2. Arraste o botão switch 'inactive' no canto superior direito para ativar.

    ![Executando Workflow](./docs/assets/pictures/main/pic_05_n8n_activate_workflow.png)
    *Legenda: Executando um workflow no N8N.*

- **Configurando Variáveis de Ambiente:**
  
  Alguns workflows deste projeto possuem um nó chamado '*__env-vars__*' usado para configurar algumas informações importantes e/ou sensíveis, como credenciais de API, tokens, logins e senhas. Para configurar, basta seguir o seguinte tutorial:

   1. Localize e abra o nó ‘env-vars’ em seu workflow.
   2. Atualize as credenciais de API e outras variáveis necessárias.

    ![Nó de Variáveis de Ambiente A](./docs/assets/pictures/main/pic_06_A_n8n_env_vars.png)
    *Legenda: Abrindo o nó `env-vars`.*

    ![Nó de Variáveis de Ambiente](./docs/assets/pictures/main/pic_06_B_n8n_env_vars.png)
    *Legenda: Configurando as Variáveis de Ambiente.*

- **Monitoramento da Execução do Workflow:**
   1. Vá para a seção 'Execuções' para monitorar as execuções do workflow.
   2. Revise os logs e resultados para garantir que tudo esteja funcionando perfeitamente.

    ![Monitorando Workflow](./docs/assets/pictures/main/pic_07_n8n_monitoring_workflows.png)
    *Legenda: Monitorando a execução do workflow.*

### Referências

#### Livros

Evans, E. (2003). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley.

#### Documentação de API

SharpSpring. (2024). *Documentação da API SharpSpring*. Obtido de [https://api.sharpspring.com/](https://api.sharpspring.com/)

Movidesk. (2024). *Documentação da API Movidesk*. Obtido de [https://api.movidesk.com/public/v1](https://api.movidesk.com/public/v1)

#### Documentação de Aplicações

N8N. (2024). *Documentação N8N*. Obtido de [https://docs.n8n.io/](https://docs.n8n.io/)

---