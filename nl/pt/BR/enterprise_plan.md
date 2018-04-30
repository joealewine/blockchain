---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Sobre o Enterprise Plan

O {{site.data.keyword.blockchainfull}} Platform Enterprise Plan é uma oferta pronta para produção para organizações que gostariam de criar ou se associar a uma rede de blockchain para empresas reais. Esse plano fornece a infraestrutura chave juntamente com as ferramentas e suporte para iniciar facilmente uma rede altamente segura e pronta para produção.

**Nota**: o {{site.data.keyword.blockchainfull_notm}} Platform Enterprise Plan fornece um ambiente de produção. Se você precisar de um ambiente de desenvolvimento e teste, veja [Sobre o Starter Plan](starter_plan.html).

Para membros que irão iniciar a rede, a IBM fornece uma interface gráfica com o usuário para guiar o inicializador de rede pelas etapas principais para configurar e provisionar a rede. Isso inclui convidar outros membros e configurar regras de governança. Para obter mais informações, veja [Governar a rede do Enterprise Plan](get_start.html). Após a rede ser implementada, uma interface gráfica com o usuário interativa, o Monitor de rede, está disponível para monitorar o funcionamento e a atividade da rede; gerenciar atividades de rede chaves que incluem novas implementações, inclusão ou remoção de membros, ciclo de vida do chaincode e gerenciamento de canal; e buscar suporte técnico. Localize mais informações sobre o Monitor de rede, veja [Opere a rede do Enterprise Plan](v10_dashboard.html).

Inscreva-se agora para a sua associação do [{{site.data.keyword.blockchainfull_notm}} ![Ícone de link externo](images/external_link.svg "Ícone de link externo")](https://console.bluemix.net/catalog/services/blockchain?env_id=ibm:yp:us-south&taxonomyNavigation=apps).

O {{site.data.keyword.blockchainfull_notm}} Platform foi construído com os componentes chave do Hyperledger Fabric que incluem uma Autoridade de certificação (CA) e pelo menos 1 peer (máximo de 6). O Enterprise Plan também fornece um serviço de solicitação do Kafka tolerante a falhas de travamento (CFT) para os membros de rede.

A autoridade de certificação do Fabric é a fornecida com o Enterprise Plan. Duas CAs intermediárias são fornecidas por membro, as quais concedem associação à rede. Usando a autoridade de certificação, o membro também pode fornecer associação (certificações) aos usuários da rede.

É importante entender que para uma transação ser anexada ao livro-razão, há três fases que estão envolvidas:  
1. Simulação e Endosso de Transação (peer)
2. Pedido (serviço de solicitação)
3. Validação e Confirmação (peer)

Os peers do Fabric pertencentes aos membros são a interface ou o gateway para aplicativos para execução do chaincode, fornecendo a lógica de negócios para executar transações com relação ao livro-razão.  Todas as transações devem ser aprovadas. Os outros membros da rede fazem esse endosso. Após a aprovação, as transações são enviadas para um serviço de solicitação fornecido pela IBM (Kafka).

Além dos componentes de blockchain principais, a opção Associação Corporativa fornece uma infraestrutura com armazenamento de dados seguros e comunicações (TLS), além de alta disponibilidade.  Embora as redes do Fabric compartilhem esses recursos de infraestrutura, é fornecido isolamento para os nós do componente do Fabric em uma rede e cada nó é executado em um contêiner do docker seguro que protege o ambiente de execução.

O único aspecto que deve ser determinado é o tamanho dos peers que a rede requer. Essa decisão é baseada no número de canais que são necessários, além da carga de trabalho por canal, do uso de memória e do espaço em disco (armazenamento).

É necessário usar o Enterprise Plan para implementações mais estáveis, de produção ou quase no nível de produção. Para fins de teste, use [Starter Plan](starter_plan.html), [desenvolver no IBM Container Service](https://ibm-blockchain.github.io/) ou [instalar imagens do Docker localmente](http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html).

<!--- The Enterprise plan provides the ordering service and CA. The membership fee is $1,000, and a per peer fee of $1,000 that is associated with the network. If you want to have high availability (HA), you must purchase an additional peer to provide the HA capabilities. For example, one organization (associated membership fee of $1,000) of two peers ($1,000 X 2 peers) with HA ($1,000 X 2 HA peers) requires a monthly charge of $5,000.  --->

## Precificação  
Para usar o Enterprise Plan, membros de rede devem pagar US$ 1.000 por mês como a taxa de associação e adicionalmente US$ 1.000 por mês para cada um de seus peers na rede. As taxas mensais são faturadas diariamente rateadas. Por exemplo, um membro (taxa de participação associada de U$ 1.000) de dois peers (por taxa peer de U$ 1.000 × 2 peers) precisa pagar U$ 3.000 por mês.  Se o mês tiver 30 dias, o membro pagará U$ 100 (U$ 3.000/30) todos os dias.  Observe que se a alta disponibilidade (HA) for necessária, será necessário dobrar os números de peers necessários para fornecer os recursos de HA.

Os membros de rede podem pagar a sua conta com as suas próprias contas do {{site.data.keyword.cloud_notm}} que contêm o espaço para criar a instância de rede. Como alternativa, um membro de rede pode cobrir a conta para todos os membros na rede. Para obter mais informações sobre como pagar pelas redes de blockchain, veja [Pagando pela rede](howto/pay_for_the_network.html).
