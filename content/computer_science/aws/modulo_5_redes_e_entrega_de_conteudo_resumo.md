# Resumo: AWS Módulo 5 - Redes e Entrega de Conteúdo

Este documento apresenta um resumo executivo do **Módulo 5 de AWS Academy Cloud Foundations**, focando nos pontos principais de cada seção. Para detalhes completos, consulte [[modulo_5_redes_e_entrega_de_conteudo]].

---

## 📌 Visão Geral

O módulo cobre três serviços fundamentais da AWS para redes e entrega de conteúdo: **Amazon VPC**, **Amazon Route 53** e **Amazon CloudFront**. O conteúdo está estruturado em seis seções principais que abordam desde conceitos básicos de redes até serviços avançados de CDN.

**Para mais detalhes sobre objetivos de aprendizagem e atividades práticas:** [[modulo_5_redes_e_entrega_de_conteudo#Visão Geral do Módulo]]

---

## 🌐 Seção 1: Noções Básicas de Redes

### Conceitos Fundamentais

**Endereçamento IP:** As redes utilizam endereços IP para identificar máquinas. IPv4 usa 32 bits (exemplo: `192.0.2.0`), enquanto IPv6 usa 128 bits para acomodar mais dispositivos.

**CIDR (Classless Inter-Domain Routing):** Método para descrever redes usando o formato `IP/bits-fixos`. Por exemplo, `192.0.2.0/24` fornece 256 endereços IP, enquanto `192.0.2.0/16` fornece 65.536 endereços.

**Modelo OSI:** Modelo conceitual de sete camadas que explica como os dados viajam em uma rede. Hubs e switches operam na camada 2, enquanto roteadores operam na camada 3.

**Para informações completas sobre endereçamento e modelo OSI:** [[modulo_5_redes_e_entrega_de_conteudo#Seção 1 Noções Básicas de Redes]]

---

## ☁️ Seção 2: Amazon VPC

### O Serviço Amazon VPC

O **Amazon Virtual Private Cloud (VPC)** permite provisionar uma seção logicamente isolada da nuvem AWS onde você executa seus recursos com controle total sobre configuração de rede.

### Componentes Essenciais

**VPCs:** Redes virtuais isoladas que pertencem a uma única região AWS e podem abranger múltiplas zonas de disponibilidade.

**Sub-redes:** Intervalos de endereços IP dentro de uma VPC que pertencem a uma única zona de disponibilidade. Podem ser classificadas como públicas (com acesso direto à Internet) ou privadas (sem acesso direto).

**Blocos CIDR:** Ao criar uma VPC, você atribui um bloco CIDR IPv4 que não pode ser alterado posteriormente. O tamanho varia de /16 (65.536 endereços) a /28 (16 endereços).

**Endereços IP Reservados:** A AWS reserva cinco endereços IP em cada sub-rede para uso do sistema (rede, roteador, DNS, uso futuro e transmissão).

### Tipos de Endereços IP

**IP Privado:** Atribuído automaticamente a cada instância.

**IP Público:** Pode ser solicitado ao criar a instância.

**IP Elástico:** Endereço IPv4 público e estático que pode ser remapeado rapidamente entre instâncias para mascarar falhas.

**Interface de Rede Elástica (ENI):** Interface virtual que pode ser anexada/removida de instâncias, permitindo redirecionar tráfego de rede.

### Tabelas de Rotas

Contêm regras que direcionam o tráfego de rede de sub-redes. Cada tabela possui uma rota local padrão para comunicação interna da VPC que não pode ser excluída.

**Para detalhes completos sobre componentes VPC e configurações:** [[modulo_5_redes_e_entrega_de_conteudo#Seção 2 Amazon VPC]]

---

## 🔗 Seção 3: Redes VPC

### Opções de Conectividade

**Gateway da Internet:** Componente escalável e altamente disponível que permite comunicação entre instâncias na VPC e a Internet. Necessário para tornar sub-redes públicas.

**Gateway NAT:** Permite que instâncias em sub-redes privadas se conectem à Internet para atualizações, mas impede que a Internet inicie conexões com essas instâncias. É um serviço gerenciado preferível a instâncias NAT.

**Compartilhamento de VPC:** Permite compartilhar sub-redes com outras contas AWS na mesma organização, facilitando a gestão centralizada e reduzindo custos operacionais.

**Emparelhamento de VPC:** Conexão de rede entre duas VPCs que permite roteamento privado de tráfego. Não suporta emparelhamento transitivo e os intervalos de IP não podem se sobrepor.

**AWS Site-to-Site VPN:** Conecta sua VPC a redes remotas (data centers corporativos) criando uma rede privada virtual através da Internet.

**AWS Direct Connect:** Estabelece conexão de rede dedicada e privada entre sua rede e um local AWS, oferecendo melhor desempenho, maior largura de banda e experiência mais consistente que conexões via Internet.

**VPC Endpoint:** Permite conectar privadamente sua VPC a serviços AWS compatíveis sem necessidade de gateway da Internet, NAT, VPN ou Direct Connect. Existem dois tipos: endpoints de interface (cobrados) e endpoints de gateway (sem custo adicional).

**AWS Transit Gateway:** Solução hub-and-spoke que simplifica a conectividade entre centenas de VPCs, eliminando a necessidade de conexões ponto-a-ponto individuais.

**Para informações detalhadas sobre cada opção de conectividade:** [[modulo_5_redes_e_entrega_de_conteudo#Seção 3 Redes VPC]]

---

## 🔒 Seção 4: Segurança da VPC

### Camadas de Firewall

**Grupos de Segurança:**

- Operam no **nível da instância**
- São **stateful** (mantêm informações de estado)
- Permitem apenas **regras de permissão** (não de negação)
- Todas as regras são avaliadas antes de permitir tráfego
- Por padrão, não possuem regras de entrada e permitem todo tráfego de saída

**ACLs de Rede (Network ACLs):**

- Operam no **nível da sub-rede**
- São **stateless** (não mantêm informações de estado)
- Suportam **regras de permissão e negação**
- Regras são avaliadas em **ordem numérica**
- Por padrão, a ACL padrão permite todo tráfego; ACLs personalizadas negam todo tráfego até que regras sejam adicionadas

### Comparação Rápida

|Aspecto|Grupos de Segurança|ACLs de Rede|
|---|---|---|
|Escopo|Instância|Sub-rede|
|Estado|Stateful|Stateless|
|Regras|Apenas permissão|Permissão e negação|
|Avaliação|Todas as regras|Ordem numérica|

**Para detalhes completos sobre segurança e exercício prático:** [[modulo_5_redes_e_entrega_de_conteudo#Seção 4 Segurança da VPC]]

---

## 🌍 Seção 5: Amazon Route 53

### Serviço DNS na Nuvem

O **Amazon Route 53** é um serviço web de DNS altamente disponível e escalável que converte nomes de domínio (como `www.example.com`) em endereços IP (como `192.0.2.1`).

### Recursos Principais

**Registro de Domínio:** Permite comprar e gerenciar nomes de domínio com configuração automática de DNS.

**Verificações de Integridade:** Monitora a saúde de recursos e roteia tráfego apenas para endpoints íntegros.

**Fluxo de Tráfego:** Gerencia tráfego globalmente com editor visual simples, combinando múltiplos tipos de roteamento.

### Políticas de Roteamento

**Roteamento Simples:** Para um único recurso executando uma função.

**Roteamento Ponderado:** Distribui tráfego entre múltiplos recursos em proporções especificadas (pesos de 0 a 255).

**Roteamento de Latência (LBR):** Direciona usuários para a região AWS com melhor latência.

**Roteamento de Localização Geográfica:** Roteia tráfego baseado na localização geográfica dos usuários, útil para conteúdo localizado e restrições de distribuição.

**Roteamento de Geoproximidade:** Roteia baseado na localização de recursos com opção de redirecionamento.

**Roteamento de Failover:** Configura failover ativo-passivo, redirecionando para sites de backup quando o primário falha.

**Roteamento de Valores Múltiplos:** Retorna até oito registros íntegros selecionados aleatoriamente, melhorando disponibilidade.

### Alta Disponibilidade

Route 53 permite criar arquiteturas multirregião altamente disponíveis com failover automático. Por exemplo, configurar um registro primário apontando para um load balancer e um registro secundário apontando para um site estático no S3.

**Para detalhes sobre cada tipo de roteamento e casos de uso:** [[modulo_5_redes_e_entrega_de_conteudo#Seção 5 Amazon Route 53]]

---

## 🚀 Seção 6: Amazon CloudFront

### CDN Global da AWS

O **Amazon CloudFront** é um serviço de rede de entrega de conteúdo (CDN) que acelera a distribuição de dados, vídeos, aplicativos e APIs globalmente com baixa latência e altas velocidades de transferência.

### Como Funciona

**Locais de Borda:** Data centers distribuídos globalmente que armazenam em cache conteúdo popular e entregam com a menor latência possível.

**Caches Regionais:** Caches intermediários maiores entre a origem e os locais de borda, mantendo conteúdo menos popular por mais tempo próximo aos usuários.

**Conteúdo Estático e Dinâmico:** CloudFront armazena em cache conteúdo estático (HTML, CSS, JS, imagens) e também acelera a entrega de conteúdo dinâmico através de conexões otimizadas.

### Benefícios Principais

**Rápido e Global:** Rede massiva de locais de borda e caches regionais para entrega com baixa latência.

**Segurança na Borda:** Proteção integrada com AWS Shield Standard sem custo adicional, além de suporte a certificados SSL personalizados via AWS Certificate Manager.

**Altamente Programável:** Integração com Lambda@Edge para executar código personalizado nos locais de borda, personalizando a experiência do usuário.

**Integrado à AWS:** Conexão direta com infraestrutura AWS e outros serviços como S3, EC2 e Elastic Load Balancing.

**Econômico:** Modelo de pagamento conforme o uso sem compromissos mínimos, eliminando necessidade de provisionar capacidade extra.

### Modelo de Preços

Cobranças baseadas em quatro áreas: transferência de dados para fora, solicitações HTTP(S), solicitações de invalidação (1.000 caminhos/mês gratuitos), e SSL personalizado com IP dedicado (USD 600/mês).

**Para informações completas sobre arquitetura e preços:** [[modulo_5_redes_e_entrega_de_conteudo#Seção 6 Amazon CloudFront]]

---

## 📚 Recursos para Estudo Adicional

Todos os links e documentações oficiais da AWS estão disponíveis na seção de recursos adicionais do documento completo: [[modulo_5_redes_e_entrega_de_conteudo#Recursos Adicionais]]

---

## ✅ Checklist de Aprendizagem

Após estudar este módulo, você deve ser capaz de:

- [ ] Reconhecer conceitos básicos de redes (IP, CIDR, modelo OSI)
- [ ] Descrever componentes da Amazon VPC (VPCs, sub-redes, tabelas de rotas)
- [ ] Identificar opções de conectividade VPC (gateways, peering, VPN, Direct Connect)
- [ ] Diferenciar grupos de segurança de ACLs de rede
- [ ] Projetar arquiteturas básicas de VPC com alta disponibilidade
- [ ] Explicar políticas de roteamento do Route 53
- [ ] Reconhecer benefícios do Amazon CloudFront para entrega de conteúdo

---

_Para conteúdo completo e detalhado, sempre consulte: [[modulo_5_redes_e_entrega_de_conteudo]]_