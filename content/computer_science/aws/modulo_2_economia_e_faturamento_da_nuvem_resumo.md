
> 📘 Este é um resumo do [[modulo_2_economia_e_faturamento_da_nuvem]]. Para detalhes completos, consulte o arquivo principal.

---

## 🎯 Objetivos do Módulo

Ao concluir este módulo, você será capaz de:

- Explicar a **filosofia de preço da AWS**
- Calcular o **custo total de propriedade (TCO)**
- Usar **AWS Organizations** para gerenciar múltiplas contas
- Gerenciar faturamento com **AWS Billing and Cost Management**
- Identificar planos de **suporte técnico**

📖 *Detalhes completos em* [[modulo_2_economia_e_faturamento_da_nuvem#Objetivos de Aprendizagem]]

---

## 💰 Seção 1: Fundamentos da Definição de Preço

### Três Fatores Fundamentais de Custo

1. **Computação**
2. **Armazenamento**
3. **Transferência de dados de saída**

> 💡 Transferência de dados de **entrada** é gratuita na maioria dos casos.

📖 *Veja detalhes em* [[modulo_2_economia_e_faturamento_da_nuvem#Três Fatores Fundamentais de Custo]]

---

### Filosofia de Preço AWS

**Princípio Central**: "Pague apenas pelo que usar"

**Características**:
- ✅ Sem contratos de longo prazo
- ✅ Início/parada a qualquer momento
- ✅ Pagamento mensal pelo consumo

📖 *Mais informações em* [[modulo_2_economia_e_faturamento_da_nuvem#Filosofia de Preço da AWS]]

---

### Quatro Modelos de Preço

| Modelo | Descrição | Economia |
|--------|-----------|----------|
| **Pagamento Conforme Uso** | Pague apenas o que consumir | Sem despesas iniciais |
| **Reserva** | Compromisso de longo prazo | Até 75% de desconto |
| **Volume** | Quanto mais usa, menos paga | Descontos por volume |
| **Crescimento AWS** | Benefícios do crescimento global | 75 reduções de preço desde 2006 |

📖 *Detalhes de cada modelo em* [[modulo_2_economia_e_faturamento_da_nuvem#Modelos de Preço da AWS]]

---

### Instâncias Reservadas (3 tipos)

1. **AURI** - Pagamento total antecipado → Maior desconto
2. **PURI** - Pagamento parcial antecipado → Desconto médio
3. **NURI** - Sem pagamento antecipado → Menor desconto

📖 *Comparação completa em* [[modulo_2_economia_e_faturamento_da_nuvem#Instâncias Reservadas]]

---

### 🎁 Nível Gratuito da AWS

**Duração**: 1 ano para novos clientes

**Principais serviços incluídos**:
- Amazon EC2 (microinstância T2)
- Amazon S3
- Amazon EBS
- Elastic Load Balancing
- Transferência de dados

📖 *Lista completa em* [[modulo_2_economia_e_faturamento_da_nuvem#Nível Gratuito da AWS]]

---

### 🆓 Serviços Sempre Gratuitos

- **Amazon VPC** - Rede virtual isolada
- **AWS IAM** - Gerenciamento de acesso
- **Cobrança Consolidada** - Faturamento unificado
- **Elastic Beanstalk** - Implantação de apps
- **CloudFormation** - Infraestrutura como código
- **Auto Scaling** - Dimensionamento automático
- **OpsWorks** - Gerenciamento de aplicativos

> ⚠️ Os serviços são gratuitos, mas recursos provisionados podem gerar custos.

📖 *Detalhes e exceções em* [[modulo_2_economia_e_faturamento_da_nuvem#Serviços Sem Custo Adicional]]

---

## 📊 Seção 2: Custo Total de Propriedade (TCO)

### On-Premises vs Nuvem

| Aspecto | On-Premises | Nuvem AWS |
|---------|-------------|-----------|
| **Custos** | Fixos (CapEx) | Variáveis (OpEx) |
| **Escalabilidade** | Lenta e cara | Rápida e simples |
| **Redução** | Não reduz custos | Reduz custos imediatamente |
| **Gestão** | Equipe própria | Provedor gerencia |

📖 *Comparação detalhada em* [[modulo_2_economia_e_faturamento_da_nuvem#On-Premises vs Nuvem]]

---

### O Que é TCO?

**Definição**: Estimativa financeira dos custos diretos e indiretos de um produto/sistema.

**Inclui**:
- Custo do serviço
- Custos de propriedade (instalações, energia, equipe)
- Custos operacionais contínuos

📖 *Componentes completos em* [[modulo_2_economia_e_faturamento_da_nuvem#Custo Total de Propriedade]]

---

### Custos do Data Center

**Quatro categorias principais**:

1. 🖥️ **Servidor** - Hardware, software, instalações
2. 💾 **Armazenamento** - Hardware, administração, instalações
3. 🌐 **Rede** - Hardware, administração, instalações
4. 👥 **Mão de Obra TI** - Administração da solução

📖 *Custos detalhados em* [[modulo_2_economia_e_faturamento_da_nuvem#Custos do Data Center]]

---

### Exemplo: Economia de 96% em 3 Anos

**Cenário**: VM com 4 CPUs, 16 GB RAM

| Opção | Custo (3 anos) |
|-------|----------------|
| **On-Premises** | US$ 167.422 |
| **AWS** (instância reservada) | US$ 7.509 |
| **Economia** | US$ 159.913 (96%) |

**Por quê?** AWS cobra apenas quando recursos estão em uso.

📖 *Análise completa em* [[modulo_2_economia_e_faturamento_da_nuvem#Exemplo de Comparação de Custos]]

---

### 🧮 Calculadora de Preços da AWS

**Funcionalidades**:
- Estimar custos mensais
- Identificar oportunidades de economia
- Modelar soluções antes de criar
- Explorar preços e configurações
- Organizar por grupos (departamento, projeto, etc.)

🔗 **Acesse**: [calculator.aws](https://calculator.aws/#/)

📖 *Guia de uso em* [[modulo_2_economia_e_faturamento_da_nuvem#Calculadora de Preços da AWS]]

---

### Benefícios: Rígidos vs Flexíveis

**Rígidos** (quantificáveis):
- ✅ Redução de custos de computação/armazenamento
- ✅ Redução de compras de hardware
- ✅ Redução de equipe operacional

**Flexíveis** (difíceis de quantificar, mas valiosos):
- ✨ Reutilização de serviços
- ✨ Aumento de produtividade
- ✨ Foco em inovação

📖 *Análise ROI completa em* [[modulo_2_economia_e_faturamento_da_nuvem#Análise de ROI]]

---

## 🏢 Seção 3: AWS Organizations

### O Que É?

Serviço de **gerenciamento centralizado** de múltiplas contas AWS.

**Principais recursos**:
- Cobrança consolidada
- Controle centralizado de políticas
- Automação de criação de contas
- Descontos por volume agregado

📖 *Detalhes completos em* [[modulo_2_economia_e_faturamento_da_nuvem#AWS Organizations]]

---

### 4 Principais Benefícios

1. 📋 **Políticas Centralizadas** - Controle de acesso em todas as contas
2. 🔒 **Controle de Serviços** - SCPs para limitar serviços
3. 🤖 **Automação** - Criação de contas via API
4. 💰 **Faturamento Único** - Uma fatura para todas as contas

📖 *Exemplos de uso em* [[modulo_2_economia_e_faturamento_da_nuvem#Principais Benefícios]]

---

### SCPs vs Políticas IAM

| Aspecto | AWS IAM | AWS Organizations (SCP) |
|---------|---------|-------------------------|
| **Escopo** | Usuários/grupos/funções | Contas inteiras |
| **Afeta raiz?** | ❌ Não | ✅ Sim |
| **Aplicação** | Dentro da conta | Entre contas |
| **Uso** | Controle granular | Controle organizacional |

> ⚠️ **Organizations NÃO substitui IAM** - use ambos juntos!

📖 *Diferenças detalhadas em* [[modulo_2_economia_e_faturamento_da_nuvem#AWS Organizations vs AWS IAM]]

---

### Configuração em 4 Etapas

1. **Criar organização** - Definir conta primária
2. **Criar UOs** - Organizar contas em unidades
3. **Criar SCPs** - Definir políticas de controle
4. **Testar políticas** - Validar com simulador

📖 *Passo a passo completo em* [[modulo_2_economia_e_faturamento_da_nuvem#Configurando o AWS Organizations]]

---

## 💳 Seção 4: AWS Billing and Cost Management

### O Que É?

Serviço para **gerenciar faturamento e custos** da AWS.

**Permite**:
- Pagar faturas
- Monitorar uso
- Controlar custos
- Prever gastos futuros

📖 *Funcionalidades completas em* [[modulo_2_economia_e_faturamento_da_nuvem#AWS Billing and Cost Management]]

---

### Principais Ferramentas

| Ferramenta | Função |
|------------|--------|
| **AWS Bills** | Visualizar faturas detalhadas |
| **Cost Explorer** | Analisar e visualizar custos |
| **AWS Budgets** | Definir orçamentos e alertas |
| **Relatórios de Uso** | Dados detalhados de consumo |

📖 *Guia de cada ferramenta em* [[modulo_2_economia_e_faturamento_da_nuvem#Ferramentas no Painel de Faturamento]]

---

### Recursos de Análise

**Personalização**:
- 📅 Período customizado (mensal/diário)
- 🔍 Filtros por dimensões
- 📊 Agrupamento de dados
- 📈 Identificação de tendências

**Objetivo**: Encontrar oportunidades de otimização

📖 *Análise avançada em* [[modulo_2_economia_e_faturamento_da_nuvem#Funcionalidades Principais]]

---

## 📚 Recursos Importantes

### Links Essenciais

- 🔗 [Preços AWS](https://aws.amazon.com/pricing/)
- 🔗 [Nível Gratuito](https://aws.amazon.com/free/)
- 🔗 [Calculadora de Preços](https://calculator.aws/#/)
- 🔗 [Documentação Completa](https://docs.aws.amazon.com/)

📖 *Todos os recursos em* [[modulo_2_economia_e_faturamento_da_nuvem#Recursos Adicionais]]
