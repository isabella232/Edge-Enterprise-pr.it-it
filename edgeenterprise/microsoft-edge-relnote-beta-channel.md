---
title: Note sulla versione di Microsoft Edge per il canale Beta
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Beta
ms.openlocfilehash: 3c1b87b2ecaf68acf0bca447553b25d0b202e7ea
ms.sourcegitcommit: ceecf4d9baf9dc677652ca07a6d2f2e17ef5b3b7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440307"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Note sulla versione per il canale Microsoft Edge Beta

Queste note sulla versione contengono informazioni sulle nuove funzionalità e gli aggiornamenti non relativi alla sicurezza inclusi nel canale Microsoft Edge Beta. Le versioni precedenti di queste note sulla versione sono archiviate [qui](microsoft-edge-relnote-archive-beta-channel.md).

> [!NOTE]
> Abbiamo aggiornato la nota sulla versione di Microsoft Edge Beta [versione 89.0.774.18: febbraio 3](#version-89077418-february-3), in modo da riflettere le funzionalità disponibili.

<!-- begin major 90 -->
## <a name="version-90081808-march-16"></a>Versione 90.0.818.08: 16 marzo

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Single Sign-On (SSO) è ora disponibile per gli account di Azure Active Directory (Azure AD) e l’account Microsoft (MSA) in macOS**. Un utente che ha eseguito l'accesso a Microsoft Edge su macOS eseguirà automaticamente l'accesso su siti Web configurati per consentire l'accesso singolo con gli account di lavoro e Microsoft (ad esempio, bing.com, office.com, msn.com e outlook.com).

- **Stampa:**

  - **Nuova modalità di rasterizzazione di stampa per stampanti non PostScript**. A partire da Microsoft Edge versione 90, gli amministratori possono usare un nuovo criterio per definire la modalità di rasterizzazione della stampa per gli utenti. Questo criterio controlla la modalità di stampa di Microsoft Edge su stampanti non PostScript in Windows.  A volte i processi di stampa su stampanti non PostScript devono essere rasterizzati per essere stampati correttamente. Le opzioni di stampa sono Full e Fast.

  - **Altre opzioni di ridimensionamento della pagina per la stampa**. Gli utenti possono ora personalizzare il ridimensionamento durante la stampa di pagine Web e documenti PDF usando opzioni aggiuntive. L'opzione "Adatta alla pagina" garantisce che la pagina Web o il documento si adatti allo spazio disponibile nel "Formato carta" selezionato per la stampa. L'opzione "Dimensioni effettive" garantisce che non vengano apportate modifiche alle dimensioni del contenuto stampato indipendentemente dal "Formato carta" selezionato.

- **Produttività:**

  - **I suggerimenti per il riempimento automatico vengono estesi per includere il contenuto dei campi indirizzo dagli Appunti.** Il contenuto degli Appunti viene analizzato quando si fa clic su un campo di profilo/indirizzo (ad esempio, telefono, e-mail, CAP, città, stato e così via) da visualizzare come suggerimenti di riempimento automatico.

  - **Gli utenti possono cercare suggerimenti di riempimento automatico anche se non viene rilevato un modulo o un campo**. Ora, se le informazioni vengono salvate in Microsoft Edge, i suggerimenti per il riempimento automatico vengono visualizzati automaticamente e consentono di risparmiare tempo durante la compilazione dei moduli. Nei casi in cui il riempimento automatico non è presente in un modulo o se si vogliono recuperare dati in moduli che in genere non prevedono il riempimento automatico (come i moduli temporanei), è possibile cercare le informazioni con il riempimento automatico.

- **Accedere ai download da un riquadro a comparsa nella barra dei menu.** I download verranno visualizzati nell'angolo in alto a destra, con tutti i download attivi in un'unica posizione. Questo menu è facilmente ignorabile, quindi gli utenti possono continuare l'esplorazione senza interruzioni e monitorare l'avanzamento complessivo del download direttamente dalla barra degli strumenti. [Altre informazioni](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).

- **Miglioramenti al rendering dei tipi di carattere**. A partire da Microsoft Edge versione 90, sono stati apportati miglioramenti al rendering del testo per migliorare la chiarezza e aumentare la nitidezza. Parte dei miglioramenti al rendering dei tipi di carattere sarà disponibile nella versione Beta 90, ma è disabilitata per impostazione predefinita.


### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti 7 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti:

- [ApplicationGuardFavoritesSyncEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled): sincronizzazione dei preferiti di Application Guard abilitata
- [ManagedConfigurationPerOrigin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin): imposta i valori di configurazione gestita per i siti Web su origini specifiche
- [PrintRasterizationMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printrasterizationmode): modalità rasterizzazione di stampa
- [QuickViewOfficeFilesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled): gestire la funzionalità QuickView dei file di Office in Microsoft Edge
- [SSLErrorOverrideAllowedForOrigins](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins): consente agli utenti di procedere dalla pagina di avviso HTTPS per origini specifiche
- [WindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#windowocclusionenabled): abilita l’occlusione della finestra
- [WindowsHelloForHTTPAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled): autenticazione di Windows Hello per HTTP abilitata

#### <a name="deprecated-policies"></a>Criteri deprecati

- [NativeWindowOcclusionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled): abilita occlusione finestra nativa
- [SSLVersionMin](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sslversionmin): versione TLS minima abilitata
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a>Versione 89.0.774.54: 13 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077450-march-10"></a>Versione 89.0.774.50: 10 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077448-march-8"></a>Versione 89.0.774.48: 8 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077445-march-3"></a>Versione 89.0.774.45: 3 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077439-february-26"></a>Versione 89.0.774.39: 26 febbraio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077434-february-22"></a>Versione 89.0.774.34: 22 febbraio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077427-february-12"></a>Versione 89.0.774.27: 12 febbraio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-89077423-february-8"></a>Versione 89.0.774.23: 8 febbraio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin major 89 -->
## <a name="version-89077418-february-3"></a>Versione 89.0.774.18: 3 febbraio

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **La modalità tutto schermo offre altre funzionalità di blocco.** A partire da Microsoft Edge versione 89, abbiamo aggiunto altre funzionalità di blocco all'interno della modalità tutto schermo per consentire ai clienti di lavorare in modo produttivo e sicuro. [Altre informazioni](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- **Lo strumento Enterprise Mode Site List Manager sarà disponibile nel browser tramite la pagina *edge://compat***. È possibile usare questo strumento per creare, modificare ed esportare il file XML con l’elenco dei siti per la modalità Internet Explorer di Microsoft Edge. Se necessario, è possibile abilitare l'accesso a questo strumento tramite Criteri di gruppo. [Altre informazioni](https://docs.microsoft.com/deployedge/edge-ie-mode-site-list-manager).

- **Miglioramento delle prestazioni del browser con le schede di sospensione**. Le schede di sospensione migliorano le prestazioni del browser mettendo in sospensione le schede inattive per liberare risorse di sistema come la memoria e la CPU, che potranno essere utilizzate dalle schede attive o da altre applicazioni. Gli utenti possono impedire che i siti attivino la modalità sospensione e configurare l’intervallo di tempo prima che una scheda inattiva entri in sospensione. Per mantenere gli utenti nel flusso di lavoro, sono anche disponibili sistemi [euristici](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434) che evitano che determinati siti entrino in modalità sospensione, ad esempio i siti Intranet. Questa funzionalità può essere gestita tramite i criteri di gruppo.

  > [!NOTE]
  > "Miglioramento delle prestazioni del browser con le schede di sospensione" è un aggiornamento delle note sulla versione del 3 febbraio per la versione principale 89.0.774.18.

- **Reimpostare manualmente i dati di sincronizzazione di Microsoft Edge nel cloud**. Introduzione alla modalità di reimpostazione dei dati di sincronizzazione di Microsoft Edge dall'interno del prodotto. In questo modo i dati degli utenti vengano cancellati dai servizi Microsoft, oltre a risolvere alcuni problemi del prodotto che in precedenza richiedevano un ticket di supporto.

- **Miglioramenti all'esperienza di selezione del testo nei documenti in formato PDF**. Gli utenti inizieranno a ricevere un'esperienza più fluida e coerente di selezione del testo nei documenti PDF aperti in Microsoft Edge, a partire dalla versione 89.

- **Il campo Data di nascita ora è supportato nel riempimento automatico.** Oggi Microsoft Edge permette di risparmiare tempo e fatica nella compilazione di moduli e nella creazione di account online compilando automaticamente i dati, come indirizzi, nomi, numeri di telefono e così via. A partire da Microsoft Edge versione 89, viene aggiunto il supporto per un altro campo che può essere salvato e compilato automaticamente: la data di nascita. Un utente può visualizzare, modificare ed eliminare queste informazioni in qualsiasi momento dalle impostazioni del profilo.

- **Supporto per la ricerca in linguaggio naturale sulla barra degli indirizzi, nella pagina di ricerca nella cronologia e nell'hub della cronologia**. A partire da Microsoft Edge versione 89, trovare un articolo/sito Web sarà più facile con la ricerca in linguaggio naturale sulla barra degli indirizzi, nella pagina della cronologia e nell'hub della cronologia. Gli utenti possono cercare contenuti/descrizioni/intervalli di tempo (ad esempio"ricetta per torta della settimana scorsa") oltre a titoli/corrispondenze con parole chiave dell'URL. Questa funzionalità è limitata a un gruppo di utenti selezionati casualmente che hanno abilitato la sperimentazione. Questi utenti stanno fornendo un feedback al team responsabile della caratteristica.

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

- [BrowsingDataLifetime](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsingdatalifetime): impostazioni vita utile dati di esplorazione
- [maMEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#mamenabled): gestione delle app per dispositivi mobili abilitata
- [DefinePreferredLanguages](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#definepreferredlanguages): definisce un elenco ordinato di lingue preferite in cui i siti internet dovrebbero essere visualizzati, se sono supportate
- [ShowRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showrecommendationsenabled): consente suggerimenti e notifiche promozionali da Microsoft Edge
- [StampaAllowedBackgroundGraphicsModes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingallowedbackgroundgraphicsmodes): limita la modalità di stampa grafica in background
- [printingBackgroundGraphicsDefault](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingbackgroundgraphicsdefault): modalità di stampa grafica in background predefinita
- [elenco SmartActionsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartactionsblocklist): blocca le azioni intelligenti per un elenco di servizi

#### <a name="obsoleted-policies"></a>Criteri obsoleti

- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy): usa un criterio di referrer predefinito di no-referrer-when-downgrade
- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled): abilita la segnalazione dei dati correlati all'uso e agli arresti anomali
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices): invia informazioni sul sito per migliorare i servizi Microsoft
<!-- end major 89 -->

## <a name="version-88070556-january-29"></a>Versione 88.0.705.56: 29 gennaio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-88070549-january-20"></a>Versione 88.0.705.49: 20 gennaio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-88070545-january-15"></a>Versione 88.0.705.45: 15 gennaio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-88070541-january-11"></a>Versione 88.0.705.41: 11 gennaio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-88070529-december-21"></a>Versione 88.0.705.29: 21 dicembre

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin major 88 -->
## <a name="version-88070518-december-9"></a>Versione 88.0.705.18: 9 dicembre

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Elementi deprecati:**

  - È stato deprecato il supporto per il protocollo FTP. Il supporto per il protocollo FTP legacy è stato rimosso da Microsoft Edge. Se si tenta di navigare verso un collegamento FTP, il browser indirizzerà il sistema operativo ad aprire un'applicazione esterna per gestire tale collegamento. In alternativa, gli amministratori IT possono configurare Microsoft Edge per l'utilizzo della modalità IE per i siti che si basano sul protocollo FTP.
  - Il supporto di Adobe Flash sarà rimosso. A partire da Microsoft Edge Beta versione 88, la funzionalità e il supporto di Adobe Flash saranno rimossi. Altre informazioni: [aggiornamento sulla fine del supporto di Adobe Flash Player - Blog di Microsoft Edge (Windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **Autenticazione:**

  - Single Sign-on (SSO) ora disponibile per gli account di Azure Active Directory (Azure AD) e per l'account Microsoft (MSA) in macOS e Windows legacy. Un utente che ha eseguito l'accesso a Microsoft Edge su macOS o su Microsoft Windows (7, 8.1) eseguirà automaticamente l'accesso su siti Web configurati per consentire l'accesso Single Sign-On con gli account lavoro e Microsoft (ad esempio, bing.com, office.com, msn.com, outlook.com).<br>Nota: se l'utente ha eseguito l'accesso a Microsoft Edge con una versione precedente a Microsoft Edge 88 per sfruttare questa funzionalità, potrebbe essere necessario disconnettersi e quindi accedere di nuovo.
  - Passare automaticamente gli utenti di macOS al profilo di lavoro per i siti che eseguono l'autenticazione con l'account di lavoro. A partire da Microsoft Edge versione 88, su macOS offriamo la possibilità di passare ai siti che eseguono l'autenticazione con il profilo di lavoro di un utente.<br>Nota: se l'utente ha eseguito l'accesso a Microsoft Edge con una versione precedente a Microsoft Edge 88 per sfruttare questa funzionalità, potrebbe essere necessario disconnettersi e quindi accedere di nuovo.

- **Opzione modalità tutto schermo per terminare la sessione**. Il pulsante "Termina sessione" è ora disponibile in un'esperienza di navigazione pubblica in modalità tutto schermo. Questa funzionalità assicura che i dati e le impostazioni del browser vengano eliminati alla chiusura di Microsoft Edge. Ulteriori informazioni sulle funzionalità della modalità tutto schermo e sulla roadmap sono disponibili in [Configura la modalità tutto schermo di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode).

- **Sicurezza e privacy:**

  - Gli avvisi vengono generati se la password di un utente viene trovata in una fuga di notizie online. Le password degli utenti vengono confrontate con un repository di credenziali violate note ed invia all'utente un avviso se viene trovata una corrispondenza. Per garantire la sicurezza e la privacy, le password degli utenti vengono sottoposte ad hash e crittografate quando vengono confrontate col il database delle credenziali trapelate.
  - Aggiornare automaticamente il contenuto misto. Le pagine sicure inviate tramite HTTPS possono contenere immagini di riferimento inviate attraverso HTTP non protetto. Per migliorare la privacy e la sicurezza in Microsoft Edge 88, le immagini verranno recuperate tramite HTTPS. Se l'immagine non è disponibile tramite HTTPS, non verrà caricata.
  - Visualizzare le autorizzazioni del sito per sito e per attività recenti. A partire da Microsoft Edge 88, gli utenti potranno gestire più facilmente le autorizzazioni del sito. Saranno in grado di visualizzare le autorizzazioni per sito Web anziché solo per il tipo di autorizzazione. Inoltre, è stata aggiunta una sezione delle attività recenti che mostrerà a un utente tutte le ultime modifiche alle autorizzazioni del sito.
  - Maggior controlli per i cookie del browser. A partire da Microsoft Edge 88, gli utenti possono eliminare i cookie di terze parti senza influire sui cookie di prima parte. Gli utenti potranno anche filtrare i cookie di prima o terze parte in base al nome, al numero di cookie e alla quantità di dati archiviati e all'ultima modifica.

- **Prestazioni:**

  - Migliorare le prestazioni del browser con le schede di sospensione. Le schede di sospensione migliorano le prestazioni del browser mettendo in sospensione le schede inattive per liberare risorse di sistema come la memoria e la CPU, che potranno essere utilizzate dalle schede attive o da altre applicazioni. Gli utenti possono impedire che i siti attivino la modalità sospensione e configurare il periodo di tempo che intercorre prima che una scheda inattiva entri in sospensione. Per mantenere gli utenti nel flusso, esistono anche sistemi euristici per evitare che determinati siti entrino in modalità sospensione, ad esempio i siti Intranet. Questa funzionalità è limitata a un gruppo di utenti selezionati casualmente che hanno abilitato la sperimentazione. Stiamo programmando di implementare per impostazione predefinita la funzionalità delle schede di sospensione con Microsoft Edge versione 89. Questa funzionalità può essere gestita tramite i criteri di gruppo.
  - Migliorare la velocità di avvio di Microsoft Edge con il potenziamento di avvio. Per migliorare la velocità di avvio di Microsoft Edge, abbiamo sviluppato una caratteristica denominata potenziamento di avvio. Il potenziamento di avvio rende Microsoft Edge più veloce, poiché ne permette l'esecuzione in background. Nota: questa funzionalità è limitata a un gruppo di utenti selezionato in modo casuale, i quali hanno abilitato la sperimentazione. Questi utenti stanno fornendo un feedback al team responsabile della caratteristica.

- **Produttività:**

  - Migliorare la produttività e il multitasking con le schede verticali. Con l'aumento graduale del numero di schede orizzontali, i titoli dei siti iniziano a essere tagliati e i controlli struttura a schede vengono persi con il restringimento di ogni scheda. Tale operazione interrompe il flusso di lavoro degli utenti, che si trovano a dover dedicare più tempo alla ricerca, al cambio e alla gestione delle schede e meno tempo sull'attività del momento. Le schede verticali consentono agli utenti di spostare le schede sul lato, dove le icone allineate verticalmente e i titoli dei siti più lunghi semplificano la ricerca, l'individuazione e il passaggio rapidi alla scheda che vogliono aprire.
  - Riempimento automatico del campo data di nascita. Microsoft Edge consente già di risparmiare tempo e fatica durante la compilazione di moduli e la creazione di account online tramite il riempimento automatico di dati utente quali indirizzi, nomi, numeri di telefono e così via. Microsoft Edge ora supporta il campo data di nascita, che gli utenti possono salvare e riempire automaticamente. Un utente può visualizzare, modificare ed eliminare queste informazioni in qualsiasi momento dalle impostazioni del profilo.
  - Miglioramenti alla sezione Chiuse di recente della cronologia. La sezione Chiuse di recente ora conserva le ultime 25 schede e finestre di qualsiasi sessione di esplorazione passata, piuttosto che limitarsi alla sessione precedente. Gli utenti possono selezionare Chiuse di recente dalla nuova esperienza di Cronologia, in modo da visualizzare tutte le schede aperte.
  - La funzionalità “La tua giornata in breve” è stata abilitata per impostazione predefinita. A partire dalla versione 88 di Microsoft Edge, gli operatori dell’informazione possono trarre vantaggio dalle funzionalità di produttività intelligenti nella pagina Nuova scheda (NTP). Offriamo agli utenti che effettuano l’accesso con il loro account di lavoro o dell'istituto di istruzione contenuto personalizzato e pertinente con tecnologia M365 Graph. Gli utenti possono analizzare rapidamente i moduli di "La tua giornata in breve", in modo da tenere facilmente traccia delle riunioni e del lavoro recente, nonché per avviare rapidamente le applicazioni che desiderano usare.

- **PDF:**

  - Visualizzazione del documento PDF nella vista libro (due pagine). A partire da Microsoft Edge versione 88, gli utenti possono visualizzare i documenti PDF in una singola pagina o nella visualizzazione libro a due pagine. Per modificare la visualizzazione, fare clic sul pulsante **Visualizzazione pagina** sulla barra degli strumenti.
  - Supporto di note di testo ancorate per i file PDF. A partire da Microsoft Edge versione 87, gli utenti possono aggiungere note a qualsiasi testo nei file PDF.
  - Esperienza più agevole di selezione del testo nei documenti PDF. Gli utenti riceveranno un'esperienza più fluida e coerente di selezione del testo nei documenti PDF aperti in Microsoft Edge.
  - Visualizzare le pagine Web salvate come file PDF nella barra dei download. Gli utenti possono ora visualizzare i file PDF generati impostando "Salva come PDF" come destinazione della stampante per le pagine Web nella barra di download.

- **Tipi di carattere:**

  - Le icone del browser vengono aggiornate nel sistema di progettazione Office Fluent. Come parte del nostro lavoro continuo relativo a Fluent Design nel browser, abbiamo apportato modifiche alle icone di allineamento più ravvicinate nel nuovo sistema di icone Microsoft. Queste modifiche avranno un impatto su diverse delle nostre interfacce utente high touch, incluse le schede, la barra degli indirizzi, nonché le icone di spostamento e di interazione presenti nei vari menu.
  - Rendering migliorato del tipo di carattere. Il rendering del testo è migliorato per aumentare la chiarezza e ridurre la sfocatura.

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti sedici nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti.

- [BlockExternalExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#blockexternalextensions): blocca l'installazione delle estensioni esterne.
- [InternetExplorerIntegrationLocalFileAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileallowed): consente l'avvio di file locali in modalità Internet Explorer.
- [InternetExplorerIntegrationLocalFileExtensionAllowList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileextensionallowlist):apre i file locali nell'elenco Consenti estensione file in modalità Internet Explorer.
- [InternetExplorerIntegrationLocalFileShowContextMenu](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileshowcontextmenu): mostra il menu di scelta rapida per aprire un collegamento in modalità Internet Explorer.
- [IntranetRedirectBehavior](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intranetredirectbehavior): comportamento del reindirizzamento delle Intranet.
- [PrinterTypeDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printertypedenylist): disabilita i tipi di stampante nell'elenco degli indirizzi non consentiti.
- [ShowMicrosoftRewards](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showmicrosoftrewards): mostra le esperienze di Microsoft Rewards.
- [SleepingTabsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsenabled): configura le schede di sospensione.
- [SleepingTabsTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabstimeout): imposta il timeout di inattività della scheda in background per le schede di sospensione.
- [SleepingTabsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsblockedforurls): blocca le schede di sospensione in siti specifici.
- [StartupBoostEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#startupboostenabled) attiva il potenziamento di avvio.
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride): specifica in che modo Microsoft Edge Update gestisce gli aggiornamenti disponibili da Microsoft Edge.
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed): configura la disponibilità di un layout verticale per le schede sul lato del browser.
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols): consenti downgrade TLS/DTLS legacy in WebRTC.

#### <a name="deprecated-policies"></a>Criteri deprecati

I criteri seguenti sono deprecati.

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled): abilita l'autenticazione proattiva.
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist): configura le regole di esclusione di proxy.
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode): configura le impostazioni del server proxy.
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl): imposta l'URL del file .pac del proxy.
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver): configura l'indirizzo o l'URL del server proxy.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies): consente a WebDriver di eseguire la sostituzione dei criteri non compatibili.

