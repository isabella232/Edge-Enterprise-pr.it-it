---
title: Note sulla versione di Microsoft Edge per il canale Stabile
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/13/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Note sulla versione di Microsoft Edge per il canale Stabile
ms.openlocfilehash: a69b6cd7ab1fa077f2a72c01fa363fcc0efdcf24
ms.sourcegitcommit: 498a62144b099a1198c06f98ad010cf95aa33727
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "11268237"
---
# Note sulla versione del canale Stabile Microsoft Edge

Queste note sulla versione offrono informazioni sulle nuove funzionalità e sugli aggiornamenti non di sicurezza inclusi nel canale Stabile Microsoft Edge.

- Tutti gli aggiornamenti della sicurezza sono elencati [qui](microsoft-edge-relnotes-security.md).
- Le note sulla versione del canale Stable di Microsoft Edge archiviate sono disponibili [qui](microsoft-edge-relnote-archive-stable-channel.md).

 Per informazioni sui canali Microsoft Edge, vedere la [Panoramica dei canali Microsoft Edge](microsoft-edge-channels.md).

> [!NOTE]
> Per il canale Stable, gli aggiornamenti verranno implementati gradualmente su uno o più giorni. Per altre informazioni, vedere [Implementazioni progressive degli aggiornamenti di Microsoft Edge](microsoft-edge-update-progressive-rollout.md).

## Versione 87.0.664.75: 7 gennaio

Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-7-2021).

## Versione 87.0.664.66: 17 dicembre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 87.0.664.60: 10 dicembre

Risolti diversi bug e problemi relativi alle prestazioni.

## Versione 87.0.664.57: 7 dicembre

Risolti diversi bug e problemi relativi alle prestazioni. Gli aggiornamenti della sicurezza sono elencati [qui](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#december-7-2020).

## Versione 87.0.664.55: 3 dicembre

Risolti diversi bug e problemi relativi alle prestazioni. La funzionalità seguente è stata aggiornata per questa versione.

- **Shopping è abilitato per impostazione predefinita**. A partire da Microsoft Edge versione 87, gli utenti aziendali possono trarre vantaggio dallo shopping in Microsoft Edge. Grazie alla funzionalità Shopping, Microsoft Edge consente agli utenti di trovare buoni sconto e prezzi migliori durante lo shopping online. (L'esperienza dei buoni sconto è stata rilasciata con la versione stabile 87.0.664.41). L'esperienza di confronto dei prezzi è ora disponibile con questo aggiornamento. Questa funzionalità può essere configurata usando il criterio [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled). Vedere il [Blog](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) e [Altre informazioni](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping) su Microsoft Shopping.

## Versione 87.0.664.52: 30 novembre

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

Sono stati risolti diversi bug e problemi relativi alle prestazioni.

<!-- Archived to version 84.0.522.40: July 16 -->

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
