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

# 名詞解釋
{: #glossary}

「{{site.data.keyword.blockchainfull}} 平台」簡化了使用區塊鏈的程序。本主題定義在此文件中出現的術語，用來向您介紹區塊鏈的概念。若要深入瞭解各術語，您可以參閱 [Hyperledger Fabric ![外部鏈結圖示](images/external_link.svg "外部鏈結圖示")](http://hyperledger-fabric.readthedocs.io/en/master/glossary.html)。
{:shortdesc}

## 資產 (Asset)
有形或無形的商品、服務或財產，以在區塊鏈網路上交易的項目來代表。

## 區塊 (Block)
排定次序的交易集，以加密方式鏈結至通道中的前一個區塊。

## 商業網路 (Business network)
區塊鏈網路的定義，其中包含區塊鏈解決方案的資料模型、交易邏輯及存取控制規則。「商業網路定義」是使用 [Hyperledger Composer](#hyperledger-composer) 建立而成。商業網路定義會包裝在可部署的 **.bna** 檔案（商業網路保存檔）中。

## CA
憑證管理中心 (Certificate Authority)。核發憑證給所有參與成員的區塊鏈網路資源。這些憑證代表成員的身分。網路中的所有實體（對等節點、排序節點、用戶端等等）都必須要有身分，才能進行通訊、鑑別，最後進行交易。只要是直接參與區塊鏈網路，都需要這些身分。您可以為 CA 建立商業網路卡。然後可以匯入該 [CA 卡](develop_starter.html#developing-business-networks-with-starter-plan)，並使用該卡來將管理者密碼交換成「入門範本方案」憑證管理中心提供的有效憑證。

## 鏈 (Chain)
分類帳的鏈是交易日誌，結構化成交易的雜湊鏈結區塊。對等節點會從排序服務接收交易的區塊；根據背書原則和並行違規，將區塊的交易標示為有效或無效；然後在對等節點的檔案系統上，將該區塊附加至雜湊鏈。

## 鏈碼 (Chaincode)
鏈碼又稱為「智慧型合約」，是構成軟體的組件，其中包含可用來查詢或更新分類帳的一組函數。

## 通道 (Channel)
由想要進行私密交易的網路成員子集組成。通道提供資料隔離和機密性，可讓通道成員建立特定規則和個別的分類帳，僅供通道成員存取。其功能是作為組織之交易端點的對等節點，會加入通道。

## 用戶端 (Client)
用戶端是代表使用者行動的實體。其必須連接至對等節點，才能與區塊鏈通訊。用戶端可以連接至其選擇的任何對等節點。用戶端會建立進而呼叫交易。用戶端會將實際交易呼叫提交給背書者，並將交易提案播送至排序服務。

## 連線設定檔 (Connection profile)
在「網路監視器」上按一下**連線設定檔**按鈕，連線設定檔就會顯示在「概觀」畫面中。該資訊為 JSON 格式，其中包含您的網路資源（亦即，對等節點、排序節點及 CA）的 API 端點資訊和 enrollID/secret。您的應用程式會透過這些 API 端點來與網路資源互動。

## 共識 (Consensus)
讓整個網路中的分類帳交易保持同步的協同處理程序。共識可確保唯有當適當的參與者核准交易時，才會更新分類帳，並確保分類帳會依相同順序使用相同的交易進行更新。達到共識的演算方式有很多種。

## 動態成員資格 (Dynamic membership)
具有 **registrar**（登記員）專用權的使用者，可以將成員動態新增至網路。成員也會獲指派一些角色及屬性，這些角色及屬性可控制他們對網路的存取權及權限。但角色或屬性都不能以動態方式指派。Hyperledger Fabric 支援新增或移除成員、對等節點及排序服務節點，而無損於整體網路的運作。當商業關係調整，並且因為各種原因而需要新增或移除實體時，動態成員資格極為重要。

## 背書 (Endorsement)
用來驗證鏈碼交易的處理程序。背書規則是藉由指定背書原則來實作。

## 背書原則 (Endorsement policy)
定義通道中必須執行特定鏈碼應用程式所附加交易的對等節點，以及回應的必要組合（背書）。原則可以要求，在指派給特定鏈碼應用程式的背書對等節點中，必須要有最低數量的背書對等節點、最低百分比的背書對等節點，或所有背書對等節點來為交易背書。背書對等節點可以根據應用程式以及對違反原則（是否蓄意）所需的備援層次來策劃原則。所提交的交易必須滿足背書原則，才能確定對等節點來將其標示為有效。另外也需要安裝及實例化交易的相異背書原則。

## 初始區塊 (Genesis Block)
起始設定區塊鏈網路或通道的配置區塊，也是區塊鏈上的第一個區塊。

## HSM
硬體安全模組 (Hardware Security Module)。提供隨需應變加密、金鑰管理及金鑰儲存空間作為受管理服務。HSM 是實體應用裝置，可處理加密法處理的資源密集型作業，並減少應用程式的延遲時間。如需相關資訊，請參閱[硬體安全模組 ![外部鏈結圖示](images/external_link.svg "外部鏈結圖示")](https://www.ibm.com/cloud/hardware-security-module)

## Hyperledger Composer
[Hyperledger Composer ![外部鏈結圖示](images/external_link.svg "外部鏈結圖示")](https://hyperledger.github.io/composer/latest/introduction/introduction.html) 是開放程式碼開發工具集。其使用定製的模型化語言，結合 JavaScript 交易和存取控制規則來建立完整的區塊鏈商業網路模型。在將任何項目部署至實際區塊鏈之前，您可以先使用 Hyperledger Composer 來將現有的系統和資料與區塊鏈應用程式整合。

## Hyperledger Fabric
[Hyperledger Fabric ![外部鏈結圖示](images/external_link.svg "外部鏈結圖示")](http://hyperledger-fabric.readthedocs.io/en/master/) 是由 Linux Foundation 管理的商業區塊鏈架構，用來作為開發具有模組架構之區塊鏈應用程式或解決方案的基礎。像共識和成員資格服務這些 Hyperledger Fabric 元件都是隨插即用。

## 安裝 (Install)
將鏈碼放置在對等節點檔案系統上的處理程序。您必須在將執行此鏈碼的每個對等節點上安裝鏈碼。

## 實例化 (Instantiate)
在特定通道上啟動及起始設定鏈碼容器的處理程序。將鏈碼安裝在「對等節點」上，且每個「對等節點」都已加入通道之後，必須在通道上將鏈碼實例化。實例化會執行鏈碼的任何必要起始設定，這包括設定包含鏈碼起始廣域狀態的鍵值組。實例化之後，已安裝鏈碼的對等節點即可接受鏈碼呼叫。

## 分類帳 (Ledger)
由所謂的「區塊鏈」組成，區塊中儲存不可變、序列化的交易記錄，以及用來維護現行狀態的狀態資料庫。每個通道各有一個分類帳，共識處理程序會依據特定通道的原則來管理其更新項目。

## 成員 (Member)
又稱為「組織」，區塊鏈網路中的成員，類似於任何群組的成員，構成網路的結構。成員可以大至國際企業，小至個人。成員需以憑證來登入網路，該憑證授權他們以服務提供者（例如，發出憑證、驗證/排序交易）或消費者的身分來使用網路。前者提供基礎區塊鏈服務，包括交易驗證、交易排序，以及憑證管理服務。消費者成員則是使用網路來針對分散式分類帳呼叫交易。成員可以有多個「對等節點」。

## MSP
成員資格服務提供者 (Membership Service Provider)。一組加密機制和通訊協定，可在整個區塊鏈網路中發出及驗證憑證和身分。在成員資格服務提供者範圍內發出的身分，可以在該成員資格服務提供者的規則驗證原則內進行評估。MSP 安裝在每一個通道對等節點上，以確保發出給對等節點的交易要求是來自經鑑別及授權的使用者身分。

## 網路 (Network)
{{site.data.keyword.cloud_notm}} 上的「{{site.data.keyword.blockchainfull_notm}} 平台」服務實例。

## 網路認證 (Network Credentials)
可以從「網路監視器」的 "API" 畫面查看。認證包括您在 Swagger 使用者介面中的 "key"（使用者名稱）和 "secret"（密碼）。您需要使用這些網路認證來鑑別，才能開始試用 REST API。 

## 網路監視器 (Network Monitor)
「{{site.data.keyword.blockchainfull_notm}} 平台」提供的 GUI 儀表板，可用來檢視及管理區塊鏈網路。

## 節點 (Node)
區塊鏈的通訊實體。節點有三種類型：CA、對等節點及排序服務（通道的排序節點集合）節點。

## 排序節點 (Orderer)
「排序服務」節點。提供用戶端鑑別服務的區塊鏈網路資源。此外，它還提供將交易排序及播送的服務。

## 組織 (Organization)
請參閱[成員](#member)。

## 排序服務 (Ordering Service)
每個區塊鏈網路都需要「排序服務」。排序服務會收集網路成員的交易、將交易排序，並將其組合成區塊。然後排序服務會將新的區塊配送至對等節點，對等節點會再驗證區塊，並將其新增至每個通道上的分類帳。排序服務也是整體網路的共同連結。其中包含每個成員的相關加密身分資料，並且會鑑別用戶端和對等節點的身分來存取網路。

## 參與者 (Participant)
與區塊鏈網路互動的任何組織、個人、應用程式或裝置。在「參與者」的大傘之下，有兩個不同的分組，分別為成員和使用者。

## 對等節點 (Peer)
區塊鏈網路資源，提供服務來執行及驗證交易，以及維護分類帳。「對等節點」會執行鏈碼，且其為交易歷程以及網路通道中資產現行狀態（也就是分類帳）的持有者。其由組織所擁有及管理，並且會加入通道。

## 服務認證 (Service credentials)
服務認證為 JSON 格式，其中包含您的網路資源（亦即，對等節點、排序節點及 CA）的 API 端點資訊和 enrollID/secret。您的應用程式會透過這些 API 端點來與網路資源互動。

## SDK
Hyperledger Fabric 支援兩種「軟體開發套件 (SDK)」：Node SDK 和 Java SDK。Node SDK 可以透過 NPM 來安裝，Java SDK 則是透過 Maven 來安裝。SDK 有自己的 Git 儲存庫，也就是 [Fabric Node SDK ![外部鏈結圖示](images/external_link.svg "外部鏈結圖示")](https://github.com/hyperledger/fabric-sdk-node) 和 [Fabric Java SDK ![外部鏈結圖示](images/external_link.svg "外部鏈結圖示")](https://github.com/hyperledger/fabric-sdk-java)，並附有可用 API 的文件。Hyperledger Fabric Client SDK 可讓用戶端應用程式與區塊鏈網路互動。

## SOLO
Hyperledger Fabric 的共識外掛程式實作，會在區塊鏈網路中產生單一排序服務節點。「入門範本方案」網路會使用 SOLO 實作。SOLO 實作不適用於正式作業網路。SOLO 的替代方案為 Kafka 叢集。

## 交易 (Transaction)
區塊鏈網路上的參與者用來與資產互動的機制。交易會建立新的鏈碼，或是呼叫現有鏈碼中的作業。

## 使用者 (User)
使用者是區塊鏈網路中的參與者，可透過與現有成員的信任關係，間接存取分類帳。
