# AWS Academy Cloud Foundations - Módulo 1: Visão Geral dos Conceitos de Nuvem

**Versão:** 2.0.14  
**Curso:** AWS Academy Cloud Foundations (PT)

---

## 📋 Tópicos do Módulo

- Introdução à computação em nuvem
- Vantagens da computação em nuvem
- Introdução à Amazon Web Services (AWS)
- AWS Cloud Adoption Framework (AWS CAF)

---

## 🎯 Objetivos de Aprendizagem

Após concluir este módulo, você deverá ser capaz de:

- ✅ Definir diferentes tipos de computação em nuvem
- ✅ Descrever seis vantagens da computação em nuvem
- ✅ Reconhecer as principais categorias dos serviços da AWS e os principais serviços
- ✅ Analisar o AWS Cloud Adoption Framework (AWS CAF)

---

## 📖 Seção 1: Introdução à Computação em Nuvem

### O que é Computação em Nuvem?

> **Definição:** Computação em nuvem é a entrega sob demanda de poder computacional, banco de dados, armazenamento, aplicativos e outros recursos de TI pela Internet com uma definição de preço conforme o uso.

**Características principais:**
- Recursos executados em computadores servidores localizados em grandes datacenters
- Provedor de serviços (como AWS) é proprietário dos computadores
- Recursos podem ser usados em conjunto como componentes básicos
- Objetivo: criar soluções que atendam metas de negócios e requisitos tecnológicos

