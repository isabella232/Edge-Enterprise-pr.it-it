---
title: Note sulla versione di Microsoft Edge per il canale Beta
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/25/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Beta
ms.openlocfilehash: d6912d275ca74bdd46b4d5997e34d62502562986
ms.sourcegitcommit: 43e123dcb1a871e3fb9e0fdab096b8ea3d372bc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2021
ms.locfileid: "11925323"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Note sulla versione per il canale Microsoft Edge Beta

Queste note sulla versione contengono informazioni sulle nuove funzionalità e gli aggiornamenti non relativi alla sicurezza inclusi nel canale Microsoft Edge Beta. Le versioni precedenti di queste note sulla versione sono disponibili [qui](microsoft-edge-relnote-archive-beta-channel.md).

> [!NOTE]
> La piattaforma Web Microsoft Edge si evolve costantemente per migliorare l'esperienza utente, la sicurezza e la privacy. Per altre informazioni, vedere [Modifiche in arrivo in Microsoft Edge che influiscono sulla compatibilità dei siti](/microsoft-edge/web-platform/site-impacting-changes).

## <a name="version-93096127-august-20"></a>Versione 93.0.961.27: 20 agosto

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-93096124-august-18"></a>Versione 93.0.961.24: 18 agosto

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-93096111-august-3"></a>Versione 93.0.961.11: 3 agosto

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Preferenze iniziali in Microsoft Edge.**  A partire Microsoft Edge versione 93, la distribuzione di Microsoft Edge nell'organizzazione sarà più semplice con l'aggiunta di Preferenze iniziali.

- **La modalità IE Microsoft Edge supporterà il comportamento "nomerge".**  A partire Microsoft Edge versione 93, la modalità IE Microsoft Edge supporterà _nomerge_. Per un utente finale, quando una nuova finestra del browser viene avviata da un'applicazione in modalità IE, si trova in una sessione separata, in modo analogo al comportamento in Internet Directory Online. Sarà necessario modificare l'elenco dei siti per configurare i siti che devono impedire la condivisione delle sessioni. Dietro le quinte, per ogni finestra di Microsoft Edge, la prima volta che viene visitata una scheda della modalità IE all'interno di tale finestra, se si tratta di uno dei siti designati "nomerge", tale finestra viene bloccata in una sessione "nomerge" diversa da tutte le altre finestre di Microsoft Edge almeno fino alla chiusura dell'ultima scheda della modalità IE in tale finestra. Altre informazioni sono disponibili [qui](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--nomerge--option-that-was-supported-in-internet-explorer-11-).

- **Gruppi di schede.**  La possibilità di categorizzare le schede in gruppi definiti dall'utente consente di trovare, cambiare e gestire le schede in modo più efficace in più workstream. A tale scopo, viene attivato il raggruppamento delle schede a partire Microsoft Edge versione 93.

- **Nascondere la barra del titolo quando si utilizzano le schede verticali.**  Recuperare i pochi pixel in più nascondendo la barra del titolo del browser, mentre è in Schede verticali. A partire Microsoft Edge versione 93, è possibile passare a edge://settings/appearance e nella sezione Personalizza barra degli strumenti selezionare l'opzione per nascondere la barra del titolo in modalità Tabulazione verticale.

- **Immagine video in immagine (PiP) dalla barra degli strumenti al passaggio del mouse.**  A partire Microsoft Edge versione 93, sarà ancora più facile accedere a Immagine in modalità Immagine (PiP). Quando si passa il mouse su un video supportato, viene visualizzata una barra degli strumenti che consente di visualizzare il video in una finestra di PiP.  Nota: questa opzione è attualmente disponibile per Microsoft Edge utenti in macOS.  Controllare di nuovo a breve mentre continuiamo l'implementazione per Windows utenti.

