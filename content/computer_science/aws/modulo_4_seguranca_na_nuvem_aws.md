# Módulo 4: Segurança na Nuvem AWS

## Informações do Curso

- **Curso**: AWS Academy Cloud Foundations (PT)
- **Módulo**: 04 - Segurança na Nuvem AWS
- **Versão**: 2.0.16
- **Código**: 100-ACCLFO-20-PT-SG

---

## Visão Geral do Módulo

A segurança é a **maior prioridade** na Amazon Web Services (AWS). A AWS oferece um ambiente de computação em nuvem escalável, projetado para oferecer alta disponibilidade e confiabilidade, além de fornecer as ferramentas que permitem executar uma grande variedade de aplicativos.

### Objetivo Central

Ajudar a proteger a **confidencialidade**, a **integridade** e a **disponibilidade** de seus sistemas e dados é essencial para a AWS, assim como manter a confiança e a convicção do cliente.

### Estrutura do Módulo

Este módulo fornece uma introdução à abordagem da AWS à segurança, incluindo:

- Controles no ambiente da AWS
- Produtos e recursos da AWS para segurança
- Práticas recomendadas de conformidade

---

## Tópicos Abordados

1. **Modelo de responsabilidade compartilhada da AWS**
2. **AWS Identity and Access Management (IAM)**
3. **Proteção de novas contas da AWS**
4. **Proteção de contas**
5. **Proteção de dados na AWS**
6. **Garantia da conformidade**
7. **Serviços e recursos de segurança adicionais**

### Atividades Práticas

- **Seção 1**: Atividade com instrutor sobre modelo de responsabilidade compartilhada
- **Seção 2**: Demonstração gravada do IAM + laboratório prático no Console de Gerenciamento da AWS
- **Final**: Teste de conhecimento para avaliar compreensão dos conceitos

---

## Objetivos de Aprendizagem

Após concluir este módulo, você deverá ser capaz de:

✓ Reconhecer o modelo de responsabilidade compartilhada  
✓ Identificar a responsabilidade do cliente e a da AWS  
✓ Reconhecer usuários, grupos e funções do IAM  
✓ Descrever diferentes tipos de credenciais de segurança no IAM  
✓ Identificar as etapas para a proteção de novas contas da AWS  
✓ Explorar usuários e grupos do IAM  
✓ Reconhecer como proteger dados da AWS  
✓ Reconhecer programas de conformidade da AWS

---

# Seção 1: Modelo de Responsabilidade Compartilhada da AWS

## Conceito Fundamental

Segurança e conformidade são **responsabilidades compartilhadas** entre a AWS e o cliente. Esse modelo foi projetado para:

- Reduzir a carga operacional do cliente
- Oferecer flexibilidade e controle ao cliente
- Permitir a implantação de soluções personalizadas

### Diferenciação Principal

A responsabilidade é normalmente diferenciada pelas expressões:

- **Segurança "DA" nuvem** → Responsabilidade da AWS
- **Segurança "NA" nuvem** → Responsabilidade do cliente

---

## Responsabilidades da AWS (Segurança DA Nuvem)

A AWS opera, gerencia e controla os componentes desde a camada de virtualização de software até a segurança física das instalações.

### Infraestrutura Protegida pela AWS

**Hardware e Instalações Físicas:**

- Segurança física de datacenters com acesso controlado e baseado em necessidades
- Localização em instalações não identificadas
- Guardas de segurança 24 horas por dia, 7 dias por semana
- Autenticação de dois fatores
- Revisão e registro em log de acesso
- Vigilância por vídeo
- Desmagnetização e destruição de discos

**Infraestrutura de Hardware:**

- Servidores
- Dispositivos de armazenamento
- Outros dispositivos dos quais a AWS depende

**Infraestrutura de Software:**

- Sistemas operacionais host
- Aplicativos de serviço
- Software de virtualização
- Sistema operacional host bare metal
- Camada de virtualização do hipervisor

**Infraestrutura de Rede:**

- Roteadores
- Switches
- Load balancers
- Firewalls
- Cabeamento
- Monitoramento contínuo da rede em limites externos
- Proteção de pontos de acesso
- Infraestrutura redundante com detecção de intrusão

### Infraestrutura Global

A AWS é responsável pela proteção da infraestrutura global que executa todos os serviços oferecidos na Nuvem AWS:

- **Regiões da AWS**
- **Zonas de disponibilidade**
- **Pontos de presença**

---

## Responsabilidades do Cliente (Segurança NA Nuvem)

O cliente é responsável pela segurança de tudo o que coloca na nuvem, incluindo o que é implementado com o uso dos serviços da AWS e os aplicativos conectados à AWS.

### Principais Responsabilidades

**Criptografia e Dados:**

- Criptografia de dados em repouso
- Criptografia de dados em trânsito

**Configuração de Rede:**

- Garantir que a rede esteja configurada para segurança
- Configurações de grupos de segurança
- Configurações de firewall
- Configurações de rede

**Credenciais e Acesso:**

- Gerenciamento seguro de credenciais e logins de segurança
- Gerenciamento seguro de contas

**Sistemas Operacionais e Aplicativos:**

- Configuração do sistema operacional que é executado nas instâncias de computação
- Atualizações e patches de segurança
- Proteção de aplicativos executados em recursos da AWS
- Seleção e proteção de qualquer sistema operacional de instância

### Controle de Conteúdo

Os clientes mantêm **controle total** sobre o conteúdo e são responsáveis por:

- **Escolha do conteúdo**: Qual conteúdo armazenar na AWS
- **Seleção de serviços**: Quais serviços da AWS são usados com o conteúdo
- **Localização geográfica**: Em qual país esse conteúdo é armazenado
- **Formato e estrutura**: Como o conteúdo é formatado, se é mascarado, anonimizado ou criptografado
- **Gestão de acesso**: Quem tem acesso e como os direitos de acesso são concedidos, gerenciados e revogados

---

## Modelos de Serviço e Responsabilidades

### Infraestrutura como Serviço (IaaS)

**Definição:** Serviços que fornecem componentes básicos da TI.

**Características:**

- Acesso para configuração de redes
- Computadores (virtuais ou em hardware dedicado)
- Espaço para armazenamento de dados
- **Mais alto nível de flexibilidade e controle** de gerenciamento
- Semelhantes aos recursos de computação locais existentes

**Exemplo:** Amazon EC2

**Responsabilidades do Cliente para IaaS:**

- Executar **todas** as tarefas de configuração e gerenciamento de segurança necessárias
- Gerenciar o sistema operacional convidado (incluindo atualizações e patches)
- Gerenciar software de aplicativo instalado nas instâncias
- Configurar os grupos de segurança fornecidos pela AWS

---

### Plataforma como Serviço (PaaS)

**Definição:** Serviços que eliminam a necessidade de o cliente gerenciar a infraestrutura subjacente.

**Características:**

