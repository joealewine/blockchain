---

copyright:
  years: 2017, 2018
lastupdated: "2018-3-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Distribuzione di una rete di business su Enterprise Plan

Gli strumenti per gli sviluppatori di {{site.data.keyword.blockchainfull}} Platform: Develop ti aiutano a creare una BND (**Business Network Definition**) che può quindi essere impacchettata in un archivio di rete di business (`.bna`). L'ambiente per gli sviluppatori ti consente di distribuire i file `.bna` a una {{site.data.keyword.blockchain}} locale o cloud per lo sviluppo e la condivisione.

Questa esercitazione si occupa del passo successivo di un ciclo di vita della rete di business, che consiste nell'attivare la tua rete di business distribuendo il `.bna` a {{site.data.keyword.blockchainfull_notm}} Platform Enterprise Plan.

## Prima di cominciare

Assicurati di avere installato l'ambiente per gli sviluppatori {{site.data.keyword.blockchainfull}}: Develop e di essere a tuo agio con lo sviluppo e la distribuzione di rete di business. Le istruzioni relative alla scrittura di reti di business sono disponibili nella [documentazione di Hyperledger Composer](https://hyperledger.github.io/composer/latest/business-network/business-network-index).

Devi accedere a un'istanza Enterprise Plan di {{site.data.keyword.blockchainfull_notm}} Platform. Per ulteriori informazioni su {{site.data.keyword.blockchainfull_notm}} Platform Enterprise Plan, vedi la [panoramica di Enterprise Plan](./enterprise_plan.html).

## Passo uno: Creazione di un profilo di connessione per {{site.data.keyword.blockchainfull_notm}} Platform

1. Crea una directory per memorizzare i tuoi dettagli della connessione, ad esempio:

        /Users/myUserId/.composer-connection-profiles/bmx-hlfv1

    Ogni profilo di connessione deve contenere un file `connection.json`. Crea una nuova directory in `.composer-connection-profiles`, in questo caso `bmx-hlfv1`. Questo sarà il nome del profilo che userai quando lavorerai con Hyperledger Composer e {{site.data.keyword.blockchainfull_notm}} Platform.

        mkdir -p ~/.composer-connection-profiles/bmx-hlfv1
        cd ~/.composer-connection-profiles/bmx-hlfv1

2. Dovresti avere ora la seguente struttura di directory:

        /Users/myUserId/.composer-connection-profiles/bmx-hlfv1

    Crea un file nel nome directory appena creato e denominalo `connection.json`. Puoi utilizzare il seguente modello per il file `connection.json`:

        {
            "name": "bmx-hlfv1",
            "description": "A description for a V1 Profile",
            "type": "hlfv1",
            "orderers": [
                {
                    "url": "grpcs://abca.4.secure.blockchain.ibm.com:12345"
                }
            ],
            "ca": {
                "url": "https://abc.4.secure.blockchain.ibm.com:98765",
                "name": "PeerOrg1CA"
            },
            "peers": [
                {
                    "requestURL": "grpcs://abcd.4.secure.blockchain.ibm.com:22222",
                    "eventURL": "grpcs://abcd.4.secure.blockchain.ibm.com:33333"
                }
            ],
            "keyValStore": "/Users/jeff/.composer-credentials-mychannel-hsbn",
            "channel": "mychannel",
            "mspID": "PeerOrg1",
            "globalCert": "-----BEGIN CERTIFICATE-----\r\n...LotsOfStuff\r\n-----END CERTIFICATE-----\r\n-----BEGIN CERTIFICATE-----\r\nMorestuff\r\n-----END CERTIFICATE-----\r\n",
            "timeout": 300
        }

    Compilerai il file `connection.json` appena creato con gli attributi forniti tramite il tuo dashboard {{site.data.keyword.blockchainfull_notm}} Platform. Dal tuo dashboard, seleziona **Overview**, quindi il pulsante **Service Credentials** per visualizzare le informazioni su endpoint e certificato per i membri del canale.

## Passo due: Aggiunta delle informazioni sull'ordinante

1. Ora possiamo iniziare a modificare il modello con le informazioni fornite dalle Credenziali del servizio. Nelle Credenziali del servizio ci potrebbero essere più ordinanti ma ne è richiesto solo uno per un file `connection.json`.

    Sostituisci i valori dell'url dell'ordinante con le informazioni pertinenti per le tue credenziali di servizio nel seguente formato: 

        “url”: “grpcs://abca.4.secure.blockchain.ibm.com:12345”

## Passo tre: Aggiunta delle informazioni dell'Autorità di certificazione

1. Sostituisci il valore ca in `connection.json` con sia l'**url** che il **caName** dalle rispettive voci nella sezione **certificateAuthorities**.

## Passo quattro: Aggiunta delle informazioni dei peer

