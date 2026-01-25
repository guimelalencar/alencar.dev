# AWS Academy Cloud Foundations - Módulo 5: Redes e Entrega de Conteúdo

**Curso:** AWS Academy Cloud Foundations (PT)  
**Versão:** 2.0.19  
**Código:** 100-ACCLFO-20-PT-SG

---

## Visão Geral do Módulo

Este módulo abrange três serviços fundamentais da Amazon Web Services (AWS) para entrega de conteúdo e redes: **Amazon Virtual Private Cloud (Amazon VPC)**, **Amazon Route 53** e **Amazon CloudFront**.

### Tópicos Abordados

O módulo cobre os seguintes tópicos essenciais:

- Noções básicas de redes
- Amazon Virtual Private Cloud (Amazon VPC)
- Redes da VPC
- Segurança da VPC
- Amazon Route 53
- Amazon CloudFront

### Atividades Práticas

O módulo inclui diversas atividades práticas:

- Rotular um diagrama de rede
- Projetar uma arquitetura básica de VPC
- Demonstração gravada sobre o assistente de VPC para criar VPC com sub-redes públicas e privadas
- Laboratório prático: criar uma VPC e iniciar um servidor web
- Teste de conhecimento para avaliar a compreensão dos conceitos

### Objetivos de Aprendizagem

Após concluir este módulo, você será capaz de:

- Reconhecer conceitos básicos de redes
- Descrever redes virtuais na nuvem com a Amazon VPC
- Rotular um diagrama de rede
- Projetar uma arquitetura básica de VPC
- Indicar as etapas para criar uma VPC
- Identificar grupos de segurança
- Criar sua própria VPC e incluir outros componentes para produzir uma rede personalizada
- Identificar os fundamentos do Amazon Route 53
- Reconhecer os benefícios do Amazon CloudFront

---

## Seção 1: Noções Básicas de Redes

Esta seção analisa conceitos básicos de redes que fornecem a base necessária para compreender o serviço de rede da AWS, Amazon Virtual Private Cloud (Amazon VPC).

### Conceitos Fundamentais de Rede

#### O que é uma Rede de Computadores

Uma **rede de computadores** consiste em duas ou mais máquinas cliente conectadas para compartilhar recursos. Uma rede pode ser particionada logicamente em **sub-redes**. A rede requer um dispositivo de rede, como um **roteador** ou **switch**, para conectar todos os clientes e permitir a comunicação entre eles.

#### Endereços IP

Cada máquina cliente em uma rede possui um **endereço IP (Internet Protocol)** exclusivo que a identifica. Um endereço IP é um rótulo numérico em formato decimal, que é convertido internamente em binário.

##### IPv4

**Exemplo:** `192.0.2.0`

- Possui quatro números separados por pontos (`.`)
- Cada número representa **8 bits** no formato binário
- Total de **32 bits**
- Este é um endereço **IPv4**

##### IPv6

Endereços **IPv6**, com **128 bits**, também estão disponíveis, permitindo acomodar mais dispositivos.

**Exemplo:** `2600:1f18:22ba:8c00:ba86:a05e:a5ba:00FF`

- Composto de **oito grupos** de quatro caracteres hexadecimais
- Separados por dois pontos (`:`)
- Cada grupo representa **16 bits**
- Total de **128 bits**

### Classless Inter-Domain Routing (CIDR)

Um método comum para descrever redes é o **CIDR (Roteamento sem classe entre domínios)**.

#### Formato CIDR

O endereço CIDR é expresso como:

```
[Endereço IP]/[número de bits fixos]
```

Os bits restantes são **flexíveis**.

#### Exemplos de CIDR

**Exemplo 1:** `192.0.2.0/24`

- Os primeiros **24 bits** são fixos
- Os últimos **8 bits** podem variar
- Fornece **256 endereços IP** disponíveis
- Intervalo: `192.0.2.0` a `192.0.2.255`

**Exemplo 2:** `192.0.2.0/16`

- Fixa os primeiros **16 bits**
- Permite **65.536 endereços IP**
- Intervalo: `192.0.0.0` a `192.0.255.255`

#### Casos Especiais de CIDR

**Endereço IP Fixo:** `192.0.2.0/32`

- Cada bit é fixo
- Representa um **único endereço**
- Útil para regras de firewall

**Internet Completa:** `0.0.0.0/0`

- Todos os bits são flexíveis
- Representa toda a Internet

### Modelo OSI (Open Systems Interconnection)

O **modelo OSI** é um modelo conceitual para explicar como os dados viajam em uma rede.

#### Características do Modelo OSI

- Consiste em **sete camadas**
- Mostra protocolos e endereços usados para enviar dados em cada camada
- **Hubs e switches** operam na **camada 2** (link de dados)
- **Roteadores** operam na **camada 3** (rede)
- Auxilia na compreensão da comunicação em uma VPC

### ICA (Independent Computing Architecture)

O **ICA** é uma arquitetura de computação independente:

- Desenvolvida pela **Citrix Systems**
- Projetada para otimizar a transferência de dados entre servidor e cliente

---

## Seção 2: Amazon VPC

Muitos dos conceitos de uma rede on-premises se aplicam a uma rede baseada na nuvem, mas boa parte da complexidade da configuração de uma rede foi abstraída sem sacrificar o controle, a segurança e a usabilidade.

### O que é Amazon VPC

O **Amazon Virtual Private Cloud (Amazon VPC)** é um serviço que permite provisionar uma seção logicamente isolada da Nuvem AWS (chamada de **nuvem privada virtual** ou **VPC**) onde você pode executar seus recursos da AWS.

#### Recursos e Controle

A Amazon VPC oferece controle sobre seus recursos de rede virtual, incluindo:

- Seleção do seu próprio **intervalo de endereços IP**
- Criação de **sub-redes**
- Configuração de **tabelas de rotas** e **gateways de rede**
- Uso de **IPv4** e **IPv6** na VPC para acesso seguro a recursos e aplicativos