📚 **Recurso adicional:** [O que é computação em nuvem? (AWS)](https://aws.amazon.com/what-is-cloud-computing/)

---

### 🔄 Mudança de Paradigma: Hardware vs Software

#### Modelo Tradicional (Hardware)

**Limitações:**
- ❌ Infraestrutura física que exige espaço
- ❌ Necessidade de equipe dedicada
- ❌ Segurança física complexa
- ❌ Planejamento extensivo
- ❌ Despesas de capital (CAPEX) elevadas
- ❌ Ciclo longo de aquisição (aquisição → provisionamento → manutenção)

**Problemas de capacidade:**
- Provisionamento baseado em "adivinhação" de picos máximos
- **Superestimação:** Recursos ociosos caros
- **Subestimação:** Capacidade insuficiente
- **Mudanças:** Tempo, esforço e dinheiro para nova solução

**Exemplo prático:**  
*Provisionar um novo site: comprar hardware → montar → empilhar → datacenter → gerenciar*  
→ **Abordagem cara e demorada**

---

#### Modelo de Nuvem (Software)

**Vantagens:**
- ✅ Infraestrutura flexível
- ✅ Seleção de serviços sob medida
- ✅ Provisionamento e encerramento sob demanda
- ✅ Pagamento apenas pelo uso
- ✅ Escalabilidade elástica e automatizada
- ✅ Recursos temporários e descartáveis

**Benefícios para desenvolvedores:**
- Evita trabalho genérico (aquisição, manutenção, planejamento de capacidade)
- Foco no que realmente importa para o negócio
- Implementação rápida com baixos custos iniciais
- Mudanças rápidas, fáceis e econômicas

---

### 🏗️ Modelos de Serviços em Nuvem

Cada modelo representa uma parte diferente da pilha de computação em nuvem:

#### 1. **IaaS** - Infrastructure as a Service (Infraestrutura como Serviço)

**Características:**
- Componentes básicos da TI em nuvem
- Acesso a recursos de rede e computadores (virtual ou hardware dedicado)
- Espaço para armazenamento de dados
- **Mais alto nível** de flexibilidade e controle de gerenciamento
- Semelhante aos recursos de TI tradicionais

**Quando usar:** Necessidade de controle total sobre a infraestrutura

---

#### 2. **PaaS** - Platform as a Service (Plataforma como Serviço)

**Características:**
- Reduz necessidade de gerenciar infraestrutura subjacente
- Foco na implantação e gerenciamento de aplicativos
- Hardware e sistemas operacionais gerenciados pelo provedor

**Quando usar:** Concentrar-se no desenvolvimento de aplicações

---

#### 3. **SaaS** - Software as a Service (Software como Serviço)

**Características:**
- Produto completo executado e gerenciado pelo provedor
- Aplicativos de usuário final
- Sem necessidade de manutenção de serviço
- Sem gerenciamento de infraestrutura subjacente

**Exemplo comum:** Webmail (enviar/receber e-mails sem gerenciar servidores)

**Quando usar:** Foco apenas no uso do software

---

### ☁️ Modelos de Implantação em Nuvem

#### 1. **Nuvem** (Cloud)

**Características:**
- Aplicativo totalmente implantado na nuvem
- Todas as partes executadas na nuvem
- Criados na nuvem OU migrados de infraestrutura existente

**Níveis de implementação:**
- Infraestrutura de baixo nível
- Serviços de nível superior (abstração de gerenciamento, arquitetura, escalabilidade)

---

#### 2. **Híbrida** (Hybrid)

**Características:**
- Conexão entre recursos baseados na nuvem e recursos locais
- Método mais comum: nuvem + infraestrutura local
- Ampliação e expansão gradual para a nuvem
- Integração com sistemas internos

**Quando usar:** Transição gradual para a nuvem mantendo sistemas legados

---

#### 3. **No Local** (On-Premises / Nuvem Privada)

**Características:**
- Uso de ferramentas de gerenciamento de virtualização
- Recursos dedicados
- Não oferece muitos benefícios da nuvem
- Semelhante à infraestrutura de TI antiga
- Tecnologias de virtualização para aumentar utilização de recursos

**Quando usar:** Requisitos específicos de recursos dedicados ou compliance

---

### 🔗 Semelhanças: AWS vs TI Tradicional

| **AWS** | **TI Tradicional Local** |
|---------|--------------------------|
| Security Groups, Network ACLs, IAM | Firewalls, ACLs, Administradores |
| Elastic Load Balancing, Amazon VPC | Roteadores, pipelines de rede, switches |
| AMIs, Amazon EC2 | Servidores locais |
| Amazon EBS, EFS, S3, RDS | DAS, SAN, NAS, RDBMS |

> **Conclusão:** Com AWS, você pode fazer praticamente tudo o que faria com um datacenter tradicional.

---

### 📌 Principais Lições - Seção 1

1. **Computação em nuvem** = Entrega de recursos de TI sob demanda pela Internet, com pagamento conforme o uso
2. **Mudança de paradigma:** Infraestrutura como software (não hardware)
3. **Três modelos de serviço:** IaaS, PaaS, SaaS
4. **Três modelos de implantação:** Nuvem, Híbrida, No local
5. **Equivalência:** Serviços AWS similares aos da TI tradicional

---

## 💡 Seção 2: Vantagens da Computação em Nuvem

### Vantagem 1: Troque Despesas de Capital por Despesas Variáveis

**CAPEX (Capital Expenditure) - Despesas de Capital:**
- Fundos para adquirir, atualizar e manter ativos físicos
- Propriedades, edifícios industriais, equipamentos
- Pagamento por recursos que podem permanecer ociosos
- Investimento substancial antecipado

**Despesas Variáveis:**
- ✅ Pode ser alterada ou evitada facilmente
- ✅ Pagamento apenas pelo consumo real
- ✅ Economia de dinheiro em tecnologia
- ✅ Adaptação a novos aplicativos em minutos (não semanas/dias)
- ✅ Redução de manutenção
- ✅ Foco em objetivos principais da empresa

---

### Vantagem 2: Beneficie-se da Grande Economia de Escala

**Como funciona:**
- Agregação de centenas de milhares de clientes na nuvem
- Provedores obtêm economias de escala maiores
- **Resultado:** Custos variáveis inferiores aos de ambientes locais
- **Benefício:** Preços mais baixos com pagamento conforme o uso

---

### Vantagem 3: Pare de Tentar Adivinhar a Capacidade

**Problemas do modelo tradicional:**
- ❌ Decisões de capacidade antes da implantação
- ❌ Recursos ociosos caros
- ❌ Capacidade limitada insuficiente

**Solução em nuvem:**
- ✅ Acesso à quantidade desejada
- ✅ Ajuste de escala em minutos
- ✅ Elasticidade conforme necessidade

---

### Vantagem 4: Aumente a Velocidade e Agilidade

**Comparação:**

| **Tradicional** | **Nuvem** |
|-----------------|-----------|
| Semanas para disponibilizar recursos | Minutos para disponibilizar recursos |
| Alto custo e tempo de teste/desenvolvimento | Baixo custo e tempo reduzido |
| Agilidade limitada | Agilidade substancial |

**Impacto:** Recursos de TI ao alcance com apenas um clique

---

### Vantagem 5: Pare de Gastar Dinheiro na Execução e Manutenção de Datacenters

**Mudança de foco:**
- ❌ **Antes:** Infraestrutura (racks, empilhamento, alimentação de servidores)
- ✅ **Agora:** Projetos que diferenciam a empresa
- ✅ **Resultado:** Concentração nos clientes, não no trabalho pesado

---

### Vantagem 6: Tenha Alcance Global em Minutos

**Benefícios:**
- 🌍 Implantação em várias regiões AWS com poucos cliques
- ⚡ Latência menor
- 😊 Melhor experiência para clientes
- 💰 Custo mínimo e simplicidade

---

### 📌 Principais Lições - Seção 2

As **seis vantagens da computação em nuvem:**

1. ✅ Troque despesas de capital por despesas variáveis
2. ✅ Grande economia de escala
3. ✅ Pare de tentar adivinhar a capacidade
4. ✅ Aumente a velocidade e agilidade
5. ✅ Pare de gastar dinheiro com operação e manutenção de datacenters
6. ✅ Tenha alcance global em minutos

---

## 🌐 Seção 3: Introdução à Amazon Web Services (AWS)

### O que é um Serviço Web?

**Definição:**
- Qualquer software disponibilizado pela Internet ou redes privadas (intranet)
- Usa formato padronizado: **XML** ou **JSON**
- Para solicitação e resposta de API
- Não vinculado a sistema operacional ou linguagem de programação específica
- Autodescritivo via arquivo de definição de interface
- Detectável

---

### O que é AWS?

> **Amazon Web Services (AWS):** Plataforma de nuvem segura que oferece um amplo conjunto de produtos globais baseados na nuvem.

**Características:**
- Acesso sob demanda via Internet
- Recursos disponíveis:
  - Computação
  - Armazenamento
  - Rede
  - Banco de dados
  - Outros recursos de TI
- Ferramentas de gerenciamento incluídas
- Provisionamento e execução imediatos (minutos)

---

### 🔧 Flexibilidade da AWS

**Recursos de reconfiguração:**
- ✅ Atualização sob demanda
- ✅ Aumento/redução automática de escala
- ✅ Otimização de gastos conforme padrões de uso
- ✅ Encerramento temporário ou permanente

**Mudança financeira:**
- ❌ **Antes:** Despesa de capital (CAPEX)
- ✅ **Agora:** Despesa operacional (OPEX)

**Design modular:**
- Serviços projetados para funcionar juntos
- Suporte a qualquer tipo de aplicativo ou carga de trabalho
- Blocos fundamentais para soluções sofisticadas e escaláveis
- Ajustáveis conforme necessidades mudam

---

### 📦 Categorias de Serviços AWS

Os serviços AWS são organizados em **categorias diferentes**, cada uma contendo um ou mais serviços específicos.

#### Exemplo Prático: Aplicativo de Banco de Dados

**Fluxo de dados:**

1. **Clientes** → Enviam dados
2. **Amazon EC2** (Computação) → Recebe dados
3. **Agrupamento** → Lotes em incrementos de 1 minuto
4. **Amazon S3** (Armazenamento) → Um objeto por cliente
5. **Amazon DynamoDB** (Banco de dados não relacional) → Índice para busca
6. **Amazon VPC** (Rede) → Execução dentro de rede privada virtual

**Objetivo do exemplo:** Ilustrar seleção de serviços de diferentes categorias para criar uma solução integrada.

---

### 💻 Principais Serviços de Computação AWS

A escolha depende dos **objetivos empresariais** e **requisitos de tecnologia**.

| **Serviço** | **Caso de Uso** |
|-------------|-----------------|
| **Amazon EC2** | Controle total sobre recursos de computação |
| **AWS Lambda** | Executar código sem gerenciar/provisionar servidores |
| **AWS Elastic Beanstalk** | Serviço que implanta, gerencia e escala aplicativos web |
| **Amazon Lightsail** | Plataforma leve para aplicativo web simples |
| **AWS Batch** | Executar centenas de milhares de cargas de trabalho em lote |
| **AWS Outposts** | Executar infraestrutura AWS no datacenter local |
| **Amazon ECS / EKS / Fargate** | Arquitetura de contêineres ou microsserviços |
| **VMware Cloud on AWS** | Migrar plataforma de virtualização local para AWS |

**Observação:** Variedade de serviços continua crescendo em todas as categorias.

---

### 🎓 Serviços Focados no Curso

Este curso concentra-se nos serviços mais comuns nas seguintes categorias:

- ⚙️ Computação
- 💾 Armazenamento
- 🗄️ Banco de dados
- 🌐 Entrega de redes e conteúdo
- 🔒 Segurança, identidade e conformidade
- 📊 Gerenciamento e governança
- 💰 Gerenciamento de custos da AWS

---

### 🔑 Principais Serviços AWS Abordados

1. **Amazon EBS** - Elastic Block Store
2. **Amazon EC2** - Elastic Compute Cloud
3. **Amazon ECR** - Elastic Container Registry
4. **Amazon ECS** - Elastic Container Service
5. **Amazon EFS** - Elastic File System
6. **Amazon EKS** - Elastic Kubernetes Service
7. **Amazon RDS** - Relational Database Service
8. **Amazon S3** - Simple Storage Service
9. **Amazon VPC** - Virtual Private Cloud
10. **AWS IAM** - Identity and Access Management
11. **AWS KMS** - Key Management Service

---

### 🛠️ Três Maneiras de Acessar a AWS

#### 1. **Console de Gerenciamento da AWS**

**Características:**
- Interface gráfica avançada
- Maioria dos recursos disponíveis
- **Observação:** Novos recursos podem não ter todas as capacidades no console inicialmente

---

#### 2. **AWS CLI** - Interface da Linha de Comando

**Características:**
- Conjunto de utilitários executáveis via script
- Plataformas: Linux, macOS, Microsoft Windows
- Automação de tarefas

---

#### 3. **SDKs** - Software Development Kits

**Características:**
- Pacotes para linguagens de programação populares
- Integração com aplicativos existentes
- Criação de aplicativos para implantar e monitorar sistemas complexos via código

---

**Base comum:** As três opções são criadas em uma **API semelhante à REST**.

📚 **Recurso adicional:** [Ferramentas para criar na AWS](https://aws.amazon.com/tools/)

---

### 📌 Principais Lições - Seção 3

1. **AWS** = Plataforma de nuvem segura com amplo conjunto de produtos globais (serviços)
2. **Categorias diversas** de serviços AWS
3. **Escolha baseada** em objetivos empresariais e requisitos de tecnologia
4. **Três formas de interação:** Console, CLI, SDKs

---

## 🚀 Seção 4: Mudança para a Nuvem AWS - AWS Cloud Adoption Framework (CAF)

### Por que o AWS CAF?

**Contexto:**
- Computação em nuvem oferece muitas vantagens
- Adoção não acontece instantaneamente para a maioria das organizações
- **Três elementos devem estar alinhados:** Pessoas, Processos, Tecnologia

**Mudanças significativas:**
- Como a tecnologia é obtida, utilizada e gerenciada
- Orçamento e pagamento por serviços de tecnologia
- Necessidade de alterações fundamentais em toda a organização
- Apoio de partes interessadas em todas as unidades (dentro e fora da TI)

---

### O que é AWS CAF?

> **AWS Cloud Adoption Framework (AWS CAF):** Orientação e melhores práticas para ajudar organizações a identificar lacunas em habilidades e processos, criando uma abordagem abrangente para a computação em nuvem.

**Objetivos:**
- ✅ Identificar lacunas em habilidades e processos
- ✅ Criar abordagem abrangente
- ✅ Aplicar em toda a organização
- ✅ Cobrir todo o ciclo de vida de TI
- ✅ Acelerar adoção bem-sucedida da nuvem

---

### 🧩 Estrutura do AWS CAF

**Organização:** Seis áreas de foco chamadas **perspectivas**

**Cobertura:** Pessoas, Processos, Tecnologia

**Composição de cada perspectiva:**
- Conjunto de **capacidades**
- Responsabilidades distintas
- Gerenciadas por partes interessadas funcionalmente relacionadas

**Uso das capacidades:**
- Identificar áreas que exigem atenção
- Criar fluxos de trabalho prescritivos
- Apoiar jornada bem-sucedida para a nuvem

---

### 📊 Divisão das Perspectivas

#### **Foco em Negócios:**
1. Perspectiva Empresarial
2. Perspectiva das Pessoas
3. Perspectiva da Governança

#### **Foco Técnico:**
4. Perspectiva da Plataforma
5. Perspectiva de Segurança
6. Perspectiva de Operações

---

### 1️⃣ Perspectiva Empresarial (Business)

**Partes interessadas:**
- Gerentes de negócios
- Gerentes financeiros
- Proprietários de orçamento
- Partes interessadas da estratégia

**Uso do AWS CAF:**
- ✅ Criar caso de negócios forte para adoção da nuvem
- ✅ Priorizar iniciativas de adoção
- ✅ Garantir alinhamento entre estratégias/metas de negócios e de TI

---

### 2️⃣ Perspectiva das Pessoas (People)

**Partes interessadas:**
- Recursos humanos
- Equipes
- Gerentes de pessoas

**Uso do AWS CAF:**
- ✅ Avaliar estruturas e funções organizacionais
- ✅ Identificar novos requisitos de habilidades e processos
- ✅ Identificar lacunas
- ✅ Priorizar treinamento, equipe e alterações organizacionais
- ✅ Criar organização ágil

**Ferramenta:** Análise de necessidades e lacunas

---

### 3️⃣ Perspectiva da Governança (Governance)

**Partes interessadas:**
- CIO (Diretor de Tecnologia da Informação)
- Gerentes de programas
- Arquitetos empresariais
- Analistas de negócios
- Gerentes de portfólio

**Uso do AWS CAF:**
- ✅ Alinhar estratégia e metas de TI com estratégia e metas empresariais
- ✅ Maximizar valor empresarial do investimento em TI
- ✅ Minimizar riscos empresariais

**Foco:** Habilidades e processos necessários para alinhamento estratégico

---

### 4️⃣ Perspectiva da Plataforma (Platform)

**Partes interessadas:**
- CTO (Diretor de Tecnologia)
- Gerentes de TI
- Arquitetos de soluções

**Uso do AWS CAF:**
- ✅ Compreender e comunicar sistemas de TI e relacionamentos
- ✅ Descrever detalhadamente arquitetura do ambiente de estado de destino
- ✅ Aplicar princípios e padrões para implantação de novas soluções
- ✅ Migrar cargas de trabalho locais para a nuvem

**Ferramentas:** Dimensões e modelos de arquitetura variados

---

### 5️⃣ Perspectiva de Segurança (Security)

**Partes interessadas:**
- CISO (Diretor de Segurança da Informação)
- Gerentes de segurança de TI
- Analistas de segurança de TI

**Uso do AWS CAF:**
- ✅ Garantir objetivos de segurança:
  - Visibilidade
  - Auditoria
  - Controle
  - Agilidade
- ✅ Estruturar seleção e implantação de controles de segurança
- ✅ Atender necessidades específicas da organização

---

### 6️⃣ Perspectiva de Operações (Operations)

**Partes interessadas:**
- Gerentes de operações de TI
- Gerentes de suporte de TI

**Uso do AWS CAF:**
- ✅ Definir como atividades são realizadas (diárias, trimestrais, anuais)
- ✅ Alinhar e suportar operações da empresa
- ✅ Definir procedimentos operacionais atuais
- ✅ Identificar alterações de processo necessárias
- ✅ Identificar treinamentos necessários para implementação bem-sucedida

---

### 📌 Principais Lições - Seção 4

1. **Adoção da nuvem** exige estratégia e alinhamento consciente (não é instantânea)
2. **AWS CAF** ajuda a desenvolver planos eficientes e eficazes
3. **Seis perspectivas** como áreas de foco
4. **Perspectivas consistem** em conjuntos de capacidades empresariais ou tecnológicas
5. **Responsabilidade** das principais partes interessadas

---

## 📝 Resumo do Módulo

Neste módulo, você aprendeu a:

1. ✅ **Definir** diferentes tipos de computação em nuvem
2. ✅ **Descrever** seis vantagens da computação em nuvem
3. ✅ **Reconhecer** as principais categorias dos serviços da AWS e os principais serviços
4. ✅ **Analisar** a estrutura de adoção da Nuvem AWS (AWS CAF)

---

## ❓ Questão de Avaliação

**Pergunta:** Por que a AWS é mais econômica do que datacenters tradicionais para aplicações com workloads de computação variáveis?

**Opções:**

A) Os custos do Amazon EC2 são cobrados mensalmente  
B) Os clientes mantêm acesso administrativo completo às instâncias do Amazon EC2  
C) As instâncias do Amazon EC2 podem ser executadas sob demanda quando necessário  
D) Os clientes podem executar instâncias suficientes permanentemente para lidar com picos de workload