1. È necessario impostare **requestURL** e **eventURL** per ogni peer. Sostituisci l'attributo **url** con il valore **url** disponibile nelle credenziali del servizio. Sostituisci l'attributo **eventURL** con l'**eventUrl** presente nelle tue Credenziali del servizio. Dopo aver apportato le modifiche, la sezione peer di `connection.json` dovrebbe avere il seguente formato:

        "peers": [
          {
              "requestURL": "grpcs://abca.4.secure.blockchain.ibm.com:12345",
              "eventURL": "grpcs://abca.4.secure.blockchain.ibm.com:12345"

## Passo cinque: Aggiunta delle informazioni keyValStore

1. Imposta l'attributo **keyValStore** in modo che punti alla directory appropriata. Crea una directory da utilizzare per il tuo **keyValStore**. Ad esempio, una nuova directory sotto la tua directory home denominata `.composer-credentials-mychannel`. Assicurati che l'attributo **keyValStore** punti alla tua directory appena creata nel seguente formato:

        "keyValStore": "/Users/myUserId/.composer-credentials-mychannel",

## Passo sei: Aggiunta delle informazioni del canale

1. Sostituisci il valore di canale in `connection.json` in modo che corrisponda al canale in cui intendi creare e distribuire la tua rete di business.

## Passo sette: Aggiunta di un mspID

Il valore **mspID** nel tuo file `connection.json` dovrebbe essere impostato sull'mspID della tua organizzazione. Le credenziali del servizio forniscono un elenco delle organizzazioni con i loro valori mspid associati. Devi utilizzare il valore dall'attributo **mspid** per la tua organizzazione.

## Passo otto: Aggiunta del globalCert
1. {{site.data.keyword.blockchainfull_notm}} Platform utilizza un certificato TLS comune per gli ordinanti e i peer. Per ogni ordinante e peer, c'è un attributo **tlsCACerts** che contiene lo stesso certificato. Sostituisci il valore fittizio nel file `connection.json` con il valore **tlsCACerts**. Dovrebbe assumere il seguente formato:

        "globalCert": "-----BEGIN CERTIFICATE-----\r\.......

## Passo nove: Preparazione dei tuoi peer

**Nota**: questo passo **deve** essere eseguito prima che crei il canale a cui distribuire una rete di business. Se questo passo viene eseguito dopo la creazione del canale, una rete di business distribuita **non verrà avviata**.

Nel documento delle credenziali di servizio, in **certificateAuthorities**, c'è un attributo **registrar** che contiene gli attributi per **enrollId** e **enrollSecret** nel seguente formato:

        "registrar": [
            {
                "affiliation": "org1",
                "enrollId": "admin",
                "enrollSecret": "PA55W0RD12"
            }
        ],

1. Richiedi i certificati utilizzando il seguente comando:

        composer identity request -p bmx-hlfv1 -i admin -s PA55W0RD12

    Questo scarica tre file nella directory `.identityCredentials` sotto la tua directory home. I file rilevanti sono basati su **enrollId**. Quindi, nell'esempio di cui sopra, ci saranno due file denominati **admin-pub.pem** e **admin-priv.pem**

3. Seleziona **Members** dal menu di navigazione e seleziona quindi l'opzione di menu **Certificates** e fai clic sul pulsante **Add Certificate**.

4. Immetti un nome univoco per questo certificato nel campo **Name**; questo nome non può includere trattini o segni meno.

5. Apri il file `admin-pub.pem` creato in precedenza e copia il contenuto di questo file nel campo **Key** e premi il pulsante **Submit**.

6. Utilizza l'interfaccia utente per arrestare i peer e quindi per avviarli.

7. Il certificato dovrebbe ora essere presente nell'elenco di certificati.

## Passo dieci: Creazione del tuo canale

1. Seleziona **Channels** dal menu di navigazione nel pannello di sinistra e fai clic sul pulsante **New Channel**.

2. Immetti un nome canale e una descrizione facoltativa e fai clic su **Next**. Nota: il nome canale deve corrispondere al nome da te specificato nel profilo di connessione per l'attributo del canale.

3. Concedi le autorizzazioni come necessario e fai clic su **Next**.

4. Seleziona la politica del numero di operatori che devono accettare gli aggiornamenti del canale e inoltra la richiesta.

5. Dovresti ora essere indirizzato alla sezione **Notifications** dove dovrebbe esserci una nuova richiesta da revisionare. Fai clic sul pulsante **Review Request**.

6. Fai clic sul pulsante **Accept**; verrai riportato alla sezione **Notifications** dove puoi vedere che la richiesta può ora essere inoltrata. Fai clic sul pulsante **Submit Request** per aprire la finestra di dialogo di inoltro e fai quindi clic sul pulsante **Submit**. Il nuovo canale è stato creato.

7. Seleziona **Channels** dal menu di navigazione. Il nuovo canale è presente nell'elenco di canali e dovrebbe avere “No peers added yet”. Fai clic sul menu delle azioni accanto ad esso e seleziona **Join Peers**. Seleziona le caselle di spunta accanto ai peer che vuoi aggiungere e premi **Add Selected**.

## Passo undici: Importazione di una nuova identità per amministrare la tua rete di business

Crea un'identità in Composer utilizzando i certificati richiesti in precedenza. Questa nuova identità disporrà dell'autorizzazione necessaria per installare il chaincode nei peer che hanno il tuo certificato pubblico caricato e sarà un emittente per le Autorità di certificazione.

1. Per creare la nuova identità, esegui questo comando:

        composer identity import -p bmx-hlfv1 -u admin -c ~/.identityCredentials/admin-pub.pem -k ~/.identityCredentials/admin-priv.pem

    Dove `bmx-hlfv1` è il nome del profilo da te precedentemente creato. Ora siamo pronti a distribuire il tuo `.bna` a{{site.data.keyword.blockchainfull_notm}} Platform.


## Passo dodici: Distribuzione della rete di business

Ora puoi distribuire il tuo file `.bna` a {{site.data.keyword.blockchainfull_notm}} Platform.

1. Con l'identità da te creata nel passo precedente, distribuisci la rete di business utilizzando il seguente comando:

        composer network deploy -a myNetwork.bna -p bmx-hlfv1 -i admin -s anyString