- Cliente se concentra totalmente na implantação e gerenciamento de aplicativos
- Não precisa se preocupar com:
    - Aquisição de recursos
    - Planejamento de capacidade
    - Manutenção de software
    - Aplicação de patches

**Exemplos:** AWS Lambda, Amazon RDS

**Responsabilidades:**

- **AWS gerencia**: Camada de infraestrutura, sistema operacional e plataformas
- **Cliente gerencia**:
    - Dados
    - Classificação de ativos
    - Aplicação de permissões apropriadas
- A AWS realiza tarefas básicas de segurança como aplicação de patches, configuração de firewall e recuperação de desastres

---

### Software como Serviço (SaaS)

**Definição:** Serviços que fornecem software hospedado de maneira centralizada.

**Características:**

- Acessível por meio de navegador web, aplicativo móvel ou API
- Modelo de licenciamento: assinatura ou pagamento conforme o uso
- Cliente não precisa gerenciar a infraestrutura

**Exemplos na AWS:**

**AWS Trusted Advisor:**

- Ferramenta on-line que analisa seu ambiente da AWS
- Fornece orientações e recomendações em tempo real
- Ajuda a provisionar recursos seguindo práticas recomendadas
- Oferecido como parte do plano do AWS Support
- Recursos básicos gratuitos para todas as contas
- Business Support e Enterprise Support: acesso ao conjunto completo de verificações

**AWS Shield:**

- Serviço gerenciado de proteção contra DDoS (negação de serviço distribuída)
- Protege aplicativos executados na AWS
- Detecção e mitigações automáticas e sempre ativas
- Minimiza tempo de inatividade e latência
- Shield Standard: habilitado automaticamente sem custo adicional
- Shield Advanced: serviço pago opcional para proteção adicional
    - Necessita Enterprise Support ou Business Support para contato com equipe de resposta a DDoS

**Amazon Chime:**

- Serviço de comunicação para encontrar, conversar e realizar chamadas de negócios
- Um só aplicativo para comunicação interna e externa
- Modelo de pagamento conforme o uso
- Sem taxas adiantadas, compromissos ou contratos de longo prazo

---

## Principais Lições da Seção 1

🔑 **Pontos-chave:**

- AWS e cliente compartilham responsabilidades de segurança
- **AWS é responsável** pela segurança DA nuvem (infraestrutura)
- **Cliente é responsável** pela segurança NA nuvem (dados, aplicativos, configurações)
- AWS protege: hardware, software, redes e instalações
- Para serviços IaaS: cliente executa todas as tarefas de configuração e gerenciamento de segurança
- Isso inclui: grupos de segurança, firewall, patches e atualizações de SO convidado

---

# Seção 2: AWS Identity and Access Management (IAM)

## Visão Geral do IAM

O **AWS Identity and Access Management (IAM)** permite controlar o acesso a serviços de computação, armazenamento, banco de dados e aplicativos na Nuvem AWS.

### Funções Principais

**Autenticação:**

- Lidar com a autenticação de usuários e sistemas

**Autorização:**

- Especificar e aplicar políticas de autorização
- Definir quais usuários podem acessar quais serviços

**Gerenciamento Centralizado:**

- Gerenciar de maneira centralizada o acesso à execução, configuração, gerenciamento e encerramento de recursos
- Fornece controle granular sobre o acesso a recursos
- Capacidade de especificar exatamente quais chamadas de API o usuário está autorizado a fazer

### Aplicação Universal

Todas as interações com serviços da AWS são chamadas de API:

- Console de Gerenciamento da AWS
- CLI da AWS
- SDKs da AWS

### Características Principais

✓ Gerenciar quais recursos podem ser acessados por quem  
✓ Definir como esses recursos podem ser acessados  
✓ Conceder permissões diferentes a pessoas distintas para recursos variados  
✓ **Serviço gratuito** incluído na conta da AWS

### Exemplos de Controle Granular

- Permitir a alguns usuários acesso total ao EC2, S3, DynamoDB, Redshift e outros serviços
- Conceder a outros usuários acesso somente leitura a apenas alguns buckets do S3
- Permitir que alguns usuários administrem apenas instâncias do EC2 específicas
- Permitir que alguns usuários acessem apenas informações de faturamento

---

## Componentes do IAM

### 1. Usuário do IAM

**Definição:** Pessoa ou aplicativo definido em uma conta da AWS que deve fazer chamadas de API para produtos da AWS.

**Características:**

- Deve ter um **nome exclusivo** (sem espaços) na conta da AWS
- Possui um conjunto de **credenciais de segurança** não compartilhadas
- Credenciais diferentes das do usuário raiz da conta
- Definido em uma **única conta da AWS**

---

### 2. Grupo do IAM

**Definição:** Conjunto de usuários do IAM.

**Finalidade:**

- Simplificar a especificação e o gerenciamento de permissões
- Aplicar permissões a vários usuários simultaneamente

---

### 3. Política do IAM

**Definição:** Documento que define permissões para determinar o que os usuários podem fazer na conta da AWS.

**Características:**

- Formato: **JSON (JavaScript Object Notation)**
- Concede acesso a recursos específicos
- Especifica o que o usuário pode fazer com esses recursos
- Pode negar explicitamente o acesso

---

### 4. Função do IAM

**Definição:** Ferramenta para conceder acesso temporário a recursos específicos da AWS em uma conta da AWS.

**Diferenças em relação ao usuário:**

- Não é exclusivamente associada a uma pessoa
- Destina-se a ser assumida por qualquer pessoa que precisar
- Não tem credenciais de longo prazo (senha ou chaves de acesso)
- Fornece credenciais de segurança temporárias para a sessão

---

## Autenticação no IAM

### Conceito de Autenticação

**Autenticação** é um conceito básico de segurança: um usuário ou sistema deve primeiro comprovar a identidade.

**Analogia:** Semelhante a apresentar identificação na segurança do aeroporto antes de entrar em área restrita.

### Tipos de Acesso

Ao definir um usuário do IAM, você pode atribuir dois tipos diferentes de acesso:

#### 1. Acesso Programático

**Requisitos:**

- ID de chave de acesso
- Chave de acesso secreta

**Uso:**

- CLI da AWS
- SDK da AWS
- Outras ferramentas de desenvolvimento

#### 2. Acesso ao Console de Gerenciamento da AWS

**Requisitos de Login:**

- ID da conta com 12 dígitos ou alias da conta
- Nome de usuário do IAM
- Senha do IAM
- Código de autenticação MFA (se habilitado)

### Multi-Factor Authentication (MFA)

**Recomendação:** Habilitar MFA para aumentar a segurança.

**Funcionamento:**

- Usuários e sistemas devem fornecer um token MFA
- Token necessário **além** das credenciais regulares de login

**Opções para Gerar Token MFA:**

1. **Aplicativos MFA Virtuais:**
    
    - Google Authenticator
    - Authy 2-Factor Authentication
2. **Dispositivos de Chave de Segurança U2F:**
    
    - Dispositivos físicos de segurança