- **Rimozione di 3DES in TLS.**  A partire Microsoft Edge versione 93, il supporto per la famiglia TLS_RSA_WITH_3DES_EDE_CBC_SHA di crittografia verrà rimosso. Questa modifica si verifica nel progetto Chromium, su cui Microsoft Edge è basato. Per ulteriori informazioni, passare alla voce [Stato piattaforma Chrome.](https://chromestatus.com/feature/6678134168485888) Inoltre, nella Microsoft Edge 93, il criterio [TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) sarà disponibile per supportare gli scenari che devono mantenere la compatibilità con i server obsoleti. Questo criterio di compatibilità diventerà obsoleto e smetterà di funzionare Microsoft Edge versione 95. Assicurarsi di aggiornare i server interessati prima di allora.

- **Criteri per ignorare i ClickOnce e DirectInvoke.**  I criteri sono stati aggiornati per abilitare il bypass dei prompt di ClickOnce e dell'app di DirectInvoke per i tipi di file specificati, dai domini specificati. A tale scopo, è necessario:

  - Abilitare [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled) o [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled)
  - Abilitare [il criterio AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) e impostare l'elenco di tipi di file specifici per cui ClickOnce e DirectInvoke devono essere disabilitati
  - Abilitare il [criterio AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) e impostare l'elenco di domini specifici per i ClickOnce e DirectInvoke per

  Nota: AutoOpenAllowedForURLs è un criterio di supporto per AutoOpenFileTypes. Se AutoOpenAllowedForURLs non è impostato e AutoOpenFileTypes è impostato, i tipi di file elencati verranno aperti automaticamente da tutti gli URL.

### <a name="new-policies"></a>Nuovi criteri

- [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) Consentire la riproduzione automatica di elementi multimediali in siti specifici
- [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) CeCPQ2 post-quantum key-agreement abilitato per TLS
- [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer) Configurare la funzionalità Visualizza in Esplora file per SharePoint pagine in Microsoft Edge
- [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) Controllare l'utilizzo di JavaScript JIT
- [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled) Consenti alle notifiche di impostare Microsoft Edge lettore PDF predefinito
- [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) Configurare la possibilità per gli utenti di ignorare i flag di funzionalità
- [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) Abilitare l'accesso implicito
- [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) Configurare l'elenco Enterprise siti cloud in modalità avanzata
- [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) Configurare la frequenza di aggiornamento dell'elenco siti Enterprise modalità utente
- [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) Consenti a JavaScript di usare JIT in questi siti
- [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) Impedire a JavaScript di usare JIT in questi siti
- [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled) Abilitare Windows ricerca nei dati di esplorazione Microsoft Edge locale
- [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled) Usa sempre Microsoft AutoUpdate come programma di aggiornamento per Microsoft Edge
- [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) Consentire l'accesso Single #A0 per i siti Microsoft che usano questo profilo
- [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced) Autenticazione OneAuth Flow applicata per l'accesso
- [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) Consentire agli utenti di ottenere un suggerimento per password complessa ogni volta che creano un account online
- [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) Configura un'impostazione che richiede agli utenti di immettere la password del dispositivo durante l'uso del riempimento automatico della password
- [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) Imposta il layout per la stampa
- [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) Consenti debug remoto
- [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) Impostare l'intervallo di tempo per il riavvio
- [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) Abilitare l'assistenza di viaggio
- [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) Abilitare le suite di crittografia 3DES in TLS

#### <a name="deprecated-policy"></a>Criteri deprecati

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) Abilita l'impostazione predefinita del comportamento dei cookie SameSite legacy

#### <a name="obsoleted-policy"></a>Criteri obsoleti

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) Configurare la nuova Microsoft Edge pagina nuova scheda

#### <a name="additional-change"></a>Modifica aggiuntiva

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) Aggiungere il supporto della piattaforma Mac

## <a name="version-93096118-august-10"></a>Versione 93.0.961.18: 10 agosto

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090262-july-29"></a>Versione 92.0.902.62: 29 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090255-july-21"></a>Versione 92.0.902.55: 21 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090245-july-12"></a>Versione 92.0.902.45: 12 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090240-july-6"></a>Versione 92.0.902.40: 6 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-92090222-june-21"></a>Versione 92.0.902.22: 21 giugno

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Ricerca in linguaggio naturale della cronologia del browser sulla barra degli indirizzi.** Trovare l'articolo/sito Web che si sta cercando è ora più semplice grazie alla ricerca in linguaggio naturale direttamente dalla barra degli indirizzi. È possibile trovare i risultati della ricerca in base al contenuto/descrizione/intervallo della pagina (ad esempio "ricetta torta della settimana scorsa") oltre a titoli/corrispondenze di parole chiave URL.
Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non è disponibile, controllare di nuovo a breve mentre l'implementazione prosegue.

