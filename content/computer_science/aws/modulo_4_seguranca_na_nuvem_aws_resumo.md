# Módulo 4: Segurança na Nuvem AWS - Resumo

> **Nota:** Este é um resumo executivo. Para detalhes completos, consulte [[modulo_4_seguranca_na_nuvem_aws]].

---

## Visão Geral

A **segurança é a maior prioridade** na AWS. Este módulo apresenta a abordagem da AWS à segurança, incluindo controles, ferramentas e práticas recomendadas para proteger a confidencialidade, integridade e disponibilidade de sistemas e dados.

**Para objetivos de aprendizagem detalhados**, veja [[modulo_4_seguranca_na_nuvem_aws#Objetivos de Aprendizagem]].

---

## Seção 1: Modelo de Responsabilidade Compartilhada

### Conceito Principal

Segurança e conformidade são **responsabilidades compartilhadas** entre AWS e cliente.

**Diferenciação:**

- **AWS**: Segurança "DA" nuvem (infraestrutura)
- **Cliente**: Segurança "NA" nuvem (dados, aplicativos, configurações)

### Responsabilidades da AWS

- Infraestrutura física (datacenters, hardware, instalações)
- Software de virtualização e sistemas operacionais host
- Rede (roteadores, switches, firewalls)
- Infraestrutura global (regiões, zonas de disponibilidade)

### Responsabilidades do Cliente

- Criptografia de dados (em repouso e em trânsito)
- Configuração de rede e grupos de segurança
- Gerenciamento de credenciais e acesso
- Sistema operacional convidado e patches
- Controle de conteúdo armazenado

### Modelos de Serviço

**IaaS (ex: Amazon EC2):**

- Cliente tem máximo controle e responsabilidade
- Gerencia SO, aplicativos, segurança completa

**PaaS (ex: AWS Lambda, Amazon RDS):**

- AWS gerencia infraestrutura e SO
- Cliente gerencia dados e permissões

**SaaS (ex: AWS Trusted Advisor, AWS Shield, Amazon Chime):**

- AWS gerencia toda infraestrutura e software
- Cliente usa o serviço

**Para detalhes sobre cada modelo e exemplos**, consulte [[modulo_4_seguranca_na_nuvem_aws#Modelos de Serviço e Responsabilidades]].

---

## Seção 2: AWS Identity and Access Management (IAM)

### O que é IAM

Serviço que controla o acesso a recursos da AWS através de **autenticação** e **autorização**.

- Gerenciamento centralizado de acesso
- Controle granular sobre recursos
- Serviço gratuito

### Componentes Principais do IAM

1. **Usuário do IAM**: Pessoa ou aplicativo com credenciais únicas
2. **Grupo do IAM**: Conjunto de usuários para simplificar gerenciamento
3. **Política do IAM**: Documento JSON que define permissões
4. **Função do IAM**: Acesso temporário a recursos específicos

**Para exemplos de configuração**, veja [[modulo_4_seguranca_na_nuvem_aws#Componentes do IAM]].

### Autenticação

**Tipos de acesso:**

- **Programático**: ID de chave de acesso + chave secreta (para CLI, SDK)
- **Console**: ID da conta + nome de usuário + senha (+ MFA se habilitado)

**Recomendação**: Habilitar **Multi-Factor Authentication (MFA)** para aumentar segurança.

**Opções de MFA**: Aplicativos virtuais (Google Authenticator, Authy), dispositivos U2F, dispositivos hardware.

### Autorização

**Modelo padrão**: Todas as ações são **negadas** por padrão (negação implícita).

**Princípio do Privilégio Mínimo**: Conceder apenas permissões mínimas necessárias.

**Avaliação de políticas**:

1. Verifica negação explícita → Nega acesso
2. Verifica permissão explícita → Permite acesso
3. Sem permissão explícita → Negação implícita

**Para entender tipos de políticas e exemplos JSON**, consulte [[modulo_4_seguranca_na_nuvem_aws#Políticas do IAM em Detalhes]].

### Grupos e Funções

**Grupos do IAM**:

- Simplificam gerenciamento de permissões
- Um usuário pode pertencer a vários grupos
- Grupos não podem ser aninhados

**Funções do IAM**:

- Acesso temporário (sem credenciais de longo prazo)
- Podem ser assumidas por qualquer pessoa que precisar
- Essenciais para acesso entre contas, aplicativos móveis, identidades externas

**Para casos de uso detalhados**, veja [[modulo_4_seguranca_na_nuvem_aws#Funções do IAM em Detalhes]].

---

## Seção 3: Proteção de Nova Conta AWS

### Usuário Raiz

O **usuário raiz** tem acesso completo a todos os recursos.

**⚠️ Recomendação crítica**: **NÃO usar** usuário raiz para operações diárias.

### Etapas para Proteger Conta Nova

1. **Criar usuário IAM** para uso diário (não usar raiz)
2. **Criar grupo IAM** com permissões apropriadas
3. **Desabilitar/remover chaves de acesso** do usuário raiz
4. **Habilitar MFA** para usuário raiz e todos os usuários
5. **Configurar política de senha** forte
6. **Armazenar credenciais do usuário raiz** em local seguro

**Para processo passo a passo completo**, consulte [[modulo_4_seguranca_na_nuvem_aws#Etapas para Parar de Usar o Usuário Raiz]].

### Ferramentas de Monitoramento

**AWS CloudTrail**:

- Registra todas as solicitações de API
- Habilitado por padrão (últimos 90 dias)
- Permite auditoria operacional

**Relatórios de Faturamento**:

- Monitoram uso e custos
- Atualizados pelo menos uma vez por dia

**Para detalhes sobre CloudTrail e relatórios**, veja [[modulo_4_seguranca_na_nuvem_aws#AWS CloudTrail]].

---

## Seção 4: Proteção de Contas

### AWS Organizations

Serviço de gerenciamento centralizado de múltiplas contas AWS.

**Recursos de segurança:**

1. **Unidades Organizacionais (OUs)**: Agrupamento de contas com políticas diferentes
2. **Integração com IAM**: Controle no nível da conta
3. **Políticas de Controle de Serviço (SCPs)**: Definem permissões máximas

**SCPs**: Nunca concedem permissões, apenas limitam o máximo permitido. Sobrepõem decisões de administradores de contas.

**Para entender como SCPs funcionam**, consulte [[modulo_4_seguranca_na_nuvem_aws#Políticas de Controle de Serviço (SCPs) - Detalhes]].

### Outros Serviços de Segurança

**AWS Key Management Service (KMS)**:

- Cria e gerencia chaves de criptografia
- Usa módulos de segurança de hardware (HSMs)
- Integra-se com a maioria dos serviços AWS

**Amazon Cognito**:

- Controla acesso a recursos AWS a partir de aplicativos
- Suporta SAML 2.0 e SSO
- Conformidade com HIPAA, PCI DSS, SOC, ISO

**AWS Shield**:

- Proteção contra ataques DDoS
- Shield Standard: gratuito e automático
- Shield Advanced: proteção adicional (pago)

**Para detalhes sobre cada serviço**, veja [[modulo_4_seguranca_na_nuvem_aws#Seção 4 Proteção de Contas]].

---

## Seção 5: Proteção de Dados

### Criptografia de Dados

**Dados em Repouso**:

- Algoritmo: AES-256
- AWS KMS processa criptografia automaticamente
- Recomendação: habilitar em todos os serviços que armazenam dados

**Dados em Trânsito**:

- Protocolo: TLS 1.2 (anteriormente SSL)
- Criptografia: AES-256
- HTTP não é seguro; HTTPS é criptografado

**Para exemplos de cenários de criptografia**, consulte [[modulo_4_seguranca_na_nuvem_aws#Criptografia de Dados em Trânsito - Cenários]].

### AWS Certificate Manager

Serviço para provisionar, gerenciar e implantar certificados SSL/TLS.

- Renovação automática de certificados
- Uso com load balancers e CloudFront

### Segurança do Amazon S3

**Padrão**: Todos os buckets são privados.

**Ferramentas de controle de acesso**:

1. **Amazon S3 Block Public Access**: Evita exposição não intencional
2. **Políticas do IAM**: Especificam usuários/funções com acesso
3. **Políticas de Bucket**: Definem acesso quando não há autenticação IAM
4. **Instrução de Negação**: Restringe acesso mesmo com outras permissões
5. **ACLs**: Opção menos usada
6. **AWS Trusted Advisor**: Verifica permissões de bucket

**Para práticas recomendadas detalhadas**, veja [[modulo_4_seguranca_na_nuvem_aws#Segurança do Amazon S3]].

---

## Seção 6: Garantia da Conformidade

### Programas de Conformidade da AWS

AWS contrata certificadores externos e auditores independentes para fornecer informações sobre políticas, processos e controles.

**Exemplo de certificação**: ISO/IEC 27001:2013

**Regulamentos suportados**:

- HIPAA (Health Insurance Portability and Accountability Act)
- GDPR (Regulamento Geral de Proteção de Dados da UE)
- PCI DSS, SOC, ISO/IEC 27001, 27017, 27018, ISO 9001

**Para lista completa de programas**, consulte a documentação da AWS ou [[modulo_4_seguranca_na_nuvem_aws#Programas de Conformidade da AWS]].

### AWS Config

Serviço para estimar, auditar e avaliar configurações de recursos AWS.

**Funcionalidades**:

- Monitora e registra configurações continuamente
- Avalia configurações em relação às desejadas
- Sinaliza recursos não compatíveis
- Serviço regional (habilitar em todas as regiões usadas)

**Para detalhes sobre recursos agregadores**, veja [[modulo_4_seguranca_na_nuvem_aws#AWS Config]].

### AWS Artifact

Fornece downloads sob demanda de documentos de segurança e conformidade.

**Documentos disponíveis**:

- Relatórios de certificações ISO
- Relatórios PCI e SOC
- Contratos (ex: BAA para HIPAA)

**Importante**: AWS Artifact fornece documentos apenas sobre a AWS. Cliente é responsável por documentos da própria empresa.

**Para uso de contratos para múltiplas contas**, consulte [[modulo_4_seguranca_na_nuvem_aws#AWS Artifact]].

---

## Práticas Recomendadas - Resumo Rápido

🔐 **Segurança de Conta**:

- ✓ Habilitar MFA
- ✓ Não usar usuário raiz
- ✓ Criar usuários IAM individuais
- ✓ Aplicar privilégio mínimo
- ✓ Usar grupos para gerenciar permissões
- ✓ Configurar política de senha forte
- ✓ Usar funções em vez de compartilhar credenciais
- ✓ Monitorar com CloudTrail

🔒 **Proteção de Dados**:

- ✓ Criptografar dados em repouso (AES-256)
- ✓ Criptografar dados em trânsito (TLS 1.2)
- ✓ Usar AWS KMS para gerenciar chaves
- ✓ Habilitar S3 Block Public Access
- ✓ Revisar permissões de bucket regularmente

📋 **Conformidade**:

- ✓ Usar AWS Config para auditoria
- ✓ Acessar relatórios via AWS Artifact
- ✓ Implementar SCPs com AWS Organizations
- ✓ Consultar programas de conformidade relevantes

---

## Recursos Adicionais

Para informações completas e exemplos detalhados, sempre consulte:

- [[modulo_4_seguranca_na_nuvem_aws]] - Versão completa deste módulo
- [Página de segurança da AWS](https://aws.amazon.com/security/)
- [Práticas recomendadas do IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- Blog de segurança da AWS
- AWS Well-Architected Framework - Pilar da Segurança

---

**Módulo 4 - AWS Academy Cloud Foundations (PT)**  
_Versão 2.0.16_