#### Personalização de Rede

Você pode personalizar a configuração de rede da VPC de várias formas:

**Exemplo de arquitetura:**

- Criar uma **sub-rede pública** para seus servidores web que podem acessar a Internet pública
- Colocar sistemas de back-end (bancos de dados ou servidores de aplicativos) em **sub-redes privadas** sem acesso público à Internet
- Usar várias camadas de segurança, incluindo **grupos de segurança** e **listas de controle de acesso à rede (ACLs de rede)** para controlar o acesso às instâncias do Amazon EC2 em cada sub-rede

### Componentes Fundamentais da VPC

#### VPCs e Regiões

- Uma **VPC** é uma rede virtual **isolada logicamente** de outras redes virtuais na Nuvem AWS
- Dedicada à sua conta
- Pertence a uma **única região da AWS**
- Pode abranger **múltiplas zonas de disponibilidade**

#### Sub-redes

Depois de criar uma VPC, você pode dividi-la em uma ou mais **sub-redes**.

**Características das sub-redes:**

- Uma sub-rede é um **intervalo de endereços IP** em uma VPC
- Pertence a uma **única zona de disponibilidade**
- Criar sub-redes em diferentes zonas de disponibilidade aumenta a **disponibilidade**

**Classificação das sub-redes:**

- **Sub-redes públicas:** têm acesso direto à Internet
- **Sub-redes privadas:** não têm acesso direto à Internet

### Endereçamento IP em VPCs

#### Blocos CIDR IPv4

Ao criar uma VPC, você atribui um **bloco CIDR IPv4** (um intervalo de endereços IPv4 privados) a ela.

**Importante:**

- Depois de criar uma VPC, **não é possível alterar** esse intervalo
- A escolha deve ser **cuidadosa**

**Tamanhos de blocos CIDR:**

- Pode variar de `/16` (**65.536 endereços**) a `/28` (**16 endereços**)

#### IPv6 em VPCs

Como opção, é possível:

- Associar um **bloco CIDR IPv6** à VPC e às sub-redes
- Atribuir endereços IPv6 desse bloco aos recursos na VPC

#### Blocos CIDR de Sub-redes

O bloco CIDR de uma sub-rede pode ser:

- **Igual** ao bloco CIDR da VPC (uma única sub-rede na VPC)
- Um **subconjunto** do bloco da VPC, permitindo a definição de várias sub-redes

**Regra importante:** Se criar mais de uma sub-rede em uma VPC, os blocos CIDR **não podem se sobrepor**, evitando endereços IP duplicados.

📚 **Referência:** Para mais detalhes sobre endereçamento IP em VPCs, consulte a [documentação da AWS](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html).

### Endereços IP Reservados pela AWS

Ao criar uma sub-rede, ela requer seu próprio bloco CIDR. Para cada bloco CIDR especificado, a **AWS reserva cinco endereços IP**, que **não estão disponíveis para uso**.

#### Os 5 Endereços Reservados

1. **Endereço de rede**
2. **Roteador local da VPC** (comunicações internas)
3. **Resolução do sistema de nomes de domínio (DNS)**
4. **Uso futuro**
5. **Endereço de transmissão de rede**

**Exemplo prático:**

- Uma sub-rede com bloco CIDR IPv4 de `10.0.0.0/24` possui **256 endereços IP**
- Apenas **251 estão disponíveis** (256 - 5 = 251)
- Cinco são reservados pela AWS

### Tipos de Endereços IP

#### Endereço IP Privado

- Cada instância obtém **automaticamente** um endereço IP privado ao ser criada em uma VPC

#### Endereço IP Público

- É possível solicitar um endereço IP público ao criar a instância
- Modifica as propriedades de atribuição automática da sub-rede

#### Endereço IP Elástico

Um **endereço IP elástico** é um endereço IPv4 público e estático projetado para computação em nuvem dinâmica.

**Características:**

- Pode ser associado a qualquer instância ou interface de rede em qualquer VPC da conta
- Permite mascarar falhas de instâncias remapeando rapidamente o endereço para outra instância
- Associar o IP elástico a uma **interface de rede** (em vez de diretamente à instância) permite mover todos os atributos da interface para outra instância de uma vez

**⚠️ Custos:**

- Custos adicionais podem ser aplicados
- É importante **liberar IPs elásticos** quando não forem mais necessários

📚 **Referência:** [Documentação sobre IPs Elásticos](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-eips.html)

### Interface de Rede Elástica (ENI)

Uma **interface de rede elástica** é uma interface de rede virtual que pode ser anexada ou removida de uma instância em uma VPC.

#### Características da ENI

- Os atributos da interface seguem quando ela é reanexada a outra instância
- Redireciona o tráfego de rede
- Cada instância possui uma **interface de rede primária** à qual é atribuído um endereço IPv4 privado da VPC
- **Não é possível separar** a interface primária da instância
- É possível criar e anexar **interfaces adicionais**
- O número máximo varia conforme o **tipo de instância**

📚 **Referência:** [Documentação sobre Interfaces de Rede Elásticas](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)

### Tabelas de Rotas

Uma **tabela de rotas** contém regras (rotas) que direcionam o tráfego de rede de uma sub-rede.

#### Componentes de uma Rota

Cada rota especifica:

- **Destino:** bloco CIDR de destino
- **Alvo:** destino pelo qual o tráfego é enviado

#### Rota Local Padrão

Por padrão, cada tabela de rotas contém:

- Uma **rota local** para comunicação dentro da VPC
- É possível personalizar tabelas de rotas adicionando novas rotas
- A entrada de rota local **não pode ser excluída**

#### Associação de Sub-redes