### ✅ Resposta Correta

**C) As instâncias do Amazon EC2 podem ser executadas sob demanda quando necessário**

**Justificativa:** A capacidade de executar instâncias sob demanda permite que você pague apenas pelo que usa, evitando recursos ociosos caros e capacidade insuficiente - características essenciais para workloads variáveis.

### ❌ Respostas Incorretas

- **A:** Custos são cobrados por uso, não mensalmente de forma fixa
- **B:** Acesso administrativo não relacionado diretamente à economia de custos
- **D:** Executar instâncias permanentemente para picos é o modelo tradicional (ineficiente)

---

## 📚 Recursos Adicionais

1. 🎥 [O que é a AWS? (Vídeo)](https://aws.amazon.com/awstv/watch/3059da9f36d/)
2. 🌐 [Site: Computação em nuvem com a AWS](https://aws.amazon.com/what-is-aws/)
3. 📄 [Artigo técnico: Visão geral do Amazon Web Services](https://d1.awsstatic.com/whitepapers/aws-overview.pdf)
4. 📄 [Artigo técnico: Visão geral do AWS Cloud Adoption Framework](https://d1.awsstatic.com/whitepapers/aws_cloud_adoption_framework.pdf)
5. 📝 [Blog AWS: 6 estratégias para migrar aplicativos para a nuvem](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)

---

**Fim do Módulo 1**