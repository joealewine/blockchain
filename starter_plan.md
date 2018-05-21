---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-21"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# About Starter Plan
{: #overview}

{{site.data.keyword.blockchainfull}} Platform Starter Plan is an entry level option that enables organizations to simulate multi-organization blockchain networks, quickly develop applications, and work with supplied examples. It also boasts the same UI experience as other membership options, helping to eliminate any learning curve. Starter Plan networks are built on Hyperledger Fabric V1.1.
{:shortdesc}

**Note**: {{site.data.keyword.blockchainfull_notm}} Platform Starter Plan is a development and testing environment, and is not suitable for production workloads. If you need a production environment, see [About Enterprise Plan](enterprise_plan.html). You might check  [Starter Plan considerations](#considerations) before you use Starter Plan.

Sign up for your [{{site.data.keyword.blockchainfull_notm}} membership ![External link icon](images/external_link.svg "External link icon")](https://console.bluemix.net/catalog/services/blockchain?env_id=ibm:yp:us-south&taxonomyNavigation=apps) and try the Starter Plan now! Note that you must choose **US South** as the region in {{site.data.keyword.cloud_notm}} to create blockchain networks with Starter Plan Beta.


## Target audiences

If you fit into one of the following situations, the Starter Plan is suitable for you to start your blockchain journey.
- **_Learn {{site.data.keyword.blockchainfull_notm}} Platform._**  
    If you are curious about {{site.data.keyword.blockchainfull_notm}} Platform or even new to blockchain, Starter Plan offers you a great way to learn how to develop and govern a real blockchain network. You can find the components that a network consists of, learn how to deploy and manage chaincode (also known as "smart contracts"), how to add channels (and to manage channel permissions), and track when a new block is generated, just as in a production network.
- **_Want to act as multiple organizations to facilitate network development._**  
    Starter Plan enables you to act as multiple organizations, which allows you to see how the IBM Blockchain Platform (IBP) manages collaborative tasks like channel creation and chaincode instantiation, as well as testing applications and invoking transactions. You can also invite others to collaborate in a Starter Plan network (as in Enterprise plans).
- **_Build demo solutions in a live network._**  
    Starter Plan provides a powerful environment for testing network definitions (by integrating a `.bna` file that is developed by using {{site.data.keyword.blockchainfull_notm}} Platform: Develop) and blockchain applications. The ready-to-use blockchain network enables quick presentations to colleagues, management, and partners through the operational and management tools that the Network Monitor provides.
- **_Iteratively develop and test blockchain applications._**  
    Starter Plan offers you a staging area to continuously develop and test your code on a blockchain network. You can iteratively develop your code and deploy into your continuous integration and continuous deployment architecture. Starter Plan provides the same blockchain network functionalities as well as operational and management tooling as the Enterprise Plan. After you are ready to push your project to one of the Enterprise plans, you can operate the same way as in Starter Plan, but with more opportunities to grow your network.
- **_Test projects before production._**  
    Starter Plan provides an environment for developers and testers to quickly move from their local environment to a real cloud blockchain environment.  This mechanism allows developers and testers to focus on functionalities and to easily move from unit test to functional test. System, solution, and performance test teams can also use the environment without the extra effort to set up a network locally.
- **_Educational operational {{site.data.keyword.blockchainfull_notm}} Platform._**  
    {{site.data.keyword.blockchainfull_notm}} Platform provides virtually the same user interface<!--the same user interface--> in Starter Plan and the Enterprise plans, ensuring that your customized training uses the same workflows that your organization will use in an Enterprise plan.
- **_Deploy sample applications quickly using Toolchain._**  
    Starter Plan allows the deployment of sample applications by using Toolchain with only a few clicks. These samples will assist developers by providing a growing set of samples with code to modify and move forward.


## Starter Plan specializations

Starter Plan offers the ability to managing membership with Certificate Authority (CA), performing transaction endorsement, providing ordering services, building private channels, managing chaincode lifecycles, and collaborating with others in a live network, just as in an Enterprise plan.

Specifically, Starter Plan offers a pre-configured blockchain network that you can develop, govern, and operate through the Network Monitor. It also provides simple approaches to deploy sample applications and integrates your applications that you develop with {{site.data.keyword.blockchainfull_notm}} Platform: Develop.

- **_One-click-ready network_**  
    Starter Plan provisions you a network with an ordering service, CAs, a default channel, and two organizations (with one peer per organization) with a single click. {{site.data.keyword.blockchainfull_notm}} Platform handles the creation and configuration of this network (you'll be able to update it after it goes live).  <!--The free trial provides you up to two organizations and two peers.-->
- **_Cost efficiency_**  
    The Starter Plan membership option provides many of the same blockchain capabilities as Enterprise Plan membership options, but at a lower cost.  <!--During a trial period of Starter Plan, you can provision a blockchain network with basic network resources for free.-->At the Beta stage, you can use Starter Plan for free.
- **_Multi-organization network simulation_**  
    You can use Starter Plan to simulate building a network with multiple organizations. You do not need to actually invite other organizations to your network, but can act as other organizations yourself. This mechanism enables you to learn how a new organization can join the network, how multiple organizations work together in the network, and so on. You can switch between your organizations from the Network Monitor to view and manage the network from different organizations' view.
    <!--**Note**: It might cause extra cost if you exceed the free trial resource limits of two organizations and two peers.-->
- **_Swagger APIs_**  
    Starter Plan exposes several REST APIs that you can try out from a Swagger interface. For more information, see [Using Swagger APIs](swagger_apis.html).
- **_Sample applications_**  
    Starter Plan leverages the Toolchain service in {{site.data.keyword.cloud_notm}} and enables sample deployment with simple clicks.  After you deploy and launch a sample, the chaincode and applications automatically run for your blockchain network.  For more information about sample applications, see [Deploying sample applications](howto/prebuilt_samples.html).
- **_{{site.data.keyword.blockchainfull_notm}} Platform: Develop application Integration_**  
    Starter Plan enables you to deploy {{site.data.keyword.blockchainfull_notm}} Platform: Develop applications to your network.  For more information, see [Importing IBP: Develop applications](link).

<!--
## Migrate to enterprise membership options
After you are confident to run your real business in {{site.data.keyword.blockchainfull_notm}} Platform, you can migrate from Starter Plan to Enterprise Plan.
-->

<!--
## Pricing
Starter Plan offers you a free trial for 60 days.  During the trial period, you can have a blockchain network with the basic configuration of 2 organizations and 1 peer per each organization.  After the trial period, you must pay $300 per month for your network with the same basic configuration.  If you need more peers, you must pay $75 per month for each additional peer.
The monthly fees are prorated and billed daily. For example, a member with basic network configuration (associated fee of $300) and 2 additional peers (per peer fee of $75 X 2 peers) needs to pay $450 every month. If the month has 30 days, the member pays $15 ($450/30) every day.
Network members can pay their bill with their own {{site.data.keyword.cloud_notm}} accounts that contain the space to create the network instance.  Alternatively, one network member can cover the bill for all members in the network.  For more details about how to pay for the blockchain networks, see [Paying for the network](howto/pay_for_the_network.html).
-->

## Starter Plan considerations
{: #considerations}

Starter Plan is an entry point to {{site.data.keyword.blockchainfull_notm}} Platform and is for developing and testing purpose.  Check the following items before you use Starter Plan.

- **{{site.data.keyword.cloud_notm}} account requirement**  
    Starter Plan is free during Beta.  However, you must upgrade your {{site.data.keyword.cloud_notm}} account to a paid account, for example, a **Pay-As-You-Go** type. All membership plans that {{site.data.keyword.blockchainfull_notm}} Platform offers require an  {{site.data.keyword.cloud_notm}} paid account. To upgrade your account to a Pay-As-You-Go type, go to **Manage** > **Billing and Usage** > **Billing** in the {{site.data.keyword.cloud_notm}} console, and click **Add Credit Card**.
- **Differences from Enterprise Plan**
    - [CA](glossary.html#ca) and [ordering service](glossary.html#orderer) are not fault tolerant because each organization has only one CA and a network has only one [orderer](glossary.html#orderer).
    - Ordering service uses only [SOLO](glossary.html#SOLO) [consensus](glossary.html#consensus). A Starter Plan network consists of only one [orderer](glossary.html#orderer) that performs consensus for all peers.
    - [Hardware Security Module (HSM)](glossary.html#hsm) is not available to safeguard and manage digital keys for strong authentication and crypto processing.
- **Network resource limitation**  
    Starter Plan assigns 1 CPU, 2 GB RAM, and 20 Gi storage of hardware constantly for each {{site.data.keyword.cloud_notm}} service instance. If you add more network resources to the same network, your resources share the hardware assignments. However, when you invite a member to join the network, the member creates a new service instance. Therefore, Starter Plan assigns another set of 1 CPU, 2 GB RAM, and 20 Gi storage hardware to the new member.
- **Inactive network deletion**  
    After you create a Starter Plan (Beta) network, if you don't visit the network or issue any transaction on it for 15 days, {{site.data.keyword.blockchainfull_notm}} Platform will delete the network.
    - If you don't need the network any more, you don't need to take any action and your network will be deleted automatically.
    - If you still need to use the network, you can keep it active by issuing transactions on it. You can find your Starter Plan (Beta) network in your [{{site.data.keyword.cloud_notm}} Dashboard ![External link icon](images/external_link.svg "External link icon")](https://console.bluemix.net/dashboard/apps/){:new_window}. If you don't have regular trasanctions to issue, follow the [instructions](howto/prebuilt_samples.html#deploying-sample-applications-in-starter-plan) to try the sample applications.
- **Maintenance and upgrade**  
    Starter Plan maintenance and network updates are performed on a fixed schedule. During the maintenance period, you cannot provision new networks and might notice brief periods of network interruption.
- **Data retention**  
    Starter Plan does not guarantee data retention with release upgrades, including moving from Beta to GA.
- **Migration considerations**  
    Migrating the data from a Starter Plan network to other membership plans is not currently supported. However, it is possible to migrate `.bna` files, chaincode, and applications that were tested on Starter Plan. For more information, see [Migrating from Starter Plan to Enterprise Plan](get_start_starter_plan.html#migrate).
<!--    - Starter Plan is built on Hyperledger Fabric V1.1.  If your chaincode is at Fabric V1.0 level, you need to upgrade your chaincode before you use it in Starter Plan. For more information, see [Updating chaincode for Hyperledger Fabric 1.1](knownissues.html/update-chaincode-fabric11).
-->
