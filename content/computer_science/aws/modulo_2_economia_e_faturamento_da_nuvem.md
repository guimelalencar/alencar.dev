# AWS Academy Cloud Foundations - Módulo 2: Economia e Faturamento da Nuvem

**Versão**: 2.0.16  
**Código**: 100-ACCLFO-20-PT-SG

---

## Visão Geral do Módulo

Este módulo aborda os seguintes tópicos:

- Conceitos básicos da definição de preço
- Custo total de propriedade
- AWS Organizations
- AWS Billing and Cost Management
- Suporte técnico

### Atividades Incluídas

- **Demonstração presencial**: Interação com o painel de faturamento
- **Atividade prática**: Estimativa de custos usando a Calculadora de Preços da AWS
- **Teste de conhecimento**: Avaliação da compreensão dos conceitos principais

---

## Objetivos de Aprendizagem

Após concluir este módulo, você será capaz de:

- ✅ Explicar a filosofia de definição de preço da AWS
- ✅ Reconhecer as características fundamentais da definição de preço
- ✅ Indicar os elementos do custo total de propriedade
- ✅ Discutir os resultados da Calculadora de Preços da AWS
- ✅ Identificar como configurar uma estrutura organizacional que simplifica o faturamento e a visibilidade da conta
- ✅ Identificar a funcionalidade no Painel de faturamento da AWS
- ✅ Descrever como usar as contas da AWS, o AWS Cost Explorer, o AWS Budgets e os relatórios de uso e custos da AWS
- ✅ Identificar os vários planos e recursos de suporte técnico da AWS

---

## Seção 1: Fundamentos da Definição de Preço

### Três Fatores Fundamentais de Custo

A AWS possui **três fatores fundamentais** que determinam os custos:

1. **Computação**
2. **Armazenamento**
3. **Transferência de dados de saída**

> **Nota**: Essas características variam dependendo do produto da AWS e do modelo de definição de preço escolhido.

### Transferência de Dados

#### Dados de Entrada
- **Gratuita** na maioria dos casos
- Sem cobrança pela transferência de dados entre produtos da AWS dentro da **mesma região**
- ⚠️ Existem algumas exceções - sempre verifique as taxas antes de começar

#### Dados de Saída
- **Agregada** entre serviços
- Cobrada de acordo com a taxa de transferência de dados de saída
- Aparece no relatório mensal como **"Transferência de dados para fora da AWS"**

---

### Filosofia de Preço da AWS

A filosofia de preço da AWS permanece consistente desde o início:

> **"Ao final de cada mês, você paga pelo que usar."**

#### Características Principais

- ✨ Início ou parada de uso de produtos a qualquer momento
- 🚫 **Não são necessários contratos de longo prazo**
- 💰 Pagamento apenas pelos recursos efetivamente utilizados
- 📊 Variedade de serviços com modelo de preço por consumo

---

### Modelos de Preço da AWS

#### 1. 💳 **Pagamento Conforme o Uso**

- Pague apenas pelos serviços que consumir
- Sem grandes despesas iniciais
- Sem necessidade de construir infraestrutura dispendiosa
- Elimina custos de:
  - Compra de servidores
  - Licenças de software
  - Aluguel de instalações

**Benefícios**:
- Adaptação rápida às necessidades empresariais dinâmicas
- Redirecionamento do foco para inovação e invenção
- Todos os serviços disponíveis sob demanda
- Sem contratos de longo prazo ou dependências de licenciamento complexo

---

#### 2. 🔒 **Pague Menos ao Fazer Reserva**

Para determinados serviços (**Amazon EC2** e **Amazon RDS**), é possível investir em capacidade reservada.

##### Instâncias Reservadas

**Economia**: Até **75%** em relação à capacidade sob demanda equivalente

**Três opções disponíveis**:

1. **AURI** - Instância Reservada com Pagamento Total Antecipado
   - Maior desconto
   - Pagamento completo no início

2. **PURI** - Instância Reservada com Pagamento Antecipado Parcial
   - Desconto intermediário
   - Menor investimento inicial

3. **NURI** - Instância Reservada sem Pagamento Antecipado
   - Menor desconto
   - Libera capital para outros projetos
   - Ideal para cumprir políticas de compromissos de longo prazo

