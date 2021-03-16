---
title: Note sulla versione di Microsoft Edge per il canale Stabile
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Stabile
ms.openlocfilehash: 7d08aa1d9cf1f3e04861561169d2f6a01772e5f2
ms.sourcegitcommit: b1060a5c71174ba1d2eea91efb51232beeb97bf8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "11409251"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Note sulla versione del canale Stabile Microsoft Edge

Queste note sulla versione offrono informazioni sulle nuove funzionalità e sugli aggiornamenti non di sicurezza inclusi nel canale Stabile Microsoft Edge.

- Tutti gli aggiornamenti della sicurezza sono elencati [qui](microsoft-edge-relnotes-security.md).
- Le note sulla versione del canale Stable di Microsoft Edge archiviate sono disponibili [qui](microsoft-edge-relnote-archive-stable-channel.md).

 Per informazioni sui canali Microsoft Edge, vedere la [Panoramica dei canali Microsoft Edge](microsoft-edge-channels.md).

> [!NOTE]
> Per il canale Stable, gli aggiornamenti verranno implementati gradualmente su uno o più giorni. Per altre informazioni, vedere [Implementazioni progressive degli aggiornamenti di Microsoft Edge](microsoft-edge-update-progressive-rollout.md).

## <a name="version-89077454-march-13"></a>Versione 89.0.774.54: 13 marzo

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2021-21193](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21193), che è stato segnalato al team di Chromium come un exploit in condizioni normali. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale stabile sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#march-13-2021)

## <a name="version-89077450-march-10"></a>Versione 89.0.774.50: 10 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077448-march-8"></a>Versione 89.0.774.48: 8 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

<!-- begin major 89 -->
## <a name="version-89077445-march-4"></a>Versione 89.0.774.45: 4 marzo

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166) che è stato segnalato dal team di Chromium come un exploit in natura. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#march-4-2021)

### <a name="resolved-issues"></a>Problemi risolti