3. **Dispositivos MFA de Hardware:**
    
    - Chaveiro ou cartão de exibição

---

## Autorização no IAM

### Conceito de Autorização

**Autorização** é o processo de determinar quais permissões um usuário, serviço ou aplicativo deve receber.

### Modelo de Permissões Padrão

**Padrão:** Usuários do IAM **não têm permissões** por padrão.

**Regra Fundamental:**

- Todas as ações na conta são **negadas** ao usuário por padrão (**negação implícita**)
- Permissões devem ser **explicitamente concedidas**
- Qualquer ação não permitida explicitamente é negada
- Ações negadas explicitamente serão **sempre negadas**

### Princípio do Privilégio Mínimo

**Conceito:** Conceder apenas os privilégios mínimos necessários para o usuário.

**Prática Recomendada:**

1. Determinar o que os usuários precisam fazer
2. Criar políticas que permitam apenas essas tarefas
3. Começar com conjunto mínimo de permissões
4. Conceder permissões adicionais conforme necessário

**Vantagem:** Mais seguro do que começar com permissões amplas e depois tentar restringir.

---

## Escopo Global do IAM

🌐 **Importante:** As configurações de serviço do IAM são **globais**.

- Não são definidas no nível da região da AWS
- As configurações do IAM se aplicam a **todas as regiões da AWS**

---

## Políticas do IAM em Detalhes

### Definição Formal

Uma **política do IAM** é uma declaração formal de permissões que serão concedidas a uma entidade.

### Entidades que Podem Receber Políticas

- Usuários
- Grupos
- Funções
- Recursos

**Exemplo:** Anexar política a recursos da AWS que bloqueia solicitações que não vierem de um intervalo de endereços IP aprovado.

### Funcionamento das Políticas

**Especificações:**

- Quais ações são permitidas
- Em quais recursos permitir as ações
- Qual será o efeito quando o usuário solicitar acesso

**Avaliação:**

- A ordem em que as políticas são avaliadas **não tem efeito** no resultado
- **Todas** as políticas são avaliadas
- Resultado sempre: solicitação é permitida ou negada
- Quando há conflito: a política **mais restritiva** se aplica

---

## Tipos de Políticas do IAM

### 1. Políticas Baseadas em Identidade

**Definição:** Políticas de permissões anexadas a uma entidade principal (identidade).

**Entidades:**

- Usuário do IAM
- Função do IAM
- Grupo do IAM

**Controle:**

- Quais ações a identidade pode realizar
- Em quais recursos
- Em que condições

**Subcategorias:**

**a) Políticas Gerenciadas:**

- Políticas independentes baseadas em identidade
- Podem ser anexadas a vários usuários, grupos e funções
- Reutilizáveis em toda a conta da AWS

**b) Políticas em Linha:**

- Criadas e gerenciadas diretamente
- Incorporadas em um único usuário, grupo ou função
- Específicas para uma entidade

---

### 2. Políticas Baseadas em Recursos

**Definição:** Documentos de política JSON anexados a um recurso.

**Exemplo:** Bucket do S3

**Controle:**

- Quais ações uma entidade principal pode realizar no recurso
- Em que condições

**Características:**

- Definidas somente **em linha**
- Definidas no próprio recurso
- Não são documentos de política IAM separados

**Exemplo Prático:** Para criar uma política de bucket do S3:

1. Navegar até o bucket
2. Clicar na guia **Permissions** (Permissões)
3. Clicar no botão **Bucket Policy** (Política de bucket)
4. Definir o documento de política formatado em JSON

**Outro Exemplo:** Lista de controle de acesso (ACL) do Amazon S3

---

## Estrutura de Política do IAM (JSON)

