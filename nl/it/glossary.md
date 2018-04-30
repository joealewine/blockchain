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
{:tip: .tip}

# Glossario
{: #glossary}

{{site.data.keyword.blockchainfull}} Platform semplifica la tua esperienza sulla blockchain. Questo argomento definisce i termini che compaiono in questa documentazione e intende offrirti un'introduzione ai concetti della blockchain. Per una comprensione più approfondita dei termini, puoi consultare [Hyperledger Fabric ![Icona link esterno](images/external_link.svg "Icona link esterno")](http://hyperledger-fabric.readthedocs.io/en/master/glossary.html).
{:shortdesc}

## Asset
Beni, servizi o proprietà tangibili o intangibili rappresentati come un elemento che viene negoziato sulla rete blockchain.

## Blocco
Un set ordinato di transazioni, che è crittograficamente collegato al precedente blocco su un canale.

## Rete di business
Una definizione di una rete blockchain che include il modello di dati, la logica di transazione e le regole di controllo accessi per la tua soluzione blockchain. Le BND (Business Network Definition) vengono create utilizzando [Hyperledger Composer](#hyperledger-composer). Le BND (Business Network Definition) sono assemblate in file **.bna** (business network archive) distribuibili.

## CA
Acronimo di Certificate Authority, ossia Autorità di certificazione. Una risorsa di rete blockchain che emette i certificati per tutti i membri partecipanti. Questi certificati rappresentano l'identità di un membro. Tutte le entità nella rete (peer, ordinanti, client ecc.) devono avere un'identità per comunicare, autenticare e, alla fine, interagire con il libro mastro. Queste identità sono richieste per qualsiasi partecipazione diretta nella rete blockchain. Puoi creare una scheda di rete di business per la CA. La [scheda CA](develop_starter.html#developing-business-networks-with-starter-plan) può quindi essere importata e verrà utilizzata per scambiare il segreto di amministrazione (admin secret) per i certificati validi dall'Autorità di certificazione di Starter Plan.

## Catena
La catena del libro mastro è un log di transazioni strutturato come blocchi di transazioni collegati da hash. I peer ricevono i blocchi di transazioni dal servizio di ordinazione, contrassegnano le transazioni del blocco come valide o non valide, in base alle politiche di approvazione e alle violazioni della concorrenza, e accodano il blocco alla catena hash sul file system del peer.

## Chaincode
Noti anche come "smart contract", i chaincode sono parti di software che contengono una serie di funzioni per eseguire query o aggiornamenti del libro mastro.

## Canale
Consiste in un sottoinsieme di membri della rete che vogliono eseguire transazioni in privato. I canali forniscono l'isolamento e la confidenzialità dei dati consentendo ai membri di un canale di stabilire delle specifiche regole e un libro mastro separato a cui possono accedere solo i membri del canale. I peer, che sono i nodi che fungono da endpoint delle transazioni per le organizzazioni, vengono uniti ai canali.

## Client
Il client rappresenta l'entità che agisce per conto di un utente. Deve connettersi a un peer per comunicare con la blockchain. Il client può connettersi a qualsiasi peer di sua scelta. I clienti creano e quindi richiamano le transazioni. Il client inoltra un effettivo richiamo della transazione agli approvatori e trasmette le proposte di transazione al servizio di ordinazione.

## Profilo di connessione
Il profilo di connessione è visibile nella schermata "Overview" del Network Monitor quando si fa clic sul pulsante **Connection Profile**. Le informazioni sono disponibili in formato JSON e contengono le informazioni sugli endpoint API e gli ID registrazione(enrollID)/i segreti per le tue risorse di rete, ossia peer, ordinanti e CA. La tua applicazione interagisce con le risorse di rete tramite questi endpoint API.

## Consenso
Un processo collaborativo per mantenere le transazioni del libro mastro sincronizzate nella rete. Il consenso garantisce che i libri mastri vengano aggiornati solo quando gli appropriati partecipanti approvano le transazioni e che i libri mastri vengano aggiornati con le stesse transazioni nello stesso ordine. Ci sono molti modi algoritmici differenti per raggiungere il consenso.

## Adesione dinamica
Un membro può essere aggiunto dinamicamente alla rete da un utente con il privilegio di **registrar** (conservatore del registro). Ai membri vengono anche assegnati ruoli e attributi che controllano il loro accesso e la loro autorizzazione sulla rete. Né i ruoli né gli attributi possono essere però assegnati dinamicamente. Hyperledger Fabric supporta l'aggiunta o la rimozione di membri, peer e nodi di servizio di ordinazione, senza compromettere il funzionamento della rete complessiva. L'adesione dinamica è critica quando le relazioni di business vengono regolate ed è necessario, per vari motivi, aggiungere o rimuovere entità.

## Approvazione
Il processo con cui le transazioni chaincode sono convalidate. Le regole di approvazione vengono implementate specificando le politiche di approvazione.

## Politica di approvazione
Definisce i nodi peer su un canale che devono eseguire le transazioni che sono collegate a una specifica applicazione chaincode e la combinazione richiesta di risposte (approvazioni). Una politica potrebbe richiedere che una transazione sia approvata da un numero minimo di peer di approvazione, una percentuale minima di peer di approvazione o da tutti i peer di approvazione assegnati a una specifica applicazione chaincode. Le politiche possono essere curate in base all'applicazione e al livello desiderato di resilienza contro comportamenti non corretti, deliberati o meno, dei peer di approvazione. Una transazione inoltrata deve soddisfare la politica di approvazione prima di essere contrassegnata come valida dai peer di commit. È anche richiesta una politica di approvazione distinta per installare e istanziare le transazioni.

## Blocco di genesi
Il blocco di configurazione che inizializza un canale o una rete blockchain e che funge anche da primo blocco in una catena.

## HSM
Hardware Security Module. Fornisce gestione delle chiavi, archiviazione delle chiavi e crittografia on-demand come un servizio gestito. HSM è un'appliance fisica che gestisce le attività a elevato utilizzo di risorse dell'elaborazione di crittografia e riduce la latenza per le applicazioni. Per ulteriori informazioni, vedi [Hardware Security Module ![Icona link esterno](images/external_link.svg "Icona link esterno")](https://www.ibm.com/cloud/hardware-security-module)

## Hyperledger Composer
[Hyperledger Composer ![Icona link esterno](images/external_link.svg "Icona link esterno")](https://hyperledger.github.io/composer/latest/introduction/introduction.html) è un set di strumenti di sviluppo open source. Utilizza un linguaggio di modellazione su misura, che è combinato con le transazioni JavaScript e le regole di controllo accessi per modellare completamente una rete di business blockchain. Puoi utilizzare Hyperledger Composer per integrare i sistemi e i dati esistenti con la tua applicazione blockchain prima di eseguire qualsiasi distribuzione a una vera blockchain.

## Hyperledger Fabric
[Hyperledger Fabric ![Icona link esterno](images/external_link.svg "Icona link esterno")](http://hyperledger-fabric.readthedocs.io/en/master/) è un framework blockchain di business ospitato da Linux Foundation che funge da base per lo sviluppo di applicazioni o soluzioni blockchain con un'architettura modulare.I componenti di Hyperledger Fabric quali i servizi di consenso e adesione sono plug-and-play.

## Installare
Il processo di inserire un chaincode nel file system di un peer. Devi installare il chaincode su ogni peer che eseguirà questo chaincode.

## Istanziare
Il processo di avviare e istanziare un contenitore chaincode su uno specifico canale. Dopo che il chaincode è stato installato sui peer e ogni peer ha aderito al canale, il chaincode deve essere istanziato sul canale. L'istanziazione esegue tutta l'inizializzazione necessaria del chaincode, che include l'impostazione di coppie chiave-valore che formano lo stato globale iniziale di un chaincode. Dopo l'istanziazione i peer che hanno il chaincode installato possono accettare richiami del chaincode.

## Libro mastro
Formato da una vera e propria "catena di blocchi" che memorizzano i record di transazioni immutabili e in sequenza, e un database dello stato per conservare lo stato corrente. C'è un libro mastro per canale e gli aggiornamenti ad esso vengono gestiti dal processo di consenso in base alle politiche di uno specifico canale.

## Membro
Noti anche come "organizzazioni", i membri in una rete blockchain, analogamente ai membri di qualsiasi gruppo, formano la struttura della rete. Un membro può essere grande quanto una società multinazionale o piccolo come una singola persona. I membri sono registrati nella rete con un certificato che concede loro le autorizzazioni a utilizzare la rete come un fornitore di servizi (ad esempio l'emissione di certificati e la convalida/ordinazione di transazioni) oppure come un consumatore.Nel primo caso fornisce servizi blockchain di base che includono la convalida di transazioni, gli ordini di transazioni e i servizi di gestione dei certificati. I membri consumatore utilizzano la rete per richiamare le transazioni sul libro mastro distribuito. I membri possono avere più peer.

## MSP
Membership Service Provider.  Una serie di meccanismi e protocolli crittografici per emettere e convalidare certificati e identità in tutta la rete blockchain. Le identità emesse nell'ambito di un fornitore di servizi di adesione possono essere valutate nell'ambito elle politiche di convalida delle regole del fornitore di servizi di adesione. L'MSP è installato su ciascun peer del canale per garantire che le richieste di transazione emesse al peer abbiano origine da un'identità utente autenticata e autorizzata.

## Rete
Un'istanza di un servizio {{site.data.keyword.blockchainfull_notm}} Platform su {{site.data.keyword.cloud_notm}}.

## Credenziali di rete
Visibile dalla schermata "APIs" del Network Monitor. Le credenziali includono la tua "chiave" (Nome utente) e il "segreto" (password) nell'IU Swagger. Devi utilizzare queste credenziali di rete per eseguire l'autenticazione prima di provare le API REST. 

## Network Monitor
Il dashboard GUI fornito da {{site.data.keyword.blockchainfull_notm}} Platform per visualizzare e gestire la rete blockchain.

## Nodo
L'entità di comunicazione della blockchain. Ci sono tre tipi di nodi: nodi CA, Peer e Ordering Service (Servizio di ordinazione) (la raccolta di ordinanti per un canale).

## Ordinante
Un nodo Ordering Service (Servizio di ordinazione). Una risorsa di rete blockchain che fornisce servizi di autenticazione client. Fornisce inoltre servizi per ordinare e trasmettere le transazioni.

## Organizzazione
Vedi [Membro](#member).

## Servizio di ordinazione
Ogni rete blockchain richiede un servizio di ordinazione. Il servizio di ordinazione raccoglie le transazioni dai membri della rete, ordina le transazioni e le include in blocchi. Il servizio di ordinazione distribuisce quindi i nuovi blocchi ai peer, che verificano quindi i blocchi e li aggiungono ai libri mastri su ogni canale. Il servizio di ordinazione è anche un'associazione comune per la rete complessiva.Contiene il materiale di identità crittografica associato a ciascun membro e autentica l'identità di client e peer per l'accesso alla rete.

## Partecipante
Qualsiasi organizzazione, individuo, applicazione o dispositivo che interagisce con la rete blockchain. Nell'ambito del termine 'partecipante' rientrano due raggruppamenti distinti, ossia membri e utenti. 

## Peer
Una risorsa di rete blockchain che fornisce i servizi per eseguire e convalidare le transazioni e mantenere i libri mastri. Il peer esegue la chaincode ed è il detentore della cronologia delle transazioni e dello stato corrente degli asset sui canali della rete, ossia il libro mastro. Appartengono e sono gestiti dalle organizzazioni e vengono uniti ai canali.

## Credenziali del servizio
Le credenziali del servizio sono in formato JSON e contengono le informazioni sull'endpoint API e gli ID registrazione(enrollID)/segreti per le tue risorse di rete, ossia i peer, i nodi di ordine e le CA. La tua applicazione interagisce con le risorse di rete tramite questi endpoint API.

## SDK
Hyperledger Fabric supporta due SDK (Software Development Kit). Un SDK Node e un SDK Java. L'SDK Node può essere installato tramite NPM e l'SDK Java tramite Maven.  Gli SDK hanno i propri repository git, ossia [SDK Node Fabric ![Icona link esterno](images/external_link.svg "Icona link esterno")](https://github.com/hyperledger/fabric-sdk-node) e [SDK Java Fabric ![Icona link esterno](images/external_link.svg "Icona link esterno")](https://github.com/hyperledger/fabric-sdk-java), con la documentazione per le API disponibili. Gli SDK Hyperledger Fabric Client abilitano l'interazione tra la tua applicazione client e la tua rete blockchain.

## SOLO
L'implementazione di un plugin di consenso per Hyperledger Fabric che dà come risultato un singolo nodo di servizio di ordinazione nella rete blockchain. La rete Starter Plan utilizza l'implementazione SOLO. Un'implementazione SOLO non è concepita per una rete di produzione. L'alternativa a SOLO è un cluster Kafka.

## Transazione
Il meccanismo che i partecipanti nella rete blockchain utilizzano per interagire con gli asset. Una transazione crea un nuovo chaincode o richiama un'operazione in un chaincode esistente.

## Utente
Un utente è un partecipante in una rete blockchain che ha accesso indiretto al libro mastro tramite una relazione di attendibilità a un membro esistente.