- **Aggiornamenti e correzioni delle scelte rapide da tastiera del menu Start e della barra delle applicazioni:**
  - Quando fai clic sul collegamento di Microsoft Edge nel menu Start, ora viene mostrata correttamente l'opzione per rimuovere Microsoft Edge dalla barra quando è bloccato in alto.
  - I layout di avvio che includono una [configurazione della barra delle applicazioni](https://docs.microsoft.com/windows/configuration/configure-windows-10-taskbar) per aggiungere Microsoft Edge alla barra delle applicazioni non causano più l'aggiunta di un secondo collegamento a Microsoft Edge alla barra delle applicazioni.
  - Le organizzazioni che usano i profili di roaming di Windows non vedranno più un'icona bianca vuota al posto dell'icona di Microsoft Edge sulla barra delle applicazioni quando gli utenti accedono a Windows.

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **La modalità tutto schermo offre altre funzionalità di blocco.** A partire da Microsoft Edge versione 89, abbiamo aggiunto altre funzionalità di blocco all'interno della modalità tutto schermo per consentire ai clienti di lavorare in modo produttivo e sicuro. [Altre informazioni](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- **Lo strumento Enterprise Mode Site List Manager sarà disponibile nel browser tramite la pagina *edge://compat***. È possibile usare questo strumento per creare, modificare ed esportare il file XML con l’elenco dei siti per la modalità Internet Explorer di Microsoft Edge. Se necessario, è possibile abilitare l'accesso a questo strumento tramite Criteri di gruppo. [Altre informazioni](https://docs.microsoft.com/deployedge/edge-ie-mode-site-list-manager).

- **Miglioramento delle prestazioni del browser con le schede di sospensione**. Le schede di sospensione migliorano le prestazioni del browser mettendo in sospensione le schede inattive per liberare risorse di sistema come la memoria e la CPU, che potranno essere utilizzate dalle schede attive o da altre applicazioni. Gli utenti possono impedire che i siti attivino la modalità sospensione e configurare l’intervallo di tempo prima che una scheda inattiva entri in sospensione. Per mantenere gli utenti nel flusso di lavoro, sono anche disponibili sistemi [euristici](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434) che evitano che determinati siti entrino in modalità sospensione, ad esempio i siti Intranet. Questa funzionalità può essere gestita tramite i criteri di gruppo.

- **Reimpostare manualmente i dati di sincronizzazione di Microsoft Edge nel cloud**. Introduzione alla modalità di reimpostazione dei dati di sincronizzazione di Microsoft Edge dall'interno del prodotto. In questo modo i dati degli utenti vengono cancellati dai servizi Microsoft, inoltre vengono risolti alcuni problemi del prodotto che in precedenza richiedevano un ticket di supporto.

- **Abilitazione intelligente di Single Sign-On (SSO) per tutti gli account di Windows Azure Active Directory (Azure AD) per gli utenti con un singolo profilo Microsoft Edge non Azure AD**.  Attivare automaticamente questa impostazione per gli utenti che potrebbero trarre il massimo vantaggio da questa funzionalità. Se un utente ha un solo profilo Microsoft Edge (non Azure AD o Modalità Bambini), l'impostazione verrà automaticamente attivata all'avvio di Microsoft Edge. Questo interruttore automatico verrà disattivato automaticamente se un utente sceglie in un secondo momento di accedere a un altro profilo Microsoft Edge con un account Azure AD. Gli utenti possono aggiornare manualmente le proprie preferenze per questa funzionalità in **Impostazioni > Profili > Preferenze profilo > Consenti Single Sign-On per i siti aziendali o dell'istituto di istruzione che usano questo profilo**.

- **Miglioramenti all'esperienza di selezione del testo nei documenti PDF**. Gli utenti inizieranno a ricevere un'esperienza più fluida e coerente di selezione del testo nei documenti PDF aperti in Microsoft Edge, a partire dalla versione 89.

- **Il campo Data di nascita ora è supportato nel riempimento automatico.** Oggi Microsoft Edge permette di risparmiare tempo e fatica nella compilazione di moduli e nella creazione di account online compilando automaticamente i dati, come indirizzi, nomi, numeri di telefono e così via. A partire da Microsoft Edge versione 89, viene aggiunto il supporto per un altro campo che può essere salvato e compilato automaticamente: la data di nascita. Un utente può visualizzare, modificare ed eliminare queste informazioni in qualsiasi momento dalle impostazioni del profilo.

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti 7 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti.

- [BrowsingDataLifetime](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsingdatalifetime): impostazioni vita utile dati di esplorazione
- [maMEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#mamenabled): gestione delle app per dispositivi mobili abilitata
- [DefinePreferredLanguages](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#definepreferredlanguages): definisce un elenco ordinato di lingue preferite in cui i siti internet dovrebbero essere visualizzati, se sono supportate
- [ShowRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showrecommendationsenabled) - Consenti consigli e notifiche promozionali da Edge
- [StampaAllowedBackgroundGraphicsModes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingallowedbackgroundgraphicsmodes) - Limita la modalità di stampa grafica in background
- [PrintingBackgroundGraphicsDefault](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingbackgroundgraphicsdefault) - Modalità di stampa grafica di sfondo predefinita
- [SmartActionsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartactionsblocklist) - Blocca le azioni intelligenti per un elenco di servizi

#### <a name="obsoleted-policies"></a>Criteri obsoleti

I criteri seguenti sono obsoleti.

- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy) - Usa un criterio di referrer predefinito di no-referrer-when-downgrade
- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Invia informazioni sul sito per migliorare i servizi Microsoft
<!-- end major 89 -->
## <a name="version-88070581-february-25"></a>Versione 88.0.705.81: 25 febbraio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-88070574-february-17"></a>Versione 88.0.705.74: 17 febbraio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-17-2021)

## <a name="version-88070568-february-11"></a>Versione 88.0.705.68: 11 febbraio

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-88070563-february-5"></a>Versione 88.0.705.63: 5 febbraio

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2021-21148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21148), che è stato segnalato al team di Chromium come un exploit in condizioni normali.

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-5-2021)

## <a name="version-88070562-february-4"></a>Versione 88.0.705.62: 4 febbraio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#February-4-2021)

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-88070556-january-28"></a>Versione 88.0.705.56: 28 gennaio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-88070553-january-26"></a>Versione 88.0.705.53: 26 gennaio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-88070550-january-21"></a>Versione 88.0.705.50: 21 gennaio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-21-2021)

<!--- begin major 88  --->
### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Elementi deprecati:**

  - È stato deprecato il supporto per il protocollo FTP. Il supporto per il protocollo FTP legacy è stato rimosso da Microsoft Edge. Se si tenta di navigare verso un collegamento FTP, il browser indirizzerà il sistema operativo ad aprire un'applicazione esterna per gestire tale collegamento. In alternativa, gli amministratori IT possono configurare Microsoft Edge per l'utilizzo della modalità IE per i siti che si basano sul protocollo FTP.
  - Il supporto di Adobe Flash sarà rimosso. A partire da Microsoft Edge Beta versione 88, la funzionalità e il supporto di Adobe Flash saranno rimossi. Altre informazioni: [aggiornamento sulla fine del supporto di Adobe Flash Player - Blog di Microsoft Edge (Windows.com)](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **Autenticazione:**

  - Single Sign-on (SSO) ora disponibile per gli account di Azure Active Directory (Azure AD) e per l'account Microsoft (MSA) in Windows legacy. Un utente che ha eseguito l'accesso a Microsoft Edge su Microsoft Windows di livello inferiore (7, 8.1) eseguirà automaticamente l'accesso su siti Web configurati per consentire l'accesso singolo con gli account di lavoro e Microsoft (ad esempio, bing.com, office.com, msn.com, outlook.com).<br>Nota: se l'utente ha eseguito l'accesso a Microsoft Edge con una versione precedente a Microsoft Edge 88 per sfruttare questa funzionalità, potrebbe essere necessario disconnettersi e quindi accedere di nuovo.
  
  - Single Sign-On (SSO) per siti di lavoro che usano qualsiasi account Microsoft Azure Active Directory (Azure AD) nel sistema nei profili Microsoft Edge non Azure AD. Questa funzionalità può essere abilitata per qualsiasi profilo che non è connesso con un account aziendale o dell'istituto di istruzione e non è guest o privato e consente l'uso di qualsiasi account aziendale o dell'istituto di istruzione nel sistema operativo con tale profilo. Questa caratteristica può essere configurata in **Impostazioni**  >  **Profili** >  **Preferenze profilo** >  **Consenti l'accesso Single Sign-on per i siti aziendali o dell'Istituto di istruzione usando questo profilo**.
  
    > [!NOTE]
    > "Single Sign-on (SSO) per tutti gli account di Windows che usano il profilo Microsoft Edge" è un aggiornamento delle note sulla versione del 21 gennaio.

- **Opzione modalità tutto schermo per terminare la sessione**. Il pulsante "Termina sessione" è ora disponibile in un'esperienza di navigazione pubblica in modalità tutto schermo. Questa funzionalità assicura che i dati e le impostazioni del browser vengano eliminati alla chiusura di Microsoft Edge. Ulteriori informazioni sulle funzionalità della modalità tutto schermo e sulla roadmap sono disponibili in [Configura la modalità tutto schermo di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode).

- **Sicurezza e privacy:**

  - Gli avvisi vengono generati se la password di un utente viene trovata in una fuga di notizie online. Le password degli utenti vengono confrontate con un repository di credenziali violate note ed invia all'utente un avviso se viene trovata una corrispondenza. Per garantire la sicurezza e la privacy, le password degli utenti vengono sottoposte ad hash e crittografate quando vengono confrontate col il database delle credenziali trapelate.
  - Aggiornare automaticamente il contenuto misto. Le pagine sicure inviate tramite HTTPS possono contenere immagini di riferimento inviate attraverso HTTP non protetto. Per migliorare la privacy e la sicurezza in Microsoft Edge 88, le immagini verranno recuperate tramite HTTPS. Se l'immagine non è disponibile tramite HTTPS, non verrà caricata.
  - Visualizzare le autorizzazioni del sito per sito e per attività recenti. A partire da Microsoft Edge 88, gli utenti potranno gestire più facilmente le autorizzazioni del sito. Saranno in grado di visualizzare le autorizzazioni per sito Web anziché solo per il tipo di autorizzazione. Inoltre, è stata aggiunta una sezione delle attività recenti che mostrerà a un utente tutte le ultime modifiche alle autorizzazioni del sito.
  - Maggior controlli per i cookie del browser. A partire da Microsoft Edge 88, gli utenti possono eliminare i cookie di terze parti senza influire sui cookie di prima parte. Gli utenti potranno anche filtrare i cookie di prima o terze parte in base al nome, al numero di cookie e alla quantità di dati archiviati e all'ultima modifica.

- **Password:**

  - Generatore password. Microsoft Edge offre un generatore di password forte integrato che puoi usare quando ti iscrivi per un nuovo account o quando cambi una password esistente. Basta cercare la password suggerita dal browser nel campo della password e, una volta selezionata, verrà automaticamente salvata nel browser e sincronizzata tra i dispositivi per un facile uso futuro.
  - Monitoraggio password. Quando una delle password salvate nel browser corrisponde a quelle visualizzate nell'elenco di credenziali perse, Microsoft Edge invierà una notifica e chiederà di aggiornare la password. Password Monitor cerca le corrispondenze per vostro conto ed è attivo per impostazione predefinita.
  - Modifica password. Ora è possibile modificare le password salvate direttamente nelle Impostazioni di Microsoft Edge. Ogni volta che una password viene aggiornata all'esterno di Microsoft Edge, è facile sostituire la password salvata in precedenza con quella nuova modificando la voce salvata in Impostazioni. 

- **Miglioramento della velocità di avvio di Microsoft Edge con il potenziamento di avvio**. Per migliorare la velocità di avvio di Microsoft Edge, abbiamo sviluppato una funzionalità denominata potenziamento di avvio. Il potenziamento di avvio rende Microsoft Edge più veloce, poiché ne permette l'esecuzione in background. Nota: questa funzionalità è limitata a un gruppo di utenti selezionato in modo casuale, i quali hanno abilitato la sperimentazione. Questi utenti stanno fornendo un feedback al team responsabile della caratteristica.

- **Produttività:**

  - Migliorare la produttività e il multitasking con le schede verticali. Con l'aumento graduale del numero di schede orizzontali, i titoli dei siti iniziano a essere tagliati e i controlli struttura a schede vengono persi con il restringimento di ogni scheda. Tale operazione interrompe il flusso di lavoro degli utenti, che si trovano a dover dedicare più tempo alla ricerca, al cambio e alla gestione delle schede e meno tempo sull'attività del momento. Le schede verticali consentono agli utenti di spostare le schede sul lato, dove le icone allineate verticalmente e i titoli dei siti più lunghi semplificano la ricerca, l'individuazione e il passaggio rapidi alla scheda che vogliono aprire.
  - Riempimento automatico del campo data di nascita. Microsoft Edge consente già di risparmiare tempo e fatica durante la compilazione di moduli e la creazione di account online tramite il riempimento automatico di dati utente quali indirizzi, nomi, numeri di telefono e così via. Microsoft Edge ora supporta il campo data di nascita, che gli utenti possono salvare e riempire automaticamente. Un utente può visualizzare, modificare ed eliminare queste informazioni in qualsiasi momento dalle impostazioni del profilo.
  - Miglioramenti alla sezione Chiuse di recente della cronologia. La sezione Chiuse di recente ora conserva le ultime 25 schede e finestre di qualsiasi sessione di esplorazione passata, piuttosto che limitarsi alla sessione precedente. Gli utenti possono selezionare Chiuse di recente dalla nuova esperienza di Cronologia, in modo da visualizzare tutte le schede aperte.
  - La funzionalità “La tua giornata in breve” è stata abilitata per impostazione predefinita. A partire dalla versione 88 di Microsoft Edge, gli operatori dell’informazione possono trarre vantaggio dalle funzionalità di produttività intelligenti nella pagina Nuova scheda (NTP). Anche gli utenti di Microsoft Edge 87 avranno accesso a queste caratteristiche entro 2 settimane dal rilascio di Microsoft Edge 88. Offriamo agli utenti che effettuano l’accesso con il loro account di lavoro o dell'istituto di istruzione contenuto personalizzato e pertinente con tecnologia M365 Graph. Gli utenti possono analizzare rapidamente i moduli di "La tua giornata in breve", in modo da tenere facilmente traccia delle riunioni e del lavoro recente, nonché per avviare rapidamente le applicazioni che desiderano usare.

- **Sincronizzazione cronologia e apertura delle schede**. La sincronizzazione della cronologia di navigazione e di apertura delle schede è ora disponibile per tutti gli utenti. L'attivazione di queste funzionalità consentirà agli utenti di riprendere da dove hanno interrotto rendendo disponibile la cronologia di navigazione e di apertura delle schede in tutti i dispositivi di sincronizzazione. I criteri di sincronizzazione e cronologia dei browser sono stati aggiornati, quindi ora gli utenti sono connessi e produttivi in tutti i dispositivi usando Microsoft Edge. [Ulteriori informazioni](https://blogs.windows.com/windowsexperience/2021/01/21/this-year-lets-resolve-to-make-the-most-of-our-time-online-and-better-protect-ourselves-from-online-threats/).

- **PDF:**

  - Visualizzazione del documento PDF nella vista libro (due pagine). A partire da Microsoft Edge versione 88, gli utenti possono visualizzare i documenti PDF in una singola pagina o nella visualizzazione libro a due pagine. Per modificare la visualizzazione, fare clic sul pulsante **Visualizzazione pagina** sulla barra degli strumenti.
  - Supporto di note di testo ancorate per i file PDF. A partire da Microsoft Edge versione 87, gli utenti possono aggiungere note a qualsiasi testo nei file PDF.

- **Tipi di carattere:**

  - Le icone del browser vengono aggiornate nel sistema di progettazione Office Fluent. Come parte del nostro lavoro continuo relativo a Fluent Design nel browser, abbiamo apportato modifiche alle icone di allineamento più ravvicinate nel nuovo sistema di icone Microsoft. Queste modifiche avranno un impatto su diverse delle nostre interfacce utente high touch, incluse le schede, la barra degli indirizzi, nonché le icone di spostamento e di interazione presenti nei vari menu.
  - Rendering migliorato del tipo di carattere. Il rendering del testo è migliorato per aumentare la chiarezza e ridurre la sfocatura.

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti 18 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti.

- [BasicAuthOverHttpEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#basicauthoverhttpenabled) - Consentire l'autenticazione di base per HTTP.
- [BlockExternalExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#blockexternalextensions) - blocca l'installazione delle estensioni esterne.
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
- [targetBlankImpliesNoOpener](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#targetblankimpliesnoopener) : non impostare window.opener per i collegamenti di destinazione _blank.
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride): specifica in che modo Microsoft Edge Update gestisce gli aggiornamenti disponibili da Microsoft Edge.
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed): configura la disponibilità di un layout verticale per le schede sul lato del browser.
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols): consenti downgrade TLS/DTLS legacy in WebRTC.
- [WebWidgetAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webwidgetallowed): abilita il widget Web.
- [WebWidgetIsEnabledOnStartup](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webwidgetisenabledonstartup) : consente il widget Web all'avvio di Windows.

#### <a name="deprecated-policies"></a>Criteri deprecati

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled): abilita l'autenticazione proattiva.
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist): configura le regole di esclusione di proxy.
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode): configura le impostazioni del server proxy.
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl): imposta l'URL del file .pac del proxy.
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver): configura l'indirizzo o l'URL del server proxy.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies): consente a WebDriver di eseguire la sostituzione dei criteri non compatibili.

