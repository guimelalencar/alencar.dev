# AWS Academy Cloud Foundations - Módulo 3: Infraestrutura Global da AWS

**Versão:** 2.0.16  
**Código:** 100-ACCLFO-20-PT-SG

---

## Visão Geral do Módulo

Este módulo aborda os seguintes tópicos:

- **Infraestrutura Global da AWS**
- **Visão geral dos serviços e das categorias de serviços da AWS**

### Objetivos de Aprendizagem

Após concluir este módulo, você será capaz de:

- Identificar a diferença entre **Regiões**, **Zonas de Disponibilidade** e **locais de borda** da AWS
- Identificar **categorias de serviços** e **serviços** da AWS

### Componentes do Módulo

- Demonstração com instrutor sobre detalhes da infraestrutura global da AWS
- Atividade prática explorando o Console de Gerenciamento da AWS
- Teste de conhecimento para avaliar compreensão dos conceitos-chave

---

## Seção 1: Infraestrutura Global da AWS

### Recursos para Consulta

Para informações atualizadas sobre as Regiões da AWS disponíveis:

- [AWS Global Infrastructure Map](https://aws.amazon.com/about-aws/global-infrastructure/#AWS_Global_Infrastructure_Map)
- [AWS Regions and Availability Zones](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)

> **Nota:** Esses recursos são atualizados frequentemente para mostrar a infraestrutura atual e planejada da AWS.

---

### Regiões AWS

A infraestrutura da Nuvem AWS é construída em torno de **Regiões**.

#### Características das Regiões

- **Número atual:** 22 Regiões em todo o mundo
- **Definição:** Uma **Região AWS** é uma localização geográfica física com uma ou mais **Zonas de Disponibilidade**
- **Isolamento:** As Regiões são isoladas umas das outras para alcançar tolerância a falhas e estabilidade
- **Replicação de dados:** Os recursos em uma região **não são replicados automaticamente** para outras regiões

> ⚠️ **Importante:** É **sua responsabilidade** replicar dados entre regiões, caso suas necessidades empresariais exijam isso.

#### Ativação de Regiões

- **Regiões introduzidas antes de 20 de março de 2019:** Ativadas por padrão
- **Regiões introduzidas após 20 de março de 2019:** Desativadas por padrão (exemplos: Ásia-Pacífico - Hong Kong, Oriente Médio - Bahrein)
    - É necessário ativar essas Regiões manualmente através do Console de Gerenciamento da AWS

#### Regiões com Acesso Restrito

**AWS China:**

- Conta da Amazon AWS (China) fornece acesso somente às Regiões de **Pequim** e **Ningxia**
- Mais informações: [AWS China](https://www.amazonaws.cn/en/about-aws/china/)

**AWS GovCloud (EUA):**

- Região isolada projetada para clientes e órgãos governamentais dos EUA
- Permite transferir cargas de trabalho confidenciais para a nuvem
- Atende requisitos normativos e de conformidade específicos

---

### Fatores para Seleção de Regiões

Ao selecionar a Região ou Regiões ideais, considere:

#### 1. **Governança de Dados e Requisitos Legais**

- Leis locais podem exigir que determinadas informações sejam mantidas dentro de limites geográficos
- Essas leis podem restringir as Regiões onde é possível oferecer conteúdo ou serviços
- _Exemplo:_ Diretiva de Proteção de Dados da União Europeia (UE)

#### 2. **Proximidade dos Usuários (Latência)**

- É desejável executar aplicações e armazenar dados em uma Região **mais próxima possível** do usuário
- Ajuda a **reduzir a latência**
- **CloudPing:** Site para testar latência entre sua localização e todas as Regiões AWS
    - Mais informações: [CloudPing](http://www.cloudping.info/)

#### 3. **Disponibilidade de Serviços**

- Nem todos os serviços da AWS estão disponíveis em todas as Regiões
- Consulte: [Regional Product Services](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/?p=tgi&loc=4)

#### 4. **Custo**

- Há variação no custo da execução de serviços dependendo da Região escolhida
- _Exemplo:_ Instância Linux Amazon EC2 t3.medium sob demanda:
    - **Leste dos EUA (Ohio):** $0,0416 USD/hora
    - **Ásia-Pacífico (Tóquio):** $0,0544 USD/hora

---

### Zonas de Disponibilidade

#### Definição e Estrutura

- Cada Região AWS contém **vários locais isolados**, conhecidos como **Zonas de Disponibilidade**
- Cada Zona de Disponibilidade pode incluir **múltiplos data centers** (normalmente três)
- Em dimensão integral, podem incluir **centenas de milhares de servidores**

#### Características das Zonas de Disponibilidade

- **Isolamento total:** Partições completamente isoladas da infraestrutura global da AWS
- **Infraestrutura própria:** Cada zona tem sua própria infraestrutura de energia
- **Separação física:** Fisicamente separadas por muitos quilômetros de outras Zonas de Disponibilidade
- **Proximidade:** Todas estão a **100 km umas das outras**

#### Interconexão entre Zonas

- Interconectadas com **redes de alta largura de banda e baixa latência**
- Fibra dedicada totalmente redundante
- Fornece **alta vazão** entre as Zonas de Disponibilidade
- A rede faz **replicação síncrona** entre as Zonas de Disponibilidade

#### Benefícios para Aplicações

As Zonas de Disponibilidade ajudam a criar **aplicativos altamente disponíveis**:

- Quando uma aplicação é particionada entre Zonas de Disponibilidade, as empresas estarão melhor **isoladas e protegidas** contra problemas como:
    - Relâmpagos
    - Tornados
    - Terremotos
    - Outros desastres naturais

#### Responsabilidades do Cliente

> 📌 **Você é responsável por:**
> 
> - Escolher as Zonas de Disponibilidade em que os sistemas serão armazenados
> - Sistemas podem abranger várias Zonas de Disponibilidade

**Recomendações da AWS:**

- Replicação entre Zonas de Disponibilidade para fins de **resiliência**
- Projetar sistemas para sobreviverem a uma falha temporária ou prolongada de uma Zona de Disponibilidade se ocorrer um desastre

---

### Data Centers

#### Características

- A **base da infraestrutura da AWS** são os data centers
- Clientes **não especificam** um data center para implantação de recursos
- A **Zona de Disponibilidade** é o nível de especificação mais granular que um cliente pode fazer
- Data center é o local onde os **dados reais residem**

#### Disponibilidade e Tolerância a Falhas

- Amazon opera data centers de **última geração** e **altamente disponíveis**
- Embora sejam raras, podem ocorrer falhas que afetam a disponibilidade
- Se todas as instâncias estiverem em um único local afetado por falha, nenhuma estará disponível

#### Design de Segurança

Os data centers são projetados com segurança, considerando:

**1. Avaliação de Localização**

- Cada local é cuidadosamente avaliado para **mitigar riscos do ambiente**

**2. Design Redundante**

- Design redundante que **prevê e tolera falhas** enquanto mantém níveis de serviço

**3. Backup de Componentes**

- Backup de componentes críticos do sistema em **múltiplas Zonas de Disponibilidade** para garantir disponibilidade

**4. Monitoramento Contínuo**

- AWS monitora continuamente o uso dos serviços
- Implanta infraestrutura que oferece suporte aos compromissos e requisitos de disponibilidade

**5. Segurança Física**

- Locais **não são divulgados**
- **Todo o acesso** é restrito

**6. Recuperação Automatizada**

- Em caso de falha, **processos automatizados** desviam o tráfego de dados da área afetada

#### Equipamentos de Rede

- AWS usa **equipamentos de rede personalizados** de vários fabricantes de dispositivos originais (ODMs)
- ODMs projetam e fabricam produtos com base nas especificações da AWS
- AWS cria uma nova marca para os produtos e os revende

---

### Pontos de Presença e Locais de Borda

#### Amazon CloudFront e Amazon Route 53

**Amazon CloudFront:**

- **Rede de entrega de conteúdo (CDN)** usada para distribuir conteúdo aos usuários finais
- Objetivo: **Reduzir a latência**

**Amazon Route 53:**

- **Serviço de sistema de nomes de domínio (DNS)**

**Roteamento Inteligente:**

- Solicitações enviadas para qualquer um desses serviços são **roteadas automaticamente** para o ponto de presença mais próximo
- Diminui a latência

#### Características dos Pontos de Presença

**Localização:**

- Pontos de presença da AWS estão localizados na **maioria das principais cidades do mundo**

**Otimização:**

- Medem continuamente:
    - Conectividade
    - Desempenho
    - Computação com a Internet
- Encontram a melhor maneira de rotear solicitações
- Oferecem uma melhor experiência de usuário **quase em tempo real**

**Serviços que Utilizam:**

- Amazon CloudFront
- Amazon Route 53
- AWS Shield
- AWS Web Application Firewall (AWS WAF)

#### Caches de Borda Regionais

- Usados com o **Amazon CloudFront por padrão**
- Utilizados quando há conteúdo que **não é acessado com frequência suficiente** para permanecer em um local de borda
- Absorvem esse conteúdo e fornecem uma **alternativa** para obter conteúdo do servidor de origem

---

### Benefícios da Infraestrutura Global da AWS

A infraestrutura global da AWS oferece:

#### 1. **Elasticidade e Escalabilidade**

- Recursos podem se ajustar **dinamicamente** para:
    - Aumentos ou diminuições nos requisitos de capacidade
- Ajuste **rápido** para acomodar o crescimento

#### 2. **Tolerância a Falhas**

- **Redundância de componentes integrada**
- Permite continuar as operações **apesar de falha** em um componente

#### 3. **Alta Disponibilidade**

- Requer **intervenção mínima a nenhuma intervenção humana**
- Fornece alta disponibilidade com **tempo de inatividade mínimo**

---

### Principais Lições - Seção 1

- A infraestrutura global da AWS consiste em **Regiões** e **Zonas de Disponibilidade**
- A escolha de uma Região é normalmente baseada em:
    - Requisitos de conformidade
    - Redução de latência
- Cada Zona de Disponibilidade é:
    - Fisicamente separada de outras zonas
    - Possui alimentação, redes e conectividade redundantes
- **Locais de borda** e **pontos de presença de caches regionais** melhoram o desempenho armazenando conteúdo em cache mais próximo dos usuários

---

## Seção 2: Visão Geral dos Serviços e Categorias de Serviços da AWS

### Introdução aos Serviços AWS

A AWS oferece um **amplo conjunto de produtos globais baseados na nuvem** que podem ser usados como componentes básicos para arquiteturas de nuvem.

#### Organização da Infraestrutura

A infraestrutura global da AWS pode ser dividida em **três elementos:**

1. **Regiões**
2. **Zonas de Disponibilidade**
3. **Pontos de Presença** (incluindo locais de borda)

Esta infraestrutura fornece a plataforma para serviços de:

- Redes
- Armazenamento
- Computação
- Bancos de dados

**Modelo de Serviço:**

- Fornecidos como **utilitário sob demanda**
- Disponíveis em segundos
- Definição de preço de **pagamento conforme o uso**

---

### Categorias de Serviços AWS

#### Visão Geral

- **Total de categorias:** 23 categorias diferentes de produtos ou serviços
- Cada categoria consiste em **um ou mais serviços**

#### Foco do Curso

Este curso foca em:

- Serviços **mais amplamente utilizados**
- Serviços que oferecem a **melhor introdução à Nuvem AWS**
- Serviços com **maior probabilidade de serem abordados** no exame AWS Certified Cloud Practitioner

#### Categorias Destacadas no Curso

1. **Computação**
2. **Gerenciamento de Custos**
3. **Banco de Dados**
4. **Gerenciamento e Governança**
5. **Redes e Entrega de Conteúdo**
6. **Segurança, Identidade e Conformidade**
7. **Armazenamento**

#### Recursos Adicionais

Para explorar todos os produtos da AWS:

- [AWS Products](http://aws.amazon.com/products)
- Todos os produtos são organizados por categorias de serviço
- Cada página de produto fornece:
    - Descrição detalhada do produto
    - Lista de benefícios

---

## Categorias e Serviços Detalhados

### 1. Serviços de Armazenamento

#### Amazon Simple Storage Service (Amazon S3)

**Tipo:** Serviço de armazenamento de objetos

**Características:**

- Escalabilidade
- Alta disponibilidade de dados
- Segurança
- Desempenho

**Casos de Uso:**

- Armazenar e proteger qualquer quantidade de dados
- Sites
- Aplicativos móveis
- Backup e restauração
- Arquivamento
- Aplicativos empresariais
- Dispositivos da Internet das Coisas (IoT)
- Análises de big data

---

#### Amazon Elastic Block Store (Amazon EBS)

**Tipo:** Serviço de armazenamento em blocos de alto desempenho

**Design:**

- Projetado para uso com o Amazon EC2
- Especialmente para cargas de trabalho com alto throughput
- Uso intensivo de transações

**Cenários de Uso:**

- Bancos de dados relacionais e não relacionais
- Aplicativos empresariais
- Aplicações em contêineres
- Mecanismos de análise de big data
- Sistemas de arquivos
- Fluxos de trabalho de mídia

---

#### Amazon Elastic File System (Amazon EFS)

**Tipo:** Sistema de arquivos NFS totalmente gerenciado

**Características:**

- Escalável
- Elástico
- Para uso com serviços da AWS e recursos on-premises

**Funcionalidade:**

- **Escalamento sob demanda:** Aumenta e diminui automaticamente à medida que arquivos são adicionados ou removidos
- Reduz a necessidade de provisionamento e gerenciamento manual de capacidade

---

#### Amazon Simple Storage Service Glacier

**Tipo:** Classe de armazenamento do Amazon S3

**Características:**

- Seguro
- Durável
- Custo extremamente baixo

**Finalidade:**

- Arquivamento de dados
- Backup de longo prazo

**Recursos:**

- Projetado para oferecer **11 noves de durabilidade** (99,999999999%)
- Recursos robustos de segurança e conformidade
- Atende requisitos regulatórios rigorosos

---

### 2. Serviços de Computação

#### Amazon Elastic Compute Cloud (Amazon EC2)

**Definição:** Capacidade de computação redimensionável na forma de máquinas virtuais na nuvem

**Benefícios:**

- Permite que aplicações sejam executadas com **flexibilidade**
- **Controle total** sobre os recursos

---

#### Amazon EC2 Auto Scaling

**Funcionalidade:**

- Adicionar ou remover **automaticamente** instâncias do Amazon EC2
- Baseado em condições previamente definidas

**Benefícios:**

- Manter desempenho consistente
- Otimizar custos

---

#### Amazon Elastic Container Service (Amazon ECS)

**Tipo:** Serviço de orquestração de contêineres

**Características:**

- Altamente escalável
- Alto desempenho
- Oferece suporte a **contêineres Docker**

**Benefícios:**

- Facilita a execução e o gerenciamento de aplicações conteinerizadas

---

#### Amazon Elastic Container Registry (Amazon ECR)

**Tipo:** Registro de contêineres Docker totalmente gerenciado

**Funcionalidades:**

- Permite aos desenvolvedores **armazenar, gerenciar e implantar** imagens de contêiner
- De forma segura e eficiente

---

#### AWS Elastic Beanstalk

**Tipo:** Serviço para implantação e escalabilidade de aplicativos e serviços web

**Plataformas Suportadas:**

- Apache
- Microsoft Internet Information Services (IIS)

**Benefício:**

- Abstrai a complexidade da infraestrutura subjacente

---

#### AWS Lambda

**Tipo:** Computação serverless

**Funcionalidade:**

- Executar código **sem provisionar ou gerenciar servidores**

**Modelo de Cobrança:**

- Baseado apenas no **tempo de computação consumido**
- **Não há custos** quando o código não está em execução

---

#### Amazon Elastic Kubernetes Service (Amazon EKS)

**Funcionalidade:**

- Facilita a implantação, o gerenciamento e a escalabilidade de aplicativos conteinerizados
- Utiliza **Kubernetes** na AWS

**Benefício:**

- Abstrai a complexidade da operação do plano de controle

---

#### AWS Fargate

**Tipo:** Mecanismo de computação para o Amazon ECS

**Funcionalidade:**

- Executar contêineres **sem gerenciar servidores ou clusters**
- Elimina a administração da infraestrutura subjacente

---

### 3. Serviços de Banco de Dados

#### Amazon Relational Database Service (Amazon RDS)

**Funcionalidade:**

- Facilita a configuração, a operação e a escalabilidade de bancos de dados relacionais na nuvem

**Recursos:**

- Capacidade redimensionável
- Automatiza tarefas administrativas:
    - Provisionamento de hardware
    - Configuração de banco de dados
    - Aplicação de patches
    - Backups

---

#### Amazon Aurora

**Tipo:** Banco de dados relacional

**Compatibilidade:**

- MySQL
- PostgreSQL

**Desempenho:**

- Até **5 vezes superior** ao MySQL padrão
- Até **3 vezes superior** ao PostgreSQL padrão

---

#### Amazon Redshift

**Funcionalidade:**

- Executar consultas analíticas em **petabytes de dados** armazenados localmente no Redshift
- Diretamente em **exabytes de dados** armazenados no Amazon S3

**Benefício:**

- Alta performance em qualquer escala

---

#### Amazon DynamoDB

**Tipo:** Banco de dados NoSQL (chave-valor e documentos)

**Características:**

- Latência inferior a **10 milissegundos** em qualquer escala
- Segurança integrada
- Backup e restauração
- Cache em memória

---

### 4. Serviços de Rede e Entrega de Conteúdo

#### Amazon Virtual Private Cloud (Amazon VPC)

**Funcionalidade:**

- Provisionar **seções logicamente isoladas** da Nuvem AWS
- Definir recursos de rede de forma controlada

---

#### Elastic Load Balancing

**Funcionalidade:**

- Distribui **automaticamente** o tráfego de entrada entre vários destinos

**Destinos Suportados:**

- Instâncias do Amazon EC2
- Contêineres
- Endereços IP
- Funções do AWS Lambda

---

#### Amazon CloudFront

**Tipo:** Serviço de rede de entrega de conteúdo (CDN)

**Funcionalidade:**

- Distribui dados, vídeos, aplicativos e APIs **globalmente**

**Características:**

- Baixa latência
- Altas velocidades de transferência

---

#### AWS Transit Gateway

**Funcionalidade:**

- Conectar **múltiplas VPCs** e redes locais a um **único gateway centralizado**

**Benefício:**

- Simplifica arquiteturas de rede complexas

---

#### Amazon Route 53

**Tipo:** Serviço de DNS

**Características:**

- Altamente disponível
- Escalável

**Funcionalidade:**

- Rotear usuários finais para aplicações da Internet
- Converte nomes de domínio (ex: `www.exemplo.com`) em endereços IP

---

#### AWS Direct Connect

**Funcionalidade:**

- Fornece uma conexão de rede **privada dedicada** entre:
    - Data center ou escritório do cliente
    - AWS

**Benefícios:**

- Reduz custos de rede
- Aumenta a largura de banda

---

#### VPN da AWS

**Funcionalidade:**

- Fornece um **túnel privado e seguro** entre:
    - Sua rede ou dispositivo
    - Rede global da AWS

---

### 5. Serviços de Segurança, Identidade e Conformidade

#### AWS Identity and Access Management (IAM)

**Funcionalidade:**

- Gerenciar o acesso a serviços e recursos da AWS com segurança

**Capacidades:**

- Criar e controlar **usuários**
- Criar e controlar **grupos**
- Gerenciar **permissões**

---

#### AWS Organizations

**Funcionalidade:**

- Restringir serviços e ações permitidos em **múltiplas contas AWS**

**Benefício:**

- Facilita governança e controle centralizado

---

#### Amazon Cognito

**Funcionalidade:**

- Adicionar funcionalidades de:
    - Cadastro
    - Login
    - Controle de acesso de usuários

**Aplicações:**

- Aplicações web
- Aplicações móveis

---

#### AWS Artifact

**Funcionalidade:**

- Oferece acesso **sob demanda** a:
    - Relatórios de segurança
    - Conformidade
    - Contratos da AWS

---

#### AWS Key Management Service (AWS KMS)

**Funcionalidade:**

- Criar e gerenciar **chaves criptográficas**
- Controlar o uso de criptografia em diversos serviços e aplicações

---

#### AWS Shield

**Tipo:** Serviço gerenciado de proteção contra DDoS

**Funcionalidade:**

- Proteção contra ataques **distribuídos de negação de serviço (DDoS)**
- Para aplicações executadas na AWS

---

### 6. Serviços de Gerenciamento de Custos

#### Relatório de Uso e Custos da AWS

**Funcionalidade:**

- Fornece o conjunto **mais abrangente** de dados de custos e uso

**Inclui:**

- Metadados sobre serviços
- Preços
- Reservas

---

#### AWS Budgets

**Funcionalidade:**

- Definir orçamentos personalizados
- Receber alertas quando:
    - Custos ou uso excedem os limites estabelecidos
    - Previsão de exceder os limites

---

#### AWS Cost Explorer

**Funcionalidade:**

- Interface visual para:
    - Analisar custos e uso da AWS
    - Compreender gastos
    - Gerenciar custos ao longo do tempo

---

### 7. Serviços de Gerenciamento e Governança

#### Console de Gerenciamento da AWS

**Tipo:** Interface web

**Funcionalidade:**

- Acesso e gerenciamento da conta AWS

---

#### AWS Config

**Funcionalidade:**

- Rastrear **inventário de recursos**
- Monitorar **alterações de configuração**

---

#### Amazon CloudWatch

**Funcionalidade:**

- Monitorar recursos e aplicações **em tempo real**

---

#### AWS Auto Scaling

**Funcionalidade:**

- Escalar **automaticamente** diversos recursos para atender à demanda

---

#### AWS Command Line Interface (CLI)

**Tipo:** Ferramenta unificada

**Funcionalidade:**

- Gerenciamento de serviços da AWS via **linha de comando**

---

#### AWS Trusted Advisor

**Funcionalidade:**

- Ajuda a otimizar:
    - Custos
    - Desempenho
    - Segurança
    - Tolerância a falhas

---

#### AWS Well-Architected Tool

**Funcionalidade:**

- Auxilia na **revisão e melhoria** de arquiteturas de cargas de trabalho

---

#### AWS CloudTrail

**Funcionalidade:**

- Registra atividades do usuário e chamadas à API

**Finalidade:**

- Auditoria
- Conformidade

---

## Resumo do Módulo

### O Que Você Aprendeu

Neste módulo, você aprendeu a:

✓ Identificar a diferença entre:

- **Regiões**
- **Zonas de Disponibilidade**
- **Locais de Borda** da AWS

✓ Identificar:

- **Categorias de serviços** da AWS
- **Principais serviços** da AWS

---

## Recursos Adicionais

### Links Importantes

- **Infraestrutura Global da AWS**  
    [https://aws.amazon.com/about-aws/global-infrastructure/](https://aws.amazon.com/about-aws/global-infrastructure/)
    
- **Lista de Serviços Regionais da AWS**  
    [https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)
    
- **Produtos da Nuvem AWS**  
    [https://aws.amazon.com/products/](https://aws.amazon.com/products/)
    

---

## Tags

#aws #cloud-foundations #infraestrutura #regioes #zonas-disponibilidade #servicos-aws #certificacao