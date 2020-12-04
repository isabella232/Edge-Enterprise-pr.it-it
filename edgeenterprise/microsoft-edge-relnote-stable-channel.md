---
title: Note sulla versione di Microsoft Edge per il canale Stabile
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Stabile
ms.openlocfilehash: 7975cf408a2b9d1c759ebf31e115b830649f1ee4
ms.sourcegitcommit: 2a53bdd2510770c0b7580f912864337c6ef617fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "11192527"
---
# Note sulla versione del canale Stabile Microsoft Edge

Queste note sulla versione offrono informazioni sulle nuove funzionalità e sugli aggiornamenti non di sicurezza inclusi nel canale Stabile Microsoft Edge. Per informazioni sui canali Microsoft Edge, vedere la [Panoramica dei canali Microsoft Edge](microsoft-edge-channels.md). Tutti gli aggiornamenti della sicurezza sono elencati [qui](microsoft-edge-relnotes-security.md).

> [!NOTE]
> Per il canale Stable, gli aggiornamenti verranno implementati gradualmente su uno o più giorni. Per altre informazioni, vedere [Implementazioni progressive degli aggiornamenti di Microsoft Edge](microsoft-edge-update-progressive-rollout.md).

## Versione 87.0.664.52:30 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 87.0.664.47: 23 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin major 87 --->
## Versione 87.0.664.41: 19 novembre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-19-2020).

### Aggiornamenti delle funzionalità

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

### Aggiornamenti dei criteri

#### Nuovi criteri

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

#### Criteri deprecati

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - Configura l’esperienza della pagina Nuova scheda di Microsoft Edge.

#### Criteri obsoleti

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - Riabilita le funzionalità deprecate della piattaforma Web per un periodo di tempo limitato.

<!-- end major 87 -->

## Versione 86.0.622.69: 13 novembre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-13-2020). Questo aggiornamento contiene [CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) e [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017), che sono stati segnalati al team di Chromium come un exploit in condizioni normali.

## Versione 86.0.622.68: 11 novembre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-11-2020).

## Versione 86.0.622.63: 4 novembre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-4-2020). Questo aggiornamento contiene [CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009), che è stato segnalato al team di Chromium come un exploit in condizioni normali.

## Versione 86.0.622.61: 2 novembre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 86.0.622.58: 29 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 86.0.622.56: 27 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 86.0.622.51: 22 ottobre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-22-2020).

## Versione 86.0.622.48: 20 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 86.0.622.43: 15 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin major 86 -->
## Versione 86.0.622.38 : 9 ottobre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-9-2020).

### Aggiornamenti delle funzionalità

* **Eseguire il rollback a una versione precedente di Microsoft Edge.** La funzionalità di rollback consente agli amministratori di ripristinare una nota versione valida di Microsoft Edge, in caso di un problema con la versione più recente di Microsoft Edge. **Nota:** La versione Stabile 86.0.622.38 è la prima versione in cui è possibile eseguire il rollback, il che significa che la versione Stabile 87 è la prima versione dalla quale eseguire il rollback. [Ulteriori informazioni](edge-learnmore-rollback.md).

* **Applicare l'abilitazione della sincronizzazione per impostazione predefinita in tutta l’azienda.**  Per impostazione predefinita, gli amministratori possono abilitare la sincronizzazione per gli account di Azure Active Directory (Azure AD) tramite il criterio [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync).

* **Cambio automatico del profilo in Windows 7 e 8.1.** Il cambio automatico del profilo attualmente disponibile in Microsoft Edge su Windows 10 è stato esteso alle versioni di Windows di livello inferiore (Windows 7 e 8.1). Per altre informazioni, vedere il post sul blog [cambio automatico del profilo](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/).

* **SameSite=Lax Cookies per impostazione predefinita**. Per migliorare la sicurezza web e la privacy, i cookie ora verranno sempre impostati su [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) handling per impostazione predefinita. Ciò significa che i cookie verranno inviati solo in un contesto di prime parti e verranno omessi per le richieste inviate a terze parti. Questa modifica può causare un impatto sulla compatibilità dei siti Web che richiedono cookie per il corretto funzionamento delle risorse di terze parti. Per consentire tali cookie, gli sviluppatori Web possono contrassegnare i cookie che devono essere impostati e inviati a contesti di terze parti aggiungendo espliciti `SameSite=none` e `Secure` attributi quando il cookie è impostato. Le aziende che desiderano esentare determinati siti da questa modifica possono farlo utilizzando il criterio [ LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) oppure possono disattivare la modifica su tutti i siti utilizzando il criterio [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled).

