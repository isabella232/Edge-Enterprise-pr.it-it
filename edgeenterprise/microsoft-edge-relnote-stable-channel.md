---
title: Note sulla versione di Microsoft Edge per il canale Stabile
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Stabile
ms.openlocfilehash: 6a4c65d253a88384da7393ab846777093dc86e86
ms.sourcegitcommit: 584a6a9877ae0c3fcb9acc0b8c158e280b0360ff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2021
ms.locfileid: "11912061"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Note sulla versione del canale Stabile Microsoft Edge

Queste note sulla versione offrono informazioni sulle nuove funzionalità e sugli aggiornamenti non di sicurezza inclusi nel canale Stabile Microsoft Edge.

- Tutti gli aggiornamenti della sicurezza sono elencati [qui](microsoft-edge-relnotes-security.md).
- Le note sulla versione del canale Stable di Microsoft Edge archiviate sono disponibili [qui](microsoft-edge-relnote-archive-stable-channel.md).

 Per informazioni sui canali Microsoft Edge, vedere la [Panoramica dei canali Microsoft Edge](microsoft-edge-channels.md).

> [!NOTE]
> Per il canale Stable, gli aggiornamenti verranno implementati gradualmente su uno o più giorni. Per altre informazioni, vedere [Implementazioni progressive degli aggiornamenti di Microsoft Edge](microsoft-edge-update-progressive-rollout.md).
>
> La piattaforma Microsoft Edge Web si evolve costantemente per migliorare l'esperienza utente, la sicurezza e la privacy. Per altre informazioni, vedere [Modifiche in arrivo in Microsoft Edge che influiscono sulla compatibilità dei siti](/microsoft-edge/web-platform/site-impacting-changes).

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

**I file MHTML verranno aperti per impostazione predefinita in modalità Internet Explorer.** A partire da Microsoft Edge versione 92 del canale stabile, i tipi di file MHTML verranno aperti automaticamente in modalità Internet Explorer in Microsoft Edge anziché nell'applicazione Internet Explorer (IE11). Questo si verifica più comunemente durante il tentativo di visualizzare i messaggi di posta elettronica di Outlook in un browser. La modifica avrà effetto solo se Internet Explorer 11 è il gestore predefinito per questo tipo di file. Se si preferisce modificare questa impostazione, è possibile farlo prima di installare l'aggiornamento alla versione 92 del canale stabile usando [questa guida.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)

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

**In linea con il progetto open source Chromium, Microsoft Edge sta aggiornando il modo in cui esegue il rendering delle tabelle nelle pagine Web.** Questa modifica consente di risolvere i problemi noti e avvicina Microsoft Edge al modo in cui dovrebbe essere eseguito il rendering delle tabelle sul Web o in altri browser. Si consiglia di testare i flussi di lavoro importanti nell'ambiente per problemi imprevisti. Una spiegazione completa è disponibile [qui](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit).

### <a name="new-policies"></a>Nuovi criteri

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single Sign-On per i siti aziendali o degli istituti di istruzione con questo profilo abilitato
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configura HTTPS automatico
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Controlla l'uso della modalità headless
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) Specifica se consentire a siti Web non sicuri di effettuare richieste a endpoint di rete più privati
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Consente ai siti elencati di effettuare richieste a endpoint di rete più privati da contesti non sicuri
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specifica il numero dei giorni durante i quali un sito rimane nell'elenco dei siti in modalità IE locale
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Consenti di ricaricare i siti non configurati in modalità Internet Explorer
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifica se è possibile usare elementi SharedArrayBuffer in un contesto non isolato tra origini

### <a name="deprecated-policy"></a>Criteri deprecati

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) Consente test in modalità Internet Explorer

### <a name="obsoleted-policy"></a>Criteri obsoleti

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Consente certificati firmati con SHA-1 quando emessi da trust anchor locali

## <a name="version-91086471-july-19"></a>Versione 91.0.864.71: 19 luglio

> [!Important]
>Questo aggiornamento contiene [CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563) che è stato segnalato dal team di Chromium come un exploit in the wild. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#july-19-2021)

## <a name="version-91086467-july-8"></a>Versione 91.0.864.67: 8 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086464-july-2"></a>Versione 91.0.864.64: 2 luglio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-91086459-june-24"></a>Versione 91.0.864.59: 24 giugno

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-24-2021)

## <a name="version-91086454-june-18"></a>Versione 91.0.864.54: 18 giugno

> [!Important]
> Questo aggiornamento contiene [CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554) che è stato segnalato dal team di Chromium di avere un exploit. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-18-2021)

