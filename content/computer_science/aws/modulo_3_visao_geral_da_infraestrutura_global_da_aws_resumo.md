# AWS Academy - Módulo 3: Resumo Executivo

> 📌 **Para detalhes completos, consulte:** [[modulo_3_visao_geral_da_infraestrutura_global_da_aws]]

---

## 🎯 Objetivos de Aprendizagem

- Diferenciar **Regiões**, **Zonas de Disponibilidade** e **Locais de Borda**
- Identificar **categorias** e **serviços** principais da AWS

---

## 🌍 Infraestrutura Global da AWS

### Regiões AWS

- **22 Regiões** globais (localização geográfica física)
- Cada Região contém **1+ Zonas de Disponibilidade**
- **Isolamento total** entre Regiões (sem replicação automática)
- **Cliente responsável** por replicação entre regiões

**Critérios de seleção:**

1. Conformidade legal e governança de dados
2. Latência (proximidade do usuário)
3. Disponibilidade de serviços
4. Custo

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#Regiões AWS]]

---

### Zonas de Disponibilidade (AZs)

- Múltiplas AZs por Região
- Cada AZ = **1+ data centers** isolados
- Separadas fisicamente (muitos km), mas **<100km** entre si
- Interconectadas com **baixa latência e alta largura de banda**
- **Replicação síncrona** entre AZs

**Benefício:** Alta disponibilidade e tolerância a falhas

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#Zonas de Disponibilidade]]

---

### Data Centers e Pontos de Presença

**Data Centers:**

- Base da infraestrutura AWS
- Design redundante com segurança física
- Recuperação automatizada de falhas

**Pontos de Presença (Edge Locations):**

- Presentes nas principais cidades globais
- Usados por CloudFront, Route 53, Shield, WAF
- **Caches de borda regionais** para conteúdo de baixa frequência

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#Data Centers]] e [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#Pontos de Presença e Locais de Borda]]

---

## 📦 Categorias de Serviços AWS

### 1. Armazenamento

|Serviço|Tipo|Uso Principal|
|---|---|---|
|**S3**|Armazenamento de objetos|Websites, backups, big data, IoT|
|**EBS**|Armazenamento em blocos|Bancos de dados, apps empresariais|
|**EFS**|Sistema de arquivos NFS|Escalável, elástico, on-prem + cloud|
|**S3 Glacier**|Arquivamento|Backup de longo prazo, custo baixo|

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#1. Serviços de Armazenamento]]

---

### 2. Computação

|Serviço|Descrição|
|---|---|
|**EC2**|Máquinas virtuais redimensionáveis|
|**EC2 Auto Scaling**|Escalonamento automático de instâncias|
|**ECS**|Orquestração de containers Docker|
|**ECR**|Registro de imagens Docker|
|**Elastic Beanstalk**|Deploy gerenciado de apps web|
|**Lambda**|Computação serverless (sem servidores)|
|**EKS**|Kubernetes gerenciado|
|**Fargate**|Containers sem gerenciar infraestrutura|

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#2. Serviços de Computação]]

---

### 3. Banco de Dados

|Serviço|Tipo|Características|
|---|---|---|
|**RDS**|Relacional gerenciado|MySQL, PostgreSQL, Oracle, SQL Server|
|**Aurora**|Relacional high-performance|5x MySQL, 3x PostgreSQL|
|**Redshift**|Data warehouse|Consultas em petabytes/exabytes|
|**DynamoDB**|NoSQL|<10ms latência, key-value + documentos|

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#3. Serviços de Banco de Dados]]

---

### 4. Rede e Entrega de Conteúdo

|Serviço|Função|
|---|---|
|**VPC**|Rede isolada logicamente|
|**Elastic Load Balancing**|Distribuição de tráfego|
|**CloudFront**|CDN global|
|**Transit Gateway**|Hub centralizado de conectividade|
|**Route 53**|DNS escalável|
|**Direct Connect**|Conexão privada dedicada|
|**AWS VPN**|Túnel seguro para rede AWS|

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#4. Serviços de Rede e Entrega de Conteúdo]]

---

### 5. Segurança, Identidade e Conformidade

|Serviço|Finalidade|
|---|---|
|**IAM**|Gerenciamento de acesso (usuários, grupos, permissões)|
|**Organizations**|Governança multi-conta|
|**Cognito**|Autenticação de usuários (web/mobile)|
|**Artifact**|Relatórios de conformidade|
|**KMS**|Gerenciamento de chaves criptográficas|
|**Shield**|Proteção contra DDoS|

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#5. Serviços de Segurança, Identidade e Conformidade]]

---

### 6. Gerenciamento de Custos

- **Relatório de Uso e Custos:** Dados abrangentes de gastos
- **AWS Budgets:** Orçamentos e alertas personalizados
- **Cost Explorer:** Análise visual de custos

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#6. Serviços de Gerenciamento de Custos]]

---

### 7. Gerenciamento e Governança

|Ferramenta|Uso|
|---|---|
|**Console de Gerenciamento**|Interface web|
|**AWS Config**|Rastreamento de recursos e configurações|
|**CloudWatch**|Monitoramento em tempo real|
|**Auto Scaling**|Escalonamento automático|
|**CLI**|Gerenciamento via linha de comando|
|**Trusted Advisor**|Otimização (custo, performance, segurança)|
|**Well-Architected Tool**|Revisão de arquiteturas|
|**CloudTrail**|Auditoria de atividades e API calls|

> 📖 Detalhes em: [[modulo_3_visao_geral_da_infraestrutura_global_da_aws#7. Serviços de Gerenciamento e Governança]]

---

## ✅ Pontos-Chave para Memorizar

**Infraestrutura:**

- Região → Zonas de Disponibilidade → Data Centers
- Escolha de Região: conformidade, latência, serviços, custo
- AZs isoladas fisicamente com conectividade redundante
- Edge locations para CDN e DNS

**Serviços Essenciais:**

- **Armazenamento:** S3 (objetos), EBS (blocos), EFS (arquivos)
- **Computação:** EC2 (VMs), Lambda (serverless), ECS/EKS (containers)
- **Banco de Dados:** RDS (relacional), DynamoDB (NoSQL)
- **Rede:** VPC (isolamento), ELB (balanceamento), CloudFront (CDN)
- **Segurança:** IAM (acesso), KMS (criptografia), Shield (DDoS)

---

## 🔗 Recursos Importantes

- [Infraestrutura Global](https://aws.amazon.com/about-aws/global-infrastructure/)
- [Serviços por Região](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)
- [Catálogo de Produtos](https://aws.amazon.com/products/)

---

## 📝 Preparação para Certificação

Este conteúdo cobre tópicos essenciais para o **AWS Certified Cloud Practitioner**:

- Conceitos de infraestrutura global
- Diferenciação entre componentes (Regiões, AZs, Edge)
- Conhecimento de categorias e serviços principais

> 💡 **Dica:** Revise [[modulo_3_visao_geral_da_infraestrutura_global_da_aws]] para exemplos práticos e detalhes técnicos

---

#aws #resumo #certificacao #estudo-rapido