* **Rimuovere l'API della cache delle applicazioni HTML5.**  A partire da Microsoft Edge versione 86, l'API della cache delle applicazioni legacy che abilita l'uso offline delle pagine web verrà rimossa da Microsoft Edge. Per informazioni su come sostituire l'API della cache delle applicazioni attraverso i processi di lavoro dei servizi, gli sviluppatori Web devono consultare la [Documentazione WebDev](https://web.dev/appcache-removal/).  Importante: è possibile richiedere un [Token AppCache OriginTrial](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673) che consente ai siti di continuare a usare l'API della cache delle applicazioni deprecata fino alla versione 90 di Microsoft Edge.

* **Privacy e sicurezza:**

  * **Sostituire i criteri [MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) e [SendSiteInformationToImproveServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) per le versione di livello inferiore di Windows e macOS.** Questi criteri sono deprecati nella versione 86 di Microsoft Edge e diventeranno obsoleti nella versione 89 di Microsoft Edge.<br>
Tali criteri sono sostituiti da [Consenti telemetria](https://go.microsoft.com/fwlink/?linkid=2099569) su Windows 10, e dal nuovo criterio [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) per tutte le altre piattaforme. Questo consente agli utenti di gestire i dati di diagnostica che vengono inviati a Microsoft per Windows 7, 8, 8.1 e macOS.
  * Supporto DNS sicuri (DNS-over-HTTPS).  A partire dalla versione 86 di Microsoft Edge, sono disponibili impostazioni per controllare i DNS sicuri nei dispositivi non gestiti. Queste impostazioni non sono accessibili agli utenti nei dispositivi gestiti, ma gli amministratori IT possono abilitare o disabilitare il DNS sicuro con i criteri di gruppo [dnsoverhttpsmode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#dnsoverhttpsmode).

* **Modalità Internet Explorer :** Consentire agli utenti di usare l'interfaccia utente Microsoft Edge per testare i siti in modalità Internet Explorer. A partire dalla versione 86 di Microsoft Edge, gli amministratori possono abilitare un'opzione per l'interfaccia utente in modo che gli utenti possano caricare una scheda in modalità Internet Explorer a scopo di test o come soluzione provvisoria, fin quando i siti non vengono aggiunti al file XML dell'elenco dei siti.

* **Aggiornamenti PDF:**

  * Sommario dei documenti PDF. A partire dalla versione 86, in Microsoft Edge è stato aggiunto il supporto per il sommario in modo da consentire agli utenti di spostarsi facilmente tra i documenti PDF.
  * Accedere a tutte le funzionalità PDF nelle schermate con fattore di forma piccolo. Accedere a tutte le funzionalità del lettore PDF di Microsoft Edge su dispositivi con schermi di piccole dimensioni.
  * Supporto penna per evidenziatore nei file PDF. Con questo aggiornamento gli utenti possono utilizzare la penna digitale per evidenziare direttamente il testo nei file PDF, proprio come se avessero un evidenziatore reale e un foglio di carta.
  * Scorrimento PDF migliorato. Ora sarà possibile sperimentare uno scorrimento senza interruzioni durante la navigazione in documenti PDF lunghi.

* **Gli utenti vedranno suggerimenti di completamento automatico quando iniziano a digitare una query di ricerca nel sito componenti aggiuntivi di Microsoft Edge.** Il completamento automatico consente agli utenti di completare rapidamente la query di ricerca senza dover digitare l'intera stringa. Questo può essere utile dato che gli utenti non dovranno ricordare l’ortografia corretta e potranno scegliere tra le opzioni disponibili visualizzate.

* **Aggiungere un'immagine personalizzata nella pagina nuova scheda (NTP) usando criteri di gruppo.** A partire dalla versione 86 di Microsoft Edge, NTP offre un'opzione che consente di sostituire l'immagine predefinita con un'immagine fornita dall'utente. La possibilità di gestire le proprietà di quest'immagine è supportata anche dai criteri di gruppo.

* **Abbinare i tasti di scelta rapida personalizzati al VS Code.** Microsoft Edge DevTools ora supporta la personalizzazione dei tasti di scelta rapida in DevTools da abbinare con l'editor/IDE. (Microsoft Edge 84 ha introdotto la possibilità di abbinare i tasti di scelta rapida di DevTools con VS Code).

* **Eliminare i download dal disco tramite Download Manager.** Gli utenti ora potranno eliminare i file scaricati dal disco senza uscire dal browser. La nuova funzionalità Elimina download è disponibile nel menu di scelta rapida della barra dei download o nella pagina dei download.

### Aggiornamenti dei criteri

#### Nuovi criteri

Sono stati aggiunti 23 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise). Sono stati aggiunti i nuovi criteri seguenti.

- [CollectionsServicesAndExportsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#collectionsservicesandexportsblocklist): blocca l'accesso a un elenco specificato di servizi e destinazioni di esportazione in Raccolte.
- [DefaultFileSystemReadGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultfilesystemreadguardsetting): controlla l'uso dell'API file system per la lettura.
- [DefaultFileSystemWriteGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultfilesystemwriteguardsetting): controlla l'uso dell'API file system per la scrittura.
- [DefaultSensorsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsensorssetting): impostazione predefinita per i sensori.
- [DefaultSerialGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultserialguardsetting): controlla l'uso di Serial API.
- [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata): invia dati di diagnostica necessari e facoltativi sull'uso del browser.
- [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed): consente l’accesso allo strumento Enterprise Mode Site List Manager.
- [FileSystemReadAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemreadaskforurls): consente l'accesso in lettura con l'API file system in questi siti.
- [FileSystemReadBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemreadblockedforurls): blocca l'accesso in lettura con l'API file system in questi siti.
- [FileSystemWriteAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemwriteaskforurls): consente l'accesso in scrittura ai file e alle cartelle in questi siti.
- [FileSystemWriteBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemwriteblockedforurls): blocca l'accesso in scrittura ai file e alle cartelle in questi siti.
- [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync): forza la sincronizzazione dei dati del browser e non mostra la richiesta di autorizzazione di sincronizzazione.
- [InsecureFormsWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecureformswarningsenabled): attiva gli avvisi per i moduli non sicuri.
- [InternetExplorerIntegrationTestingAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed): consente test in modalità Internet Explorer.
- [SpotlightExperiencesAndRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#spotlightexperiencesandrecommendationsenabled): permette agli utenti di consentire di ricevere immagini di sfondo personalizzate, testo, suggerimenti, notifiche e consigli per i servizi Microsoft.
- [NewTabPageAllowedBackgroundTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageallowedbackgroundtypes): configura i tipi di sfondo consentiti per il layout della pagina Nuova scheda.
- [SaveCookiesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savecookiesonexit): salva i cookie quando Microsoft Edge viene chiuso.
- [SensorsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsallowedforurls): consente l'accesso ai sensori in siti specifici.
- [SensorsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsblockedforurls): blocca l'accesso ai sensori in siti specifici.
- [SerialAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialaskforurls): consente Serial API in siti specifici.
- [SerialBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialblockedforurls): blocca Serial API in siti specifici.
- [UserAgentClientHintsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled): abilita la funzionalità User-Agent Client Hints.
- [UserDataSnapshotRetentionLimit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#userdatasnapshotretentionlimit): limita il numero di snapshot dei dati utente conservati per l'uso, in caso di ripristino di emergenza dello stato precedente.

#### Criteri deprecati

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled): abilita la segnalazione dei dati correlati all'uso e agli arresti anomali.
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices): invia informazioni sul sito per migliorare i servizi Microsoft.

#### Criteri obsoleti

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled): abilitare una funzionalità di sicurezza TLS 1.3 per trust anchor locali.

<!-- end 86 -->
## Versione 85.0.564.70: 6 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 85.0.564.68: 1 ottobre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 85.0.564.63: 23 settembre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#september-23-2020).

## Versione 85.0.564.51: 9 settembre

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#september-9-2020).

## Versione 85.0.564.44: 31 agosto

Risolti diversi bug e problemi relativi alle prestazioni.
<!-- begin 85 -->
## Versione 85.0.564.41: 27 agosto

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#august-27-2020).

### Aggiornamenti delle funzionalità

- **Sincronizzazione locale di preferiti e impostazioni**. Ora è possibile sincronizzare i preferiti e le impostazioni del browser tra i profili di Active Directory del proprio ambiente, senza eseguire la sincronizzazione nel cloud.

- **Supporto dei criteri di gruppo di Microsoft Edge per l'avvio di combinazioni di siti e app attendibili senza una richiesta di conferma**. È stato aggiunto il supporto dei criteri di gruppo, che consente agli amministratori di aggiungere combinazioni di siti e app attendibili per l'avvio senza la richiesta di conferma. Questo consente agli amministratori di configurare combinazioni di protocolli/origini attendibili (come le app di Microsoft 365) in modo che gli utenti finali possano eliminare il messaggio di conferma quando si visita un URL che contiene un protocollo dell'app.

- **Strumento di evidenziazione per PDF**. Questo strumento può essere aggiunto alla barra degli strumenti per i file PDF per evidenziare facilmente il testo importante.

- **L'API Storage Access è disponibile**. L'API Storage Access consente l'accesso a uno spazio di archiviazione di prima parte in un contesto di terza parte quando un utente mostra l'intento diretto di consentire lo spazio di archiviazione che altrimenti verrebbe bloccato dalla configurazione corrente del browser. Per altre informazioni, vedere [API Storage Access](https://www.chromestatus.com/feature/5612590694662144).

- **La funzione di invio a OneNote è disponibile per le Raccolte di Microsoft Edge**. Tutti sono entusiasti di poter inviare le informazioni delle Raccolte a OneNote, dopo possono essere incluse in progetti più grandi e usate per collaborare con altri utenti! Cosa più importante, in Microsoft Edge 85 sarà possibile inviare contenuti ai prodotti *Office per Mac* (Word, Excel e OneNote) sia per l'account Microsoft che per Azure Active Directory.

- **Aggiornamenti di DevTools**. Per i dettagli di questi aggiornamenti, vedere [Novità di DevTools (Microsoft Edge 85)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools).

   - Microsoft Edge DevTools supporta l'emulazione Surface Duo. Microsoft Edge DevTools può emulare Surface Duo in modo da poter verificare l'aspetto dei contenuti web sui dispositivi con due schermi. Per effettuare questo esperimento in DevTools, aprire la modalità Dispositivo premendo CTRL+MAIUSC+M su Windows o COMANDO+MAIUSC+M su macOS, e selezionare Surface Duo dall'elenco a discesa.
   - Microsoft Edge DevTools consente di abbinare le scelte rapide da tastiera con VS Code. Microsoft Edge DevTools supporta la personalizzazione delle scelte rapide da tastiera in DevTools in base all'editor/IDE. Microsoft Edge 85 introduce la possibilità di abbinare le scelte rapide da tastiera di DevTools con VS Code. Questo cambiamento contribuirà ad aumentare la produttività in VS Code e DevTools.

### Aggiornamenti dei criteri

#### Nuovi criteri

Sono stati aggiunti 13 nuovi criteri. Scaricare i modelli amministrativi aggiornati dalla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise). Sono stati aggiunti i nuovi criteri seguenti.

- [AutoLaunchProtocolsFromOrigins](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autolaunchprotocolsfromorigins) - Definisce un elenco di protocolli che possono avviare un'applicazione esterna da origini elencate senza richiedere la conferma dell'utente.
- [AutoOpenAllowedForURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenallowedforurls) - URL in cui è possibile applicare AutoOpenFileTypes.
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes) - Elenco dei tipi di file che devono essere aperti automaticamente allo scaricamento.
- [DefaultSearchProviderContextMenuAccessAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchprovidercontextmenuaccessallowed) - Consente l'accesso al menu di scelta rapida del provider di servizi predefinito.
- [EnableSha1ForLocalAnchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) - Consente i certificati firmati con l'algoritmo SHA-1 quando sono emessi da ancoraggi di attendibilità locali.
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disabilita gli avvisi di download basati sull'estensione del tipo di file per i tipi di file specificati nei domini.
- [IntensiveWakeUpThrottlingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intensivewakeupthrottlingenabled) - Controlla la funzionalità IntensiveWakeUpThrottling.
- [NewTabPagePrerenderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageprerenderenabled) - Attiva il precaricamento della nuova scheda per il rendering più rapido.
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox) - Configura l’esperienza della casella di ricerca della nuova scheda.
- [PasswordMonitorAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) - Consenti agli utenti di ricevere avvisi se le loro password non sono sicure.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) - Abilita l'uso di copie di roaming per i dati dei profili Microsoft Edge.
- [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) - Imposta la directory del profilo mobile.
- [TLSCsipherSuiteDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tlsciphersuitedenylist) - Specifica i pacchetti di crittografia TLS da disabilitare.

#### Criteri obsoleti

- [EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload) - Abilita il download delle azioni di dominio da Microsoft.
- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - Riattiva l'API dei componenti Web v0 fino a M84.
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies)- Consente a WebDriver di eseguire la sostituzione dei criteri incompatibili.

<!--- END 85 ---->

## Versione 84.0.522.63: 20 agosto

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#august-20-2020).

## Versione 84.0.522.61: 17 agosto

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 84.0.522.59: 11 agosto

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#august-11-2020).

## Versione 84.0.522.58: 10 agosto

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 84.0.522.52: 1 agosto

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 84.0.522.50: 31 luglio

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 84.0.522.49: 29 luglio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#july-29-2020).

## Versione 84.0.522.48: 28 luglio

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 84.0.522.44: 23 luglio

Risolti diversi bug e problemi relativi alle prestazioni.

<!-- begin 84 -->
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