- Toda sub-rede **deve estar associada** a uma tabela de rotas
- A **tabela de rotas principal** é atribuída automaticamente à VPC
- Controla o roteamento de todas as sub-redes não associadas a outra tabela
- Uma sub-rede pode estar associada a uma **única tabela de rotas** por vez
- Várias sub-redes podem **compartilhar a mesma tabela**

📚 **Referência:** [Documentação sobre Tabelas de Rotas](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)

### Principais Lições da Seção 2

✅ Uma VPC é uma seção isolada logicamente da Nuvem AWS  
✅ Uma VPC pertence a uma região e requer um bloco CIDR  
✅ Uma VPC é subdividida em sub-redes  
✅ Uma sub-rede pertence a uma zona de disponibilidade e requer um bloco CIDR  
✅ As tabelas de rotas controlam o tráfego de uma sub-rede  
✅ As tabelas de rotas têm uma rota local integrada  
✅ É possível adicionar outras rotas à tabela  
✅ Não é possível excluir a rota local

---

## Seção 3: Redes VPC

Agora que você aprendeu sobre os componentes básicos de uma VPC, pode começar a rotear o tráfego de maneiras interessantes. Nesta seção, você aprenderá sobre as diferentes opções de rede.

### Gateway da Internet (Internet Gateway)

Um **gateway da Internet** é um componente da VPC escalável, redundante e altamente disponível que permite a comunicação entre instâncias na VPC e a Internet.

#### Finalidades do Gateway da Internet

1. Fornecer um **destino** nas tabelas de rotas da VPC para tráfego roteável pela Internet
2. Executar a **conversão de endereços de rede (NAT)** para instâncias que receberam endereços IPv4 públicos

#### Como Tornar uma Sub-rede Pública

Para tornar uma sub-rede pública:

1. Anexe um gateway da Internet à VPC
2. Adicione uma rota à tabela de rotas para enviar tráfego não local por meio do gateway da Internet para a Internet (`0.0.0.0/0`)

📚 **Referência:** [Documentação sobre Gateways da Internet](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)

### Gateway NAT (NAT Gateway)

Um **gateway de conversão de endereços de rede (NAT)** permite que instâncias em uma sub-rede privada se conectem à Internet ou a outros serviços da AWS, mas **impede** que a Internet inicie uma conexão com essas instâncias.

#### Criação de um Gateway NAT

Para criar um gateway NAT, você deve:

1. Especificar uma **sub-rede pública** na qual o gateway NAT residirá
2. Especificar um **endereço IP elástico** que será associado ao gateway NAT ao criá-lo
3. Atualizar a **tabela de rota** associada a uma ou mais sub-redes privadas para apontar o tráfego vinculado à Internet para o gateway NAT

**Resultado:** As instâncias em suas sub-redes privadas podem se comunicar com a internet.

#### NAT Gateway vs Instância NAT

Você também pode usar uma **instância NAT** em uma sub-rede pública em sua VPC, em vez de um gateway NAT.

**Vantagens do Gateway NAT:**

- Serviço NAT **gerenciado**
- Fornece **melhor disponibilidade**
- **Maior largura de banda**
- **Menos esforço administrativo**

**Recomendação da AWS:** Para casos de uso comuns, a AWS recomenda que você use um **gateway NAT** em vez de uma instância NAT.

📚 **Referências:**

- [Gateways NAT](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)
- [Instâncias NAT](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_NAT_Instance.html)
- [Diferenças entre gateways NAT e instâncias NAT](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-comparison.html)

### Compartilhamento de VPC (VPC Sharing)

O **compartilhamento de VPC** permite que os clientes compartilhem sub-redes com outras contas da AWS na mesma organização no AWS Organizations.

#### Como Funciona

- A conta **proprietária da VPC** (proprietário) compartilha uma ou mais sub-redes com outras contas (**participantes**)
- Os participantes pertencem à mesma organização no AWS Organizations
- Depois que uma sub-rede é compartilhada, os participantes podem:
    - **Visualizar**, **criar**, **modificar** e **excluir** seus próprios recursos de aplicativo nas sub-redes compartilhadas

**Limitações dos participantes:**

- Não podem visualizar, modificar ou excluir recursos pertencentes a outros participantes ou proprietários da VPC

#### Benefícios do Compartilhamento de VPC

1. **Separação de responsabilidades:** A estrutura de VPC é controlada centralmente, incluindo roteamento e alocação de endereços IP
2. **Propriedade:** Permite que os proprietários de aplicativos continuem a ter recursos, contas e grupos de segurança
3. **Grupos de segurança:** Permite que participantes façam referência aos IDs de grupos de segurança uns dos outros
4. **Eficiências:** Aumenta a densidade em sub-redes e uso eficiente de VPNs e AWS Direct Connect
5. **Flexibilidade:** Evita limites rígidos (por exemplo, 50 interfaces virtuais por conexão do AWS Direct Connect)
6. **Otimização de custos:** Reutilização de gateways NAT, endpoints de interface VPC e tráfego dentro da zona de disponibilidade

#### Arquitetura

O compartilhamento de VPC permite:

- Dissociar contas e redes
- Reduzir o número de VPCs
- Permitir que aplicativos altamente interconectados se beneficiem dessa abordagem

### Emparelhamento de VPC (VPC Peering)

Uma **conexão de emparelhamento de VPC** é uma conexão de rede entre duas VPCs que permite rotear o tráfego entre elas de forma privada.

#### Características do Emparelhamento

- Instâncias em qualquer VPC podem se comunicar umas com as outras como se estivessem na **mesma rede**
- Você pode criar uma conexão de emparelhamento de VPC:
    - Entre suas próprias VPCs
    - Com uma VPC de outra conta da AWS
    - Com uma VPC em uma **Região diferente** da AWS

#### Configuração do Emparelhamento

Ao configurar a conexão de emparelhamento, você cria **regras na tabela de rota** para permitir que as VPCs se comuniquem por meio do recurso de emparelhamento.

**Exemplo:** Suponha que você tenha duas VPCs (VPC A e VPC B):