### <a name="obsoleted-policies"></a>Criteri obsoleti

- [di spostamento a pagina](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#allowpopupsduringpageunload) A una pagina di mostrare i popup durante lo scaricamento.
- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting): impostazione predefinita di Adobe Flash.
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls): consente il plug-in Adobe Flash in siti specifici.
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls): blocca il plug-in Adobe Flash in siti specifici.
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) estende l'impostazione del contenuto Adobe Flash a tutto il contenuto.
<!--- end major 88  --->
## <a name="version-87066475-january-7"></a>Versione 87.0.664.75: 7 gennaio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-7-2021)

## <a name="version-87066466-december-17"></a>Versione 87.0.664.66: 17 dicembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066460-december-10"></a>Versione 87.0.664.60: 10 dicembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066457-december-7"></a>Versione 87.0.664.57: 7 dicembre

Sono stati risolti diversi bug e problemi di prestazioni. Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#december-7-2020)

## <a name="version-87066455-december-3"></a>Versione 87.0.664.55: 3 dicembre

Risolti diversi bug e problemi relativi alle prestazioni. La funzionalità seguente è stata aggiornata per questa versione.

- **Shopping è abilitato per impostazione predefinita**. A partire da Microsoft Edge versione 87, gli utenti aziendali possono trarre vantaggio dallo shopping in Microsoft Edge. Grazie alla funzionalità Shopping, Microsoft Edge consente agli utenti di trovare buoni sconto e prezzi migliori durante lo shopping online. (L'esperienza dei buoni sconto è stata rilasciata con la versione stabile 87.0.664.41). L'esperienza di confronto dei prezzi è ora disponibile con questo aggiornamento. Questa funzionalità può essere configurata usando il criterio [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled). Vedere il [Blog](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) e [Altre informazioni](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping) su Microsoft Shopping.

## <a name="version-87066452-november-30"></a>Versione 87.0.664.52: 30 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-87066447-november-23"></a>Versione 87.0.664.47: 23 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin major 87 --->
## <a name="version-87066441-november-19"></a>Versione 87.0.664.41: 19 novembre

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-19-2020)

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Reindirizzamento automatico per siti incompatibili da Internet Explorer a Microsoft Edge**. A partire dall’aggiornamento di Microsoft Edge 87 Stable, i siti Web pubblici che mostrano un messaggio di incompatibilità in Internet Explorer verranno reindirizzati automaticamente a Microsoft Edge. Per altre informazioni e per configurare questa esperienza, vedere [Reindirizzamento dei siti incompatibili](https://docs.microsoft.com/deployedge/edge-learnmore-neededge).

- **Funzionalità di privacy in modalità tutto schermo abilitate**. A partire da Microsoft Edge versione 87, saranno abilitate le funzionalità della modalità tutto schermo in grado di garantire la privacy dei dati degli utenti. Queste funzionalità consentiranno esperienze come la cancellazione dei dati utente all'uscita, l'eliminazione dei file scaricati e il ripristino dell'esperienza di avvio configurata dopo un periodo di inattività specificato. Altre informazioni su come [Configurare le opzioni della modalità tutto schermo di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)

- **Funzionalità per gli acquisti abilitate per impostazione predefinita**. A partire da Microsoft Edge versione 87, gli utenti enterprise possono trarre vantaggio dagli acquisti in Edge. Con le funzionalità di acquisto, Microsoft Edge aiuta gli utenti a trovare coupon e prezzi migliori durante gli acquisti online. L'esperienza dei coupon è disponibile con questo aggiornamento e il confronto dei prezzi verrà rilasciato nei prossimi aggiornamenti per Microsoft Edge 87. Questa funzionalità può essere configurata tramite il criterio [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled). Vedere il [Blog](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) e [altre informazioni](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping) su Microsoft shopping.

- **Distribuzione ClickOnce abilitata per impostazione predefinita**. ClickOnce è abilitata per impostazione predefinita in Microsoft Edge 87, il che riduce gli ostacoli per le aziende nella distribuzione del software e meglio si allinea con il comportamento del browser Versione legacy di Microsoft Edge. A partire da Microsoft Edge 87, lo stato "Non configurato" del criterio ClickOnceEnabled rifletterà il nuovo stato di ClickOnce per impostazione predefinita di Abilitato (rispetto al precedente stato per impostazione predefinita di Disabilitato).

- **La pagina Nuova scheda per utenti Enterprise (NTP) integra la produttività con contenuti di feed personalizzabili e rilevanti per il lavoro**. La pagina NTP Enterprise combina la pagina di produttività di Office 365, offerta agli utenti che hanno eseguito l'accesso con il proprio account aziendale o dell'Istituto di istruzione, con feed aziendali e di settore personalizzati e rilevanti per il lavoro, organizzati in una sola pagina. Gli utenti saranno in grado di riconoscere il consueto contenuto di Office 365 e Microsoft Search for Business con tecnologia Bing. Inoltre, è possibile personalizzare facilmente "Il mio feed" scegliendo il contenuto più pertinente tra i contenuti e i moduli disponibili per l’organizzazione. Gli amministratori IT possono controllare le impostazioni del feed di notizie per la propria organizzazione, incluso il settore selezionato per la pagina della nuova scheda di Edge, accedendo all'interfaccia di amministrazione di Microsoft 365. [Altre informazioni](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

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
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) - Pulsante Abilita rivelazione password.
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) - Impedisce l'installazione dell’oggetto browser helper (BHO) per reindirizzare i siti incompatibili da Internet Explorer a Microsoft Edge.
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) - Reindirizza i siti incompatibili da Internet Explorer a Microsoft Edge.
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) - Configura il riconoscimento vocale.
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) - Abilita la funzionalità di acquisizione web in Microsoft Edge.