**Vantagens**:
- Minimização de riscos
- Gerenciamento de orçamentos mais previsível
- Cumprimento de políticas de compromissos de longo prazo

---

#### 3. 📈 **Pague Menos Quando Usar Mais**

##### Descontos Baseados em Volume

- Economias substanciais conforme o uso aumenta
- **Definição de preço estratificada** (exemplo: Amazon S3)
  - Pague menos por GB quando usar mais
- **Transferência de dados para dentro**: Sempre gratuita

##### Benefícios de Escala

- Economia de escala permite aumento da adoção
- Manutenção dos custos sob controle
- Vários serviços de armazenamento com custos mais baixos baseados nas necessidades

##### Portfólio de Serviços de Armazenamento

Opções de armazenamento otimizadas por:
- Frequência de acesso aos dados
- Desempenho necessário para recuperação
- Preservação de segurança e confiabilidade

**Escolha as combinações certas para**:
- ⬇️ Reduzir custos
- ⚡ Preservar desempenho
- 🔒 Manter segurança
- 💪 Garantir confiabilidade

---

#### 4. 🌱 **Pague Ainda Menos com o Crescimento da AWS**

A AWS se concentra constantemente em:

- 🔧 Redução dos custos de hardware do data center
- ⚙️ Melhoria das eficiências operacionais
- ⚡ Redução do consumo de energia
- 💼 Redução geral dos custos de realização de negócios

##### Otimizações e Economia de Escala

**Resultado**: Repasse das economias em forma de preços mais baixos

**Histórico**:
- Desde 2006: AWS baixou a definição de preço **75 vezes** (até setembro de 2019)
- Recursos futuros e com maior performance substituem os atuais **sem custo adicional**

##### Preços Personalizados

A AWS reconhece que cada cliente tem necessidades diferentes:
- Disponíveis para projetos de alto volume
- Para requisitos exclusivos
- Quando os modelos padrão não atendem ao projeto

---

### 🎁 Nível Gratuito da AWS (Free Tier)

#### Elegibilidade
- Disponível para **novos clientes da AWS**
- Duração: **Até 1 ano**

#### Serviços Incluídos

| Serviço | Benefício |
|---------|-----------|
| **Amazon EC2** | Microinstância T2 gratuita por 1 ano |
| **Amazon S3** | Nível gratuito de armazenamento |
| **Amazon EBS** | Armazenamento em bloco gratuito |
| **Elastic Load Balancing** | Balanceamento de carga |
| **Transferência de Dados AWS** | Transferência gratuita |

📚 **Mais informações**: [aws.amazon.com/free](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all)

---

### 🆓 Serviços Sem Custo Adicional

A AWS oferece diversos serviços gratuitos:

#### 1. **Amazon VPC** (Virtual Private Cloud)
- Provisiona uma seção da Nuvem AWS isolada logicamente
- Execute recursos da AWS em uma rede virtual definida por você

#### 2. **AWS IAM** (Identity and Access Management)
- Controla o acesso dos usuários aos serviços e recursos da AWS

#### 3. **Cobrança Consolidada**
- Recurso de faturamento do AWS Organizations
- Consolida o pagamento de várias contas da AWS ou AISPL*

**Oferece**:
- ✅ Uma fatura única para várias contas
- 📊 Rastreamento fácil de cobranças de cada conta
- 💰 Descontos de preço por volume do uso combinado
- 🎯 Benefícios em camadas consolidando todas as contas

#### 4. **AWS Elastic Beanstalk**
- Maneira fácil de implantar e gerenciar aplicativos na Nuvem AWS

#### 5. **AWS CloudFormation**
- Criação fácil de grupos de recursos da AWS relacionados
- Provisionamento de forma organizada e previsível

#### 6. **Auto Scaling**
- Adiciona ou remove recursos automaticamente
- Baseado em condições definidas
- Aumento durante picos de demanda
- Diminuição durante quedas de demanda para minimizar custos

#### 7. **AWS OpsWorks**
- Serviço de gerenciamento de aplicativos
- Facilita implantação e operação de aplicativos de todos os tipos e tamanhos

