# AWS Cloud Foundations - Módulo 1: Resumo Executivo

> 📖 **Para detalhes completos, consulte:** [[modulo_1_visao_geral_dos_conceitos_de_nuvem]]

---

## 🎯 Objetivos do Módulo

Após este módulo, você será capaz de:

- Definir tipos de computação em nuvem
- Descrever as 6 vantagens da nuvem
- Reconhecer categorias e serviços principais da AWS
- Analisar o AWS CAF

---

## 📖 1. Introdução à Computação em Nuvem

### Definição Essencial

> **Computação em nuvem** = Entrega sob demanda de recursos de TI pela Internet com **pagamento conforme o uso**

### Mudança de Paradigma

- **Antes:** Infraestrutura como hardware (física, cara, inflexível)
- **Agora:** Infraestrutura como software (flexível, sob demanda, escalável)

📚 _Detalhes completos em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Seção 1]]_

---

### Três Modelos de Serviço

|Modelo|Descrição|Controle|
|---|---|---|
|**IaaS**|Infraestrutura como Serviço|⬆️ Alto|
|**PaaS**|Plataforma como Serviço|⬆️ Médio|
|**SaaS**|Software como Serviço|⬇️ Baixo|

📚 _Comparação detalhada em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Modelos de Serviços]]_

---

### Três Modelos de Implantação

1. **Nuvem** - Totalmente na nuvem
2. **Híbrida** - Nuvem + infraestrutura local
3. **No local** - Nuvem privada (virtualização local)

📚 _Casos de uso em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Modelos de Implantação]]_

---

## 💡 2. Seis Vantagens da Computação em Nuvem

1. ✅ **CAPEX → OPEX**: Troque despesas de capital por variáveis
2. ✅ **Economia de escala**: Custos menores por agregação
3. ✅ **Capacidade elástica**: Pare de adivinhar necessidades
4. ✅ **Velocidade e agilidade**: Recursos em minutos (não semanas)
5. ✅ **Foco no negócio**: Pare de gastar com datacenters
6. ✅ **Alcance global**: Implante em minutos no mundo todo

📚 _Explicação detalhada de cada vantagem em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Seção 2]]_

---

## 🌐 3. Introdução à AWS

### O que é AWS?

Plataforma de nuvem segura com amplo conjunto de serviços globais baseados na nuvem.

### Principais Categorias de Serviços

- ⚙️ **Computação** (EC2, Lambda, ECS, EKS, Fargate)
- 💾 **Armazenamento** (S3, EBS, EFS)
- 🗄️ **Banco de dados** (RDS, DynamoDB)
- 🌐 **Redes** (VPC, Route 53, CloudFront)
- 🔒 **Segurança** (IAM, KMS)
- 📊 **Gerenciamento** (CloudWatch, CloudTrail)

📚 _Lista completa de serviços em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Principais Serviços AWS]]_

---

### Três Formas de Acesso

1. **Console de Gerenciamento** - Interface gráfica
2. **AWS CLI** - Linha de comando
3. **SDKs** - Integração com código

📚 _Detalhes de cada método em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Três Maneiras de Acessar]]_

---

## 🚀 4. AWS Cloud Adoption Framework (CAF)

### O que é?

Framework para ajudar organizações a planejar e acelerar a adoção bem-sucedida da nuvem.

### Seis Perspectivas

#### **Foco em Negócios:**

1. 🏢 **Empresarial** - Caso de negócios, ROI, priorização
2. 👥 **Pessoas** - Habilidades, treinamento, organização
3. 📋 **Governança** - Alinhamento estratégico, riscos

#### **Foco Técnico:**

4. 🏗️ **Plataforma** - Arquitetura, implantação, migração
5. 🔒 **Segurança** - Visibilidade, auditoria, controle
6. ⚙️ **Operações** - Atividades diárias, procedimentos

📚 _Detalhamento de cada perspectiva em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Seção 4]]_

---

### Alinhamento Necessário

```
Pessoas + Processos + Tecnologia = Adoção Bem-sucedida
```

📚 _Mais sobre alinhamento organizacional em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Por que o AWS CAF]]_

---

## ❓ Questão-Chave do Módulo

**Por que AWS é mais econômica para workloads variáveis?**

✅ **Resposta:** Instâncias EC2 podem ser executadas **sob demanda** quando necessário

**Palavras-chave:** Pagamento conforme o uso, elasticidade, sem recursos ociosos

📚 _Análise completa da questão em [[modulo_1_visao_geral_dos_conceitos_de_nuvem#Questão de Avaliação]]_

---

## 📚 Links Rápidos para Aprofundamento

|Tópico|Link no Documento Completo|
|---|---|
|Modelos de serviço (IaaS/PaaS/SaaS)|[[modulo_1_visao_geral_dos_conceitos_de_nuvem#Modelos de Serviços em Nuvem]]|
|Seis vantagens da nuvem|[[modulo_1_visao_geral_dos_conceitos_de_nuvem#Seção 2]]|
|Principais serviços AWS|[[modulo_1_visao_geral_dos_conceitos_de_nuvem#Principais Serviços AWS Abordados]]|
|Perspectivas do AWS CAF|[[modulo_1_visao_geral_dos_conceitos_de_nuvem#Divisão das Perspectivas]]|
|Recursos adicionais|[[modulo_1_visao_geral_dos_conceitos_de_nuvem#Recursos Adicionais]]|

---

## 🎓 Checklist de Aprendizagem

- [ ] Entendo a diferença entre IaaS, PaaS e SaaS
- [ ] Consigo explicar as 6 vantagens da nuvem
- [ ] Conheço os principais serviços AWS de cada categoria
- [ ] Compreendo as 6 perspectivas do AWS CAF
- [ ] Sei quando usar cada modelo de implantação (nuvem/híbrida/local)

---

**Versão:** 2.0.14 | **Curso:** AWS Academy Cloud Foundations (PT)