- **Gli utenti possono passare facilmente alla modalità Internet Explorer in Microsoft Edge**. A partire da Microsoft Edge versione 92, gli utenti possono ricaricare un sito in modalità Internet Explorer in Microsoft Edge anziché basarsi sull'applicazione Internet Explorer 11autonoma in attesa della configurazione di un sito nell'elenco dei siti in modalità Enterprise. Agli utenti verrà richiesto di aggiungere il sito all'elenco dei siti locali in modo che il rendering della stessa pagina in Microsoft Edge venga eseguito automaticamente in Internet Explorer per i 30 giorni successivi. È possibile usare il criterio *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* per configurare questa esperienza e consentire l'accesso ai punti di ingresso in modalità Internet Explorer, nonché la possibilità di aggiungere siti all'elenco di siti locale. È possibile usare il criterio *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* per modificare il numero di giorni di conservazione dei siti nell'elenco dei siti locali.
Si noti che è necessario KB5003698 o versione successiva per Windows 10 versione 1909 oppure KB5003690 o versione successiva per Windows 10 versione 2004, Windows 10 versione 20H2 o Windows 10 versione 21H1 per l'esperienza end-to-end.

- **I file MHTML verranno aperti per impostazione predefinita in modalità Internet Explorer.** A partire da Microsoft Edge versione 92 del canale stabile, i tipi di file MHTML verranno aperti automaticamente in modalità Internet Explorer in Microsoft Edge anziché nell'applicazione Internet Explorer (IE11). Questo si verifica più comunemente durante il tentativo di visualizzare i messaggi di posta elettronica di Outlook in un browser. La modifica avrà effetto solo se Internet Explorer 11 è il gestore predefinito per questo tipo di file. Se si preferisce modificare questa impostazione, è possibile farlo prima di installare l'aggiornamento alla versione 92 del canale stabile usando [questa guida.](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)

- **Gli strumenti di pagamento sono ora sincronizzati tra i dispositivi**. A partire da Microsoft Edge versione 92, è possibile sincronizzare le informazioni di pagamento tra i dispositivi connessi.
Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non viene visualizzata, controllare di nuovo a breve mentre si prosegue con l'implementazione.

- **L'avviso "Disabilitare le estensioni per la modalità sviluppatore" può essere ignorato definitivamente**. A partire da Microsoft Edge versione 92, è possibile disattivare l'avviso "Disabilitare le estensioni per la modalità sviluppatore" facendo clic sull'opzione "Non visualizzare più questo messaggio".
Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non viene visualizzata, controllare di nuovo a breve mentre si prosegue con l'implementazione.

- **Gestione delle estensioni direttamente dalla barra degli strumenti**. Il nuovo menu delle estensioni sulla barra degli strumenti consente di nascondere/aggiungere facilmente le estensioni. I collegamenti rapidi per gestire le estensioni e trovarne di nuove semplificano la ricerca di nuove estensioni e la gestione di quelle esistenti.
Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non viene visualizzata, controllare di nuovo a breve mentre si prosegue con l'implementazione.

- **HTTPS automatico**. Gli utenti avranno la possibilità di aggiornare la navigazione da HTTP a HTTPS nei domini che probabilmente supporteranno questo protocollo più sicuro. Questo supporto può essere configurato anche per tentare il recapito tramite HTTPS per tutti i domini.
Nota: la funzionalità è sperimentale e questo comportamento non verrà mostrato se hai rifiutato esplicitamente gli esperimenti.

- **Miglioramenti al rendering dei tipi di carattere**. Sono stati apportati miglioramenti al rendering del testo per migliorare la chiarezza e aumentare la nitidezza.
Nota: questa è un'implementazione controllata delle funzionalità. Se questa funzionalità non viene visualizzata, controllare di nuovo a breve mentre si prosegue con l'implementazione.

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti otto nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [pagina di Microsoft Edge per le aziende](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti:

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single Sign-On per i siti aziendali o degli istituti di istruzione tramite questo profilo abilitato.
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configura HTTPS automatico
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Controlla l'uso della modalità headless
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) Specifica se consentire a siti Web non sicuri di effettuare richieste a endpoint di rete più privati
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Consenti ai siti elencati di effettuare richieste a endpoint di rete più privati da contesti non sicuri
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specifica il numero dei giorni durante i quali un sito rimane nell'elenco dei siti in modalità IE locale
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Consenti di ricaricare i siti non configurati in modalità Internet Explorer
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifica se è possibile usare elementi SharedArrayBuffer in un contesto non isolato tra origini