> ⚠️ **Importante**: Embora não haja cobrança por esses serviços, pode haver cobranças associadas a outros serviços da AWS usados com eles. Por exemplo, ao dimensionar automaticamente instâncias do EC2 adicionais, haverá cobranças por essas instâncias.

#### Nota sobre Contas AISPL

**Diferença principal**: Vendedor de registro
- **Contas AWS**: Administradas pela Amazon Web Services, Inc.
- **Contas AISPL**: Administradas pela Amazon Internet Services Private Limited

**Características das Contas AISPL**:
- Para usuários com endereço indiano
- Cobradas em rúpias indianas (INR)

📚 **Saiba mais**: [Documentação sobre vendedor de registro](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/manage-account-payment-aispl.html#determine-seller)

---

### 📋 Resumo da Filosofia de Preço

> A filosofia de preço da AWS permanece consistente: ao final de cada mês, você paga apenas pelo que usar e pode começar ou parar de usar um produto a qualquer momento. Não são necessários contratos de longo prazo.

#### Como Estimar Custos

A melhor maneira de estimar custos:

1. Examine as características fundamentais de cada produto da AWS
2. Estime seu uso para cada característica
3. Mapeie esse uso para os preços publicados no site da AWS

#### Flexibilidade

A estratégia de definição de preço oferece:
- Flexibilidade de escolher os serviços necessários
- Pagamento apenas pelo que usar em cada projeto

#### Serviços Gratuitos da AWS

**Lista completa**:
- Amazon VPC
- Elastic Beanstalk
- AWS CloudFormation
- IAM
- Serviços de Auto Scaling
- AWS OpsWorks
- Cobrança Consolidada

> ⚠️ Os serviços são gratuitos, mas os recursos provisionados podem não ser.

#### Transferência de Dados

**Na maioria dos casos**:
- ✅ Sem cobrança pela transferência de dados de entrada
- ✅ Sem cobrança pela transferência entre produtos AWS na mesma Região
- ⚠️ Existem exceções - sempre verifique as taxas antes de usar

**Custos de transferência de saída**:
- Definidos em níveis (tiers)

📚 **Recursos de Aprendizagem**:
- [Preços da AWS](https://aws.amazon.com/pricing/)
- [Visão Geral de Preços da AWS (PDF)](https://d0.awsstatic.com/whitepapers/aws_pricing_overview.pdf)

---

## Seção 2: Custo Total de Propriedade (TCO)

### On-Premises vs Nuvem

Uma pergunta que muitas empresas fazem: **qual a melhor opção?**

#### 🏢 Infraestrutura On-Premises (Local)

**Definição**: Instalada localmente nos próprios computadores e servidores da empresa

**Características**:

| Aspecto | Detalhes |
|---------|----------|
| **Custos** | Custos fixos / Despesas de capital |
| **Inclui** | Instalações, hardware, licenças, equipe de manutenção |
| **Escalabilidade Vertical** | Dispendiosa e demorada |
| **Redução de Escala** | Não reduz custos fixos |

#### ☁️ Infraestrutura de Nuvem

**Definição**: Comprada de um provedor de serviços que cria e mantém a infraestrutura

**Características**:

| Aspecto | Detalhes |
|---------|----------|
| **Modelo de Pagamento** | Cliente paga pelo que é usado |
| **Escalabilidade** | Aumentar ou reduzir é simples |
| **Custos** | Fáceis de estimar, dependem do uso |
| **Gerenciamento** | Provedor cuida de instalações, hardware e manutenção |

---

### Comparação de Modelos

#### Desafio da Comparação

É difícil comparar diretamente porque usam conceitos e termos diferentes:

**TI Local envolve**:
- Discussão baseada em despesas de capital
- Longos ciclos de planejamento
- Vários componentes para comprar, criar, gerenciar e atualizar
- Recursos ao longo do tempo

**Nuvem AWS envolve**:
- Discussão sobre flexibilidade
- Foco em agilidade
- Custos baseados no consumo

---

### 💰 Custo Total de Propriedade (TCO)

#### Definição

**TCO** é uma estimativa financeira destinada a ajudar compradores e proprietários a determinar os **custos diretos e indiretos** de um produto ou sistema.

**Inclui**:
- Custo do serviço
- Todos os custos associados à propriedade do serviço

#### Objetivo

Comparar os custos da execução de um ambiente de infraestrutura inteiro para uma carga de trabalho específica:
- **Local ou colocação** vs **Infraestrutura baseada em nuvem**

**Finalidade**:
- Orçamento
- Criar caso de negócios para decisões empresariais
- Determinar a solução de implantação ideal

---

### Custos do Data Center

Alguns custos associados ao gerenciamento do data center incluem:

#### 1. 🖥️ **Custos de Servidor**
- Hardware
- Software
- Instalações para abrigar o equipamento

#### 2. 💾 **Custos de Armazenamento**
- Hardware de armazenamento
- Administração
- Instalações

#### 3. 🌐 **Custos de Rede**
- Hardware de rede
- Administração
- Instalações

#### 4. 👥 **Custos de Mão de Obra de TI**
- Necessários para administrar toda a solução

---

### Avaliação de Custos: Nuvem vs Local

#### Nuvem

**Vantagem**: A maioria dos custos é adiantada e prontamente calculada

**Características**:
- ✅ Preços transparentes
- 📊 Baseado em métricas de uso (RAM, armazenamento, largura de banda)
- 🕐 Definição de preço fixa por unidade de tempo
- 🎯 Certeza sobre a definição de preço
- 📈 Cálculo pronto baseado em estimativas de uso

#### Local

**Desafio**: Cálculos de custos internos difíceis de determinar

**Devem incluir**:

**Custos Diretos**:
- ⚡ Energia
- 🏢 Espaço reservado
- 💾 Armazenamento
- 🔧 Operações de TI para gerenciar recursos

**Custos Indiretos**:
- 🌐 Infraestrutura de rede
- 💽 Armazenamento adicional

---

### Itens de Custo Adicionais

> **Nota**: O diagrama conceitual não inclui todos os itens de custo.

**Exemplos de custos adicionais**:

**Software**:
- Banco de dados
- Gerenciamento
- Camada intermediária

**Instalações**:
- Atualizações
- Manutenção
- Segurança de edifícios
- Impostos

**Mão de Obra de TI**:
- Administração de segurança
- Administração de aplicativos

---

### 📊 Exemplo de Comparação de Custos

#### Cenário: Comparação de 3 Anos

**Ambiente On-Premises**:
- 1 máquina virtual com 4 CPUs, 16 GB de RAM
- Sistema operacional Linux
- Utilização média: 100%
- Otimizado por RAM
- **Custo Total (3 anos)**: **US$ 167.422**

**Ambiente AWS Comparável**:
- 1 instância m4.xlarge com 4 CPUs, 16 GB de RAM
- Tipo: Instância Reservada com pagamento antecipado parcial de 3 anos
- **Custo Total (3 anos)**: **US$ 7.509**

#### 💡 Resultados

| Métrica | Valor |
|---------|-------|
| **Economia Percentual** | 96% |
| **Economia Total (3 anos)** | US$ 159.913 |

#### Análise da Diferença

**Solução On-Premises**:
- ❌ Custos previstos e contínuos
- ❌ Incorre em custos independentemente do uso
- ❌ Capacidade pode ficar ociosa

**Solução AWS**:
- ✅ Encomendada quando necessário
- ✅ Desativada quando não está em uso
- ✅ Resulta em custos gerais mais baixos

---

### 🧮 Calculadora de Preços da AWS

#### O Que É?

Ferramenta para ajudar a estimar a fatura mensal da AWS.

#### Funcionalidades

A Calculadora de Preços da AWS permite:

- 💵 Estimar os custos mensais dos serviços da AWS
- 🔍 Identificar oportunidades de redução de custos
- 🏗️ Modelar suas soluções antes de criá-las
- 📊 Explorar pontos de preço e cálculos
- 🔎 Encontrar tipos de instância disponíveis e termos de contrato
- 📝 Planejar custos e uso da AWS
- ⚙️ Precificar ou configurar novos conjuntos de instâncias e serviços

#### Como Usar

**Recursos de Organização**:
- Nomeie sua estimativa
- Crie e nomeie **grupos de serviços**

**Grupos**:
- Contêineres para adicionar serviços
- Organizam e criam sua estimativa
- Podem ser organizados por:
  - Centro de custos
  - Departamento
  - Arquitetura de produto
  - Etc.

📚 **Acesse**: [calculator.aws](https://calculator.aws/#/)

---

### 📈 Análise de ROI (Retorno sobre Investimento)

#### TCO vs ROI

**TCO (Custo Total de Propriedade)**:
- Define o que será gasto com a tecnologia
- Custo para executar a solução
- Compara infraestrutura local (estado atual) vs nuvem (estado futuro)
- ⚠️ Fornece apenas uma visão restrita do impacto financeiro total

**ROI (Retorno sobre Investimento)**:
- Determina o valor gerado
- Considera gastos E economia
- Visão mais completa do impacto

---

### 💎 Benefícios Rígidos (Hard Benefits)

**Incluem**:

| Categoria | Benefícios |
|-----------|-----------|
| **Gastos Reduzidos** | Computação, armazenamento, redes, segurança |
| **Compras** | Reduções em hardware e software |
| **Operações** | Reduções nos custos operacionais |
| **Continuidade** | Backup e recuperação de desastres |
| **Equipe** | Redução na equipe de operações |

---

### 🌟 Benefícios Flexíveis (Soft Benefits)

**Definição**: Pontos de valor que desafiam quantificar com precisão, mas podem ser **mais valiosos** que as economias rígidas.

**Incluem**:

1. **Reutilização de Serviços e Aplicativos**
   - Definir e redefinir soluções
   - Usar o mesmo serviço de nuvem

2. **Aumento na Produtividade do Desenvolvedor**
   - Mais eficiência
   - Foco em inovação

> 💡 **Importante**: É essencial compreender **ambos** os benefícios (rígidos e flexíveis) para compreender o valor total da nuvem.

---

## Seção 3: AWS Organizations

### O Que É?

**AWS Organizations** é um serviço de gerenciamento de contas que permite:
- Consolidar várias contas da AWS
- Criar uma organização gerenciada de forma centralizada

### Recursos Incluídos

- 💳 Cobrança consolidada
- 🔧 Gerenciamento de contas
- 📊 Atendimento a necessidades orçamentárias, de segurança e compatibilidade

---

### 🎯 Principais Benefícios

| Benefício | Descrição |
|-----------|-----------|
| **Políticas Centralizadas** | Gerenciamento centralizado de acesso em várias contas |
| **Controle de Serviços** | Acesso controlado aos serviços AWS |
| **Automação** | Criação e gerenciamento automatizados de contas |
| **Faturamento Consolidado** | Cobrança consolidada em várias contas |

---

### Funcionalidades do AWS Organizations

#### 1. 📋 **Políticas de Controle de Serviço (SCPs)**
- Controlam centralmente os serviços da AWS
- Aplicadas em várias contas da AWS

#### 2. 📁 **Grupos de Contas**
- Crie grupos de contas
- Anexe políticas a um grupo
- Garanta aplicação das políticas corretas

#### 3. 🤖 **Automação via APIs**
- Use interfaces de programação de aplicativos (APIs)
- Automatize criação e gerenciamento de novas contas

#### 4. 💰 **Faturamento Simplificado**
- Configure um único método de pagamento
- Para todas as contas da AWS na organização

---

### Cobrança Consolidada

**Proporciona**:

- 🎯 Local central para gerenciar faturamento
- 📊 Exibição combinada das cobranças
- 💵 Aproveitamento de benefícios de preço agregado
- 📈 Descontos por volume

---

### AWS Organizations vs AWS IAM

#### ⚠️ Diferenças Importantes

**AWS Organizations NÃO substitui**:
- Associação de políticas do AWS IAM
- Políticas de usuários, grupos e funções em uma conta

#### AWS IAM

**Com políticas do IAM**:
- ✅ Permite ou nega acesso a serviços AWS (ex: Amazon S3)
- ✅ Controla recursos individuais (ex: bucket S3 específico)
- ✅ Gerencia ações de API individuais (ex: s3:CreateBucket)
- ✅ Aplicado a usuários, grupos ou funções do IAM
- ❌ **Nunca pode restringir o usuário raiz da conta**

#### AWS Organizations

**Com Políticas de Controle de Serviço (SCPs)**:
- ✅ Permite ou nega acesso a serviços AWS
- ✅ Para contas individuais ou grupos de contas em uma UO
- ✅ Ações especificadas afetam:
  - Todos os usuários IAM
  - Todos os grupos IAM
  - Todas as funções IAM
  - **Incluindo o usuário raiz da conta AWS**

---

### 🔧 Configurando o AWS Organizations

#### Pré-requisitos

- Acesso a duas contas da AWS existentes
- Permissões de administrador em cada conta

#### Etapas de Configuração

**Etapa 1: Criar a Organização**
- Use sua conta da AWS atual como conta primária
- Convide outra conta da AWS para participar
- Crie outra conta como conta-membro

**Etapa 2: Criar Unidades Organizacionais**
- Crie duas UOs na nova organização
- Coloque as contas-membro nessas UOs

**Etapa 3: Criar Políticas de Controle de Serviço**
- Aplique restrições às ações
- Delegue a usuários e funções nas contas-membro
- **SCP**: Tipo de política de controle da organização

**Etapa 4: Testar as Políticas**
- Faça login como usuário para cada função (OU1 ou OU2)
- Veja como as SCPs afetam o acesso à conta
- **Alternativa**: Use o Simulador de Políticas do IAM

---

### Simulador de Políticas do IAM

**Funcionalidade**:
- Testar e solucionar problemas
- Políticas do IAM
- Políticas baseadas em recursos
- Anexadas a usuários, grupos ou funções

📚 **Documentação**: [Simulador de Política do IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)

---

### ⚙️ Restrições de Nomenclatura

**Nomes no AWS Organizations** (contas, UOs, raízes, políticas):
- ✅ Devem ser compostos por caracteres Unicode
- ❌ Não podem exceder **250 caracteres**

**Valores Máximos e Mínimos**:
- AWS Organizations tem vários limites para entidades
- Consulte a documentação para detalhes específicos

---

## Seção 4: AWS Billing and Cost Management

### O Que É?

**AWS Billing and Cost Management** é o serviço usado para:
- 💳 Pagar sua fatura da AWS
- 📊 Monitorar seu uso
- 💰 Controlar seus custos

---

### Funcionalidades Principais

#### Previsão e Planejamento

- 🔮 Prever custos futuros
- 📈 Ter uma ideia melhor de quais serão os custos e uso
- 📅 Planejar com antecedência

#### Personalização de Período

- 📆 Definir período personalizado
- 📊 Ver dados em nível mensal ou diário

#### Filtragem e Agrupamento

- 🔍 Analisar dados detalhadamente
- 📑 Usar variedade de dimensões disponíveis

---

### 📊 Ferramenta de Relatório de Uso e Custos

**Permite**:
- 🎯 Identificar oportunidades de otimização
- 📈 Compreender tendências de dados de custo e uso
- 🏗️ Entender como você está usando a implementação da AWS

---

### Ferramentas no Painel de Faturamento

O painel de faturamento oferece acesso a várias ferramentas de gerenciamento de custos:

| Ferramenta | Descrição |
|------------|-----------|
| **AWS Bills** | Faturas e cobranças |
| **AWS Cost Explorer** | Exploração e análise de custos |
| **AWS Budgets** | Orçamentos da AWS |
| **Relatórios de Custos e Uso** | Relatórios detalhados |

**Uso**: Estimar e planejar custos da AWS

---

## 📚 Recursos Adicionais

### Documentação Importante

- [Visão Geral de Preços da AWS (PDF)](https://d0.awsstatic.com/whitepapers/aws_pricing_overview.pdf)
- [Preços da AWS](https://aws.amazon.com/pricing/)
- [Nível Gratuito da AWS](https://aws.amazon.com/free/)
- [Calculadora de Preços da AWS](https://calculator.aws/#/)
- [Simulador de Políticas do IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)
- [Vendedor de Registro (Contas AISPL)](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/manage-account-payment-aispl.html#determine-seller)