### Exemplo de Política

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "dynamodb:*",
        "s3:*"
      ],
      "Resource": [
        "arn:aws:dynamodb:region:account-id:table/table-name",
        "arn:aws:s3:::bucket-name",
        "arn:aws:s3:::bucket-name/*"
      ]
    },
    {
      "Effect": "Deny",
      "NotResource": [
        "arn:aws:dynamodb:region:account-id:table/table-name",
        "arn:aws:s3:::bucket-name",
        "arn:aws:s3:::bucket-name/*"
      ],
      "Action": [
        "dynamodb:*",
        "s3:*"
      ]
    }
  ]
}
```

### Análise do Exemplo

**Recursos Permitidos:**

- Tabela do DynamoDB específica (table-name)
- Bucket do S3 específico (bucket-name)
- Todos os objetos no bucket

**Elemento de Negação Explícita:**

- `"Effect":"Deny"` com `NotResource`
- Garante que usuários não possam usar outras ações ou recursos
- Mesmo que permissões tenham sido concedidas em outra política

**Precedência:** Uma instrução de negação explícita tem **precedência** sobre uma instrução de permissão.

---

## Comparação: Políticas Baseadas em Identidade vs. Baseadas em Recursos

### Cenário de Exemplo

**Objetivo:** Conceder ao usuário MaryMajor acesso a objetos no bucket do S3 chamado "photos"

### Método 1: Política Baseada em Identidade

- Anexar política do IAM ao usuário MaryMajor
- Política concede acesso ao bucket do S3

### Método 2: Política Baseada em Recursos

- Definir política de bucket do S3 no bucket "photos"
- Política especifica que MaryMajor tem permissão para listar e ler objetos

### Negação Explícita em Políticas de Bucket

**Importante:** Você pode definir uma instrução de **negação** em uma política de bucket para restringir acesso a usuários específicos do IAM, mesmo que tenham acesso em política separada baseada em identidade.

**Regra:** Uma instrução de negação explícita **sempre** terá precedência sobre qualquer instrução de permissão.

---

## Fluxo de Avaliação de Permissões do IAM

### Processo de Determinação

Quando o IAM determina se uma permissão é permitida:

1. **Verifica se há política de negação explícita aplicável**
    - Se sim → Acesso negado
2. **Verifica se há política de permissão explícita aplicável**
    - Se não houver → Negação implícita (padrão)
3. **Resultado:**
    - Usuário tem permissão **somente se**:
        - Ação solicitada **não** for explicitamente negada
        - **E** for explicitamente permitida

### Negação Implícita

**Definição:** Quando não há permissão explícita, o IAM **nega** o acesso por padrão.

---

## Simulador de Políticas do IAM

**Desafio:** Pode ser difícil descobrir se o acesso a um recurso será concedido quando você desenvolver políticas do IAM.

**Solução:** **Simulador de Políticas do IAM**

**Finalidade:**

- Testar políticas do IAM
- Solucionar problemas de políticas do IAM
- Validar configurações antes de implementar em produção

---

## Grupos do IAM

### Definição e Finalidade

Um **grupo do IAM** é um conjunto de usuários do IAM.

**Vantagens:**

- Maneira conveniente de especificar permissões para um conjunto de usuários
- Facilita o gerenciamento das permissões

### Exemplo Prático

**Cenário:**

1. Criar um grupo chamado **Desenvolvedores**
2. Anexar uma ou várias políticas do IAM ao grupo
3. Políticas concedem permissões que desenvolvedores geralmente precisam
4. Qualquer usuário adicionado ao grupo recebe automaticamente as permissões

**Benefícios:**

- Não é necessário anexar políticas diretamente ao usuário
- Novo usuário: simplesmente adicionar ao grupo
- Mudança de função: remover do grupo antigo, adicionar ao novo

---

### Características Importantes dos Grupos do IAM

**1. Múltiplos Usuários por Grupo:**

- Um grupo pode conter vários usuários

**2. Múltiplos Grupos por Usuário:**

- Um usuário pode pertencer a vários grupos

**3. Grupos Não Podem Ser Aninhados:**

- Um grupo pode conter apenas **usuários**, não outros grupos

**4. Não Há Grupo Padrão:**

- Não existe grupo padrão que inclua automaticamente todos os usuários
- Se desejar um grupo com todos os usuários, você deve:
    - Criar o grupo manualmente
    - Adicionar cada novo usuário a ele

---

## Funções do IAM em Detalhes

### Definição Completa

Uma **função do IAM** é uma identidade do IAM com permissões específicas.

### Semelhança com Usuário do IAM

- É uma identidade da AWS
- Pode ter políticas de permissões anexadas
- As permissões determinam o que pode e não pode fazer na AWS

### Diferenças Fundamentais em Relação ao Usuário

**1. Associação:**

- **Usuário:** Exclusivamente associado a uma pessoa
- **Função:** Destina-se a ser assumida por **qualquer pessoa** que precisar

**2. Credenciais:**

- **Usuário:** Possui credenciais de longo prazo (senha, chaves de acesso)
- **Função:** **Não** tem credenciais de longo prazo
- **Função:** Fornece credenciais de segurança **temporárias** para a sessão

---

### Casos de Uso para Funções do IAM

**1. Acesso a Recursos Não Habituais:**

- Conceder a usuários em sua conta acesso a recursos que normalmente não têm

**2. Acesso Entre Contas:**

- Conceder a usuários em uma conta da AWS acesso a recursos em **outra conta**

**3. Aplicativos Móveis:**

- Permitir que aplicativo móvel use recursos da AWS
- **Sem** incorporar chaves da AWS no aplicativo
- Vantagens:
    - Difícil alterar chaves incorporadas
    - Usuários poderiam extrair e usar chaves indevidamente

**4. Usuários com Identidades Externas:**

- Conceder acesso a usuários que já têm identidades definidas fora da AWS
- Exemplo: Diretório corporativo

**5. Acesso para Terceiros:**

- Conceder acesso à sua conta a terceiros
- Finalidade: Realizar auditoria em seus recursos

**Conclusão:** Para todos esses casos de uso, as funções do IAM são um **componente essencial** para a implantação da nuvem.

---

## Principais Lições da Seção 2

🔑 **Pontos-chave:**

- **Políticas do IAM:**
    
    - Criadas com JSON (JavaScript Object Notation)
    - Definem permissões
    - Podem ser anexadas a qualquer entidade do IAM
- **Entidades do IAM:**
    
    - Usuários do IAM
    - Grupos do IAM
    - Funções do IAM
- **Usuário do IAM:**
    
    - Fornece maneira para pessoa, aplicativo ou serviço se autenticar na AWS
- **Grupo do IAM:**
    
    - Maneira simples de anexar as mesmas políticas a vários usuários
- **Função do IAM:**
    
    - Pode ter políticas de permissões anexadas
    - Usada para delegar acesso temporário a usuários ou aplicativos

---

## Demonstração do IAM

**Disponível:** Gravação de pouco mais de quatro minutos

**Conteúdo:** Reforça conceitos discutidos nesta seção

**Recursos Configurados usando Console de Gerenciamento da AWS:**

1. Função do IAM que será usada por uma instância do EC2
2. Grupo do IAM
3. Usuário do IAM

---

# Seção 3: Proteção de uma Nova Conta da AWS

## Usuário Raiz da Conta da AWS

### Criação Inicial da Conta

Ao criar uma conta da AWS pela primeira vez:

- Você começa com uma **single identidade de login**
- Essa identidade tem **acesso completo** a todos os serviços e recursos
- Chamada de **usuário raiz da conta da AWS**

### Acesso ao Usuário Raiz

**Método de Login:**

- Console de Gerenciamento da AWS
- Endereço de e-mail usado para criar a conta
- Senha usada para criar a conta

### Características do Usuário Raiz

**Permissões:**

- Tem **e mantém** acesso total a todos os recursos na conta
- Acesso irrevogável completo

---

## Recomendação da AWS sobre Usuário Raiz

⚠️ **IMPORTANTE:** A AWS **recomenda enfaticamente** que você **não use** as credenciais de usuário raiz para interações do dia a dia com a conta.

### Abordagem Recomendada

**Em vez disso:**

1. Usar o IAM para criar usuários adicionais
2. Atribuir permissões seguindo o **princípio do privilégio mínimo**

**Exemplo:**

- Se precisar de permissões no nível de administrador:
    1. Criar um usuário do IAM
    2. Conceder a ele acesso total
    3. Usar essas credenciais para interagir com a conta

**Vantagens:**

- Se precisar revogar ou modificar permissões:
    - Excluir ou modificar políticas associadas ao usuário do IAM
    - Não afeta o usuário raiz

### Múltiplos Usuários

**Prática Recomendada:**

- Criar **credenciais exclusivas** para cada usuário
- Definir qual usuário terá acesso a quais recursos
- **Evitar** compartilhar as mesmas credenciais com vários usuários

**Exemplo:**

- Criar usuários do IAM com acesso somente leitura
- Distribuir essas credenciais para usuários que exigem apenas acesso de leitura

---

## Tarefas que Exigem Usuário Raiz

Embora o usuário raiz não deva ser usado para tarefas rotineiras, **há tarefas que só podem ser realizadas** fazendo login como usuário raiz da conta.

**Documentação:** Lista completa disponível na página "Tarefas da AWS que exigem credenciais de usuário raiz da conta da AWS"

---

## Etapas para Parar de Usar o Usuário Raiz

### Processo Passo a Passo

**1. Criar Usuário do IAM para Você Mesmo**

- Fazer login como usuário raiz da conta
- Criar usuário do IAM
- Habilitar acesso ao Console de Gerenciamento da AWS
- **Não anexar permissões ainda**
- Salvar as chaves de acesso do usuário do IAM (se necessário)

**2. Criar e Configurar Grupo do IAM**

- Criar um grupo do IAM (exemplo: nome "FullAccess")
- Anexar políticas do IAM ao grupo
- Políticas devem conceder acesso total a pelo menos alguns serviços que você usará
- Adicionar o usuário do IAM ao grupo

**3. Proteger as Chaves de Acesso do Usuário Raiz**

- Desabilitar chaves de acesso do usuário raiz (se existirem)
- Remover as chaves de acesso do usuário raiz

**4. Configurar Política de Senha**

- Habilitar uma política de senha para todos os usuários
- Copiar o link de login de usuários do IAM na página IAM Dashboard (Painel do IAM)

**5. Desconectar e Reconectar com Novo Usuário**

- Desconectar-se como usuário raiz da conta
- Navegar até o link de login de usuários do IAM copiado
- Fazer login usando as novas credenciais de usuário do IAM

**6. Armazenar Credenciais do Usuário Raiz com Segurança**

- Armazenar credenciais de usuário raiz em um **local seguro**
- Usar apenas quando absolutamente necessário

### Instruções Detalhadas

📖 Consulte: "Criação do primeiro usuário administrador e grupo de administradores do IAM" na documentação da AWS

---

## Multi-Factor Authentication (MFA)

### Recomendação de Segurança

Outra etapa **recomendada** para proteger uma nova conta da AWS é **exigir Multi-Factor Authentication (MFA)**.

### Onde Aplicar MFA

✓ Login do usuário raiz da conta  
✓ Todos os outros logins de usuário do IAM  
✓ Controle de acesso programático

**Documentação:** "Configuração do acesso à API protegido por MFA"

---

### Opções para Token de MFA

**1. Aplicativos Compatíveis com MFA Virtual:**

- Google Authenticator
- Authy Authenticator

**2. Dispositivos de Chave de Segurança U2F:**

- Dispositivos físicos de segurança

**3. Opções de MFA de Hardware:**

- Chaveiro
- Cartão de exibição

---

## AWS CloudTrail

### Definição e Finalidade

O **AWS CloudTrail** é um serviço que registra todas as solicitações de API para recursos na sua conta.

**Benefício Principal:** Permite uma **auditoria operacional** em sua conta.

### Configuração Padrão

**Por Padrão:**

- CloudTrail é **habilitado na criação de contas** em todas as contas da AWS
- Mantém registro dos **últimos 90 dias** de atividades de eventos de gerenciamento de contas

**Visualização de Atividades:**

- Você pode visualizar e fazer download dos últimos 90 dias de atividade
- Inclui operações de:
    - Criar
    - Modificar
    - Excluir
- Para serviços compatíveis com o CloudTrail
- **Sem necessidade** de criar manualmente outra trilha

---

### Habilitar Retenção Estendida

**Para habilitar:**

- Retenção de logs do CloudTrail **além dos últimos 90 dias**
- Alertas sempre que ocorrerem eventos específicos

**Solução:** Criar uma **nova trilha** (trail)

**Instruções Detalhadas:** Consulte "Criação de uma trilha" na documentação da AWS

---

## Relatórios de Faturamento

### Recomendação

Etapa adicional recomendada: **Habilitar relatórios de faturamento**

**Exemplo:** Relatório de custos e uso da AWS

### Funcionalidades

**Informações Fornecidas:**

- Uso dos recursos da AWS
- Custos estimados para esse uso

**Processo:**

- AWS fornece os relatórios para um bucket do Amazon S3 especificado por você
- Atualiza os relatórios **pelo menos uma vez por dia**

### Relatório de Custos e Uso da AWS

**Monitoramento:**

- Monitora o uso na conta da AWS
- Fornece cobranças estimadas:
    - Por hora
    - Por dia

**Documentação:** Consulte "Como criar um relatório de custos e uso da AWS"

---

## Principais Lições da Seção 3

### Práticas Recomendadas para Proteger Conta da AWS

🔐 **Recomendações Essenciais:**

1. **Proteger logins com Multi-Factor Authentication (MFA)**
    
2. **Excluir chaves de acesso do usuário raiz da conta**
    
3. **Criar usuários do IAM individuais**
    
    - Conceder permissões de acordo com o princípio do privilégio mínimo
4. **Usar grupos para atribuir permissões a usuários do IAM**
    
5. **Configurar uma política de senha forte**
    
6. **Delegar usando funções**
    
    - Em vez de compartilhar credenciais
7. **Monitorar a atividade da conta usando o AWS CloudTrail**
    

---

# Seção 4: Proteção de Contas

## AWS Organizations

### Visão Geral

O **AWS Organizations** é um serviço de gerenciamento de contas que permite:

- Consolidar **múltiplas contas da AWS**
- Criar uma organização gerenciada de modo **centralizado**

**Foco desta seção:** Recursos de segurança que o AWS Organizations oferece

---

## Recursos de Segurança do AWS Organizations

### 1. Unidades Organizacionais (OUs)

**Funcionalidade:**

- Agrupar contas em **unidades organizacionais (OUs)**
- Anexar **políticas de acesso diferentes** a cada OU

**Exemplo de Uso:**

- Contas que só devem acessar serviços que atendam a requisitos normativos específicos:
    1. Colocar essas contas em uma OU
    2. Definir política que bloqueie acesso a serviços que não atendam aos requisitos
    3. Anexar essa política à OU

---

### 2. Integração com IAM

**Expansão de Controle:**

- AWS Organizations expande o controle para o **nível da conta**
- Permite controlar o que usuários e funções de uma conta ou grupo de contas podem fazer

**Permissões Resultantes:**

- Correspondem à **interseção lógica** entre:
    - O que é permitido pelas configurações de política do AWS Organizations
    - Quais permissões são explicitamente concedidas pelo IAM na conta

**Regra:** O usuário pode acessar **apenas** o que for permitido **tanto** pelas políticas do AWS Organizations **quanto** pelas políticas do IAM.

---

### 3. Políticas de Controle de Serviço (SCPs)

**Definição:** Especificam o **número máximo de permissões** que as contas de membro na organização podem ter.

**Capacidades das SCPs:**

- Restringir quais **serviços** da AWS os usuários e funções podem acessar
- Restringir quais **recursos** os usuários e funções podem acessar
- Restringir quais **ações individuais** da AWS os usuários e funções podem acessar
- Aplicar restrições em cada conta de membro

**Poder das SCPs:**

- Essas restrições podem **sobrepor decisões de administradores** das contas de membro
- Quando o AWS Organizations bloqueia acesso:
    - Usuário ou função naquela conta **não poderá acessá-lo**
    - Mesmo que administrador de conta de membro explicitamente conceda essas permissões

---

## Políticas de Controle de Serviço (SCPs) - Detalhes

### Características Principais

**Controle Central:**

- Oferecem controle central sobre o número máximo de permissões
- Aplicam-se a todas as contas em sua organização
- Garantem que contas permaneçam de acordo com diretrizes de controle de acesso

**Requisitos:**

- Disponíveis somente em organizações que tenham **todos os recursos habilitados**
- Inclui faturamento consolidado
- **Não estarão disponíveis** se organização tiver habilitado apenas recursos de faturamento consolidado

**Habilitação:** Consulte a documentação sobre "Habilitação e desabilitação de um tipo de política em uma raiz"

---

### Semelhança com Políticas do IAM

**Formato:**

- Semelhantes às políticas de permissões do IAM
- Usam praticamente a mesma sintaxe (JSON)

**Diferença Crucial:**

- Uma SCP **nunca concede permissões**
- SCPs são políticas JSON que especificam o **número máximo** de permissões

---

### Funcionamento das SCPs

**Proteção (Guardrail):**

- Anexar SCP à raiz da organização ou a uma OU
- Define uma proteção para as ações que as contas podem realizar
- Na raiz da organização ou na OU

**Importante:**

- **Não substitui** as configurações bem gerenciadas do IAM dentro de cada conta
- Você **ainda deve anexar políticas do IAM** a usuários e funções nas contas
- Isso é necessário para **realmente conceder permissões**

---

## AWS Key Management Service (AWS KMS)

### Visão Geral

O **AWS KMS** é um serviço que permite:

- Criar e gerenciar chaves de criptografia
- Controlar o uso da criptografia
- Aplicar em:
    - Grande variedade de serviços da AWS
    - Seus aplicativos

### Características de Segurança

**Serviço Seguro e Resiliente:**

- Usa **módulos de segurança de hardware (HSMs)**
- HSMs validados — ou em processo de validação
- Conformidade com **Federal Information Processing Standards (FIPS) 140-2**
- Protege suas chaves

**Integração com CloudTrail:**

- Fornece logs que contêm toda a utilização das chaves
- Ajuda a cumprir requisitos normativos e de conformidade

---

### Chaves Mestras de Cliente (CMKs)

**Finalidade:**

- Usadas para controlar o acesso às **chaves de criptografia de dados**
- Chaves de criptografia de dados criptografam e descriptografam seus dados

**Gerenciamento:**

- Você pode criar novas chaves mestras quando desejar
- Gerenciar quem tem acesso a elas
- Definir com quais serviços elas podem ser usadas

**Importação:**

- Também é possível importar chaves de sua própria infraestrutura de gerenciamento de chaves

---

### Integração com Serviços da AWS

**Amplitude:**

- AWS KMS integra-se à **maioria dos serviços da AWS**

**Benefício:**

- Você pode usar suas chaves mestras para controlar a criptografia dos dados armazenados nesses serviços

---

## Amazon Cognito

### Visão Geral

O **Amazon Cognito** oferece soluções para **controlar o acesso** aos recursos da AWS a partir do seu aplicativo.

### Funcionalidades Principais

**Gerenciamento de Acesso:**

- Definir funções
- Mapear usuários a funções diferentes
- Aplicativo pode acessar apenas os recursos autorizados para cada usuário

**Padrões de Gerenciamento de Identidade:**

- Usa padrões comuns
- Exemplo: **Security Assertion Markup Language (SAML) 2.0**

---

### SAML 2.0

**Definição:**

- Padrão aberto para troca de informações de identidade e segurança
- Com aplicativos e provedores de serviços

**Funcionalidade:**

- Permite que usuários efetuem login usando credenciais de diretório corporativo
- Exemplo: Nome de usuário e senha do Microsoft Active Directory

**Logon Único (SSO):**

- Com SAML é possível usar SSO
- Entrar em aplicativos habilitados para SAML com um único conjunto de credenciais

---

### Conformidade e Segurança

**Requisitos Atendidos:**

- Ajuda a cumprir vários requisitos de segurança e conformidade
- Incluindo requisitos para organizações altamente regulamentadas

**Setores Suportados:**

- Empresas
- Provedores da área da saúde

**Qualificações e Conformidades:**

✓ **HIPAA** (Health Insurance Portability and Accountability Act) dos EUA  
✓ **PCI DSS** (Payment Card Industry Data Security Standard)  
✓ **SOC** (Service Organization Control) do AICPA (American Institute of CPAs)  
✓ **ISO/IEC 27001** - Segurança da informação  
✓ **ISO/IEC 27017** - Segurança da informação para serviços em nuvem  
✓ **ISO/IEC 27018** - Proteção de dados pessoais na nuvem  
✓ **ISO 9001** - Sistemas de gestão da qualidade

---

## AWS Shield

### Visão Geral

O **AWS Shield** é um serviço gerenciado de proteção contra **DDoS** (negação de serviço distribuída).

**Finalidade:**

- Protege aplicativos executados na AWS

### Características Principais

**Proteção Automática:**

- Fornece detecção e mitigações:
    - Embutidas
    - Automáticas
    - Sempre ativas
- Minimiza tempo de inatividade e latência dos aplicativos

**Facilidade:**

- **Não é necessário** interagir com o AWS Support
- Para obter benefícios básicos de proteção contra DDoS

---

### Tipos de Ataques Protegidos

**Proteção contra todos os tipos de ataques DDoS:**

1. **Ataques na Camada de Infraestrutura:**
    
    - Floods de User Datagram Protocol (UDP)
2. **Ataques de Exaustão de Estado:**
    
    - Floods de TCP SYN
3. **Ataques na Camada de Aplicativos:**
    
    - Floods HTTP GET
    - Floods HTTP POST

**Documentação:** Consulte "Guia do desenvolvedor do AWS WAF e do AWS Shield Advanced" para exemplos e detalhes de mitigação

---

### AWS Shield Standard

**Disponibilidade:**

- Habilitado automaticamente para **todos** os clientes da AWS
- **Sem custo adicional**

---

### AWS Shield Advanced

**Tipo:**

- Serviço **pago opcional**

**Proteções Adicionais:**

- Contra ataques maiores e mais sofisticados

**Aplicativos Protegidos:**

- Amazon EC2
- Elastic Load Balancing
- Amazon CloudFront
- AWS Global Accelerator
- Amazon Route 53

**Disponibilidade:**

- Disponível para todos os clientes

**Suporte:**

- Para entrar em contato com a equipe de resposta a DDoS:
    - Clientes precisam ter:
        - **Enterprise Support** do AWS Support
        - **OU** Business Support do AWS Support

---

# Seção 5: Proteção de Dados na AWS

## Criptografia de Dados

### Importância

A **criptografia de dados** é uma ferramenta essencial para proteger dados digitais.

**Funcionamento:**

- Transforma dados legíveis em um formato codificado
- Não pode ser lido por quem não tem acesso à chave secreta
- Chave secreta necessária para decodificar os dados

**Benefício:**

- Mesmo que um invasor obtenha acesso aos seus dados
- Os dados não terão utilidade sem a chave de descriptografia

---

## Dados em Repouso

### Definição

**Dados em repouso** referem-se a dados armazenados fisicamente:

- Em disco
- Em fita

### Criptografia na AWS

**Sistemas de Arquivos Criptografados:**

- Você pode criar sistemas de arquivos criptografados na AWS
- **Todos** os dados e metadados são criptografados em repouso

**Algoritmo de Criptografia:**

- **Advanced Encryption Standard (AES)-256**
- Padrão aberto

---

### Uso do AWS KMS

**Processamento Automático:**

- Quando você usa o AWS KMS:
    - Criptografia processada de maneira automática e transparente
    - Descriptografia processada de maneira automática e transparente
- **Não é preciso modificar seus aplicativos**

---

### Recomendação da AWS

**Para Organizações com Requisitos Normativos:**

- Se organização estiver sujeita a políticas corporativas ou normativas
- Que exigem criptografia de dados e metadados em repouso

**Recomendação:**

- AWS recomenda **habilitar a criptografia** em todos os serviços que armazenam seus dados

**Serviços Compatíveis:**

- Você pode criptografar dados armazenados em qualquer serviço compatível com o AWS KMS
- Consulte a documentação: "Como os serviços da AWS usam o AWS KMS"
- Para obter lista completa dos serviços compatíveis

---

## Dados em Trânsito

### Definição

**Dados em trânsito** referem-se a dados que se movem pela rede.

### Criptografia na AWS

**Protocolo:**

- **Transport Layer Security (TLS) 1.2**
- Anteriormente conhecido como **Secure Sockets Layer (SSL)**

**Criptografia:**

- **AES-256** de padrão aberto

---

## AWS Certificate Manager

### Visão Geral

O **AWS Certificate Manager** é um serviço que permite:

- Provisionar certificados SSL/TLS
- Gerenciar certificados SSL/TLS
- Implantar certificados SSL/TLS

**Uso:**

- Com serviços da AWS
- Com recursos internos conectados

---

### Finalidade dos Certificados SSL/TLS

**Proteção:**

- Protegem as comunicações de rede

**Estabelecimento de Identidade:**

- De sites na Internet
- De recursos em redes privadas

---

### Funcionalidades

**Com o AWS Certificate Manager:**

1. Solicitar um certificado
2. Implantar em recursos da AWS:
    - Load balancers
    - Distribuições do CloudFront
3. O serviço processa **renovações de certificados automaticamente**

---

### HTTP vs. HTTPS

**HTTP:**

- Tráfego web executado por HTTP **não é seguro**

**HTTPS:**

- Tráfego em HTTPS é **criptografado** com TLS/SSL
- Protege contra:
    - Espionagem
    - Ataques man-in-the-middle
- Devido à **criptografia bidirecional** da comunicação

---

## Criptografia de Dados em Trânsito - Cenários

Os serviços da AWS oferecem suporte à criptografia de dados em trânsito em muitos cenários.

### Exemplo 1: Amazon EFS

**Cenário:**

- Instância do EC2 que monta um sistema de arquivos compartilhado do Amazon EFS

**Criptografia:**

- **Todo** o tráfego de dados entre a instância e o Amazon EFS
- Criptografado com **TLS/SSL**

**Documentação:** Consulte "Criptografia de dados do EFS em trânsito" para detalhes

---

### Exemplo 2: AWS Storage Gateway

**Definição:**

- Serviço de armazenamento na nuvem híbrida
- Fornece acesso local ao armazenamento na Nuvem AWS

**Criptografia:**

- Quando Storage Gateway é conectado pela Internet ao Amazon S3
- A conexão **criptografa os dados em trânsito**

---

## Segurança do Amazon S3

### Configuração Padrão

**Por Padrão:**

- **Todos** os buckets do Amazon S3 são **privados**
- Só podem ser acessados por usuários a quem o acesso foi **explicitamente concedido**

**Essencial:**

- Gerenciar e controlar o acesso aos dados do Amazon S3

---

## Ferramentas para Controlar Acesso ao S3

A AWS oferece várias ferramentas e opções para controlar o acesso a buckets ou objetos do S3.

### 1. Amazon S3 Block Public Access

**Funcionalidade:**

- Configurações que **substituem** quaisquer outras políticas ou permissões de objeto

**Recomendação:**

- Habilitar Block Public Access para **todos** os buckets que você não deseja que sejam acessíveis publicamente

**Benefício:**

- Oferece um método simples para evitar a **exposição não intencional** de dados do Amazon S3

---

### 2. Políticas do IAM

**Uso:**

- Escrever políticas do IAM que especifiquem:
    - Usuários ou funções que podem acessar buckets e objetos específicos

---

### 3. Políticas de Bucket

**Uso:**

- Escrever políticas de bucket que definam o acesso a:
    - Buckets específicos
    - Objetos específicos

**Quando Usar:**

- Quando usuário ou sistema não pode autenticar com o IAM

**Capacidades:**

- Conceder acesso entre contas da AWS
- Conceder acesso público ou anônimo aos dados do Amazon S3

**Atenção:**

- Se usadas, devem ser escritas **cuidadosamente**
- Devem ser **testadas completamente**

---

### 4. Instrução de Negação em Política de Bucket

**Funcionalidade:**

- Especificar uma instrução de **negação** em uma política de bucket
- Para restringir o acesso

**Importante:**

- O acesso será restringido **mesmo se** os usuários tiverem permissões concedidas em:
    - Política baseada em identidade anexada aos usuários

---

### 5. Listas de Controle de Acesso (ACLs)

**Característica:**

- São anteriores ao IAM
- Opção **menos usada** atualmente

**Em Buckets e Objetos:**

- Podem ser aplicadas em buckets
- Podem ser aplicadas em objetos

**Atenção:**

- Se você usar ACLs
- **Não defina** um acesso muito aberto ou permissivo

---

### 6. AWS Trusted Advisor - Verificação de Permissões

**Recurso:**

- Verificação de permissões de bucket

**Finalidade:**

- Ferramenta útil para descobrir se algum dos buckets em sua conta tem permissões que concedem **acesso global**

---

# Seção 6: Trabalhar para Garantir a Conformidade

## Programas de Conformidade da AWS

### Certificação e Auditoria

**Processo:**

- AWS contrata **órgãos de certificação externos**
- AWS contrata **auditores independentes**

**Finalidade:**

- Fornecer aos clientes informações sobre:
    - Políticas estabelecidas e operadas pela AWS
    - Processos estabelecidos e operados pela AWS
    - Controles estabelecidos e operados pela AWS

---

### Recursos de Informação

**Listagem Completa:**

- Programas de conformidade da AWS
- Disponível na documentação

**Serviços no Escopo:**

- Para saber quais serviços da AWS estão no escopo dos programas de garantia da AWS
- Consulte: "Lista de serviços da AWS no escopo pelo programa de conformidade"

---

## Exemplo: ISO/IEC 27001:2013

### Certificação

**ISO/IEC 27001:2013:**

- Especifica os requisitos para:
    - Estabelecer Sistema de Gerenciamento de Segurança da Informação
    - Implementar Sistema de Gerenciamento de Segurança da Informação
    - Manter Sistema de Gerenciamento de Segurança da Informação
    - Melhorar continuamente Sistema de Gerenciamento de Segurança da Informação

**Base da Certificação:**

- Desenvolvimento e implementação de um **programa de segurança rigoroso**
- Define como a AWS gerencia permanentemente a segurança de modo:
    - Holístico
    - Abrangente

---

## Recursos de Segurança e Contratos Legais

A AWS oferece recursos de segurança e contratos legais criados para ajudar a oferecer suporte aos clientes com **regulamentações e leis comuns**.

### Exemplo 1: HIPAA

**HIPAA:**

- **Health Insurance Portability and Accountability Act** dos EUA
- Regulamento para proteção de informações de saúde

**Suporte da AWS:**

- Recursos e contratos específicos para conformidade com HIPAA

---

### Exemplo 2: GDPR

**GDPR:**

- **Regulamento Geral de Proteção de Dados** da União Europeia

**Objetivo:**

- Protege o direito fundamental dos titulares de dados da UE:
    - Privacidade
    - Proteção de dados pessoais

**Requisitos:**

- Introduz requisitos robustos que:
    - Elevam padrões de proteção de dados
    - Padronizam padrões de segurança
    - Elevam padrões de conformidade dos dados

**Centro do GDPR:**

- Contém muitos recursos
- Para ajudar os clientes a cumprir os requisitos de conformidade com o regulamento

---

## AWS Config

### Visão Geral

O **AWS Config** é um serviço que permite:

- Estimar configurações dos recursos da AWS
- Auditar configurações dos recursos da AWS
- Avaliar configurações dos recursos da AWS

### Funcionalidades Principais

**Monitoramento Contínuo:**

- Monitora continuamente as configurações de recursos da AWS
- Registra continuamente as configurações de recursos da AWS

**Avaliação Automatizada:**

- Permite automatizar a avaliação das configurações registradas
- Em relação às configurações desejadas

---

### Capacidades do AWS Config

**Com o AWS Config é possível:**

1. **Analisar alterações**
    
    - Nas configurações entre recursos da AWS
    - Nos relacionamentos entre recursos da AWS
2. **Revisar históricos**
    
    - Históricos detalhados de configuração de recursos
3. **Determinar conformidade**
    
    - Conformidade geral em relação às configurações especificadas nas diretrizes internas

**Benefícios:**

- Simplifica auditoria de conformidade
- Simplifica análise de segurança
- Simplifica gerenciamento de mudanças
- Simplifica solução de problemas operacionais

---

### Inventário e Conformidade

**Listagem de Inventário:**

- AWS Config mantém uma listagem de inventário de todos os recursos existentes na conta

**Verificação de Conformidade:**

- Verifica a conformidade das regras de configuração

**Recursos Não Compatíveis:**

- São sinalizados
- Alertando sobre problemas de configuração que devem ser resolvidos na conta

---

### Escopo Regional

**AWS Config é um Serviço Regional:**

- Para acompanhar recursos em todas as regiões
- Necessário habilitá-lo em todas as regiões que você usar

**Recurso Agregador:**

- AWS Config oferece um recurso agregador
- Pode mostrar uma visualização agregada dos recursos em:
    - Múltiplas regiões
    - Até mesmo múltiplas contas

---

## AWS Artifact

### Visão Geral

O **AWS Artifact** disponibiliza downloads **sob demanda** de documentos de segurança e conformidade da AWS.

### Documentos Disponíveis

**Tipos de Relatórios:**

- Relatórios de certificações **ISO** da AWS
- Relatórios de **Payment Card Industry (PCI)**
- Relatórios de **Service Organization Control (SOC)**

---

### Uso dos Documentos

**Para Auditores ou Reguladores:**

- Você pode enviar esses documentos de segurança e conformidade
- Também conhecidos como **artefatos de auditoria**

**Finalidade:**

- Demonstrar a segurança e a conformidade da:
    - Infraestrutura da AWS que você usa
    - Serviços da AWS que você usa

**Autoavaliação:**

- Usar esses documentos como diretrizes para avaliar:
    - Sua própria arquitetura de nuvem
    - A eficácia dos controles internos da sua empresa

---

### Escopo dos Documentos

**Importante:**

- AWS Artifact fornece documentos **somente sobre a AWS**

**Responsabilidade do Cliente:**

- Clientes da AWS são responsáveis por:
    - Desenvolvimento de documentos que demonstrem a segurança de suas próprias empresas
    - **OU** obtenção de documentos que demonstrem a conformidade de suas próprias empresas

---

### Contratos da AWS

**Funcionalidades:**

- Você pode usar o AWS Artifact para:
    - Analisar contratos da AWS
    - Aceitar contratos da AWS
    - Acompanhar o status de contratos da AWS

**Exemplo: BAA (Acordo de Associado Comercial):**

- Normalmente necessário para empresas sujeitas à HIPAA
- Para garantir que as informações de saúde protegidas (PHI) sejam tratadas adequadamente

**Com o AWS Artifact:**

- Aceitar contratos com a AWS
- Designar contas da AWS que podem processar legalmente informações restritas

---

### Múltiplas Contas

**Aceitar Contratos para Várias Contas:**

- É possível aceitar um contrato em nome de várias contas

**Processo:**

- Use o **AWS Organizations** para criar uma organização

---

## Principais Lições da Seção 6

🔑 **Pontos-chave:**

1. **Programas de Conformidade de Segurança da AWS:**
    
    - Fornecem informações sobre:
        - Políticas estabelecidas e operadas pela AWS
        - Processos estabelecidos e operados pela AWS
        - Controles estabelecidos e operados pela AWS
2. **AWS Config:**
    
    - Usado para avaliar configurações dos recursos da AWS
    - Usado para auditar configurações dos recursos da AWS
3. **AWS Artifact:**
    
    - Fornece acesso a relatórios de segurança e conformidade

---

# Resumo do Módulo

## O que Você Aprendeu

Neste módulo você aprendeu a:

✓ **Reconhecer o modelo de responsabilidade compartilhada**

✓ **Identificar a responsabilidade do cliente e a da AWS**

✓ **Reconhecer usuários, grupos e funções do IAM**

✓ **Descrever diferentes tipos de credenciais de segurança no IAM**

✓ **Identificar as etapas para a proteção de novas contas da AWS**

✓ **Explorar usuários e grupos do IAM**

✓ **Reconhecer como proteger dados da AWS**

✓ **Reconhecer programas de conformidade da AWS**

---

## Recursos Adicionais

Para obter mais detalhes, consulte os recursos adicionais e a documentação da AWS:

📚 **Links Importantes:**

- **Página inicial de segurança da Nuvem AWS:**  
    [https://aws.amazon.com/security/](https://aws.amazon.com/security/)
    
- **Recursos de segurança da AWS**
    
- **Blog de segurança da AWS**
    
- **Boletins de segurança**
    
- **Diretrizes sobre teste de vulnerabilidade e penetração**
    
- **AWS Well-Architected Framework – Pilar da segurança (AWS Security Pillar)**
    
- **Práticas recomendadas do IAM na documentação da AWS:**  
    [https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
    

---

## Fim do Módulo 4

Este material é parte do **AWS Academy Cloud Foundations (PT)**  
**Versão 2.0.16**  
**Código: 100-ACCLFO-20-PT-SG**