**Na tabela de rota da VPC A:**

- **Destino:** Endereço IP da VPC B
- **Alvo:** ID do recurso de emparelhamento

**Na tabela de rota da VPC B:**

- **Destino:** Endereço IP da VPC A
- **Alvo:** ID do recurso de emparelhamento

#### Restrições do Emparelhamento de VPC

1. Os **intervalos de endereços IP não podem se sobrepor**
2. O **emparelhamento transitivo não é compatível**
    - Se VPC A está conectada à VPC B e à VPC C
    - VPC B **não** estará conectada à VPC C implicitamente
3. Você pode ter apenas **um recurso de emparelhamento** entre as mesmas duas VPCs

📚 **Referência:** [Documentação sobre Emparelhamento de VPC](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-peering.html)

### AWS Site-to-Site VPN

Por padrão, as instâncias iniciadas em uma VPC não podem se comunicar com uma rede remota. Para conectar a VPC à rede remota (criando uma **rede privada virtual** ou **conexão VPN**):

#### Etapas para Criar uma Conexão VPN

1. Criar um novo dispositivo de **gateway virtual** (chamado de **gateway de rede privada virtual (VPN)**)
2. Anexá-lo à VPC
3. Definir a configuração do **dispositivo VPN** ou do **gateway do cliente**
    - _Nota:_ O gateway do cliente não é um dispositivo, mas um recurso da AWS que fornece informações à AWS sobre seu dispositivo VPN
4. Criar uma **tabela de rota personalizada** para apontar o tráfego vinculado ao data center corporativo para o gateway VPN
5. Atualizar as **regras do grupo de segurança**
6. Estabelecer uma **conexão Site-to-Site VPN** da AWS para vincular os dois sistemas
7. Configurar o **roteamento** para passar o tráfego pela conexão

