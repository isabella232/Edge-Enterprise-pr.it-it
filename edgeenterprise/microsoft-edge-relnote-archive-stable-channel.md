---
title: Note sulla versione archiviate del canale Microsoft Edge Stable
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/13/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione archiviate del canale Microsoft Edge Stable
ms.openlocfilehash: 383f2c806e0459c32c378ff91613cf240453c781
ms.sourcegitcommit: 498a62144b099a1198c06f98ad010cf95aa33727
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "11268273"
---
# Note sulla versione archiviate del canale Microsoft Edge Stable

Queste note sulla versione offrono informazioni sulle nuove funzionalità e sugli aggiornamenti non relativi alla sicurezza inclusi nel canale Microsoft Edge Stable. Tutti gli aggiornamenti della sicurezza sono elencati [qui](microsoft-edge-relnotes-security.md).

## Versione 84.0.522.40: 16 luglio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#july-16-2020).

### Aggiornamenti delle funzionalità

- Questa versione di Microsoft Edge fornisce tempi di download dell'elenco di siti ottimizzati per la modalità di Internet Explorer. È stato ridotto il ritardo di download dell'elenco di siti in modalità Internet Explorer a 0 secondi (rispetto a un'attesa di 60 secondi), in assenza di un elenco di siti memorizzato nella cache. È stato aggiunto anche il supporto per i criteri di gruppo per i casi in cui è necessario ritardare la visualizzazione della home page in modalità Internet Explorer durante il download dell'elenco di siti. Per ulteriori informazioni, consultare il criterio [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload).

- Microsoft Edge ora consente agli utenti di accedere al browser quando è eseguito in modalità "Esegui come amministratore" in Windows 10. Questo consentirà ai clienti di eseguire Microsoft Edge su Windows Server o in scenari desktop remoto e sandbox.

- Microsoft Edge ora offre il supporto completo del mouse in modalità a schermo intero. Ora è possibile usare il mouse per accedere alle schede, alla barra degli indirizzi e ad altri elementi senza uscire dalla modalità a schermo intero.

- Miglioramento acquisti online. Aggiungere nomi personalizzati alle carte di credito o di debito salvate. Ora è possibile distinguere e differenziare le carte di credito quando si effettuano acquisti online. Attribuendo nomi personalizzati alle carte di credito o di debito sarà possibile scegliere la carta corretta quando si usa il riempimento automatico per selezionare una modalità di pagamento.

- TLS/1.0 e TLS/1.1 sono disabilitati per impostazione predefinita.  Il criterio [SSLVersionMin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#sslversionmin) consente di riabilitare TLS/1.0 e TLS/1.1. Il criterio rimarrà disponibile almeno fino alla versione 88 di Microsoft Edge. Per altre informazioni, consultare [Modifiche con ripercussioni sulla compatibilità del sito in Microsoft Edge](https://docs.microsoft.com/microsoft-edge/web-platform/site-impacting-changes).

- Migliorie alle raccolte:

  - Viene aggiunta una funzionalità relativa alle note che consente di aggiungere una nota o un commento a un elemento di una raccolta. Le note sono raggruppate e rimangono allegate a un elemento anche se si ordinano gli elementi in una raccolta. Per provare questa nuova funzionalità, fare clic con il pulsante destro del mouse su un elemento e scegliere "Aggiungi nota".
  - È possibile modificare il colore sfondo delle note nelle raccolte. È possibile usare la codifica a colori per organizzare le informazioni e aumentare la produttività.
  - Sono stati apportati migliorie alle prestazioni, che consentono di esportare le raccolte in Excel in meno tempo rispetto alle versioni precedenti di Microsoft Edge.

- Supporto aggiuntivo per le API di Microsoft Edge:

  - L'API Storage Access è abilitata per la sperimentazione. Questa funzionalità è abilitata per gli utenti privati e gli utenti aziendali con i criteri di [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/deployedge/microsoft-edge-policies#experimentationandconfigurationservicecontrol) impostati su "Completo". Questa funzionalità verrà abilitata per impostazione predefinita per tutti gli utenti nella versione 85 del canale stabile di Microsoft Edge.
  
    Dato che la privacy sta diventando sempre più importante per gli utenti, sono sempre più comuni richieste di impostazioni predefinite dei browser più stringenti e impostazioni tramite consenso esplicito dell'utente come il blocco dell'accesso alle risorse di archiviazione di terze parti. Se da un lato queste impostazioni consentono di migliorare la privacy e bloccare accessi non desiderati da parte di parti non conosciute e affidabili, dall'altra potrebbero presentare effetti collaterali come il blocco di contenuti che l'utente potrebbe voler visualizzare (ad esempio, contenuti dei social media e contenuti multimediali integrati).

    L'API Storage Access consente l'accesso a uno spazio di archiviazione di prima parte in un contesto di terza parte quando un utente mostra l'intento diretto di consentire lo spazio di archiviazione che altrimenti verrebbe bloccato dalla configurazione corrente del browser. Per altre informazioni, vedere [API Storage Access](https://www.chromestatus.com/feature/5612590694662144).

  - L'API del file system nativo, per poter fornire le autorizzazioni ai siti per modificare file o cartelle tramite l'API del file system nativo.

- Migliorie ai PDF:

  - Leggi ad alta voce per PDF consente agli utenti di ascoltare il contenuto del PDF durante l'esecuzione di altre importanti attività. Consente anche gli studenti di prodotti audiovisivi di leggere i contenuti, facilitando l'apprendimento.
  - Modifica dei file PDF ottimizzata. Ora è possibile salvare una modifica apportata a un PDF nel file invece di salvare una copia ogni volta che si modifica il PDF.

- Microsoft Edge ora consente la traduzione nello strumento di lettura immersiva. Quando un utente apre la visualizzazione di lettura immersiva, ha la possibilità di tradurre la pagina nella lingua desiderata.

- Diversi aggiornamenti di DevTools, tra cui il supporto per la personalizzazione delle scelte rapide da tastiera in base al VS Code e la visualizzazione di DevTools a contrasto elevato.  Per ulteriori informazioni, consultare [Novità di DevTools (Microsoft Edge 84)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/05/devtools).

### Aggiornamenti dei criteri

#### Nuovi criteri

Sono stati aggiunti 7 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise). Sono stati aggiunti i nuovi criteri seguenti.

- [AppCacheForceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#appcacheforceenabled): consente alla funzionalità AppCache di essere riabilitata, anche se disabilitata per impostazione predefinita.
- [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy): configurare le impostazioni per il proxy contenitore di Application Guard.
- [DelayNavigationsForInitialSiteListDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload): richiede che l'elenco siti in modalità Enterprise sia disponibile prima dello spostamento tramite schede.
- [WinHttpProxyResolverEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#winhttpproxyresolverenabled): usare il resolver proxy di Windows.
- [InternetExplorerIntegrationEnhancedHangDetection](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationenhancedhangdetection): configurare il rilevamento avanzato dei blocchi per la modalità Internet Explorer.
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled): per ridurre il consumo di energia e CPU, Microsoft Edge rileverà quando una finestra è coperta da altre finestre e sospenderà i pixel di disegno.
- [NavigationDelayForInitialSiteListDownloadTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout): imposta un timeout per i ritardi nello spostamento tramite schede per l'elenco siti in modalità Enterprise.

#### Criteri deprecati

- [AllowSyncXHRInPageDismissal](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal): consente alle pagine di inviare richieste XHR sincrone durante le richieste XHR asincrone durante la chiusura della pagina.
- [BuiltinCertificateVerifierEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#builtincertificateverifierenabled): determinare se lo strumento di verifica del certificato predefinito verrà usato per la verifica dei certificati server.
- [StricterMixedContentTreatmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#strictermixedcontenttreatmentenabled): abilitare un trattamento più rigido per i contenuti misti.

#### Criteri obsoleti

[ForceNetworkInProcess](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcenetworkinprocess): forza l'esecuzione del codice di rete nel processo del browser.

<!-- End 84 -->
## Versione 83.0.478.64: 13 luglio

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 83.0.478.61: 7 luglio

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 83.0.478.58: 30 giugno

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 83.0.478.56: 24 giugno

Risolti diversi bug e problemi relativi alle prestazioni.

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#june-24-2020).

## Versione 83.0.478.54: 17 giugno

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#june-17-2020).

## Versione 83.0.478.50: 15 giugno

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 83.0.478.45: 4 giugno

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#june-4-2020).

## Versione 83.0.478.44: 1 giugno

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 83.0.478.37: 21 maggio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#may-21-2020).

### Aggiornamenti delle funzionalità

- Gli aggiornamenti di Microsoft Edge verranno implementati gradualmente. In futuro, gli aggiornamenti di Microsoft Edge verranno distribuiti agli utenti in un periodo di pochi giorni. Questo consente di proteggere più utenti da aggiornamenti non richiesti, migliorando l'esperienza di aggiornamento. Gli utenti continueranno a ottenere aggiornamenti automatici senza interruzioni. Se l'organizzazione non è iscritta agli aggiornamenti automatici, non sarà interessata da questo cambiamento. Per altre informazioni, vedere l'[articolo sulle implementazioni progressive](microsoft-edge-update-progressive-rollout.md).
- Miglioramenti apportati a Microsoft Defender SmartScreen: sono stati apportati numerosi miglioramenti al servizio Microsoft Defender SmartScreen, ad esempio una maggiore protezione da siti dannosi che reindirizzano durante il caricamento e il blocco frame di primo livello che sostituisce completamente i siti dannosi con la pagina di sicurezza di Microsoft Defender SmartScreen. Il blocco di frame di primo livello impedisce la riproduzione di audio e altri elementi multimediali dal sito dannoso, offrendo un'esperienza più facile e chiara.

- In risposta al feedback degli utenti, è ora possibile esonerare alcuni cookie dalla cancellazione automatica quando il browser viene chiuso. Questa opzione utile se esiste un sito da cui gli utenti non vogliono essere disconnessi, ma vogliono comunque cancellare tutti gli altri cookie quando il browser viene chiuso. Per usare questa funzionalità, passare a *edge://settings/clearBrowsingDataOnClose* e attivare l'opzione "Cookie e altri dati del sito".

- È ora disponibile il cambio di profilo automatico per semplificare il trasferimento del contenuto del lavoro tra i profili. Se si usano più profili al lavoro, è possibile controllarli da un sito che richiede l'autenticazione con l'account aziendale o dell'Istituto di istruzione mentre si usa il profilo personale. Quando Microsoft lo rileva, si riceve una richiesta di passare al profilo di lavoro per accedere al sito senza dover eseguire l'autenticazione. Se si sceglie il profilo di lavoro a cui si vuole passare, il sito Web si aprirà semplicemente nel profilo di lavoro. La funzionalità di cambio profilo sarà utile per separare i dati di lavoro e personali, facilitando l'accesso ai contenuti di lavoro. Se non si vuole ricevere la richiesta di cambiare profilo, è possibile scegliere l'opzione Non visualizzare più questo messaggio.

- Miglioramenti delle funzionalità e raccolte:
  - È possibile usare il trascinamento della selezione per aggiungere un elemento a una raccolta senza aprirla. Durante il trascinamento della selezione è anche possibile scegliere una posizione nell'elenco della raccolta in cui si vuole inserire l'elemento.
  - È possibile aggiungere più elementi a una raccolta invece di aggiungerne uno alla volta. Per aggiungere più elementi, selezionarli e quindi trascinarli in una raccolta. In alternativa, è possibile selezionare gli elementi, fare clic con il pulsante destro del mouse e quindi selezionare la raccolta in cui si vogliono inserire gli elementi.

- È possibile aggiungere tutte le schede in una finestra di Microsoft Edge in una nuova raccolta senza aggiungerle singolarmente. A questo scopo, fare clic con il pulsante destro del mouse su una scheda qualsiasi e scegliere "Aggiungi tutte le schede a una nuova raccolta".

- La sincronizzazione delle estensioni è ora disponibile. Ora è possibile sincronizzare le estensioni in tutti i dispositivi. Le estensioni degli store Microsoft e Chrome verranno sincronizzate con Microsoft Edge. Per usare questa funzionalità: fare clic sui puntini di sospensione (**…**) sulla barra dei menu e selezionare **Impostazioni**. Nel profilo, selezionare **Sincronizza** per vedere le opzioni di sincronizzazione. In **Profili/Sincronizza** attiva le estensioni. È possibile usare i criteri di gruppo [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) per disabilitare la sincronizzazione delle estensioni.

- È stato migliorato il messaggio nella pagina di gestione dei download per i download non sicuri bloccati.

- Miglioramenti allo strumento di lettura immersiva:
  - Aggiunta del supporto per gli avverbi nelle parti del discorso a disposizione nello strumento di lettura immersiva. Durante la lettura di un articolo all'interno dello strumento di lettura immersiva, aprire gli strumenti di grammatica e attivare gli avverbi nelle parti del discorso per evidenziare tutti gli avverbi presenti nella pagina.
  - Aggiunta la possibilità di selezionare il contenuto di una pagina Web e aprirlo nello strumento di lettura immersiva. Questa funzionalità permette agli utenti di utilizzare lo strumento di lettura immersiva e tutti gli strumenti di apprendimento, come Focus su riga e Leggi ad alta voce, in tutti i siti Web.

- Link doctor include una correzione host e una query di ricerca per gli utenti quando digitano in modo errato un URL. Ad esempio: <br>
Un utente digita in modo errato "powerbbi" invece di "powerbi".com. Link doctor suggerirà "powerbi".com come correzione e creerà un collegamento per cercare "powerbbi" nel caso in cui l'utente cerchi qualcosa di diverso.

- Consentire agli utenti di salvare la propria decisione di avviare un protocollo esterno per un sito specifico. Gli utenti possono configurare il criterio [ExternalProtocolDialogShowAlwaysOpenCheckbox]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) per abilitare o disabilitare questa funzione.

- Gli utenti possono impostare Microsoft Edge come browser predefinito direttamente da Microsoft Edge **Impostazioni**. Questo facilita agli utenti la possibilità di cambiare il proprio browser predefinito nel contesto del browser stesso, invece di cercare tra le impostazioni del sistema operativo. Per utilizzare questa funzionalità, passare a *edge://settings/defaultBrowser* e fare clic su **Rendi predefinito**.

- Numerosi aggiornamenti di DevTools, tra cui il nuovo supporto per il debug remoto, i miglioramenti dell'interfaccia utente e altro ancora. Per ulteriori informazioni, vedere [Novità di DevTools (Microsoft Edge 83)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools).

- Lo senario degli avvisi di MCAS (Microsoft Cloud Access Security) è ora disponibile. In questo modo, gli amministratori potranno impostare gli avvisi, nuove categorie di blocchi MCAS, dove l'utente può eseguire l'override di un blocco pagina MCAS. I blocchi MDATP E5 sono incorporati in modo nativo con blocchi SmartScreen in Microsoft Edge per un'esperienza senza interruzioni. Questa esperienza consente di bloccare una pagina intera con il messaggio "il sito Web è bloccato dall'organizzazione", anziché solo una notifica di tipo avviso popup.

- Impedire XmlHttpRequest sincrono nell'interruzione della pagina. L'invio di XmlHttpRequest sincroni durante lo scaricamento di una pagina Web verrà rimosso. Questa modifica migliora le prestazioni e l'affidabilità del browser, ma potrebbe influire sulle applicazioni Web non ancora aggiornate per usare API Web più moderne, tra cui sendBeacon e Fetch. I criteri di gruppo per disabilitare questa modifica e consentire l'XHR sincrono durante l'interruzione della pagina saranno disponibili fino a Microsoft Edge 88. Per altre informazioni, consultare [Modifiche con ripercussioni sulla compatibilità del sito in Microsoft Edge](https://docs.microsoft.com/microsoft-edge/web-platform/site-impacting-changes).

### Aggiornamenti dei criteri

#### Nuovi criteri

Sono stati aggiunti 15 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise). Sono stati aggiunti i nuovi criteri seguenti.

- [AllowSurfGame](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowsurfgame)-consentire il gioco Surf.
- [AllowTokenBindingForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowtokenbindingforurls): configurare l'elenco dei siti di con cui Microsoft Edge proverà a stabilire un binding di token.
- [BingAdsSuppression](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#bingadssuppression): bloccare tutti gli annunci sui risultati della ricerca di Bing.
- [BuiltinCertificateVerifierEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#builtincertificateverifierenabled): determinare se lo strumento di verifica del certificato predefinito verrà usato per la verifica dei certificati server.
- [ClearCachedImagesAndFilesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clearcachedimagesandfilesonexit): cancellare le immagini e i file memorizzati nella cache alla chiusura di Microsoft Edge.
- [ConfigureShare](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureshare): configurare l'esperienza di condivisione.
- [DeleteDataOnMigration](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#deletedataonmigration): eliminare i dati del browser obsoleti alla migrazione.
- [DnsOverHttpsMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsoverhttpsmode): controllare la modalità del protocollo DNS-over-HTTPS.
- [DnsOverHttpsTemplates](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsoverhttpstemplates): specificare il modello URI del resolver DNS-over-HTTPS desiderato.
- [FamilySafetySettingsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#familysafetysettingsenabled): consentire agli utenti di configurare Family Safety.
- [LocalProvidersEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#localprovidersenabled): consentire suggerimenti dai provider locali.
- [ScrollToTextFragmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#scrolltotextfragmentenabled): consentire lo scorrimento al testo specificato nei frammenti di URL.
- [ScreenCaptureAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#screencaptureallowed):consentire o negare l'acquisizione schermo.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): configurare l'elenco dei tipi esclusi dalla sincronizzazione.
- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled): consentire di nascondere Windows nativo.

#### Criteri deprecati

I criteri seguenti continueranno a funzionare in questa versione, ma diventeranno "obsoleti" in una versione futura.

[EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload): abilitare il download delle azioni di dominio da Microsoft

<!-- end 83 -->

## Versione 81.0.416.77: 18 maggio

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 81.0.416.72: 7 maggio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#may-7-2020).

## Versione 81.0.416.68: 29 aprile

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#april-29-2020).

## Versione 81.0.416.64: 23 aprile

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#april-23-2020).

## Versione 81.0.416.58: Aprile 17

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#april-17-2020).

## Versione 81.0.416.53: 13 aprile

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#april-13-2020).

### Aggiornamenti delle funzionalità

- Aggiunta del supporto per Windows Information Protection (WIP) che aiuta le aziende a proteggere i dati sensibili dalla divulgazione non autorizzata. [Ulteriori informazioni](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection).

- Raccolte è ora disponibile. Per iniziare, fare clic sull'icona Raccolte accanto alla barra degli indirizzi. Questa operazione aprirà il riquadro Raccolte in cui è possibile creare, modificare e visualizzare le raccolte. La funzionalità Raccolte è stata progettata in base alle attività che l'utente svolge sul Web. Raccolte può essere particolarmente utile nel caso in cui l'utente sia un acquirente, un viaggiatore, un insegnante o uno studente. [Ulteriori informazioni](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97).

- È possibile consentire la rimozione (Nascondi dalla barra degli strumenti) del pulsante Raccolte dalla barra degli strumenti di Microsoft Edge per coerenza.

- L'accesso automatico all'account Active Directory locale sarà previsto solo per le organizzazioni che lo attivano.  Se gli utenti avevano già effettuato l'accesso con un account AD locale, potranno disconnettersi. Gli utenti potranno accedere automaticamente con l'account principale sul loro sistema operativo solo se si tratta di un account Microsoft o un account Azure Active Directory. Gli amministratori possono abilitare l'accesso automatico con un account AD locale utilizzando il criterio ConfigureOnPremisesAccountAutoSignIn.

- Application Guard: il supporto per le estensioni è ora disponibile nel contenitore.

- È stato aggiunto un messaggio per informare gli utenti che Internet Explorer non è installato quando un utente accede a una pagina configurata per l'apertura in modalità Internet Explorer.

- È stato aggiornato lo strumento di visualizzazione 3D in Microsoft Edge DevTools con una nuova funzionalità che consente di eseguire il debug del contesto di impilamento z-index. La visualizzazione 3D mostra una rappresentazione della profondità DOM (Document Object Model) usando il colore e l'impilamento e la visualizzazione z index consente di isolare i diversi contesti di impilamento della pagina. [Ulteriori informazioni](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/).

- Gli strumenti di sviluppo F12 sono stati localizzati in 10 nuove lingue, in modo che corrispondano alla lingua utilizzata nel resto del browser. [Ulteriori informazioni](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/).

- È stato aggiunto il supporto per la riproduzione Dolby Vision. Su Windows 10 build 17134 (aggiornamento di aprile 2018) abilitato per Dolby Vision, i siti Web possono mostrare contenuti Dolby Vision. Vedere come abilitare i contenuti Dolby Vision su [Netflix](https://help.netflix.com/en/node/42384).

- Microsoft Edge ora può identificare e rimuovere i duplicati preferiti e unire le cartelle con lo stesso nome. Per accedere allo strumento, fare clic sulla stella presente sulla barra degli strumenti del browser e selezionare "Rimuovi preferiti duplicati".  Sarà possibile confermare le modifiche e gli aggiornamenti ai preferiti verranno sincronizzati su tutti i dispositivi.

- Gli utenti hanno segnalato che può risultare difficile distinguere una normale finestra di navigazione con tema scuro da una finestra InPrivate poiché entrambe le cornici delle finestre sono scure. La nuova pillola blu a tinta unita di InPrivate nell'angolo in alto a destra rassicura gli utenti che stanno navigando InPrivate.

- È possibile aprire i collegamenti esterni nel profilo del browser corretto. Selezionare un profilo predefinito per i collegamenti aperti per le app esterne in modo che si aprano da *edge://settings/multiProfileSettings*.

- È stato aggiunto un avviso per informare gli utenti che accedono a un profilo del browser con un account dopo aver effettuato l'accesso in precedenza con un altro account. L'avviso contribuisce a impedire l'unione involontaria di dati.

- Se sono state salvate carte di credito nel proprio account Microsoft, è possibile usarle in Microsoft Edge durante la compilazione dei moduli di pagamento. Le carte nel proprio account Microsoft verranno sincronizzate su tutti i dispositivi desktop e i dettagli completi verranno condivisi con il sito Web dopo l'autenticazione a due fattori (codice CVC e identità Microsoft). Per ulteriore comodità, è possibile scegliere di salvare in modo sicuro una copia della carta sul dispositivo durante l'autenticazione.

- Focus su riga è progettato per gli utenti che preferiscono concentrarsi su una determinata parte del contenuto durante la lettura. Consente agli utenti di concentrarsi su una, tre o cinque righe alla volta e oscura il resto della pagina per consentire una lettura senza distrazioni. Gli utenti possono scorrere tramite tocco o usando i tasti di direzione e il focus si sposterà di conseguenza.

- Microsoft Edge è ora integrato con il correttore ortografico di Windows su piattaforme Windows 8.1 e successive. Questa integrazione offre un maggiore supporto linguistico, consentendo l'accesso a più dizionari linguistici e l'utilizzo di dizionari personalizzati di Windows. Non sono necessarie ulteriori azioni da parte degli utenti una volta che una lingua è stata aggiunta nelle impostazioni della lingua del sistema operativo. È stato anche abilitato un pulsante per il controllo ortografico della lingua nelle impostazioni di Microsoft Edge.

- Quando i documenti PDF vengono aperti utilizzando Microsoft Edge, gli utenti ora potranno creare ed eliminare elementi in evidenza e modificarne il colore. Questa funzionalità consente di fare riferimento a parti importanti del documento in un secondo momento e facilitare la collaborazione.

- Quando si caricano documenti PDF lunghi che sono stati ottimizzati per il Web, le pagine visualizzate dall'utente verranno caricate più velocemente, parallelamente, mentre viene caricato il resto del documento.

- Ora è possibile avviare più facilmente lo strumento di lettura immersiva per un sito Web premendo il tasto F9.

- Ora è possibile iniziare a leggere ad alta voce più facilmente tramite tasti di scelta rapida (CTRL + MAIUSC + U).

- È stato aggiunto un parametro della riga di comando MSI che consente di eliminare la creazione dell'icona desktop quando si installa Microsoft Edge. L'esempio seguente mostra come usare questo nuovo parametro: <br>
`MicrosoftEdgeEnterpriseX64.msi DONOTCREATEDESKTOPSHORTCUT=true`<br>
Una versione futura comprenderà criteri di gruppo che supporteranno questa funzionalità.

### Aggiornamenti dei criteri

#### Nuovi criteri

Sono stati aggiunti 11 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise). Sono stati aggiunti i nuovi criteri seguenti.

- [AmbientAuthenticationInPrivateModesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#ambientauthenticationinprivatemodesenabled): abilitare l'autenticazione ambientale per i profili InPrivate e guest. 
- [AudioSandboxEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#audiosandboxenabled): consentire l'esecuzione del sandbox audio.
- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy): usare un criterio di referrer predefinito di no-referrer-when-downgrade.
- [GloballyScopeHTTPAuthCacheEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#globallyscopehttpauthcacheenabled): abilitare cache di autenticazione HTTP con ambito globale.
- [ImportExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importextensions): consentire l'importazione di estensioni.
- [ImportCookies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importcookies): consentire l'importazione di cookie.
- [ImportShortcuts](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#importshortcuts): consentire l'importazione di collegamenti.
- [InternetExplorerIntegrationSiteRedirect](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsiteredirect): specificare il comportamento degli spostamenti "nella pagina" verso i siti non configurati all'avvio dalle pagine in modalità Internet Explorer.
- [StricterMixedContentTreatmentEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#strictermixedcontenttreatmentenabled): abilitare un trattamento più rigido per i contenuti misti.
- [TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled): abilitare una funzionalità di sicurezza TLS 1.3 per trust anchor locali.
- [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin): configurare l'accesso automatico con un account di dominio Active Directory quando non esiste un account di dominio Azure AD.

#### Modifiche ai nomi dei criteri e alla didascalia

Il criterio `OmniboxMSBProviderEnabled` è stato modificato in [AddressBarMicrosoftSearchInBingProviderEnabled](https://docs.microsoft.com//DeployEdge/microsoft-edge-policies#addressbarmicrosoftsearchinbingproviderenabled) - La didascalia del criterio è "Abilitare Microsoft Search nei suggerimenti di Bing nella barra degli indirizzi".

#### Criteri deprecati

I criteri seguenti continueranno a funzionare in questa versione, ma diventeranno "obsoleti" in una versione futura.

- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled): riattivare l'API dei componenti Web v0 fino a M84.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies). consentire a WebDriver di eseguire l'override di criteri incompatibili.

#### Problemi risolti

- È stato risolto un problema per cui nella modalità IE di Microsoft Edge veniva visualizzata una finestra di dialogo di download in corso anche dopo che il file era stato scaricato.
- È stato risolto un problema per cui Microsoft Edge eliminava i cookie di sessione quando una pagina già in modalità IE causava l'apertura di una nuova scheda in modalità IE.

## Versione 80.0.361.111: 7 aprile

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 80.0.361.109: 1 aprile

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#april-1-2020).

## Versione 80.0.361.69: 19 marzo

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#march-19-2020).

## Versione 80.0.361.66: 4 marzo

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#march-4-2020).

## Versione 80.0.361.62: 25 febbraio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/deployedge/microsoft-edge-relnotes-security#february-25-2020).

## Versione 80.0.361.57: 20 febbraio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#february-20-2020).

## Versione 80.0.361.56: 19 febbraio

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 80.0.361.54: 14 febbraio

### Problemi risolti

- È stato risolto un problema per cui le password, i pagamenti e i cookie non venivano importati in Microsoft Edge.

## Versione 80.0.361.50: 11 febbraio

Risolti diversi bug e miglioramenti delle prestazioni.

## Versione 80.0.361.48: 7 febbraio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/deployedge/microsoft-edge-relnotes-security#february-7-2020).

### Aggiornamenti delle funzionalità

- È stata aggiunta la protezione SmartScreen da download di app potenzialmente indesiderate. [Scopri di più](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)
- È stato aggiunto il supporto per la riproduzione Dolby Vision.
- È stata abilitata per gli utenti di Windows Mixed Reality la possibilità di visualizzare i video a 360 ° nei visori VR.
- È stata aggiunta un'opzione alla Visualizzazione lettura per aumentare la spaziatura del testo.
- È stato aggiunto il supporto per la cancellazione dei collegamenti tramite la gomma della Penna per Surface.
- È stato aggiunto il supporto per usare i tasti di direzione e la barra spaziatrice per disegnare sugli screenshot dei feedback in modalità editor.
- È stata migliorata l'affidabilità degli screenshot in modo che non appaiano più totalmente neri durante l'invio di feedback.
- È stato aggiunto il supporto tema scuro alla pagina Nuova scheda locale visualizzata quando il dispositivo non è connesso a Internet.
- È stata aggiunta la possibilità di ripristinare i siti Web installati come applicazioni, quando viene ripristinata una sessione del browser dopo l'aggiornamento, l'arresto anomalo del sistema e così via.
- È stato aggiunto il supporto tema scuro all'interfaccia utente PDF quando il browser è gestito da Criteri di gruppo.
- Aggiornamento di Adobe Flash alla versione 32.0.0.321. [Scopri di più](https://helpx.adobe.com/flash-player/release-note/fp_32_air_32_release_notes.html)

### Aggiornamenti dei criteri

#### Nuovi criteri

Sono stati aggiunti 16 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise). Sono stati aggiunti i nuovi criteri seguenti.

- [AlternateErrorPagesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#alternateerrorpagesenabled) - Suggerisce pagine simili quando non è possibile trovare una pagina Web.
- [DefaultInsecureContentSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultinsecurecontentsetting) - Controlla l'uso di eccezioni di contenuti non sicuri.
- [DNSInterceptionChecksEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#dnsinterceptionchecksenabled) - Abilita i controlli di intercettazione DNS.
- [HideFirstRunExperience](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hidefirstrunexperience) - Nasconde l'esperienza della prima esecuzione e la schermata iniziale.
- [InsecureContentAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecurecontentallowedforurls) - Consente i contenuti non sicuri nei siti specificati.
- [InsecureContentBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecurecontentblockedforurls) - Blocca i contenuti non sicuri nei siti specificati.
- [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) - Abilita l'impostazione di comportamento dei cookie SameSite legacy predefinita.
- [LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) - Ripristina il comportamento SameSite legacy per i cookie nei siti specificati.
- [PaymentMethodQueryEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#paymentmethodqueryenabled) - Consente ai siti Web di eseguire query per i metodi di pagamento disponibili.
- [PersonalizationReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#personalizationreportingenabled) - Consente la personalizzazione degli annunci, della ricerca e delle notizie con l'invio della cronologia esplorazioni a Microsoft.
- [PinningWizardAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pinningwizardallowed) - Consente la procedura guidata per Aggiungi alla barra delle applicazioni.
- [SmartScreenPuaEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) - Configura Microsoft Defender SmartScreen per bloccare le applicazioni potenzialmente indesiderate.
- [TotalMemoryLimitMb](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#totalmemorylimitmb) - Imposta un limite per i megabyte di memoria che possono essere usati in un'unica istanza di Microsoft Edge.
- [WebAppInstallForceList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webappinstallforcelist) - Configura l'elenco delle app Web installate forzatamente.
- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - Riattiva l'API dei componenti Web v0 fino a M84.
- [WebRtcLocalIpsAllowedUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtclocalipsallowedurls) - Gestisce l'esposizione degli indirizzi IP locali tramite WebRTC.

#### Criteri deprecati

Il criterio seguente è deprecato.

- [NewTabPageCompanyLogo](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagecompanylogo) - Imposta il logo della pagina Nuova a scheda.

### Problemi risolti

- È stato risolto un problema per cui l'audio non funzionava in ambiente Citrix.
- È stato risolto un problema per cui Microsoft Edge e l'esperienza affiancata di Microsoft Edge legacy causavano collegamenti legacy interrotti e arresti in modo anomalo.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)