## <a name="version-91086448-june-11"></a>Versione 91.0.864.48: 11 giugno

> [!Important]
>Questo aggiornamento contiene [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551) che è stato segnalato dal team di Chromium come un exploit. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-11-2021)

## <a name="version-91086441-june-3"></a>Versione 91.0.864.41: 3 giugno

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#june-3-2021)

## <a name="version-91086437-may-27"></a>Versione 91.0.864.37: 27 maggio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#may-27-2021)

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **Identificare il traffico di rete proveniente dai contenitori a livello di proxy di Microsoft Defender Application Guard.** A partire da Microsoft Edge versione 91, è disponibile un supporto incorporato per contrassegnare il traffico di rete proveniente dai contenitori di Application Guard, consentendo alle aziende di identificarli e applicare criteri specifici.

- **Opzione di supporto per consentire la sincronizzazione dei Preferiti dall'host al contenitore Edge Application Guard.** A partire Microsoft Edge versione 91, gli utenti hanno la possibilità di configurare Application Guard per sincronizzare i preferiti dall'host al contenitore. Questo assicura che anche i nuovi Preferiti vengano visualizzati nel contenitore.

- **A partire da Microsoft Edge versione 91, il browser interromperà automaticamente i download di tipi che potrebbero danneggiare il computer se tali download vengono avviati senza interazione dell'utente e non sono supportati dal controllo Reputazione applicazione SmartScreen**. Gli utenti possono ignorare e continuare a scaricare facendo clic con il pulsante destro del mouse e scegliendo "Mantieni" nell'elemento di download. Gli amministratori dell'organizzazione possono rifiutare esplicitamente questo comportamento configurando i criteri seguenti:
  - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - Disabilita il download degli avvisi basati sull'estensione del tipo di file per tipi di file specificati nei domini

    Per ulteriori informazioni, vedere [Microsoft Edge Interruzioni dei download di Sicurezza](microsoft-edge-security-downloads-interruptions.md).

- **Supporto per le API di riconoscimento vocale**. A partire Microsoft Edge versione 91, verrà aggiunto il supporto api per i comandi di riconoscimento vocale Google.com e siti simili. Questa funzionalità è limitata a un gruppo di utenti selezionati casualmente che hanno abilitato la sperimentazione. Questi utenti stanno fornendo un feedback al team responsabile della caratteristica.

