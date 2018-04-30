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

# Test des API avec Swagger

La plateforme {{site.data.keyword.blockchainfull}} expose un certain nombre d'API REST pour simplifier le développement de vos applications. Vous pouvez les tester sur vos réseaux de blockchain à l'aide d'une interface utilisateur Swagger.
{:shortdesc}

Avant de commencer, vous devez créer une instance de service de plateforme [{{site.data.keyword.blockchain}} ![Icône de lien externe](../images/external_link.svg "Icône de lien externe")](https://console.bluemix.net/catalog/services/blockchain) on {{site.data.keyword.Bluemix_notm}} et créer ou rejoindre le réseau de <!--or Enterprise Plan -->blockchain d'un plan Starter.


## Extraction des données d'identification réseau

Accédez au Moniteur réseau de votre réseau de blockchain et ouvrez l'écran "API" dans le navigateur de gauche. Vous pouvez voir vos données d'identification réseau pour les API REST. Vous pourrez autoriser ultérieurement les API à l'aide des valeurs de "key" et "secret" affichées ici, puis exécuter les API avec "network_id" comme paramètre. Cliquez sur **Show secret** pour afficher la valeur de la zone de valeur confidentielle. Copiez les valeurs des zones key, secret et network_id, que vous pouvez utiliser plus tard dans l'interface utilisateur Swagger.

<!-- Removing this code snippet so people don't try to use these values
```
},
   "x-api": {
       "url": "https://ibmblockchain.bluemix.net",
       "key": "PeerOrg1",
       "network_id": "e1f5b3341b1d483bbaf829f601144023",
       "secret": "71a329aabde9ff20de0aa4bfafd72a4466d78c87f637e7ff92c2534b5ce81cc0"
   }
```
-->

La **Figure 1** illustre l'écran "API" :
![Ecran Présentation](../images/restAPI.png)
*Figure 1. API*

Si vous utilisez le plan Starter, il est possible de basculer entre les organisations dans le Moniteur réseau. Avec le plan Starter, deux organisations sont configurées par défaut. le basculement entre organisations peut être utile pour tester les API REST du point de vue de chaque organisation. Pour obtenir les données d'identification d'une autre organisation de votre réseau, cliquez sur votre nom d'utilisateur dans l'angle supérieur droit de la console Moniteur réseau. Dans le menu qui s'ouvre, cliquez sur la flèche déroulante en regard de la vue Organisation pour afficher toutes les organisations. Sélectionnez l'organisation vers laquelle vous voulez basculer et afficher les données d'identification réseau associées.

La **Figure 2** illustre le basculement entre organisations :
![Basculement entre organisations](../images/restAPIOrganization.png)
*Figure 2. Basculement entre organisations*


## Autorisation d'API Swagger

Cliquez sur le lien **Interface utilisateur swagger** sur l'écran "API" pour ouvrir l'interface utilisateur swagger.  
<!-- remove this line because the link is different depending on if you are starter or enterprise plan
You can also open the Swagger UI with the URL in the connection profiles. For example, `http://blockchain-swagger-dev.stage1.mybluemix.net`.
-->

Dans l'interface utilisateur swagger, cliquez sur le bouton **Autoriser** afin d'ouvrir la fenêtre d'autorisation. Entrez la valeur de "key" et "secret" dans vos données d'identification réseau en tant que nom d'utilisateur et mot de passe, puis cliquez sur **Autoriser** et **Terminé**. Vous êtes maintenant prêt à exécuter les API. Notez que si vous actualisez votre navigateur, vous devez autoriser de nouveau avec vos données d'identification.

Avec l'authentification de base, les données d'identification que vous indiquez dans la fenêtre Autoriser sont stockées dès que vous cliquez sur les boutons **Autoriser** et **Terminé** et elles sont transmises sur chaque appel d'API REST.

La **Figure 3** illustre la fenêtre en incrustation "Autoriser" :
![Fenêtre en incrustation Autoriser](../images/swaggerUIAuthorize.png)
*Figure 3. Fenêtre en incrustation Autoriser*


## Test des API

Cliquez sur l'API REST que vous voulez exécuter puis sur le bouton **Essayez**. Entrez les paramètres obligatoires et cliquez sur **Exécuter**. L'appel API REST s'exécute sur votre réseau.

La **Figure 4** illustre l'"interface utilisateur swagger" :
![Swagger UI](../images/swaggerUITryItOut.png)
*Figure 4. Swagger UI*


## Conseils pour l'identification et la résolution des problèmes

### 401 non autorisé  
  Vérifiez que vous avez autorisé les API REST en indiquant vos données d'identification réseau. Pour plus de détails, voir [Autorisation d'API Swagger](#authorizing-swagger-apis).

### 400 Erreur : Demande incorrecte
  Certaines API peuvent prendre un argument dans le corps de la demande qui fait office de filtre pour afficher les résultats uniquement pour un homologue spécifique. Un exemple de fragment est fourni dans le corps, lequel s'il est utilisé, doit être édité pour indiquer l'homologue ou la liste des homologues sur lesquels vous voulez filtrer. Pour éviter cette erreur, éditez le fragment afin d'indiquer un homologue de votre réseau ou de retirer le fragment dans son intégralité.
