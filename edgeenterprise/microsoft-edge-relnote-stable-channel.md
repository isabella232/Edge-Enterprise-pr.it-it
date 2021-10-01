---
title: Note sulla versione di Microsoft Edge per il canale Stabile
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 10/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Stabile
ms.openlocfilehash: f15c8e1d4dcd037b0948e7309387ba3baa5d1ffa
ms.sourcegitcommit: 2bf511511f131b8497b3e162c44286c217508885
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2021
ms.locfileid: "12057342"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Note sulla versione del canale Stabile Microsoft Edge

Queste note sulla versione offrono informazioni sulle nuove funzionalità e sugli aggiornamenti non di sicurezza inclusi nel canale Stabile Microsoft Edge.

- Tutti gli aggiornamenti della sicurezza sono elencati [qui](microsoft-edge-relnotes-security.md).
- Le note sulla versione del canale Stable di Microsoft Edge archiviate sono disponibili [qui](microsoft-edge-relnote-archive-stable-channel.md).

 Per informazioni sui canali Microsoft Edge, vedere la [Panoramica dei canali Microsoft Edge](microsoft-edge-channels.md).

> [!NOTE]
> Per il canale Stable, gli aggiornamenti verranno implementati gradualmente su uno o più giorni. Per altre informazioni, vedere [Implementazioni progressive degli aggiornamenti di Microsoft Edge](microsoft-edge-update-progressive-rollout.md).
>
> La piattaforma Microsoft Edge Web si evolve costantemente per migliorare l'esperienza utente, la sicurezza e la privacy. Per altre informazioni, vedere [Modifiche che incidono sulla compatibilità del sito in arrivo su Microsoft Edge](/ microsoft-edge/web-platform/site-impacting-changes).

## <a name="version-94099238-october-1"></a>Versione 94.0.992.38: 1 ottobre

> [!Important]
> Questo aggiornamento contiene una correzione per [CVE-2021-37975](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37975) e [CVE-2021-37976](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37976), segnalate dal team di Chromium come un exploit in natura. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#october-01-2021)

## <a name="version-94099237-september-30"></a>Versione 94.0.992.37: 30 settembre

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-94099231-september-24"></a>Versione 94.0.992.31: 24 settembre