- **Personalizzare il browser con nuovi colori del tema.** Rendi Microsoft Edge personalizzato con uno dei 14 nuovi colori del tema nella pagina Impostazioni -> Aspetto. È inoltre possibile inoltre installare temi personalizzati dal sito dei componenti aggiuntivi di Microsoft Edge. [Scopri di più](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

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

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - Abilitare l'autenticazione proattiva
<!-- end major 91 -->

## <a name="version-90081866-may-20"></a>Versione 90.0.818.66: 20 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081862-may-13"></a>Versione 90.0.818.62: 13 maggio

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#may-13-2021)

## <a name="version-90081856-may-6"></a>Versione 90.0.818.56: 6 maggio

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081851-april-29"></a>Versione 90.0.818.51: 29 aprile

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#april-29-2021)

## <a name="version-90081849-april-26"></a>Versione 90.0.818.49: 26 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081846-april-22"></a>Versione 90.0.818.46: 22 aprile ##

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#april-22-2021)

## <a name="version-90081842-april-19"></a>Versione 90.0.818.42: 19 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-90081841-april-16"></a>Versione 90.0.818.41: 16 aprile ##

> [!Important]
>Questo aggiornamento contiene [CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224) che è stato segnalato dal team di Chromium come un exploit. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#april-16-2021)

## <a name="version-90081839-april-15"></a>Versione 90.0.818.39: 15 aprile ##

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#april-15-2021)

## <a name="feature-updates"></a>Aggiornamenti delle funzionalità ##

-    **Single Sign-On (SSO) è ora disponibile per gli account di Azure Active Directory (Azure AD) e l’account Microsoft (MSA) in macOS.** Un utente che ha eseguito l'accesso a Microsoft Edge su macOS verrà automaticamente connesso a siti Web configurati per consentire l'accesso Single #A0 con account Di lavoro e Microsoft (ad esempio, bing.com, office.com, msn.com e outlook.com).

- **Modalità tutto schermo.** A partire Microsoft Edge versione 90, abbiamo bloccato le impostazioni di stampa dell'interfaccia utente per consentire solo le stampanti configurate e le opzioni "Stampa in PDF". Abbiamo anche apportato miglioramenti all'interno della modalità tutto schermo per app con accesso assegnato per limitare l'avvio di altre applicazioni dal browser. Per altre informazioni sulla funzionalità della modalità tutto schermo, vai [qui.](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)

- **Interrupt Downloads** A partire da Microsoft Edge versione 91, il browser interromperà automaticamente i download di tipi di file che potrebbero danneggiare il computer se tali download vengono avviati senza interazione dell'utente e non sono supportati dal controllo Reputazione applicazione SmartScreen. Gli utenti possono ignorare e continuare a scaricare facendo clic con il pulsante destro del mouse e scegliendo "Mantieni" nell'elemento di download.
Gli amministratori aziendali possono rifiutare esplicitamente questo comportamento tramite uno di questi due criteri:
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disabilitare gli avvisi basati sull'estensione del tipo di file di download per tipi di file specificati nei domini Per ulteriori informazioni, vedere [interruzioni dei download di sicurezza di Microsoft Edge](/deployedge/microsoft-edge-security-downloads-interruptions)

- **Stampa**:

    - **Nuova modalità di rasterizzazione di stampa per stampanti non PostScript.** A partire da Microsoft Edge versione 90, gli amministratori possono usare un nuovo criterio per definire la modalità di rasterizzazione della stampa per gli utenti. Questo criterio controlla la stampa di Microsoft Edge su stampanti non PostScript su Windows. A volte i processi di stampa su stampanti non PostScript devono essere rasterizzati per essere stampati correttamente. Le opzioni di stampa sono Completa e Rapida.
    
  - **Altre opzioni di ridimensionamento della pagina per la stampa.** Gli utenti possono ora personalizzare il ridimensionamento durante la stampa di pagine Web e documenti PDF utilizzando opzioni aggiuntive. L'opzione "Adatta alla pagina" garantisce che la pagina Web o il documento si adatti allo spazio disponibile nel "formato carta" selezionato per la stampa. L'opzione "Dimensioni effettive" garantisce che non vengano apportate modifiche alle dimensioni del contenuto stampato indipendentemente dal "Formato carta" selezionato.

-   **Produttività:**

    -   **I suggerimenti per il riempimento automatico vengono estesi per includere il contenuto dei campi indirizzo dagli Appunti.** Il contenuto degli Appunti viene analizzato quando si fa clic su un campo di profilo/indirizzo (ad esempio, telefono, e-mail, CAP, città, stato e così via) da visualizzare come suggerimenti di riempimento automatico.

    -   **Gli utenti possono cercare suggerimenti di riempimento automatico anche se non viene rilevato un modulo o un campo.** Ora, se le informazioni vengono salvate in Microsoft Edge, i suggerimenti per il riempimento automatico vengono visualizzati automaticamente e consentono di risparmiare tempo durante la compilazione dei moduli. Nei casi in cui il riempimento automatico non è presente in un modulo o se si vogliono recuperare dati in moduli che in genere non prevedono il riempimento automatico (come i moduli temporanei), è possibile cercare le informazioni con il riempimento automatico.

-   **Accedere ai download da un riquadro a comparsa nella barra dei menu.** I download verranno visualizzati nell'angolo in alto a destra, con tutti i download attivi in un'unica posizione. Questo menu è facilmente ignorabile, quindi gli utenti possono continuare l'esplorazione senza interruzioni e monitorare l'avanzamento complessivo del download direttamente dalla barra degli strumenti. [Altre informazioni](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).

-   **Miglioramenti al rendering dei tipi di carattere.** A partire da Microsoft Edge versione 90, sono stati apportati miglioramenti al rendering del testo per migliorare la chiarezza e aumentare la nitidezza. Parte dei miglioramenti al rendering dei tipi di carattere sarà disponibile nella versione Beta 90, ma è disabilitata per impostazione predefinita.

- **Modalità Bambini.** Il criterio è stato aggiornato in modo che, quando il criterio è abilitato, disabiliterà la funzionalità Modalità bambini oltre alla sicurezza familiare. Altre informazioni sulla modalità Bambini [qui](https://go.microsoft.com/fwlink/?linkid=2146910)

## <a name="policy-updates"></a>Aggiornamenti dei criteri

## <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti otto nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [pagina di Microsoft Edge per le aziende](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti:
-   [ApplicationGuardFavoritesSyncEnabled](/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled): sincronizzazione dei preferiti di Application Guard abilitata
- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) Identificazione del traffico di Application Guard
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) Porte di rete esplicitamente consentite
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) Consenti importazione delle impostazioni della pagina di avvio
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) Consentire agli utenti di risolvere un problema di matematica e ottenere una soluzione con una spiegazione dettagliata in Microsoft Edge
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) Consenti Microsoft News contenuto nella nuova scheda
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) Consenti collegamenti rapidi nella nuova scheda
-   [FetchKeepaliveDurationSecondsOnShutdown](/DeployEdge/microsoft-edge-policies#fetchkeepalivedurationsecondsonshutdown)- Recupera la durata keepalive all'arresto
-   [ManagedConfigurationPerOrigin](/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin): imposta i valori di configurazione gestita per i siti Web su origini specifiche
-   [PrintRasterizationMode](/DeployEdge/microsoft-edge-policies#printrasterizationmode): modalità rasterizzazione di stampa
-   [QuickViewOfficeFilesEnabled](/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled): gestire la funzionalità QuickView dei file di Office in Microsoft Edge
-   [SSLErrorOverrideAllowedForOrigins](/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins): consente agli utenti di procedere dalla pagina di avviso HTTPS per origini specifiche
-   [WindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#windowocclusionenabled): abilita l’occlusione della finestra
-   [WindowsHelloForHTTPAuthEnabled](/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled): autenticazione di Windows Hello per HTTP abilitata

## <a name="deprecated-policies"></a>Criteri deprecati

- [ProactiveAuthEnabled](/DeployEdge/microsoft-edge-policies#proactiveauthenabled) Abilitare l'autenticazione proattiva
-   [NativeWindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled): abilita occlusione finestra nativa
-   [SSLVersionMin](/DeployEdge/microsoft-edge-policies#sslversionmin): versione TLS minima abilitata

## <a name="version-89077477-april-14"></a>Versione 89.0.774.77: 14 aprile

> [!Important]
>Questo aggiornamento contiene [CVE-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206) e [CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220) che è stato segnalato dal team di Chromium come un exploit.  Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](/deployedge/microsoft-edge-relnotes-security#april-14-2021)

## <a name="version-89077476-april-12"></a>Versione 89.0.774.76: 12 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077475-april-8"></a>Versione 89.0.774.75: 8 aprile

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077468-april-1"></a>Versione 89.0.774.68: 1 aprile

Gli aggiornamenti della sicurezza del canale Stable sono elencati [qui](./microsoft-edge-relnotes-security.md#april-1-2021).

## <a name="version-89077463-march-25"></a>Versione 89.0.774.63: 25 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077457-march-18"></a>Versione 89.0.774.57: 18 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077454-march-13"></a>Versione 89.0.774.54: 13 marzo

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2021-21193](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21193), che è stato segnalato al team di Chromium come un exploit in condizioni normali. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale stabile sono [elencati qui.](./microsoft-edge-relnotes-security.md#march-13-2021)

## <a name="version-89077450-march-10"></a>Versione 89.0.774.50: 10 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

## <a name="version-89077448-march-8"></a>Versione 89.0.774.48: 8 marzo

Sono stati risolti diversi bug e problemi di prestazioni.

<!-- begin major 89 -->
## <a name="version-89077445-march-4"></a>Versione 89.0.774.45: 4 marzo

> [!IMPORTANT]
> Questo aggiornamento contiene [CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166) che è stato segnalato dal team di Chromium come un exploit in natura. Per altre informazioni, vedere la [Guida all'aggiornamento della sicurezza](https://msrc.microsoft.com/update-guide).

Gli aggiornamenti della sicurezza del canale Stable sono [elencati qui.](./microsoft-edge-relnotes-security.md#march-4-2021)

### <a name="resolved-issues"></a>Problemi risolti

- **Aggiornamenti e correzioni delle scelte rapide da tastiera del menu Start e della barra delle applicazioni:**
  - Quando fai clic sul collegamento di Microsoft Edge nel menu Start, ora viene mostrata correttamente l'opzione per rimuovere Microsoft Edge dalla barra quando è bloccato in alto.
  - I layout di avvio che includono una [configurazione della barra delle applicazioni](/windows/configuration/configure-windows-10-taskbar) per aggiungere Microsoft Edge alla barra delle applicazioni non causano più l'aggiunta di un secondo collegamento a Microsoft Edge alla barra delle applicazioni.
  - Le organizzazioni che usano i profili di roaming di Windows non vedranno più un'icona bianca vuota al posto dell'icona di Microsoft Edge sulla barra delle applicazioni quando gli utenti accedono a Windows.

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

- **La modalità tutto schermo offre altre funzionalità di blocco.** A partire da Microsoft Edge versione 89, abbiamo aggiunto altre funzionalità di blocco all'interno della modalità tutto schermo per consentire ai clienti di lavorare in modo produttivo e sicuro. [Altre informazioni](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features).

- **Lo strumento Enterprise Mode Site List Manager sarà disponibile nel browser tramite la pagina *edge://compat***. È possibile usare questo strumento per creare, modificare ed esportare il file XML con l’elenco dei siti per la modalità Internet Explorer di Microsoft Edge. Se necessario, è possibile abilitare l'accesso a questo strumento tramite Criteri di gruppo. [Altre informazioni](./edge-ie-mode-site-list-manager.md).

- **Miglioramento delle prestazioni del browser con le schede di sospensione**. Le schede di sospensione migliorano le prestazioni del browser mettendo in sospensione le schede inattive per liberare risorse di sistema come la memoria e la CPU, che potranno essere utilizzate dalle schede attive o da altre applicazioni. Gli utenti possono impedire che i siti attivino la modalità sospensione e configurare l’intervallo di tempo prima che una scheda inattiva entri in sospensione. Per mantenere gli utenti nel flusso di lavoro, sono anche disponibili sistemi [euristici](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434) che evitano che determinati siti entrino in modalità sospensione, ad esempio i siti Intranet. Questa funzionalità può essere gestita tramite i criteri di gruppo.

- **Reimpostare manualmente i dati di sincronizzazione di Microsoft Edge nel cloud**. Introduzione alla modalità di reimpostazione dei dati di sincronizzazione di Microsoft Edge dall'interno del prodotto. In questo modo i dati degli utenti vengono cancellati dai servizi Microsoft, inoltre vengono risolti alcuni problemi del prodotto che in precedenza richiedevano un ticket di supporto.

- **Abilitazione intelligente di Single Sign-On (SSO) per tutti gli account di Windows Azure Active Directory (Azure AD) per gli utenti con un singolo profilo Microsoft Edge non Azure AD**.  Attivare automaticamente questa impostazione per gli utenti che potrebbero trarre il massimo vantaggio da questa funzionalità. Se un utente ha un solo profilo Microsoft Edge (non Azure AD o Modalità Bambini), l'impostazione verrà automaticamente attivata all'avvio di Microsoft Edge. Questo interruttore automatico verrà disattivato automaticamente se un utente sceglie in un secondo momento di accedere a un altro profilo Microsoft Edge con un account Azure AD. Gli utenti possono aggiornare manualmente le proprie preferenze per questa funzionalità in **Impostazioni > Profili > Preferenze profilo > Consenti Single Sign-On per i siti aziendali o dell'istituto di istruzione che usano questo profilo**.

- **Miglioramenti all'esperienza di selezione del testo nei documenti PDF**. Gli utenti inizieranno a ricevere un'esperienza più fluida e coerente di selezione del testo nei documenti PDF aperti in Microsoft Edge, a partire dalla versione 89.

- **Il campo Data di nascita ora è supportato nel riempimento automatico.** Oggi Microsoft Edge permette di risparmiare tempo e fatica nella compilazione di moduli e nella creazione di account online compilando automaticamente i dati, come indirizzi, nomi, numeri di telefono e così via. A partire da Microsoft Edge versione 89, viene aggiunto il supporto per un altro campo che può essere salvato e compilato automaticamente: la data di nascita. Un utente può visualizzare, modificare ed eliminare queste informazioni in qualsiasi momento dalle impostazioni del profilo.

### <a name="policy-updates"></a>Aggiornamenti dei criteri

#### <a name="new-policies"></a>Nuovi criteri

Sono stati aggiunti 7 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoft.com/edge/business/download). Sono stati aggiunti i nuovi criteri seguenti.

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime): impostazioni vita utile dati di esplorazione
- [maMEnabled](./microsoft-edge-policies.md#mamenabled): gestione delle app per dispositivi mobili abilitata
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages): definisce un elenco ordinato di lingue preferite in cui i siti internet dovrebbero essere visualizzati, se sono supportate
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - Consenti consigli e notifiche promozionali da Edge
- [StampaAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - Limita la modalità di stampa grafica in background
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault) - Modalità di stampa grafica di sfondo predefinita
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist) - Blocca le azioni intelligenti per un elenco di servizi

#### <a name="obsoleted-policies"></a>Criteri obsoleti

I criteri seguenti sono obsoleti.

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - Usa un criterio di referrer predefinito di no-referrer-when-downgrade
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Invia informazioni sul sito per migliorare i servizi Microsoft
<!-- end major 89 -->

<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