#### <a name="obsoleted-policy"></a>Criteri obsoleti

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Consenti certificati firmati con SHA-1 quando vengono emessi da Trust Anchor locali.

## <a name="version-9209029-june-8"></a>Versione 92.0.902.9: 8 giugno

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086441-june-3"></a>Versione 91.0.864.41: 3 giugno

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086437-may-27"></a>Versione 91.0.864.37: 27 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086436-may-26"></a>Versione 91.0.864.36: 26 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086433-may-21"></a>Versione 91.0.864.33: 21 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086427-may-14"></a>Versione 91.0.864.27: 14 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086419-may-7"></a>Versione 91.0.864.19: 7 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086415-may-3"></a>Versione 91.0.864.15: 3 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086411-april-30"></a>Versione 91.0.864.11: 30 aprile

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Identificare il traffico di rete proveniente dai contenitori a livello di proxy di Microsoft Defender Application Guard.** A partire da Microsoft Edge versione 91, è disponibile un supporto incorporato per contrassegnare il traffico di rete proveniente dai contenitori di Application Guard, consentendo alle aziende di identificarli e applicare criteri specifici.

- **Opzione di supporto per consentire la sincronizzazione dei Preferiti dall'host al contenitore Edge Application Guard.** A partire Microsoft Edge versione 91, gli utenti hanno la possibilità di configurare Application Guard per sincronizzare i preferiti dall'host al contenitore. Questo assicura che anche i nuovi Preferiti vengano visualizzati nel contenitore.

- **Supporto per le API di riconoscimento vocale**. A partire Microsoft Edge versione 91, verrà aggiunto il supporto api per i comandi di riconoscimento vocale Google.com e siti simili. Questa funzionalità è limitata a un gruppo di utenti selezionati casualmente che hanno abilitato la sperimentazione. Questi utenti stanno fornendo un feedback al team responsabile della caratteristica.