#### <a name="deprecated-policy"></a>Criteri deprecati

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Configura l’esperienza della pagina Nuova scheda di Microsoft Edge.

#### <a name="obsoleted-policy"></a>Criteri obsoleti

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - Riabilita le funzionalità deprecate della piattaforma Web per un periodo di tempo limitato.

<!-- end major 87 -->

## <a name="version-86062269-november-13"></a>Versione 86.0.622.69: 13 novembre

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) e [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017), che sono stati segnalati al team di Chromium come un exploit in condizioni normali.

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-13-2020)

## <a name="version-86062268-november-11"></a>Versione 86.0.622.68: 11 novembre

Gli aggiornamenti della sicurezza del canale Stable sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-11-2020)

## <a name="version-86062263-november-4"></a>Versione 86.0.622.63: 4 novembre

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009), che è stato segnalato al team di Chromium come un exploit in condizioni normali.

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-4-2020)

## <a name="version-86062261-november-2"></a>Versione 86.0.622.61: 2 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-86062258-october-29"></a>Versione 86.0.622.58: 29 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-86062256-october-27"></a>Versione 86.0.622.56: 27 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-86062251-october-22"></a>Versione 86.0.622.51: 22 ottobre

Gli aggiornamenti della sicurezza del canale Stable sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-22-2020)

## <a name="version-86062248-october-20"></a>Versione 86.0.622.48: 20 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## <a name="version-86062243-october-15"></a>Versione 86.0.622.43: 15 ottobre

Sono stati risolti diversi bug e problemi di prestazioni.

<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