> [!Important]
> Questo aggiornamento contiene una correzione per [CVE-2021-37973](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37973) che è stata segnalata dal team di Chromium come un exploit in natura. Per altre informazioni, vedere [Guida agli aggiornamenti della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#september-24-2021)

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Microsoft Edge ha completato il passaggio a una cadenza di 4 settimane per gli aggiornamenti.**  Abbiamo adottato un nuovo ciclo di rilascio di 4 settimane per le versioni principali. Per saperne di più, vedere: https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/

- **Offerta una nuova opzione Stabile estesa.**  Stiamo offrendo una nuova opzione Stabile estesa ai nostri clienti aziendali gestiti. L'opzione Stabile estesa rimarrà attiva per le revisioni pari e verrà aggiornata ogni 8 settimane. Sarà disponibile un aggiornamento della sicurezza bisettimanale.  Altre informazioni qui: https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **Miglioramenti al comportamento predefinito dell'apertura di file MHTML.**  I file MHTML continueranno ad aprirsi in modalità IE se è abilitata la modalità IE, a meno che il file MHTML non sia stato salvato da Microsoft Edge (usando le opzioni Salva con nome o Salva pagina con nome in Microsoft Edge). Se il file è stato salvato da Microsoft Edge, verrà ora aperto in Microsoft Edge.  Questa modifica consente di risolvere un problema di rendering rilevato quando si apre un file MHTML in modalità IE se salvato da Microsoft Edge.

- **Limitare le richieste di rete privata ai contesti sicuri.** L'accesso alle risorse nelle reti locali (Intranet) dalle pagine su Internet richiede che tali pagine siano recapitate tramite HTTPS. Questa modifica si verifica nel progetto Chromium, su cui Microsoft Edge è basato. Per altre informazioni, passare alla voce [Chrome Platform Status](https://chromestatus.com/feature/5436853517811712). Sono disponibili due criteri di compatibilità per supportare scenari che devono mantenere la compatibilità con le pagine non protette: [InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) e [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls).

- **Bloccare i download di contenuto misto.** Le pagine protette scaricano solo i file ospitati in altre pagine protette e i download ospitati in pagine non protette (non HTTPS) verranno bloccati se avviati da una pagina protetta. Questa modifica si verifica nel progetto Chromium, su cui Microsoft Edge è basato. Per altre informazioni, passare alla [voce del blog sulla sicurezza di Google](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html).

- **Abilitare l'accesso implicito per gli account locali.** Abilitando il criterio [OnlyOnPremisesImplicitSigninEnabled](/deployedge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled), solo gli account locali verranno abilitati per l'accesso implicito.  Microsoft Edge non tenterà di accedere in modo implicito agli account MSA o AAD. Verrà arrestato anche l'aggiornamento dagli account locali agli account AAD.

- **Nuova pagina delle impostazioni di accessibilità.**  Abbiamo riunito le impostazioni relative all'accessibilità in una singola pagina. Puoi trovare la nuova pagina edge://settings/accessibility nell'elenco delle impostazioni principale. Qui puoi trovare le impostazioni per ingrandire la pagina Web, mostrare un contorno ad alta visibilità intorno all'area di stato attivo e altre impostazioni che possono contribuire a migliorare l'esperienza di esplorazione del Web. Continueremo ad aggiungere nuove impostazioni qui nelle versioni future di Microsoft Edge.

***Nuovi criteri***

- 
            [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) Ignora la configurazione dell'elenco di siti di Application Guard ed esplora Edge normalmente
- 
            [OnlyOnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) Solo gli account locali verranno abilitati per l'accesso implicito
- 
            [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) Abilita il supporto per le regole della tabella di routing del sistema operativo Windows quando si effettuano connessioni peer-to-peer tramite WebRTC

***Criteri obsoleti***

- 
            [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) Abilita la funzionalità User-Agent Client Hints

## <a name="version-93096152-september-16"></a>Versione 93.0.961.52: 16 settembre

>[!Important]
>Questo aggiornamento contiene una correzione per [CVE-2021-30633](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30632) che è stata segnalata dal team di Chromium come un exploit in natura. Per altre informazioni, vedere la [Guida agli aggiornamenti della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono elencati [qui](/deployedge/microsoft-edge-relnotes-security#september-16-2021).

## <a name="version-93096147-september-11"></a>Versione 93.0.961.47: 11 settembre

> [!Important]
> Questo aggiornamento contiene un correzione per [CVE-2021-30632](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30632) che è stato segnalato dal team di Chromium come un exploit in natura. Per altre informazioni, vedere la [Guida agli aggiornamenti della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono elencati [qui](/deployedge/microsoft-edge-relnotes-security#september-11-2021).

## <a name="version-93096144-september-9"></a>Versione 93.0.961.44: 9 settembre

Gli aggiornamenti della sicurezza del canale stabile sono elencati [qui](/deployedge/microsoft-edge-relnotes-security#september-09-2021).

## <a name="version-93096138-september-2"></a>Versione 93.0.961.38: 2 settembre

Gli aggiornamenti della sicurezza del canale stabile sono elencati [qui](/deployedge/microsoft-edge-relnotes-security#september-02-2021).

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Preferenze iniziali in Microsoft Edge.**  Microsoft Edge ora supporta un numero limitato di preferenze iniziali (in precedenza Preferenze master). Gli amministratori IT possono distribuire queste impostazioni come predefinite prima che il browser venga eseguito per la prima volta dagli utenti. Ulteriori informazioni qui: [Configurare Microsoft Edge utilizzando le impostazioni delle preferenze iniziali per la prima esecuzione.](/deployedge/initial-preferences-support-on-microsoft-edge-browser)

- **La modalità IE Microsoft Edge supporterà il comportamento di "no-merge".**  Per un utente finale, quando una nuova finestra del browser viene avviata da un'applicazione in modalità IE, si trova in una sessione separata, in modo analogo al comportamento di no-merge in IE11. Sarà necessario modificare l'elenco dei siti per configurare i siti che devono impedire la condivisione della sessione come "no-merge". Dietro le quinte, per ogni finestra di Microsoft Edge, la prima volta che viene visitata una scheda della modalità IE all'interno di tale finestra, se si tratta di uno dei siti di "no-merge" designati, tale finestra viene bloccata in una sessione di IE diversa da tutte le altre finestre di Microsoft Edge almeno fino alla chiusura dell'ultima scheda della modalità IE in quella finestra. Questo comportamento segue il comportamento precedente in cui gli utenti potevano avviare IE con no merge e possono anche avviare Microsoft Edge senza no-merge tramite altri meccanismi.  Altre informazioni qui: [Risoluzione dei problemi in modalità IE e domande frequenti | Microsoft Docs](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--nomerge--option-that-was-supported-in-internet-explorer-11-)

- **Nuovo criterio per interrompere l'accesso implicito.**  Il [criterio ImplicitSignInEnabled](/deployedge/microsoft-edge-policies#implicitsigninenabled) consente agli amministratori di sistema di disabilitare l'accesso implicito sul browser Microsoft Edge.

- **Criteri per ignorare i prompt ClickOnce e DirectInvoke.** I criteri sono stati aggiornati per abilitare il bypass dei prompt di ClickOnce e dell'app di DirectInvoke per tipi di file specificati, dai domini specificati. A tale scopo, è necessario:

  - Abilitare [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled) o [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled)
  - Abilitare [il criterio AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) e impostare l'elenco di tipi di file specifici per cui ClickOnce e DirectInvoke devono essere disabilitati
  - Abilitare il [criterio AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) e impostare l'elenco di domini specifici per cui ClickOnce e DirectInvoke verranno disabilitati.

  Nota: AutoOpenAllowedForURLs è un criterio di supporto per AutoOpenFileTypes. Se AutoOpenAllowedForURLs non è impostato e AutoOpenFileTypes è impostato, i tipi di file elencati verranno aperti automaticamente da tutti gli URL.

- **Gruppi di schede.**  Stiamo attivando il raggruppamento delle schede che consente di categorizzare le schede in gruppi definiti dall'utente e consente di trovare, cambiare e gestire le schede in modo più efficace in più workstream.  

- **Nascondere la barra del titolo quando si utilizzano le schede verticali.**  Recuperare i pochi pixel in più nascondendo la barra del titolo del browser, mentre è in Schede verticali. A questo punto si può andare a edge://settings/appearance e nella sezione Personalizza barra degli strumenti selezionare l'opzione per nascondere la barra del titolo in modalità Tabulazione verticale.

- **Immagine video in immagine (PiP) dalla barra degli strumenti al passaggio del mouse.**  Quando si passa il mouse su un video supportato, viene visualizzata una barra degli strumenti che consente di visualizzare il video in una finestra di PiP.  Nota: questa opzione è attualmente disponibile per Microsoft Edge utenti su macOS.  

- **Rimozione di 3DES in TLS. Il supporto per i pacchetti di crittografia TLS_RSA_WITH_3DES_EDE_CBC_SHA verrà rimosso.** Questa modifica si verifica nel progetto Chromium, su cui Microsoft Edge è basato. Per altre informazioni, passare alla voce [Chrome Platform Status](https://chromestatus.com/feature/6678134168485888). Inoltre, nella Microsoft Edge versione 93, il criterio [TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) sarà disponibile per supportare gli scenari che devono mantenere la compatibilità con i server obsoleti. Questi criteri di compatibilità diventeranno obsoleti e smetteranno di funzionare in Microsoft Edge versione 95. Assicurarsi di aggiornare i server interessati prima di tale aggiornamento.

***Nuovi criteri***

- 
            [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) Consenti la riproduzione automatica di file multimediali in siti specifici
- 
            [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) Accordo chiave post-quantistico CECPQ2 abilitato per TLS
- 
            [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer) Configura la funzionalità Visualizza in Esplora file per le pagine di SharePoint in Microsoft Edge
- 
            [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) Controlla l'uso di JavaScript JIT
- 
            [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled) Consenti alle notifiche di impostare Microsoft Edge come lettore PDF predefinito
- 
            [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) Configura la possibilità per gli utenti di ignorare i flag delle funzionalità
- 
            [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) Abilita l'accesso implicito
- 
            [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) Configura l'elenco dei siti cloud in modalità Enterprise
- 
            [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) Configura la frequenza di aggiornamento dell'elenco siti in modalità Enterprise
- 
            [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) Consenti a JavaScript di usare JIT in questi siti
- 
            [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) Impedisci a JavaScript di usare JIT in questi siti
- 
            [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled) Consenti a Windows di cercare i dati di esplorazione locali di Microsoft Edge
- 
            [MaUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled) Usa sempre Microsoft AutoUpdate come programma di aggiornamento per Microsoft Edge
- 
            [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) Consenti l'accesso Single Sign-On per i siti Microsoft che usano questo profilo
- 
            [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced) Flusso di autenticazione OneAuth applicato per l'accesso
- 
            [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) Consenti agli utenti di ottenere un suggerimento per password complessa ogni volta che creano un account online
- 
            [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) Configura un'impostazione che richieda agli utenti di immettere la password del dispositivo durante l'uso del riempimento automatico della password
- 
            [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) Imposta il layout per la stampa
- 
            [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) Consenti debug remoto
- 
            [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) Imposta l'intervallo di tempo per il riavvio
- 
            [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) Abilita assistenza di viaggio
- 
            [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) Abilita suite di crittografia 3DES in TLS
- 
            [WAMAuthBelowWin10RS3Enabled](/DeployEdge/microsoft-edge-policies#wamauthbelowwin10rs3enabled) WAM per l'autenticazione Windows 10 WAMAuthBelowWin10RS3Enabled abilitato

***Criteri deprecati***

- 
            [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) Abilita l'impostazione predefinita del comportamento dei cookie SameSite legacy

***Criteri obsoleti***

- 
            [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) Configura l’esperienza della pagina Nuova scheda di Microsoft Edge

***Modifica aggiuntiva***

- 
            [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Aggiungi il supporto della piattaforma Mac
- 
            [PasswordMonitorAllowed](/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) Aggiungi il supporto della piattaforma Mac

## <a name="version-92090284-august-26"></a>Versione 92.0.902.84: 26 agosto

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090278-august-19"></a>Versione 92.0.902.78: 19 agosto

Gli aggiornamenti della sicurezza del canale stabile sono elencati [qui](/deployedge/microsoft-edge-relnotes-security#august-19-2021).

## <a name="version-92090273-august-12"></a>Versione 92.0.902.73: 12 agosto

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090267-august-5"></a>Versione 92.0.902.67: 5 agosto

Gli aggiornamenti della sicurezza del canale stabile sono elencati [qui](/deployedge/microsoft-edge-relnotes-security#august-05-2021).

## <a name="version-92090262-july-29"></a>Versione 92.0.902.62: 29 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

### <a name="modified-policy"></a>Criteri modificati

- AutoplayAllowed: l’impostazione su "Disattivato" ora imposta la riproduzione automatica dei file multimediali su "Limita"

## <a name="version-92090255-july-22"></a>Versione 92.0.902.55: 22 luglio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#july-22-2021)

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità


            **Gli utenti possono passare facilmente alla modalità Internet Explorer in Microsoft Edge**. A partire da Microsoft Edge versione 92, gli utenti possono ricaricare un sito in modalità Internet Explorer in Microsoft Edge anziché basarsi sull'applicazione Internet Explorer 11autonoma in attesa della configurazione di un sito nell'elenco dei siti in modalità Enterprise. Agli utenti verrà richiesto di aggiungere il sito all'elenco dei siti locali in modo che il rendering della stessa pagina in Microsoft Edge venga eseguito automaticamente in Internet Explorer per i 30 giorni successivi. È possibile usare il criterio [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) per configurare questa esperienza e consentire l'accesso ai punti di ingresso in modalità Internet Explorer, nonché la possibilità di aggiungere siti all'elenco di siti locale. È possibile usare il criterio [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) per modificare il numero di giorni di conservazione dei siti nell'elenco dei siti locali. Si noti che è necessario KB5003698 o versione successiva per Windows 10 versione 1909 oppure KB5003690 o versione successiva per Windows 10 versione 2004, Windows 10 versione 20H2 o Windows 10 versione 21H1 per l'esperienza end-to-end. Per ulteriori informazioni, vedere [Elenco siti locali in modalità IE.](/deployedge/edge-ie-mode-local-site-list)


            **I file MHTML verranno aperti per impostazione predefinita in modalità Internet Explorer.** 
           A partire da Microsoft Edge versione 92 del canale stabile, i tipi di file MHTML verranno aperti automaticamente in modalità Internet Explorer in Microsoft Edge anziché nell'applicazione Internet Explorer (IE11). Questo si verifica più comunemente durante il tentativo di visualizzare i messaggi di posta elettronica di Outlook in un browser. La modifica avrà effetto solo se Internet Explorer 11 è il gestore predefinito per questo tipo di file. Se si preferisce modificare questa impostazione, è possibile farlo prima di installare l'aggiornamento alla versione 92 del canale stabile usando [questa guida.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)


            **L'avviso "Disabilitare le estensioni per la modalità sviluppatore" può essere ignorato per 2 settimane**. A partire da Microsoft Edge versione 92, è possibile posporre l'avviso "Disabilitare le estensioni per la modalità sviluppatore" di 2 settimane selezionando l'opzione corrispondente nell'elenco a discesa della finestra di avviso.


            **Gestione delle estensioni direttamente dalla barra degli strumenti**. Il nuovo menu delle estensioni sulla barra degli strumenti consente di nascondere/aggiungere facilmente le estensioni. I collegamenti rapidi per gestire le estensioni e trovarne di nuove semplificano la ricerca di nuove estensioni e la gestione di quelle esistenti.


            **Il valore predefinito per la riproduzione automatica verrà impostato su Limita**.  Per garantire la concentrazione dell'utente online, l'impostazione predefinita per la riproduzione automatica dei contenuti multimediali è stata modificata da Limita a Consenti, a partire da Microsoft Edge versione 92.


            **Gli strumenti di pagamento sono ora sincronizzati tra i dispositivi**. A partire da Microsoft Edge versione 92, è possibile sincronizzare le informazioni di pagamento tra i dispositivi connessi. Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non è disponibile, controllare di nuovo a breve mentre l'implementazione prosegue.
Attualmente questa funzionalità è disponibile solo negli Stati Uniti e solo per gli utenti MSA (non AAD)


            **Miglioramenti al rendering dei tipi di carattere**. Sono stati apportati miglioramenti al rendering del testo per migliorare la chiarezza e aumentare la nitidezza. Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non è disponibile, controllare di nuovo a breve mentre l'implementazione prosegue.


            **Le funzionalità dei pulsanti della barra degli strumenti, ad esempio Preferiti e Raccolte, ricordano la scelta dell'utente di bloccarle sul lato della finestra**. Per impostazione predefinita, ora se l'utente sceglie di bloccare un pulsante della barra degli strumenti, verrà sempre aperto nello stato bloccato fino a quando non decide di sbloccarlo.


            **Gli utenti ora possono gestire l'opzione "Consenti l'accesso Single Sign-On per i siti aziendali o dell'istituto di istruzione con questo profilo" tramite Criteri di gruppo**.  L'opzione "Consenti Single Sign-On per i siti aziendali o dell'istituto di istruzione con questo profilo" consente ai profili non AAD di poter utilizzare il Single Sign-On per i siti aziendali o dell'istituto di istruzione utilizzando le credenziali presenti nel computer. Questa opzione viene visualizzata per gli utenti finali come interruttore in Impostazioni -> Profili -> Preferenze profilo solo per i profili non AAD.  È possibile usare il criterio [AADWebSiteSSOUsingThisProfileEnabled](/deployedge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) per configurare il comportamento.  


            **Integrità delle password**: è importante usare password complesse e univoche in diversi account per rimanere al sicuro online. Tuttavia, è più facile a dirsi che a farsi e la maggior parte degli utenti di solito usa password deboli e facili da indovinare o riutilizza le stesse password complesse tra vari account.

Con questa ultima versione di Microsoft Edge, l'utilizzo di password complesse e univoche è un po' più facile. Microsoft Edge ora indicherà se le password salvate sono sufficientemente complesse e indicherà anche se sono state usate in più siti, consentendo di rimanere più sicuri online. È possibile trovare le informazioni sull'integrità delle password nell'elenco delle password salvate nella pagina edge://settings/passwords.
  

            **Aggiunta della privacy per le password salvate**: se si usa un dispositivo condiviso con altri utenti o se il computer è stato lasciato sbloccato per qualsiasi motivo, ora è possibile scegliere una seconda verifica usando la password del dispositivo per evitare che altri utenti possano accedere alle password del sito Web. Semplice!


            **Estensione di Outlook**.  Consente di mantenere il controllo della posta in arrivo, del calendario, delle attività e di altre funzionalità di Microsoft Outlook senza dover aprire una nuova finestra del browser.  È possibile ottenere la nuova estensione di Outlook qui: [Microsoft Outlook - Componenti aggiuntivi di Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/microsoft-outlook/kkpalkknhlklpbflpcpkepmmbnmfailf?hl=en-US)


            **In linea con il progetto open source Chromium, Microsoft Edge sta aggiornando il modo in cui esegue il rendering delle tabelle nelle pagine Web.** 
           Questa modifica consente di risolvere i problemi noti e avvicina Microsoft Edge al modo in cui dovrebbe essere eseguito il rendering delle tabelle sul Web o in altri browser. Si consiglia di testare i flussi di lavoro importanti nell'ambiente per problemi imprevisti. Una spiegazione completa è disponibile [qui](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit).

### <a name="new-policies"></a>Nuovi criteri

- 
            [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single Sign-On per i siti aziendali o degli istituti di istruzione con questo profilo abilitato
- 
            [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configura HTTPS automatico
- 
            [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Controlla l'uso della modalità headless
- 
            [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) Specifica se consentire a siti Web non sicuri di effettuare richieste a endpoint di rete più privati
- 
            [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Consente ai siti elencati di effettuare richieste a endpoint di rete più privati da contesti non sicuri
- 
            [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specifica il numero dei giorni durante i quali un sito rimane nell'elenco dei siti in modalità IE locale
- 
            [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Consenti di ricaricare i siti non configurati in modalità Internet Explorer
- 
            [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifica se è possibile usare elementi SharedArrayBuffer in un contesto non isolato tra origini

### <a name="deprecated-policy"></a>Criteri deprecati

- 
            [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) Consente test in modalità Internet Explorer

### <a name="obsoleted-policy"></a>Criteri obsoleti

- 
            [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Consente certificati firmati con SHA-1 quando emessi da trust anchor locali

## <a name="version-91086471-july-19"></a>Versione 91.0.864.71: 19 luglio

> [!Important]
>Questo aggiornamento contiene una correzione per [CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563) che è stata segnalata dal team di Chromium come un exploit in natura. Per altre informazioni, vedere [Guida agli aggiornamenti della sicurezza](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#july-19-2021)

## <a name="version-91086467-july-8"></a>Versione 91.0.864.67: 8 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086464-july-2"></a>Versione 91.0.864.64: 2 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086459-june-24"></a>Versione 91.0.864.59: 24 giugno

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-24-2021)

## <a name="version-91086454-june-18"></a>Versione 91.0.864.54: 18 giugno

> [!Important]
> Questo aggiornamento contiene una correzione per [CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554) che è stata segnalata dal team di Chromium come un exploit in natura. Per altre informazioni, vedere [Guida agli aggiornamenti della sicurezza](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-18-2021)

## <a name="version-91086448-june-11"></a>Versione 91.0.864.48: 11 giugno

> [!Important]
>Questo aggiornamento contiene una correzione per [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551) che è stata segnalata dal team di Chromium come un exploit in natura. Per altre informazioni, vedere [Guida agli aggiornamenti della sicurezza](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-11-2021)

## <a name="version-91086441-june-3"></a>Versione 91.0.864.41: 3 giugno

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-3-2021)

## <a name="version-91086437-may-27"></a>Versione 91.0.864.37: 27 maggio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#may-27-2021)

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- 
            **Identificare il traffico di rete proveniente dai contenitori a livello di proxy di Microsoft Defender Application Guard.** 
           A partire da Microsoft Edge versione 91, è disponibile un supporto incorporato per contrassegnare il traffico di rete proveniente dai contenitori di Application Guard, consentendo alle aziende di identificarli e applicare criteri specifici.

- 
            **Opzione di supporto per consentire la sincronizzazione dei Preferiti dall'host al contenitore Edge Application Guard.** 
           A partire Microsoft Edge versione 91, gli utenti hanno la possibilità di configurare Application Guard per sincronizzare i preferiti dall'host al contenitore. Questo assicura che anche i nuovi Preferiti vengano visualizzati nel contenitore.

- 
            **A partire da Microsoft Edge versione 91, il browser interromperà automaticamente i download di tipi che potrebbero danneggiare il computer se tali download vengono avviati senza interazione dell'utente e non sono supportati dal controllo Reputazione applicazione SmartScreen**. Gli utenti possono ignorare e continuare a scaricare facendo clic con il pulsante destro del mouse e scegliendo "Mantieni" nell'elemento di download. Gli amministratori dell'organizzazione possono rifiutare esplicitamente questo comportamento configurando i criteri seguenti:
  - 
            [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - Disabilita il download degli avvisi basati sull'estensione del tipo di file per tipi di file specificati nei domini

    Per ulteriori informazioni, vedere [Microsoft Edge Interruzioni dei download di Sicurezza](microsoft-edge-security-downloads-interruptions.md).

- 
            **Supporto per le API di riconoscimento vocale**. A partire Microsoft Edge versione 91, verrà aggiunto il supporto api per i comandi di riconoscimento vocale Google.com e siti simili. Questa funzionalità è limitata a un gruppo di utenti selezionati casualmente che hanno abilitato la sperimentazione. Questi utenti stanno fornendo un feedback al team responsabile della caratteristica.

- 
            **Personalizzare il browser con nuovi colori del tema.** 
           Rendi Microsoft Edge personalizzato con uno dei 14 nuovi colori del tema nella pagina Impostazioni -> Aspetto. È inoltre possibile inoltre installare temi personalizzati dal sito dei componenti aggiuntivi di Microsoft Edge. [Scopri di più](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti sei nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [pagina di Microsoft Edge per le aziende](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti:

- 
            [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Identificazione del traffico di Application Guard
- 
            [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - Porte di rete esplicitamente consentite
- 
            [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - Consenti l'importazione delle impostazioni della pagina di avvio
- 
            [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) : consente agli utenti di risolvere un problema matematico e ottenere la soluzione con una spiegazione dettagliata in Microsoft Edge
- 
            [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - Consenti il contenuto di Microsoft News nella nuova scheda
- 
            [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - Consenti collegamenti rapidi nella nuova scheda

#### <a name="obsoleted-policy"></a>Criteri obsoleti

- 
            [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - Abilita l'autenticazione proattiva
<!-- end major 91 -->

<!-- Archive from 89.0.774.45: March 4 to 90.0.818.66: May 20 ->
<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
