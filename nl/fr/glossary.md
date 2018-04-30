﻿---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Glossaire
{: #glossary}

La plateforme {{site.data.keyword.blockchainfull}} Platform simplifie votre parcours sur la blockchain. Cette rubrique définit les termes utilisés dans cette documentation et elle présente les concepts de blockchain. Pour une meilleure compréhension de ces termes, vous pouvez consulter [Hyperledger Fabric ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](http://hyperledger-fabric.readthedocs.io/en/master/glossary.html).
{:shortdesc}

## AC
Autorité de certification. Ressource de réseau de blockchain qui émet des certificats pour tous les membres participants. Ces certificats représentent l'identité d'un membre. Toutes les entités du réseau (homologues, programmes de tri, clients, etc.) doivent posséder une identité pour communiquer, authentifier et enfin effectuer des transactions. Ces identités sont nécessaires à toute participation directe au réseau de blockchain.  Vous pouvez créer une carte réseau d'entreprise pour l'autorité de certification. La [Carte AC](develop_starter.html#developing-business-networks-with-starter-plan) peut ensuite être importée et elle sera utilisée pour l'échange de valeur confidentielle admin pour les certificats valides de l'autorité de certification du plan Starter

## Adhésion
Processus par lequel les transactions de code blockchain sont validées. Les règles d'adhésion sont implémentées en indiquant des règles d'adhésion.

## Appartenance dynamique
Un membre peut être ajouté de manière dynamique au réseau par un utilisateur disposant du privilège **registre**. Les membres se voient également affecter des rôles et des attributs, qui contrôlent leur accès et leurs droits sur le réseau. Les rôles et les attributs ne peuvent pas être affectés de manière dynamique. Hyperledger Fabric prend en charge l'ajout ou le retrait de membres, homologues, et noeuds de service de classement, sans compromettre les opérations du réseau dans son ensemble. L'appartenance dynamique est essentielle lors de l'ajustement des relations commerciales et que les entités doivent être ajoutées ou retirées pour différentes raisons.

## Bloc
Ensemble ordonné de transactions, lié cryptographiquement au bloc précédent dans un canal.

## Bloc d'origine
Bloc de configuration qui initialise un réseau de blockchain ou un canal, et fait également office de premier bloc dans une chaîne.

## Canal
Un canal se compose d'un sous-ensemble de membres réseau qui souhaitent effectuer des transactions en mode privé. Les canaux fournissent l'isolement de données et la confidentialité en autorisant les membres d'un canal à établir des règles spécifiques et un registre, auxquels seuls les membres du canal peuvent accéder. Les homologues, qui sont les noeuds qui fonctionnent en tant que noeuds finaux de transaction pour les organisations, sont joints aux canaux.

## Chaîne 
La chaîne du registre est un journal des transactions structuré sous la forme de blocs de transactions liés par hachage. Les homologues reçoivent des blocs de transactions du service de commande, marquent les transactions de bloc comme étant valides ou non valides sur la base de règles d'adhésion et de violations des accès concurrents, puis ajoutent les blocs à la chaîne de hachage sur le système de fichiers de l'homologue.

## Client
Le client représente l'entité qui agit pour le compte d'un utilisateur. Il doit se connecter à un homologue pour communiquer avec la blockchain. Le client peut se connecter à un homologue de son choix. Les clients créent et par conséquent appellent des transactions. Le client soumet un appel de transaction aux approbateurs, puis diffuse les propositions de transaction au service de commande.

## Code blockchain
Egalement appelés "contrats intelligents", les codes blockchain sont les éléments logiciels qui contiennent un ensemble de fonctions permettant d'interroger et de mettre à jour le registre. 

## Consensus
Processus collaboratif qui permet de conserver les transactions de registre synchronisées au sein du réseau. Le consensus garantit que les registres sont mises à jour uniquement lorsque les participants appropriés approuvent les transactions, et que les registres sont mis à jour avec les mêmes transactions dans le même ordre. De nombreux modes algorithmiques différents permettent d'atteindre ce consensus.

## Données d'identification du service
Les données d'identification du service sont disponibles au format JSON et elles contiennent les informations de noeud final d'API et les ID d'inscription/valeurs confidentielles de vos ressources réseau, c'est-à-dire les homologues, les noeuds de programmes de tri et les autorités de certification. Votre application interagit avec les ressources réseau via ces noeuds finaux d'API.

## Données d'identification réseau
Les données d'identification sont visibles depuis l'écran "API" du Moniteur réseau. Elles incluent votre "clé" (nom d'utilisateur) et votre "valeur confidentielle" (mot de passe) dans l'interface utilisateur Swagger. Vous devez utiliser ces données d'identification réseau pour vous authentifier avant de tester les API REST. 

## Homologue
Ressource de réseau blockchain qui fournit les services permettant d'exécuter et de valider les transactions, et de gérer les registres. L'homologue exécute du code blockchain et il détient l'historique de transactions ainsi que l'état en cours des actifs sur les canaux du réseau, c'est-à-dire le registre. Ceux-ci sont détenus et gérés par des organisations et associés à des canaux.

## HSM
Module de sécurité matérielle (HSM). Permet un chiffrement à la demande, la gestion des clés et le stockage de clés en tant que service géré. HSM est un dispositif physique qui gère les tâches gourmandes en ressources de chiffrement et réduit le temps de latence des applications. Pour plus d'informations, voir [Module de sécurité matérielle ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://www.ibm.com/cloud/hardware-security-module)

## Hyperledger Composer
[Hyperledger Composer ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://hyperledger.github.io/composer/latest/introduction/introduction.html) est un jeu d'outils de développement en open source. Il utilise un langage de modélisation spécifique, qui est associé à des transactions JavaScript, ainsi qu'à des règles de contrôle d'accès pour modéliser un réseau d'entreprise de modèle en totalité. Vous pouvez utiliser Hyperledger Composer pour intégrer des systèmes et données existants à votre application de blockchain avant de déployer quoi que ce soit dans une véritable blockchain.

## Hyperledger Fabric
[Hyperledger Fabric ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](http://hyperledger-fabric.readthedocs.io/en/master/) est une architecture de blockchain d'entreprise hébergée par Linux Foundation pour servir de base au développement d'applications ou de solutions blockchain avec une architecture modulaire. Les composants Hyperledger Fabric comme les services de consensus et d'appartenance sont de type plug-and-play.

## Installer
Processus consistant à placer un code blockchain sur le système de fichiers d'un homologue. Vous devez installer le code blockchain sur chaque homologue qui va exécuter le code blockchain.  

## Instancier
Processus consistant à démarrer et à initialiser un conteneur de code blockchain sur un canal spécifique. Dès que le code blockchain est installé sur les homologues et que chaque homologue a rejoint le canal, le code blockchain doit être instancié sur le canal. L'instanciation doit effectuer l'initialisation nécessaire du code blockchain, ce qui inclut la base de données "world state" initiale d'un code blockchain. Après l'instanciation, les homologues sur lesquels le code blockchain est installé peuvent accepter les appels de code blockchain.

## Membre
Egalement appelés "organisations", les membres d'un réseau de blockchain, semblables aux membres d'un groupe, forment la structure du réseau. Un membre peut avoir la taille d'une multinationale ou d'un individu. Les membres sont inscrits sur le réseau avec un certificat qui leur accorde le droit d'utiliser le réseau en tant que fournisseur de services (par exemple, en émettant des certificats, en validant/ordonnant des transactions) ou en tant que consommateur. Le premier fournit des services de blockchain de base qui incluent la validation de transaction, le classement des transactions ainsi que des services de gestion de certificats. Les membres consommateurs utilisent le réseau pour appeler des transactions par rapport au registre partagé. Les membres peuvent comporter plusieurs homologues. 

## Moniteur réseau
Tableau de bord de l'interface graphique fourni par la plateforme {{site.data.keyword.blockchainfull_notm}} pour afficher et gérer le réseau de blockchain.

## MSP
Membership Service Provider (Fournisseur de services aux membres). Ensemble de mécanismes et protocoles de chiffrement pour l'émission et la validation des certificats et des identités au sein du réseau de blockchain. Les identités qui sont émises dans la portée d'un fournisseur de services d'appartenance peuvent être évaluées au sein des règles de validation des règles du fournisseur de services d'appartenance. Le fournisseur MSP est installé sur chaque homologue de canal afin de garantir que les demandes de transaction qui sont émises pour l'homologue proviennent d'une identité utilisateur authentifiée et autorisée.

## Noeud
Entité de communication de la blockchain. Il existe trois types de noeuds : AC, Homologue et Service de tri (collection des programmes de tri d'un canal).

## Organisation
Voir [Membre](#member).

## Participant
Organisation, individu, application ou appareil qui interagit avec le réseau de blockchain. Sous l'appellation participant, on distingue deux groupes : les membres et les utilisateurs.

## Profil de connexion
Le profil de connexion est visible dans l'écran "Présentation" du Moniteur réseau lorsque vous cliquez sur le bouton **Profil de connexion**. Les informations sont disponibles au format JSON et elles contiennent les informations de noeud final d'API et les ID d'inscription/valeurs confidentielles de vos ressources réseau, c'est-à-dire les homologues, les programmes de tri et les autorités de certification. Votre application interagit avec les ressources réseau via ces noeuds finaux d'API.

## Programme de tri
Noeud du service de tri. Ressource de réseau de blockchain qui fournit des services d'authentification de client. Fournit également des services pour le tri et le classement de transactions.

## Registre
Le registre comprend une "chaîne de blocs" littérale qui stocke un enregistrement immuable et séquencé de transactions, ainsi qu'une base de données d'état pour le maintien de l'état en cours. Il y a un registre par canal, et les mises à jour de ce dernier sont gérées par le processus de consensus en fonction des règles d'un canal particulier.

## Règle d'adhésion
Définit les noeuds homologue sur un canal qui doivent exécuter des transactions liées à une application de code blockchain spécifique, ainsi que la combinaison nécessaire de réponses (adhésions). Une règle peut exiger qu'une transaction soit validée par un nombre minimum d'homologues d'adhésion, un pourcentage minimum d'homologues d'adhésion ou par tous les homologues d'adhésion qui sont affectés à une application de code blockchain spécifique. Les règles peuvent être organisées en fonction de l'application et du niveau souhaité de résilience par rapport à un comportement inapproprié, qu'il soit ou non délibéré, par les homologues d'adhésion. Une transaction soumise doit respecter la règle d'adhésion pour pouvoir être marquée comme valide par les homologues d'adhésion. Une règle distincte d'adhésion pour l'installation et l'instanciation des transactions est également requise.

## Réseau
Instance d'un service de plateforme {{site.data.keyword.blockchainfull_notm}} sur {{site.data.keyword.cloud_notm}}.

## Réseau d'entreprise
Définition d'un réseau de blockchain, qui inclut le modèle de données, la logique de transaction et les règles de contrôle d'accès de votre solution blockchain. Les définitions de réseau d'entreprise sont créées à l'aide de [Hyperledger Composer](#hyperledger-composer). Les définitions de réseau d'entreprise sont regroupées dans des fichiers **.bna** (business network archive) déployables.

## Ressource
Biens matériels ou immatériels, services ou propriété représentés en tant qu'élément qui fait l'objet d'une transaction sur le réseau de blockchain.

## SDK
Hyperledger Fabric prend en charge deux kits SDK : Node SDK et Java SDK. Node SDK peut être installé via NPM et Java SDK via Maven. Les kits SDK ont leurs propres référentiels Git, c'est-à-dire, [Fabric Node SDK ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://github.com/hyperledger/fabric-sdk-node) et  [Fabric Java SDK ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://github.com/hyperledger/fabric-sdk-java), ainsi que la documentation associée aux API disponibles. Les kits SDK de Hyperledger Fabric Client permettent l'interaction entre votre application client et votre réseau de blockchain.

## Service de tri
Chaque réseau de blockchain nécessite un service de tri. Ce service collecte les transactions des membres réseau, ordonne les transactions et les regroupe dans des blocs. Il distribue ensuite les nouveaux blocs aux homologues, lesquels peuvent vérifier les blocs et les ajouter aux registres sur chaque canal. Le service de tri est aussi une liaison commune pour le réseau global. Il contient les identités de chiffrement qui sont liées à chaque membre et authentifie l'identité des clients et des homologues pour l'accès au réseau.

## SOLO
Implémentation de plug-in de consensus pour Hyperledger Fabric qui se traduit par un seul service de tri dans le réseau de blockchain. Le réseau de plan Starter utilise l'implémentation SOLO. Une implémentation SOLO n'est pas destinée à un réseau de production. L'alternative au consensus SOLO est un cluster Kafka.

## Transaction
Mécanisme mis en oeuvre par les participants sur le réseau de blockchain pour interagir avec les ressources. Une transaction crée un nouveau code blockchain ou appelle une opération dans un code blockchain existant.

## Utilisateur
Un utilisateur a le rôle d'un participant au sein d'un réseau de blockchain et qui a un accès indirect au registre via une relation d'accréditation avec un membre existant.  
