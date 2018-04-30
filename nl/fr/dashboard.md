---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

# Exploitation d'un réseau de plan Starter
{: #operate-starter-plan-network}

La plateforme {{site.data.keyword.blockchainfull}} comporte un Moniteur réseau qui fournit une vue d'ensemble de votre environnement de blockchain, notamment des composants réseau, des membres, des canaux rejoints, des données de performance et des codes blockchain déployés. Le Moniteur réseau constitue également un point d'entrée pour l'exécution des API Swagger, le développement d'un réseau avec la plateforme {{site.data.keyword.blockchainfull_notm}} : Develop, et le test de modèles d'application.
{:shortdesc}

Le Moniteur réseau présente les écrans suivants dans trois sections. Vous pouvez accéder à chaque écran dans le navigateur de gauche du Moniteur réseau.
- La section **Mon réseau** contient les écrans "[Présentation](#overview)", "[Membres](#members)", "[Canaux](#channels)", "[Notifications](#notifications)" et "[API](#apis)".
- La section **Mon code** contient les écrans "[Ecriture de code](#write_code)", "[Installer le code](#chaincode)" et "[Essayer les modèles](#samples)".
- L'écran "[Obtenir de l'aide](#support)".

Vous pouvez [basculer entre les organisations](#switch_organizations) dont vous êtes propriétaire et [réinitialiser n votre réseau](#reset_network) à partir du menu déroulant dans l'angle supérieur droit du Moniteur réseau.

Ce tutoriel décrit chacun des écrans et fonctions ci-dessus.

## Présentation
{: #overview}

L'écran "Présentation" affiche des informations d'état en temps réel concernant vos ressources blockchain, notamment le programme de tri, l'autorité de certification et l'homologue. Chaque ressource s'affiche sous quatre en-têtes distincts : **Type**, **Nom**, **Statut** et **Actions**. Lorsque votre réseau démarre, un programme de tri, une autorité de certification et un homologue s'exécutent. L'autorité de certification est spécifique à l'organisation, alors que le programme de tri est un noeud final commun qui est partagé au sein du réseau.

La **Figure 1** illustre l'écran "Présentation" :

![Présentation du réseau](images/myresources_starter.png "Présentation du réseau")
*Figure 1. Présentation du réseau*

### Actions de noeud
  L'en-tête **Actions** du tableau comporte des boutons qui permettent de démarrer ou d'arrêter vos composants. Vous pouvez également démarrer ou arrêter un groupe de noeuds en sélectionnant plusieurs noeuds et en cliquant sur le bouton **Démarrer les éléments sélectionnés** ou **Arrêter les éléments sélectionnés**. Le bouton **Démarrer les éléments sélectionnés** ou **Arrêter les éléments sélectionnés** apparaît au-dessus du tableau lorsque vous sélectionnez un ou plusieurs noeuds.

  Vous pouvez également consulter les journaux de composant en cliquant sur **Afficher les journaux** dans la liste déroulante sous l'en-tête **Actions**. Ces journaux présentent les appels de procédure entre les différentes ressources réseau et ils sont utiles pour le débogage et le traitement des incidents. Vous pouvez par exemple les tester en arrêtant un homologue et en le ciblant avec une transaction ; vous verrez alors des erreurs de connectivité. Lorsque vous redémarrez l'homologue et relancez la transaction, vous verrez qu'une connexion est réussie. Vous
pouvez aussi arrêter un homologue pendant une longue période alors que vos canaux continuent à effectuer des transactions. l'homologue est redémarré, vous remarquez une synchronisation du registre dès qu'il reçoit les blocs qui ont été validés alors qu'il était arrêté. Une fois que le registre est complètement synchronisé, vous pouvez procéder à des appels et des requêtes normaux.

### Profil de connexion
  Vous pouvez consulter le ficher JSON pour les informations réseau de faible niveau de chaque ressource en cliquant sur le bouton **Profil de connexion**. Le profil de connexion contient toutes les informations de configuration dont vous avez besoin pour une application. Cependant, ce fichier contient uniquement les adresses de vos composants spécifiques et du programme de tri ; si vous devez cibler des homologues supplémentaires, vous devez obtenir leurs noeuds finaux. L'en-tête "url" affiche le noeud final d'API pour chaque composant. Ces noeuds finaux sont requis pour cibler les composants réseau spécifiques d'une application côté client, et leurs définitions résident généralement dans un fichier de configuration modélisé JSON qui est fourni avec l'application. Si vous personnalisez une application qui nécessite l'adhésion d'homologues qui ne font pas partie de votre organisation, vous devrez obtenir ces adresses IP auprès des opérateurs concernés dans le cadre d'une opération externe. Les clients doivent pouvoir se connecter aux homologues dont ils attendent une réponse.

### Ajout d'homologues
{: #peers}
Les membres du réseau doivent comporter des homologues qui stockent leurs copies de registre et exécutent du code blockchain pour interroger ou mettre à jour le registre. Si la règle d'adhésion définit un homologue en tant qu'homologue d'adhésion, l'homologue renvoie également les résultats d'adhésion aux applications.

  Le plan Starter crée un homologue pour chacune des deux organisations par défaut. Vous pouvez ajouter d'autres homologues pour vos organisations en fonction de vos besoins. Vous pouvez vous trouver dans différents scénarios lorsque vous avez besoin d'homologues supplémentaires. Par exemple, vous pouvez souhaiter que plusieurs homologues rejoignent le même canal à des fins de redondance. Chaque homologue traite les transactions du canal et leurs copies respectives du registre. Dans le cas où l'un des homologues est défaillant, les autres peuvent poursuivre le traitement des transactions et des demandes d'application. Vous pouvez équilibrer de manière symétrique toutes les demandes d'applications entre homologues, ou vous pouvez cibler différents homologues pour différentes fonctions. Par exemple, vous pouvez utiliser un homologue pour interroger le registre et utiliser un autre homologue pour traiter les adhésions pour les mises à jour du registre.

  Cliquez sur le bouton **Ajouter des homologues** dans l'angle supérieur droit pour ajouter des noeuds homologue à votre réseau. Dans la fenêtre contextuelle "Ajouter des homologues", sélectionnez le nombre et la taille des noeuds homologue que vous voulez ajouter.


## Membres
{: #members}

L'écran "Membres" comporte deux onglets qui affichent des informations relatives aux membres du réseau (onglet "Membres") et des informations sur les certificats (onglet "Certificats").

### Membres
{: #members_tab}
La **Figure 2** illustre l'écran "Membres" initial qui affiche les membres de votre réseau sous l'onglet "Membres" :

![Onglet Membres de l'écran Membres](images/monitor_members_starter.png "Membres du réseau")
*Figure 2. Membres du réseau*

Cliquez sur **Ajouter un membre** pour inviter d'autres membres à rejoindre votre réseau. Dans le plan Starter, vous avez deux options :
- **Inviter un membre**. Vous pouvez inviter d'autres organisations à devenir membres du réseau. Les organisation invitées peuvent rejoindre votre réseau et collaborer avec vous.
- **Créer un membre**. Vous pouvez également créer un membre en utilisant votre adresse e-mail. Vous avez sur ce dernier le même contrôle que sur les deux organisations que vous recevez avec le plan Starter par défaut.

La **Figure 3** illustre l'écran "Ajouter un membre". 

![Ajouter un membre](images/invite_member_starter.png "Ajouter un membre")
*Figure 3. Ajouter un membre*

### Certificats
La **Figure 4** présente l'écran "Membres" initial qui affiche les certificats de membre sous l'onglet "Certificats" :

![Onglet Certificats de l'écran Membres](images/monitor_certificates_starter.png "Certificats")
*Figure 4. Certificats*

Les opérateurs peuvent gérer les certificats des membres d'une même institution sous l'onglet "Certificats". Cliquez sur **Ajouter le certificat** pour afficher l'écran "Ajouter le certificat". Donnez un nom à votre certificat, collez vos certificats côté client au format PEM dans la zone "Clé", puis cliquez sur **Soumettre**. Vous devez redémarrer vos homologues pour que les certificats côté client puissent être pris en compte.

Pour plus d'informations sur la génération de votre clé de certificat, voir [Génération de certificats côté client](v10_application.html#generating-the-client-side-certificates).


## Canaux
{: #channels}

Les canaux, qui se composent d'un sous-ensemble de membres réseau qui souhaitent effectuer des transactions en privé, fournissent l'isolement de données et la confidentialité en autorisant les membres d'un canal à établir des règles spécifiques et un registre distinct, auxquels seuls les membres du canal peuvent accéder. Chaque réseau doit comporter au moins un canal pour que les transactions puissent s'effectuer. Chaque canal a un registre unique et les utilisateurs doivent être correctement authentifiés pour exécuter des opérations de lecture/écriture sur ce registre. Si vous n'êtes pas sur un canal, vous ne pouvez voir aucune donnée.

La **Figure 5** illustre l'écran de tableau de bord initial qui affiche une présentation de tous les canaux de votre réseau.

![Canaux](images/channels_starter.png "Canaux")
*Figure 5. Canaux*

La création d'un canal entraîne la génération d'un registre spécifique à un canal. Pour plus d'informations, voir [Création d'un canal](howto/create_channel.html).

Vous pouvez aussi sélectionner un canal existant afin d'afficher des détails plus précis sur ce canal, l'appartenance et les codes blockchain actifs. Pour plus d'informations, voir [Surveillance d'un réseau](howto/monitor_network.html).


## Notifications
{: #notifications}

Vous pouvez traiter les demandes en attente et consulter les demandes terminées dans l'écran "Notifications".

La **Figure 6** illustre l'écran "Notifications" :

![Notifications](images/notifications_starter.png "Notifications")
*Figure 6. Notifications*

Lorsque vous créez un canal ou êtes invité à rejoindre un nouveau canal, une notification s'affiche dans le moniteur réseau.

Les demandes sont regroupées dans les sous-onglets "Toutes", "En attente" et "Terminée". Les nombres figurant à la suite de l'en-tête indiquent le nombre de demandes dans chaque sous-onglet.
   * Vous pouvez trouver toutes vos demandes sous le sous-onglet "Toutes".
   * Les demandes que vous n'avez pas acceptées ou que vous avez refusées, ou que vous n'avez pas encore consultées, figurent sous le sous-onglet "En attente". Cliquez sur le bouton **Inspecter la demande** pour consulter la demande, qui comporte la règle de canal et les membres, ainsi que le statut de vote. Si vous être un opérateur de canal, vous pouvez soit **Accepter** soit **Décliner** la demande, ou la traiter à un autre moment en cliquant sur **Plus tard**. Si la demande est acceptée par suffisamment d'opérateurs de canal, vous pouvez cliquer sur **Soumettre une demande** pour activer la mise à jour de canal.
   * Une demande soumise apparaît alors dans le sous-onglet "Terminée".  Vous pouvez cliquez sur **Inspecter la demande** pour afficher ses détails.

Si vous avez une longue liste de demandes, vous pouvez rechercher dans la zone de recherche située dans la partie supérieure de l'écran.

Les demandes en attente peuvent être supprimées en sélectionnant la case en regard et en cliquant sur **Supprimer la demande**.


## API
{: #apis}

Pour faciliter le développement d'applications, la plateforme {{site.data.keyword.blockchainfull_notm}} expose les API que vous pouvez tester sur votre réseau dans une interface utilisateur Swagger.

La **Figure 7** illustre l'écran "API" :

![API](images/API_screen_starter.png "API")
*Figure 7. API*

Cliquez sur le lien **Interface utilisateur swagger** pour ouvrir l'identificateur Swagger. Notez que vous devez autoriser l'interface utilisateur swagger à l'aide de vos données d'identification réseau (qui se trouvent sur la page d'API) avant d'exécuter les API. Pour plus de détails, voir [Test des API avec Swagger](howto/swagger_apis.html).


## Ecriture de code
{: #write-code}

Le plan Starter intègre la plateforme {{site.data.keyword.blockchainfull_notm}} : Develop et fournit un environnement de développement avec des outils et des technologies standard du secteur. Vous pouvez développer votre réseau dans l'environnement en ligne ou en local. Dès que vous avez développé un réseau, vous pouvez le redéployer dans votre réseau de plan Starter.

La **Figure 8** illustre l'écran "API" :

![Ecriture de code](images/write_code_starter.png "Ecriture de code")
*Figure 8. Ecriture de code*

Pour plus d'informations sur le développement et le déploiement de votre code avec le plan Starter, voir [Déploiement d'un réseau d'entreprise dans un plan Starter](develop_starter.html).


## Installer le code
{: #chaincode}

Les codes blockchain, également appelés "contrats intelligents", sont les éléments logiciels qui contiennent un ensemble de fonctions permettant d'interroger et de mettre à jour le registre. Ils sont installés sur des homologues et instanciés sur un canal.

La **Figure 9** illustre l'écran "Installer le code" :

![Installer le code](images/chaincode_install_overview_starter.png "Installer le code")
*Figure 9. Code blockchain*

Un code blockchain est tout d'abord installé sur le système de fichiers d'un homologue, puis il est instancié sur un canal. Pour plus d'informations, voir [Installation et instanciation d'un code blockchain](howto/install_instantiate_chaincode.html).


## Essayer les modèles
{: #samples}

Des modèles d'application vous permettent d'avoir une meilleure compréhension d'un réseau de blockchain et du développement d'application. Le plan Starter vous permet de déployer et de lancer des modèles d'application dans le Moniteur réseau.

La **Figure 10** illustre l'écran "Essayer les modèles" :

![Essayer les modèles](images/sample_overview_starter.png "Essayer les modèles")
*Figure 10. Essayer les modèles*

L'exemple de déploiement optimise le [service DevOps Toolchain![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://console.bluemix.net/devops/toolchains) pour automatiser votre processus de contrôle des sources, de delivery pipeline et d'activation du code blockchain. Sélectionnez un modèle d'application, puis cliquez sur **Deployer via Toolchain**. Pour plus d'informations, voir [Déploiement de modèles d'application](howto/prebuilt_samples.html).


## Obtenir de l'aide
{: #support}

L'écran "Obtenir de l'aide" comporte deux onglets qui fournissent des informations de support sous l'onglet "Support" et une description des fonctions nouvelles et modifiées de chaque édition sous l'onglet "Notes sur l'édition".

La **Figure 11** illustre l'écran "Support" initial qui comporte des informations de support sous l'onglet "Support" :

![Support](images/support_starter.png "Support")
*Figure 11. Support Blockchain*

Utilisez les liens et les ressources de cet écran pour accéder à des forums de dépannage et de support.

* [Docs de service {{site.data.keyword.blockchainfull_notm}}](index.html), qui est le présent site de documentation, fournit une aide sur la mise en route de la plateforme {{site.data.keyword.blockchainfull}} sur {{site.data.keyword.Bluemix_notm}}. Vous pouvez accéder aux rubriques correspondantes depuis le navigateur de gauche ou rechercher un terme à l'aide de la fonction de recherche située en haut de l'écran.
* [IBM Developer Works ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://developer.ibm.com/blockchain/) sous **Aide communautaire** comporte des ressources et des informations pour les développeurs.
* [IBM dWAnswers ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://developer.ibm.com/answers/smartspace/blockchain/) sous **Ticket de demande de service** fait office de plateforme pour les questions et les réponses. Vous pouvez rechercher des réponses à des questions préalablement posées ou soumettre une nouvelle question. Assurez-vous d'inclure le mot clé **blockchain** dans votre question.
  Vous pouvez également soumettre un ticket pour l'équipe de support {{site.data.keyword.blockchainfull_notm}} à l'aide de l'option **Ouvrir un ticket de demande de service {{site.data.keyword.Bluemix_notm}}**. Partagez les détails et les fragments de code de votre instance {{site.data.keyword.Bluemix_notm}} spécifique.
* [Modèles d'application![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://github.com/ibm-blockchain) sous **Modèles d'application blockchain** fournit une aide et des exemples de fragment de code pour vous aider dans le développement d'applications.
* [Hyperledger Fabric ![Icône de lien externe](images/external_link.svg "Icône de lien externe")](http://hyperledger-fabric.readthedocs.io/) et [Communauté Hyperledger Fabric![Icône de lien externe](images/external_link.svg "Icône de lien externe")](http://jira.hyperledger.org/secure/Dashboard.jspa) sous **Hyperledger Fabric** fournissent des données plus détaillées sur la pile Hyperledger Fabric.
  Dialoguez avec un [expert Hyperledger![Icône de lien externe](images/external_link.svg "Icône de lien externe")](https://chat.hyperledger.org/channel/general) si vous avez des questions sur le code Hyperledger Fabric.

Si vous ne parvenez pas à déboguer votre problème ou à obtenir une réponse à votre question, soumettez un cas sur le portail IBM Cloud Service Portal. Pour plus d'informations, voir [Support](ibmblockchain_support.html).

La **Figure 12** illustre l'écran "Support" initial qui comporte les fonctions nouvelles et modifiées de chaque édition sous l'onglet "Notes sur l'édition" :

![Notes sur l'édition Helios](images/releasenotes_helios_starter.png "Notes sur l'édition Helios")
![Notes sur l'édition Fabric](images/releasenotes_Fabric_starter.png "Notes sur l'édition Fabric")
*Figure 12. Notes sur l'édition*


## Basculement entre les organisations
{: #switch-organizations}

Si vous simulez un réseau de blockchain pour plusieurs organisations sur votre réseau, vous pouvez basculer entre les organisations dont vous êtes propriétaire, par exemple, l'organisation A. Ensuite, vous pouvez afficher et gérer les ressources réseau de l'organisation A, par exemple les homologues, les canaux et les codes blockchain dans le Moniteur réseau. Cette fonction vous permet de créer un canal en appliquant les stratégies de canal et en ajoutant des homologues de plusieurs organisations au canal.

Cliquez dans l'angle supérieur droit de l'interface utilisateur, où vous devez voir votre nom. Dans le menu déroulant sous **Changer d'organisation**, choisissez le nom de l'organisation vers laquelle vous souhaitez basculer. L'organisation A est sélectionnée par défaut. Une fois que vous avez choisi une organisation vers laquelle basculer, votre Moniteur réseau est automatiquement actualisé et vous pouvez voir le réseau de cette organisation.

La **Figure 13** présente la fonction de "basculement entre les organisations" :

![Basculer entre les organisations](images/switch_orgs.png "Basculer entre les organisations")
*Figure 13. Basculement entre les organisations


## Réinitialisation du réseau
{: #reset-network}

Le plan Starter vous offre la possibilité de modifier votre configuration réseau sans supprimer et recréer un réseau. Votre réseau est réinitialisé sur sa configuration réseau initiale, qui comprend deux organisations, un homologue par organisation, ainsi qu'un canal par défaut. Ceci est utile, par exemple, lorsque vous exécutez des tests sur le réseau de blockchain, ce qui vous permet de reprendre à partir d'un réseau relativement propre.

**Attention **: Une fois que vous avez réinitialisé le réseau, les noeuds finaux d'API de vos homologues, le programme de tri et l'autorité de certification sont modifiés. Vous devez ajuster les informations de noeud final d'API dans vos applications.

Cliquez dans l'angle supérieur droit et ouvrez le menu déroulant. Cliquez sur le bouton **Réinitialiser le réseau**. Si vous êtes prêt à réinitialiser votre réseau, cliquez sur **OK** pour continuer. Votre Moniteur réseau est actualisé pour refléter les nouveaux paramètres.

La **Figure 14** présente la fonction de "basculement entre les organisations" :

![Réinitialiser le réseau](images/reset_network.png "Réinitialiser le réseau")
*Figure 14. Réinitialiser le réseau*