📚 **Referência:** [Documentação sobre Conexões VPN](https://docs.aws.amazon.com/vpc/latest/userguide/vpn-connections.html)

### AWS Direct Connect (DX)

Um dos desafios da comunicação de rede é o **desempenho da rede**, que pode ser afetado se o data center estiver localizado longe da região da AWS.

#### O que é AWS Direct Connect

O **AWS Direct Connect (DX)** permite estabelecer uma conexão de rede **dedicada e privada** entre a rede e um dos locais do DX.

#### Benefícios do Direct Connect

- **Reduzir custos de rede**
- **Aumentar a taxa de transferência de largura de banda**
- Fornecer uma **experiência de rede mais consistente** do que conexões baseadas na Internet
- Usa **Virtual Local Area Networks (VLANs)** padrão 802.1q

📚 **Referência:** [Página de produto do AWS Direct Connect](https://aws.amazon.com/directconnect/)

### VPC Endpoint

Um **VPC endpoint** é um dispositivo virtual que permite conectar de forma privada sua VPC aos serviços da AWS compatíveis e aos serviços de endpoint de VPC desenvolvidos pelo AWS PrivateLink.

#### Vantagens dos VPC Endpoints

A conexão com esses serviços **não exige**:

- Gateway da internet
- Dispositivo NAT
- Conexão VPN
- Conexão do AWS Direct Connect

**Benefício adicional:**

- As instâncias na VPC não exigem endereços IP públicos para se comunicar com recursos no serviço
- O tráfego entre a VPC e os outros serviços **não deixa a rede da Amazon**

#### Tipos de VPC Endpoints

**1. Endpoints de Interface**

- Permitem conexão a serviços desenvolvidos pelo **AWS PrivateLink**, incluindo:
    - Serviços da AWS
    - Serviços hospedados por outros clientes da AWS e parceiros da rede de parceiros da AWS (APN)
    - Serviços compatíveis de parceiros do APN do AWS Marketplace
- O proprietário do serviço é o **provedor de serviços**
- Você, como criador do endpoint de interface, é o **consumidor do serviço**
- **Você é cobrado pelo uso do endpoint**

**2. Endpoints de Gateway**

- **Não geram custo adicional**
- Apenas aplicam-se as cobranças padrão pela transferência de dados e uso de recursos

📚 **Referências:**

- [Conceitos de VPC Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/concepts.html)
- [Criar Endpoints de Interface](https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html)

### AWS Transit Gateway

À medida que organizações crescem, gerenciar conectividade entre centenas de VPCs se torna complexo e caro.

#### O Problema

- Clientes da AWS frequentemente gerenciam **centenas de VPCs** distribuídas entre contas e regiões
- Cada VPC precisaria se conectar individualmente a todas as outras (conectividade **ponto a ponto**)
- Isso se torna **complexo e caro**

#### A Solução: AWS Transit Gateway

O **AWS Transit Gateway** permite criar e gerenciar uma **única conexão do gateway central** para cada VPC, data center ou escritório remoto.

#### Arquitetura Hub-and-Spoke

- O **Transit Gateway** funciona como um **hub**
- As redes conectadas atuam como **spokes** (raios)

#### Benefícios do Transit Gateway

- Simplifica o roteamento
- Reduz custos operacionais
- Qualquer nova VPC se conecta **automaticamente** às redes já conectadas
- Facilita a escalabilidade da rede

### Principais Lições da Seção 3

✅ Existem várias opções de rede da VPC:

- Gateway da Internet
- Gateway NAT
- VPC Endpoint
- Emparelhamento de VPC
- Compartilhamento de VPC
- AWS Site-to-Site VPN
- AWS Direct Connect
- AWS Transit Gateway

✅ Você pode usar o **assistente da VPC** para implementar seu projeto

---

## Seção 4: Segurança da VPC

Você pode incorporar segurança em sua arquitetura de VPC de várias maneiras para ter controle total sobre o tráfego de entrada e de saída. Nesta seção, você aprenderá sobre duas opções de firewall da Amazon VPC que podem ser usadas para proteger sua VPC.

### Grupos de Segurança (Security Groups)

Um **grupo de segurança** atua como um firewall virtual da instância e controla o tráfego de entrada e saída.

#### Características dos Grupos de Segurança

- Operam no **nível da instância**, não no nível da sub-rede
- Cada instância em uma sub-rede na VPC pode ser atribuída a um **conjunto diferente** de grupos de segurança
- É uma maneira de filtrar o tráfego direcionado às suas instâncias

#### Regras dos Grupos de Segurança

**Regras de Entrada (Inbound):**

- Quando você cria um grupo de segurança, ele **não possui regras de entrada**
- **Nenhum tráfego de entrada** originado de outro host para sua instância será permitido até que você adicione regras de entrada

**Regras de Saída (Outbound):**

- Por padrão, um grupo de segurança inclui uma **regra de saída** que permite **todo o tráfego de saída**
- Você pode remover essa regra e adicionar regras de saída que permitem apenas tráfego específico
- Se o grupo de segurança não tiver nenhuma regra de saída, nenhum tráfego de saída originário da instância será permitido

#### Grupos de Segurança são Stateful

Os grupos de segurança são **stateful**, o que significa que as informações de estado são mantidas mesmo depois que uma solicitação é processada.

**Implicações práticas:**

- Se você enviar uma solicitação da instância, o tráfego de resposta dessa solicitação terá permissão para fluir, **independentemente das regras de entrada** do grupo de segurança
- As respostas ao tráfego de entrada permitido podem sair, **independentemente das regras de saída**

#### Regras de Permissão

Ao criar um grupo de segurança personalizado:

- Você pode especificar **regras de permissão**, mas **não de negação**
- **Todas as regras são avaliadas** antes da decisão de permitir o tráfego

### Listas de Controle de Acesso à Rede (ACLs de Rede)

Uma **lista de controle de acesso à rede (ACL de rede)** é uma camada **opcional** de segurança para a Amazon VPC.

#### O que é uma ACL de Rede

- Atua como um **firewall** para controlar o tráfego de entrada e saída de uma ou mais **sub-redes**
- Adiciona outra camada de segurança à sua VPC
- Você pode configurar ACLs de rede com regras semelhantes às dos seus grupos de segurança

#### Associação de Sub-redes

- Toda sub-rede em sua VPC **deve ser associada** a uma ACL de rede
- Se você não associar explicitamente uma sub-rede a uma ACL de rede, as sub-redes serão associadas automaticamente à **ACL de rede padrão**
- É possível associar uma ACL de rede a **várias sub-redes**
- Uma sub-rede pode ser associada a apenas **uma ACL de rede** por vez
- Quando uma ACL de rede é associada a uma sub-rede, a associação anterior é removida

#### Regras da ACL de Rede

- Uma ACL de rede tem **regras de entrada e de saída separadas**
- Cada regra pode **permitir ou rejeitar** tráfego

**ACL de Rede Padrão:**

- Sua VPC já vem com uma ACL de rede padrão **modificável**
- Por padrão, permite todos os tráfegos de **IPv4** de entrada e saída
- Se aplicável, também permite o tráfego **IPv6**

#### ACLs de Rede são Stateless

As ACLs de rede são **stateless**, o que significa que **nenhuma informação** sobre uma solicitação é mantida depois que ela é processada.

#### ACL de Rede Personalizada

Você pode criar uma ACL de rede personalizada e associá-la a uma sub-rede.

**Comportamento padrão:**

- Por padrão, enquanto você não adicionar regras, toda ACL de rede personalizada **negará todo e qualquer tráfego** de entrada e saída

#### Avaliação de Regras

- Uma ACL de rede contém uma **lista numerada de regras**
- São avaliadas em **ordem**, começando com a regra de **menor número**
- O objetivo é determinar se o tráfego é permitido para dentro ou para fora de qualquer sub-rede associada à ACL de rede
- O **número mais alto** que é possível usar para uma regra é **32.766**

**Recomendação da AWS:**

- Criar regras em **incrementos** (por exemplo, incrementos de 10 ou 100)
- Permite inserir novas regras onde necessário posteriormente

📚 **Referência:** [Documentação sobre ACLs de Rede](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)

### Comparação: Grupos de Segurança vs ACLs de Rede

|Característica|Grupos de Segurança|ACLs de Rede|
|---|---|---|
|**Nível de operação**|Nível da instância|Nível da sub-rede|
|**Tipos de regras**|Apenas regras de permissão|Regras de permissão e de negação|
|**Comportamento**|Stateful|Stateless|
|**Avaliação de regras**|Todas as regras são avaliadas antes de permitir o tráfego|Regras são avaliadas em ordem numérica antes de tomar a decisão|

### Exercício Prático: Projetar uma VPC

**Cenário:** Você é proprietário de uma pequena empresa com um site hospedado em uma instância do Amazon EC2. Você tem dados de clientes armazenados em um banco de dados de back-end que deseja manter privados.

**Requisitos:**

1. O servidor web e o servidor de banco de dados devem estar em **sub-redes separadas**
2. O primeiro endereço da rede deve ser **10.0.0.0**
3. Cada sub-rede deve ter **256 endereços IPv4**
4. Seus clientes devem **sempre ser capazes** de acessar seu servidor web
5. Seu servidor de banco de dados deve ser capaz de **acessar a Internet** para fazer atualizações de patches
6. Sua arquitetura deve ser **altamente disponível** e usar pelo menos uma **camada de firewall personalizada**

### Principais Lições da Seção 4

✅ Criar segurança em sua arquitetura de VPC  
✅ Grupos de segurança e ACLs de rede são opções de firewall que você pode usar para proteger sua VPC  
✅ Grupos de segurança operam no nível da instância e são stateful  
✅ ACLs de rede operam no nível da sub-rede e são stateless

---

## Seção 5: Amazon Route 53

O **Amazon Route 53** é um serviço web de sistema de nomes de domínio (DNS) na nuvem altamente disponível e dimensionável.

### O que é Amazon Route 53

#### Propósito Principal

Foi projetado para oferecer a desenvolvedores e empresas uma maneira **confiável e econômica** de direcionar os usuários para aplicações de Internet.

**Como funciona:**

- Converte nomes, como `www.example.com`
- Em endereços IP numéricos, como `192.0.2.1`
- Que os computadores usam para se conectar uns aos outros

**Compatibilidade:**

- Totalmente compatível com **IPv6**

📚 **Referência:** [Saiba mais sobre DNS](https://aws.amazon.com/route53/what-is-dns/)

#### Conectividade

O Amazon Route 53 conecta com eficiência as solicitações de usuários com a infraestrutura executada na AWS:

- Instâncias do **Amazon EC2**
- Balanceadores de carga do **Elastic Load Balancing**
- Buckets do **Amazon S3**
- Também pode ser usado para direcionar usuários a **infraestruturas fora da AWS**

### Recursos do Amazon Route 53

#### Verificações de Integridade (Health Checks)

- Você pode usar o Amazon Route 53 para configurar **verificações de integridade do DNS**
- Permite rotear o tráfego para **endpoints íntegros**
- Ou monitorar de forma independente a integridade do seu aplicativo e de seus endpoints

#### Fluxo de Tráfego (Traffic Flow)

O **fluxo de tráfego** do Amazon Route 53 ajuda a gerenciar o tráfego globalmente por meio de vários tipos de roteamento:

**Características:**

- Podem ser **combinados** com failover de DNS
- Habilita diversas arquiteturas de **baixa latência** e **tolerantes a falhas**
- Usa um **editor visual simples** para gerenciar como os usuários são roteados para os endpoints do aplicativo
- Funciona para aplicativos em uma única região da AWS ou distribuídos em todo o mundo

#### Registro de Nome de Domínio

O Amazon Route 53 também oferece **registro de nome de domínio**:

- Você pode comprar e gerenciar nomes de domínio, como `example.com`
- O Amazon Route 53 definirá automaticamente as **configurações de DNS** para seus domínios

### Fluxo de Solicitação DNS

Este é o padrão básico que o Amazon Route 53 segue quando um usuário inicia uma solicitação de DNS:

1. O **resolvedor de DNS** verifica com seu domínio no Route 53
2. Obtém o **endereço IP**
3. Retorna o endereço IP para o usuário

### Políticas de Roteamento

O Amazon Route 53 oferece suporte a vários tipos de **políticas de roteamento**, que determinam como responde às consultas.

#### 1. Roteamento Simples (Round Robin)

**Quando usar:**

- Para um **único recurso** que executa uma função para seu domínio
- Exemplo: Um servidor web que fornece conteúdo para `example.com`

#### 2. Roteamento Ponderado Round Robin

**Funcionalidade:**

- Permite rotear o tráfego para vários recursos nas **proporções especificadas**
- Atribui **pesos** a conjuntos de registros de recursos para determinar a frequência com que diferentes respostas são atendidas

**Exemplo:**

- Se houver dois conjuntos de registros associados a um nome de DNS:
    - Um com peso **3**
    - Outro com peso **1**
- O Route 53 retornará o conjunto de registros com peso 3 em **75% do tempo**
- E o conjunto de registros com peso 1 em **25% do tempo**
- Os pesos podem variar de **0 a 255**

#### 3. Roteamento de Latência (LBR)

**Quando usar:**

- Quando há recursos em **múltiplas regiões da AWS**
- O objetivo é rotear o tráfego para a região que oferece a **melhor latência**

**Como funciona:**

- Direciona os clientes para o endpoint da AWS que proporciona a **experiência mais rápida**
- Baseado em **medidas de desempenho reais** das diferentes regiões onde o aplicativo é executado

#### 4. Roteamento de Localização Geográfica

**Funcionalidade:** Permite rotear o tráfego com base na **localização dos usuários**.

**Casos de uso:**

- Traduzir conteúdo
- Apresentar partes do site em idiomas específicos
- Restringir a distribuição de conteúdo a regiões onde há direitos legais de distribuição
- Balancear a carga entre endpoints de maneira **previsível**
- Garantir que cada local de usuário seja roteado para o mesmo endpoint **consistentemente**

#### 5. Roteamento de Geoproximidade

**Funcionalidade:**

- Permite rotear o tráfego com base na **localização de recursos**
- Opcionalmente, redirecionar tráfego de recursos em um local para outro

#### 6. Roteamento de Failover (Failover de DNS)

**Funcionalidade:**

- Possibilita configurar **failover ativo-passivo**
- Detecta interrupções e redireciona usuários para **locais alternativos** onde o aplicativo está funcionando corretamente

**Como funciona:**

- **Agentes de verificação de integridade** monitoram cada endpoint para determinar sua disponibilidade
- Aumenta a **disponibilidade do aplicativo**

#### 7. Roteamento de Resposta com Valores Múltiplos

**Funcionalidade:**

- Permite que o Route 53 responda a consultas DNS com **até oito registros íntegros** selecionados aleatoriamente
- Retorna somente valores de recursos **íntegros**

**Importante:**

- Embora não substitua um **load balancer**, melhora a disponibilidade e o balanceamento de carga via DNS

### Caso de Uso: Implantação em Várias Regiões

**Cenário típico:**

- Registros **ALIAS** podem apontar para múltiplos **Elastic Load Balancers** em diferentes regiões
- Direciona automaticamente os usuários para o balanceador de carga **mais próximo**

**Benefícios:**

- Roteamento com base na **latência**
- Balanceamento de carga para **zonas de disponibilidade**

### Melhorando a Disponibilidade com Route 53

O Amazon Route 53 permite melhorar a disponibilidade de aplicativos na AWS:

#### Recursos de Alta Disponibilidade

- Configurar **cenários de backup e failover**
- Habilitar **arquiteturas multirregião altamente disponíveis**
- Criar **verificações de integridade** para monitorar:
    - Desempenho de aplicativos web
    - Servidores web
    - Outros recursos

#### Verificações de Integridade

- Cada **health check** pode monitorar:
    - A integridade de um **recurso específico**
    - O status de outras **health checks**
    - Alarmes do **Amazon CloudWatch**

### Arquitetura de Failover Típica

**Arquitetura de aplicativo web multicamadas:**

1. O Route 53 passa o tráfego para um **balanceador de carga**
2. O balanceador distribui para **instâncias do EC2**

**Configuração para alta disponibilidade:**

**Registro DNS Primário:**

- **CNAME:** `www`
- **Política de roteamento:** Failover
- **Aponta para:** Load balancer do aplicativo web

**Registro DNS Secundário:**

- **CNAME:** `www`
- **Política de roteamento:** Failover
- **Aponta para:** Site estático do Amazon S3

**Como funciona:**

- As **verificações de integridade** garantem que o tráfego use a pilha primária
- Se o servidor principal ficar **indisponível**, aciona failover para o **site de backup**

### Principais Lições da Seção 5

✅ O Amazon Route 53 é um serviço web de DNS na nuvem altamente disponível e escalável  
✅ Converte nomes de domínio em endereços IP  
✅ Oferece suporte a vários tipos de políticas de roteamento  
✅ A implantação em várias regiões melhora o desempenho para um público global  
✅ O failover do Route 53 aumenta a disponibilidade das aplicações

---

## Seção 6: Amazon CloudFront

O objetivo das redes é compartilhar informações entre recursos conectados. A entrega de conteúdo também ocorre em redes, por exemplo, quando você faz streaming de um filme do seu serviço de streaming favorito. Nesta seção final, você aprenderá sobre o Amazon CloudFront, que é um serviço de rede de entrega de conteúdo (CDN).

### Desafios da Entrega de Conteúdo

#### Desempenho de Rede

Um dos desafios da comunicação de rede é o **desempenho da rede**.

**O problema:**

- Quando você navega em um site ou faz streaming de vídeo, sua solicitação é roteada por **múltiplas redes diferentes** para acessar um servidor de origem
- O **servidor de origem** (ou origem) armazena as versões **originais e definitivas** dos objetos (páginas da web, imagens e arquivos de mídia)

**Fatores que afetam o desempenho:**

- O **número de saltos de rede**
- A **distância** que a solicitação deve percorrer
- A **latência de rede** é diferente em várias localizações geográficas

**Solução:** Uma rede de entrega de conteúdo (CDN)

### O que é uma CDN

Uma **rede de entrega de conteúdo (CDN)** é um sistema distribuído globalmente de servidores de armazenamento em cache.

#### Conteúdo Estático

Uma CDN armazena em cache cópias de arquivos normalmente solicitados (**conteúdo estático**):

- HTML
- CSS
- JavaScript
- Arquivos de imagem

**Como funciona:**

- Esses arquivos são hospedados no **servidor de origem** do aplicativo
- A CDN entrega uma cópia local do conteúdo solicitado de uma **borda de cache** ou **ponto de presença**
- Fornece a **entrega mais rápida** para o solicitante

#### Conteúdo Dinâmico

As CDNs também fornecem **conteúdo dinâmico** exclusivo do solicitante e não armazenável em cache.

**Vantagens da entrega de conteúdo dinâmico:**

- A CDN estabelece e mantém **conexões seguras** mais próximas do solicitante
- Se a CDN estiver na mesma rede que a origem, o **roteamento de volta** para a origem para recuperar conteúdo dinâmico será **acelerado**
- Conteúdo como dados de formulário, imagens e texto podem ser **ingeridos e enviados de volta** para a origem
- Aproveita as **conexões de baixa latência** e o **comportamento de proxy** do PoP

### O que é Amazon CloudFront

O **Amazon CloudFront** é um serviço de CDN rápido que entrega dados, vídeos, aplicativos e APIs aos clientes globalmente com **baixa latência** e **altas velocidades de transferência**.

#### Características Principais

- Oferece um ambiente **amigável para desenvolvedores**
- Entrega arquivos aos usuários por meio de uma **rede global** de:
    - Locais de borda
    - Pontos de presença de caches regionais

#### Diferencial do CloudFront

O Amazon CloudFront é diferente das soluções tradicionais de entrega de conteúdo:

- Permite que você obtenha rapidamente os benefícios da entrega de conteúdo de **alto desempenho**
- **Sem contratos negociados**
- **Sem preços altos**
- **Sem taxas mínimas**

**Modelo de negócio:**

- Como outros serviços da AWS, é uma oferta de **autoatendimento**
- Com definição de preço de **pagamento conforme o uso**

### Arquitetura do CloudFront

#### Locais de Borda (Edge Locations)

O Amazon CloudFront entrega conteúdo por meio de uma rede mundial de data centers denominados **locais de borda**.

**Como funciona:**

1. Quando um usuário solicita conteúdo fornecido por você com o CloudFront
2. Ele é roteado para o **ponto de presença com a menor latência**
3. O conteúdo é entregue com a **melhor performance possível**

**Otimização de cache:**

- Os locais de borda do CloudFront são projetados para fornecer **conteúdo popular rapidamente** aos visualizadores
- À medida que os objetos são **menos acessados**, locais de borda poderão **removê-los** para liberar espaço para conteúdo mais solicitado

#### Caches de Presença Regionais

Para **conteúdo menos popular**, o CloudFront possui **caches de presença regionais**.

**Características:**

- São os locais do CloudFront implantados **globalmente** e **próximos dos visualizadores**
- Localizados **entre o servidor de origem e os locais de borda globais**
- Fornecem conteúdo diretamente aos visualizadores

**Vantagens:**

- Um cache de presença regional tem um cache **maior** do que um ponto de presença individual
- Os objetos permanecem no cache do ponto regional por **mais tempo**
- Mais conteúdo permanece **mais próximo dos visualizadores**
- Reduz a necessidade de o CloudFront voltar para o servidor de origem
- Melhora o **desempenho geral** para os visualizadores

📚 **Referência:** [Como o Amazon CloudFront funciona](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowCloudFrontWorks.html#HowCloudFrontWorksContentDelivery)

### Benefícios do Amazon CloudFront

#### 1. Rápido e Global

- Possui **escalabilidade massiva** e é distribuído globalmente
- Para entregar conteúdo aos usuários finais com **baixa latência**
- Utiliza uma rede global que consiste em:
    - Locais de borda
    - Caches regionais

#### 2. Segurança na Borda

- Oferece proteção no nível da **rede** e do **aplicativo**
- Seu tráfego e suas aplicações se beneficiam de várias **proteções integradas**:
    - **AWS Shield Standard** (sem custo adicional)
- Recursos configuráveis:
    - **AWS Certificate Manager (ACM):** Permite criar e gerenciar certificados SSL personalizados sem custo adicional

#### 3. Altamente Programável

- Os recursos do Amazon CloudFront podem ser **personalizados** para requisitos específicos de aplicativos
- Integra-se ao **Lambda@Edge**:
    - Permite executar código personalizado em locais da AWS em todo o mundo
    - Move lógica complexa de aplicativos para mais perto dos usuários
    - Melhora a capacidade de resposta
- Oferece suporte a integrações com outras ferramentas e interfaces de automação para **DevOps**
- Ambientes de **integração e entrega contínuas (CI/CD)**

#### 4. Profundamente Integrado à AWS

- Integrado à AWS, com localizações físicas **diretamente conectadas** à infraestrutura global da AWS
- Integra-se a outros serviços
- Você pode usar **APIs** ou o **Console de Gerenciamento da AWS** para configurar programaticamente todos os recursos na CDN

#### 5. Econômico

**Vantagens financeiras:**

- Não tem **compromissos mínimos**
- Cobra apenas pelo que você usa
- Em comparação com a **hospedagem própria**, evita:
    - Despesas e complexidade de operar uma rede de servidores de cache em vários sites na Internet
- Elimina a necessidade de **provisionar capacidade em excesso** para picos de tráfego
- Reduz a carga nos **servidores de origem**

**Integração com origens AWS:**

- Se você usar origens da AWS, como **Amazon S3** ou **Elastic Load Balancing**
- Pagará apenas pelos **custos de armazenamento**
- **Não** pelos dados transferidos entre esses serviços e o CloudFront

### Modelo de Preços do Amazon CloudFront

As cobranças do Amazon CloudFront se baseiam no **uso real do serviço** em quatro áreas:

#### 1. Transferência de Dados para Fora

- Você será cobrado pelo **volume de dados** transferidos de locais de borda do CloudFront
- Medidos em **GB**, para a Internet ou para sua origem
- O custo é calculado por **regiões geográficas específicas**
- O uso de serviços AWS como origem de arquivos será **cobrado separadamente**

#### 2. Solicitações HTTP(S)

- Você é cobrado pelo **número de solicitações HTTP(S)** feitas ao CloudFront para seu conteúdo

#### 3. Solicitações de Invalidação

- Você é cobrado **por caminho** na solicitação de invalidação
- Um caminho listado representa o **URL do objeto** que deseja invalidar no cache
- Até **1.000 caminhos por mês** são **gratuitos**
- Após isso, você é cobrado por caminho listado

#### 4. IP Dedicado Personalizado SSL

- Você paga **USD 600 por mês** para cada certificado SSL personalizado associado a uma ou mais distribuições do CloudFront usando IP dedicado
- Tarifado por **hora proporcional**

📚 **Referência:** [Preços do Amazon CloudFront](https://aws.amazon.com/cloudfront/pricing/)

### Principais Lições da Seção 6

✅ Uma CDN é um sistema distribuído globalmente de servidores de armazenamento em cache que acelera a entrega de conteúdo  
✅ O Amazon CloudFront é um serviço de CDN rápido que entrega dados, vídeos, aplicativos e APIs com segurança em uma infraestrutura global, com baixa latência e altas velocidades de transferência  
✅ O Amazon CloudFront oferece muitos benefícios:

- Rápido e global
- Segurança na borda
- Alta programabilidade
- Profunda integração com a AWS
- Economia

---

## Resumo do Módulo

Neste módulo você aprendeu a:

✅ Reconhecer os conceitos básicos de redes  
✅ Descrever as redes virtuais na nuvem com a Amazon VPC  
✅ Rotular um diagrama de rede  
✅ Projetar uma arquitetura básica de VPC  
✅ Indicar as etapas para criar uma VPC  
✅ Identificar grupos de segurança  
✅ Criar sua própria VPC e adicionar componentes adicionais para produzir uma rede personalizada  
✅ Identificar os fundamentos do Amazon Route 53  
✅ Reconhecer os benefícios do Amazon CloudFront

---

## Recursos Adicionais

Para aprofundar seus conhecimentos sobre os tópicos abordados neste módulo, consulte os seguintes recursos:

### Amazon VPC

📚 [Página de visão geral da Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

📚 [Whitepaper sobre as opções de conectividade da Amazon VPC](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/introduction.html)

📚 [Blog "One to Many: Evolving VPC Design AWS Architecture"](https://aws.amazon.com/blogs/architecture/one-to-many-evolving-vpc-design/)

📚 [Guia do usuário da Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

### Amazon CloudFront

📚 [Página de visão geral do Amazon CloudFront](https://aws.amazon.com/cloudfront/?nc=sn&loc=1)

---

_Documento baseado em: AWS Academy Cloud Foundations (PT) - Module 05 Student Guide - Version 2.0.19_