#### <a name="obsoleted-policies"></a>Criteri obsoleti

I criteri seguenti sono obsoleti.

- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting): impostazione predefinita di Adobe Flash.
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls): consente il plug-in Adobe Flash in siti specifici.
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls): blocca il plug-in Adobe Flash in siti specifici.
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) estende l'impostazione del contenuto Adobe Flash a tutto il contenuto.

<!-- end major 88 -->

## <a name="version-87066455-december-3"></a>Versione 87.0.664.55: 3 dicembre

Risolti diversi bug e problemi relativi alle prestazioni. La seguente nuova funzionalità è supportata in questa versione.

- **Vengono generati degli avvisi se la password di un utente viene trovata in una falla online**. Le password degli utenti vengono confrontate con un repository di credenziali violate note ed invia all'utente un avviso se viene trovata una corrispondenza. Per garantire la sicurezza e la privacy, le password degli utenti vengono sottoposte ad hash e crittografate quando vengono confrontate col il database delle credenziali trapelate.

## <a name="version-87066452-november-30"></a>Versione 87.0.664.52: 30 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066440-november-18"></a>Versione 87.0.664.40:18 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066436-november-16"></a>Versione 87.0.664.36:16 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066430-november-9"></a>Versione 87.0.664.30: 9 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066424-november-2"></a>Versione 87.0.664.24: 2 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066418-october-26"></a>Versione 87.0.664.18: 26 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin major 87 -->
## <a name="version-87066412-october-20"></a>Versione 87.0.664.12: 20 ottobre

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Funzionalità di privacy in modalità tutto schermo abilitate**. A partire da Microsoft Edge versione 87, saranno abilitate le funzionalità della modalità tutto schermo in grado di garantire la privacy dei dati degli utenti. Queste funzionalità consentiranno esperienze come la cancellazione dei dati utente all'uscita, l'eliminazione dei file scaricati e il ripristino dell'esperienza di avvio configurata dopo un periodo di inattività specificato. Altre informazioni su come [Configurare le opzioni della modalità tutto schermo di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)
- **Distribuzione ClickOnce abilitata per impostazione predefinita**. ClickOnce è abilitata per impostazione predefinita in Microsoft Edge 87, il che riduce gli ostacoli per le aziende nella distribuzione del software e meglio si allinea con il comportamento del browser Versione legacy di Microsoft Edge. A partire da Microsoft Edge 87, lo stato "Non configurato" del criterio ClickOnceEnabled rifletterà il nuovo stato di ClickOnce per impostazione predefinita di Abilitato (rispetto al precedente stato per impostazione predefinita di Disabilitato).
- **La pagina Nuova scheda per utenti Enterprise (NTP) integra la produttività con contenuti di feed personalizzabili e rilevanti per il lavoro**. La pagina NTP Enterprise combina la pagina di produttività di Office 365, offerta agli utenti che hanno eseguito l'accesso con il proprio account aziendale o dell'Istituto di istruzione, con feed aziendali e di settore personalizzati e rilevanti per il lavoro, organizzati in una sola pagina. Gli utenti saranno in grado di riconoscere il consueto contenuto di Office 365 e Microsoft Search for Business con tecnologia Bing. Inoltre, possono facilmente passare a un “My Feed” personalizzabile con contenuti e moduli rilevanti per l'utente, la sua società o il suo settore, nonché a una selezione di altri feed resi disponibili dall'organizzazione. [Ulteriori informazioni](https://docs.microsoft.com/microsoft-365/admin/manage/manage-industry-news?view=o365-worldwide&preserve-view=true).

- **Privacy e sicurezza:**

  - Supportare l’associazione di token TLS per i siti configurati dai criteri. L'associazione di token TLS aiuta a prevenire gli attacchi per il furto di token per assicurare che i cookie non possano essere riutilizzati da un dispositivo diverso dal dispositivo in cui sono stati inizialmente impostati. L'uso dell'associazione di token TLS richiede l'impostazione del criterio [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) e richiede che i siti elencati supportino questa funzionalità.

- **Supporto per tastiera per evidenziatore nei file PDF**. Gli utenti possono usare i tasti della tastiera per evidenziare qualsiasi testo in un file PDF.

- **Stampa:**

  - Scegliere il lato da capovolgere quando si stampa su entrambi i lati. Gli utenti possono scegliere di capovolgere il lato lungo o il lato corto di un foglio quando si stampa su entrambi i lati.
  - Scegliere la modalità di rasterizzazione della stampa per l'azienda. Controllare il modo in cui Microsoft Edge stampa su una stampante non-PostScript in Windows. A volte i processi di stampa su stampanti non-PostScript devono essere rasterizzati per essere stampati correttamente. Le opzioni di stampa sono "Completa" e "Rapida".

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti dieci nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti.

- [ConfigureFriendlyURLFormat](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configurefriendlyurlformat) - Configura il formato incolla predefinito degli URL copiati da Microsoft Edge e determina se saranno disponibili formati aggiuntivi per gli utenti.
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) - Shopping in Microsoft Edge abilitato.
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) - Nasconde la finestra di dialogo di reindirizzamento una tantum e il banner su Microsoft Edge.
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) - Configura la modifica della barra degli indirizzi per l'esperienza di navigazione pubblica in modalità tutto schermo.
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) - Elimina i file scaricati durante le sessioni a tutto schermo quando Microsoft Edge si chiude.
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) - Abilita il pulsante di rivelazione della password.
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) - Impedisce l'installazione di BHO per reindirizzare i siti incompatibili da Internet Explorer a Microsoft Edge.
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) - Reindirizza i siti incompatibili da Internet Explorer a Microsoft Edge.
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) - Configura il riconoscimento vocale.
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) - Abilita la funzionalità di acquisizione web in Microsoft Edge.

#### <a name="deprecated-policy"></a>Criteri deprecati

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Configura l’esperienza della pagina Nuova scheda di Microsoft Edge.

#### <a name="obsoleted-policy"></a>Criteri obsoleti

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - Riabilita le funzionalità della piattaforma Web deprecate per un periodo di tempo limitato.

<!-- end major 87 -->

## <a name="version-86062243-october-16"></a>Versione 86.0.622.43: 16 ottobre

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-86062236-october-7"></a>Versione 86.0.622.36: 7 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-86062231-october-1"></a>Versione 86.0.622.31: 1 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-86062228-september-28"></a>Versione 86.0.622.28: 28 settembre

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-86062215-september-14"></a>Versione 86.0.622.15: 14 settembre

Sono stati risolti diversi bug e problemi di prestazioni.

<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