- **Personalizzare il browser con nuovi colori del tema.** Rendi Microsoft Edge personalizzato con uno dei 14 nuovi colori del tema nella pagina Impostazioni -> Aspetto. È inoltre possibile inoltre installare temi personalizzati dal sito dei componenti aggiuntivi di Microsoft Edge. [Altre informazioni](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- **Interruzione dei download** A partire da Microsoft Edge versione 91, il browser interromperà automaticamente il download dei tipi che potrebbero danneggiare il computer se vengono avviati senza interazione dell'utente e non sono supportati dal controllo di Reputazione applicazione SmartScreen. Gli utenti possono ignorare e continuare a scaricare facendo clic con il pulsante destro del mouse e scegliendo "Mantieni" nell'elemento di download.
Gli amministratori aziendali possono rifiutare esplicitamente questo comportamento tramite uno di questi due criteri:
    - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disabilita il download degli avvisi basati sull'estensione del tipo di file per i tipi di file specificati nei domini. Per altre informazioni, vedere [Interruzioni dei download potenzialmente pericolosi](/deployedge/microsoft-edge-security-downloads-interruptions) nella sezione Sicurezza di Microsoft Edge

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti sei nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [pagina di Microsoft Edge per le aziende](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti:

- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Identificazione del traffico di Application Guard
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - Porte di rete esplicitamente consentite
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - Consenti l'importazione delle impostazioni della pagina di avvio
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) : consente agli utenti di risolvere un problema matematico e ottenere la soluzione con una spiegazione dettagliata in Microsoft Edge
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - Consenti il contenuto di Microsoft News nella nuova scheda
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - Consenti collegamenti rapidi nella nuova scheda

#### <a name="obsoleted-policy"></a>Criteri obsoleti

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - Abilita l'autenticazione proattiva
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a>Versione 90.0.818.46: 22 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081842-april-20"></a>Versione 90.0.818.42: 20 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081841-april-16"></a>Versione 90.0.818.41: 16 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081838-april-14"></a>Versione 90.0.818.38: 14 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081836-april-12"></a>Versione 90.0.818.36: 12 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081827-april-2"></a>Versione 90.0.818.27: 2 aprile

Sono stati risolti diversi bug e problemi di prestazione.

## <a name="version-90081822-march-29"></a>Versione 90.0.818.22: 29 marzo

Sono stati risolti diversi bug e problemi di prestazione.

## <a name="version-90081814-march-22"></a>Versione 90.0.818.14: 22 marzo

Sono stati risolti diversi bug e problemi di prestazioni.
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a>Versione 90.0.818.8: 16 marzo

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Single Sign-On (SSO) è ora disponibile per gli account di Azure Active Directory (Azure AD) e l’account Microsoft (MSA) in macOS**. Un utente che ha eseguito l'accesso a Microsoft Edge su macOS verrà automaticamente connesso a siti Web configurati per consentire l'accesso Single #A0 con account Di lavoro e Microsoft (ad esempio, bing.com, office.com, msn.com e outlook.com).

- **Modalità tutto schermo.** A partire Microsoft Edge versione 90, abbiamo bloccato le impostazioni di stampa dell'interfaccia utente per consentire solo le stampanti configurate e le opzioni "Stampa in PDF". Abbiamo anche apportato miglioramenti all'interno della modalità tutto schermo per app con accesso assegnato per limitare l'avvio di altre applicazioni dal browser. Altre informazioni sulle funzionalità della modalità tutto schermo sono disponibili [qui.](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)

- **Stampa:**

  - **Nuova modalità di rasterizzazione di stampa per stampanti non PostScript**. A partire da Microsoft Edge versione 90, gli amministratori possono usare un nuovo criterio per definire la modalità di rasterizzazione della stampa per gli utenti. Questo criterio controlla la modalità di stampa di Microsoft Edge su stampanti non PostScript in Windows.  A volte i processi di stampa su stampanti non PostScript devono essere rasterizzati per essere stampati correttamente. Le opzioni di stampa sono Full e Fast.

  - **Altre opzioni di ridimensionamento della pagina per la stampa**. Gli utenti possono ora personalizzare il ridimensionamento durante la stampa di pagine Web e documenti PDF utilizzando opzioni aggiuntive. L'opzione "Adatta alla pagina" garantisce che la pagina Web o il documento si adatti allo spazio disponibile nel "formato carta" selezionato per la stampa. L'opzione "Dimensioni effettive" garantisce che non vengano apportate modifiche alle dimensioni del contenuto stampato indipendentemente dal "Formato carta" selezionato.

- **Produttività:**

  - **I suggerimenti per il riempimento automatico vengono estesi per includere il contenuto dei campi indirizzo dagli Appunti.** Il contenuto degli Appunti viene analizzato quando si fa clic su un campo di profilo/indirizzo (ad esempio, telefono, e-mail, CAP, città, stato e così via) da visualizzare come suggerimenti di riempimento automatico.

  - **Gli utenti possono cercare suggerimenti di riempimento automatico anche se non viene rilevato un modulo o un campo**. Ora, se le informazioni vengono salvate in Microsoft Edge, i suggerimenti per il riempimento automatico vengono visualizzati automaticamente e consentono di risparmiare tempo durante la compilazione dei moduli. Nei casi in cui il riempimento automatico non è presente in un modulo o se si desidera recuperare dati in moduli che in genere non dispongono di riempimento automatico (come i moduli temporanei), è possibile cercare le informazioni utilizzando il riempimento automatico.

- **Accedere ai download da un riquadro a comparsa nella barra dei menu.** I download verranno visualizzati nell'angolo in alto a destra, con tutti i download attivi in un'unica posizione. Questo menu è facilmente ignorabile, quindi gli utenti possono continuare l'esplorazione senza interruzioni e monitorare l'avanzamento complessivo del download direttamente dalla barra degli strumenti. [Altre informazioni](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).


### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti 7 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti:

- [ApplicationGuardFavoritesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled): sincronizzazione dei preferiti di Application Guard abilitata
- [ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin): imposta i valori di configurazione gestita per i siti Web su origini specifiche
- [PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode): modalità rasterizzazione di stampa
- [QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled): gestire la funzionalità QuickView dei file di Office in Microsoft Edge
- [SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins): consente agli utenti di procedere dalla pagina di avviso HTTPS per origini specifiche
- [WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled): abilita l’occlusione della finestra
- [WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled): autenticazione di Windows Hello per HTTP abilitata

#### <a name="deprecated-policies"></a>Criteri deprecati

- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled): abilita occlusione finestra nativa
- [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin): versione TLS minima abilitata
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

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
