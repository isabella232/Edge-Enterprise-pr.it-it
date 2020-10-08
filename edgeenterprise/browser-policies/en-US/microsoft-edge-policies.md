---
title: Documentazione sui criteri del browser Microsoft Edge
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 09/28/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione di Windows e Mac per tutti i criteri supportati dal browser Microsoft Edge
ms.openlocfilehash: dc780166f05afd7d667f901a1198ce125831d01b
ms.sourcegitcommit: 3478cfcf2b03944213a7c7c61f05490bc37aa7c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "11094610"
---
# Microsoft Edge - Criteri
La versione più recente di Microsoft Edge include i criteri riportati di seguito. È possibile usare questi criteri per configurare la modalità di esecuzione di Microsoft Edge nell'organizzazione.

Sono disponibili informazioni su un set aggiuntivo di criteri utilizzati per controllare come e quando viene aggiornato Microsoft Edge nell'articolo dei [riferimenti sui criteri di aggiornamento di Microsoft Edge](microsoft-edge-update-policies.md).

È possibile scaricare il [Microsoft Security Compliance Toolkit](https://www.microsoft.com/download/details.aspx?id=55319) per le impostazioni di base relative alla configurazione consigliata per Microsoft Edge. Per altre informazioni, consultare il [Blog sulle basi di riferimento della sicurezza di Microsoft](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Criteri disponibili
In queste tabelle sono elencati tutti i criteri di gruppo correlati al browser disponibili in questa versione di Microsoft Edge. Usa i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.

|||
|-|-|
|[Impostazioni di Application Guard](#application-guard-settings)|[Cast](#cast)|
|[Impostazioni contenuto](#content-settings)|[Provider di ricerca predefinito](#default-search-provider)|
|[Extensions](#extensions)|[Autenticazione HTTP](#http-authentication)|
|[Impostazioni modalità tutto schermo](#kiosk-mode-settings)|[Messaggistica nativa](#native-messaging)|
|[Gestione e protezione delle password](#password-manager-and-protection)|[Stampa](#printing)|
|[Server proxy](#proxy-server)|[Impostazioni di SmartScreen](#smartscreen-settings)|
|[Avvio, home page e pagina Nuova scheda](#startup-home-page-and-new-tab-page)|[Ulteriori informazioni](#additional)|


### [*Impostazioni di Application Guard*](#application-guard-settings-policies)
|Nome criterio|Didascalia|
|-|-|
|[ApplicationGuardContainerProxy](#applicationguardcontainerproxy)|Proxy contenitore di Application Guard|
### [*Cast*](#cast-policies)
|Nome criterio|Didascalia|
|-|-|
|[EnableMediaRouter](#enablemediarouter)|Abilita Google Cast|
|[ShowCastIconInToolbar](#showcasticonintoolbar)|Mostra l'icona di cast nella barra degli strumenti|
### [*Impostazioni contenuto*](#content-settings-policies)
|Nome criterio|Didascalia|
|-|-|
|[AutoSelectCertificateForUrls](#autoselectcertificateforurls)|Seleziona automaticamente i certificati client per questi siti|
|[CookiesAllowedForUrls](#cookiesallowedforurls)|Consenti i cookie in siti specifici|
|[CookiesBlockedForUrls](#cookiesblockedforurls)|Blocca i cookie in siti specifici|
|[CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)|Limita i cookie da siti Web specifici alla sessione corrente|
|[DefaultCookiesSetting](#defaultcookiessetting)|Configura i cookie|
|[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)|Controlla l'uso dell'API file system per la lettura|
|[DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)|Controlla l'uso dell'API file system per la scrittura|
|[DefaultGeolocationSetting](#defaultgeolocationsetting)|Impostazione predefinita di georilevazione|
|[DefaultImagesSetting](#defaultimagessetting)|Impostazione predefinita per le immagini|
|[DefaultInsecureContentSetting](#defaultinsecurecontentsetting)|Controlla l'uso di eccezioni di contenuti non sicuri|
|[DefaultJavaScriptSetting](#defaultjavascriptsetting)|Impostazione predefinita di JavaScript|
|[DefaultNotificationsSetting](#defaultnotificationssetting)|Impostazione predefinita per le notifiche|
|[DefaultPluginsSetting](#defaultpluginssetting)|Impostazione predefinita di Adobe Flash|
|[DefaultPopupsSetting](#defaultpopupssetting)|Impostazione predefinita della finestra popup|
|[DefaultWebBluetoothGuardSetting](#defaultwebbluetoothguardsetting)|Controlla l'uso dell'API Web Bluetooth|
|[DefaultWebUsbGuardSetting](#defaultwebusbguardsetting)|Controlla l'uso dell'API WebUSB|
|[FileSystemReadAskForUrls](#filesystemreadaskforurls)|Consente l'accesso in lettura con l'API file system in questi siti|
|[FileSystemReadBlockedForUrls](#filesystemreadblockedforurls)|Consente l'accesso in lettura tramite l'API file system in questi siti|
|[FileSystemWriteAskForUrls](#filesystemwriteaskforurls)|Consente l'accesso in scrittura ai file e alle cartelle in questi siti|
|[FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls)|Non consente l'accesso in scrittura ai file e alle cartelle in questi siti|
|[ImagesAllowedForUrls](#imagesallowedforurls)|Consente le immagini in questi siti|
|[ImagesBlockedForUrls](#imagesblockedforurls)|Blocca le immagini in siti specifici|
|[InsecureContentAllowedForUrls](#insecurecontentallowedforurls)|Consente contenuti non sicuri in siti specifici|
|[InsecureContentBlockedForUrls](#insecurecontentblockedforurls)|Blocca contenuti non sicuri in siti specifici|
|[JavaScriptAllowedForUrls](#javascriptallowedforurls)|Consente JavaScript in siti specifici|
|[JavaScriptBlockedForUrls](#javascriptblockedforurls)|Blocca JavaScript in siti specifici|
|[LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled)|Abilita l'impostazione di comportamento dei cookie SameSite legacy predefinita|
|[LegacySameSiteCookieBehaviorEnabledForDomainList](#legacysamesitecookiebehaviorenabledfordomainlist)|Ripristina il comportamento SameSite legacy dei cookie in siti specifici|
|[NotificationsAllowedForUrls](#notificationsallowedforurls)|Consente le notifiche in siti specifici|
|[NotificationsBlockedForUrls](#notificationsblockedforurls)|Blocca le notifiche in siti specifici|
|[PluginsAllowedForUrls](#pluginsallowedforurls)|Consente il plug-in di Adobe Flash in siti specifici|
|[PluginsBlockedForUrls](#pluginsblockedforurls)|Blocca il plug-in di Adobe Flash in siti specifici|
|[PopupsAllowedForUrls](#popupsallowedforurls)|Consente le finestre popup in siti specifici|
|[PopupsBlockedForUrls](#popupsblockedforurls)|Blocca le finestre popup in siti specifici|
|[RegisteredProtocolHandlers](#registeredprotocolhandlers)|Registra i gestori di protocollo|
|[SpotlightExperiencesAndRecommendationsEnabled](#spotlightexperiencesandrecommendationsenabled)|Scegli se consentire agli utenti di ricevere immagini di sfondo personalizzate, testo, suggerimenti, notifiche,
e suggerimenti per i servizi Microsoft|
|[WebUsbAllowDevicesForUrls](#webusballowdevicesforurls)|Concede l'accesso a siti specifici per connettersi a dispositivi USB specifici|
|[WebUsbAskForUrls](#webusbaskforurls)|Consente WebUSB in siti specifici|
|[WebUsbBlockedForUrls](#webusbblockedforurls)|Blocca WebUSB in siti specifici|
### [*Provider di ricerca predefinito*](#default-search-provider-policies)
|Nome criterio|Didascalia|
|-|-|
|[DefaultSearchProviderEnabled](#defaultsearchproviderenabled)|Abilita il provider di ricerca predefinito|
|[DefaultSearchProviderEncodings](#defaultsearchproviderencodings)|Codifiche del provider di ricerca predefinito|
|[DefaultSearchProviderImageURL](#defaultsearchproviderimageurl)|Specifica la funzionalità di ricerca per immagini per il provider di ricerca predefinito|
|[DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams)|Parametri per un URL immagine che usa POST|
|[DefaultSearchProviderKeyword](#defaultsearchproviderkeyword)|Parola chiave del provider di ricerca predefinito|
|[DefaultSearchProviderName](#defaultsearchprovidername)|Nome del provider di ricerca predefinito|
|[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)|URL del servizio di ricerca del provider di ricerca predefinito|
|[DefaultSearchProviderSuggestURL](#defaultsearchprovidersuggesturl)|URL del provider di ricerca predefinito per i suggerimenti|
|[NewTabPageSearchBox](#newtabpagesearchbox)|Configura l’esperienza della nuova scheda di casella di ricerca|
### [*Extensions*](#extensions-policies)
|Nome criterio|Didascalia|
|-|-|
|[ExtensionAllowedTypes](#extensionallowedtypes)|Configura i tipi di estensioni consentiti|
|[ExtensionInstallAllowlist](#extensioninstallallowlist)|Consente l'installazione di estensioni specifiche|
|[ExtensionInstallBlocklist](#extensioninstallblocklist)|Controlla le estensioni che non è possibile installare|
|[ExtensionInstallForcelist](#extensioninstallforcelist)|Controlla le estensioni installate automaticamente|
|[ExtensionInstallSources](#extensioninstallsources)|Configura le origini di installazione di script utente ed estensione|
|[ExtensionSettings](#extensionsettings)|Configura le impostazioni di gestione delle estensioni|
### [*Autenticazione HTTP*](#http-authentication-policies)
|Nome criterio|Didascalia|
|-|-|
|[AllowCrossOriginAuthPrompt](#allowcrossoriginauthprompt)|Consentire gli avvisi di autenticazione HTTP con origini multiple|
|[AuthNegotiateDelegateAllowlist](#authnegotiatedelegateallowlist)|Specifica un elenco di server ai quali Microsoft Edge può delegare le credenziali utente|
|[AuthSchemes](#authschemes)|Schemi di autenticazione supportati|
|[AuthServerAllowlist](#authserverallowlist)|Configura l'elenco di server di autenticazione consentiti|
|[DisableAuthNegotiateCnameLookup](#disableauthnegotiatecnamelookup)|Disabilita la ricerca di CNAME durante la negoziazione dell'autenticazione Kerberos|
|[EnableAuthNegotiatePort](#enableauthnegotiateport)|Include una porta non-standard nell'SPN di Kerberos|
|[NtlmV2Enabled](#ntlmv2enabled)|Controlla se è abilitata l'autenticazione NTLMv2|
### [*Impostazioni modalità tutto schermo*](#kiosk-mode-settings-policies)
|Nome criterio|Didascalia|
|-|-|
|[KioskDeleteDownloadsOnExit](#kioskdeletedownloadsonexit)|Eliminare i file scaricati durante la sessione a tutto schermo quando Microsoft Edge si chiude|
### [*Messaggistica nativa*](#native-messaging-policies)
|Nome criterio|Didascalia|
|-|-|
|[NativeMessagingAllowlist](#nativemessagingallowlist)|Controlla quali host di messaggistica nativa possono usare gli utenti|
|[NativeMessagingBlocklist](#nativemessagingblocklist)|Configura l'elenco di indirizzi bloccati per la messaggistica nativa|
|[NativeMessagingUserLevelHosts](#nativemessaginguserlevelhosts)|Consente gli host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministrazione)|
### [*Gestione e protezione delle password*](#password-manager-and-protection-policies)
|Nome criterio|Didascalia|
|-|-|
|[PasswordManagerEnabled](#passwordmanagerenabled)|Abilita il salvataggio delle password con lo strumento di gestione delle password|
|[PasswordMonitorAllowed](#passwordmonitorallowed)|Consenti agli utenti di ricevere avvisi se le loro password non sono sicure|
|[PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl)|Configura l'URL di modifica della password|
|[PasswordProtectionLoginURLs](#passwordprotectionloginurls)|Configura l'elenco di URL di accesso aziendale dove il servizio della password di protezione dovrebbe acquisire hash salati di una password|
|[PasswordProtectionWarningTrigger](#passwordprotectionwarningtrigger)|Configura il trigger di avviso per la password di protezione|
### [*Stampa*](#printing-policies)
|Nome criterio|Didascalia|
|-|-|
|[DefaultPrinterSelection](#defaultprinterselection)|Regole di selezione della stampante predefinita|
|[PrintHeaderFooter](#printheaderfooter)|Stampa intestazioni e piè di pagina|
|[PrintPreviewUseSystemDefaultPrinter](#printpreviewusesystemdefaultprinter)|Imposta la stampante predefinita del sistema come stampante predefinita|
|[PrintingEnabled](#printingenabled)|Abilita la stampa|
|[PrintingPaperSizeDefault](#printingpapersizedefault)|Dimensioni della pagina di stampa predefinite|
|[UseSystemPrintDialog](#usesystemprintdialog)|Stampa usando la finestra di dialogo della stampante di sistema|
### [*Server proxy*](#proxy-server-policies)
|Nome criterio|Didascalia|
|-|-|
|[ProxyBypassList](#proxybypasslist)|Configura le regole di esclusione di proxy|
|[ProxyMode](#proxymode)|Configura le impostazioni del server proxy|
|[ProxyPacUrl](#proxypacurl)|Imposta l'URL del file .pac del proxy|
|[ProxyServer](#proxyserver)|Configura l'indirizzo o l'URL del server proxy|
|[ProxySettings](#proxysettings)|Impostazioni proxy|
### [*Impostazioni di SmartScreen*](#smartscreen-settings-policies)
|Nome criterio|Didascalia|
|-|-|
|[PreventSmartScreenPromptOverride](#preventsmartscreenpromptoverride)|Impedisce di ignorare i prompt di Microsoft Defender SmartScreen per i siti|
|[PreventSmartScreenPromptOverrideForFiles](#preventsmartscreenpromptoverrideforfiles)|Impedisce di ignorare gli avvisi di Microsoft Defender SmartScreen sui download|
|[SmartScreenAllowListDomains](#smartscreenallowlistdomains)|Configura l'elenco di domini per i quali Microsoft Defender SmartScreen non attiva gli avvisi|
|[SmartScreenEnabled](#smartscreenenabled)|Configura Microsoft Defender SmartScreen|
|[SmartScreenForTrustedDownloadsEnabled](#smartscreenfortrusteddownloadsenabled)|Forza i controlli di Microsoft Defender SmartScreen sui download da origini attendibili|
|[SmartScreenPuaEnabled](#smartscreenpuaenabled)|Configura Microsoft Defender SmartScreen per bloccare le applicazioni potenzialmente indesiderate|
### [*Avvio&comma; home page e pagina Nuova scheda*](#startup-home-page-and-new-tab-page-policies)
|Nome criterio|Didascalia|
|-|-|
|[HomepageIsNewTabPage](#homepageisnewtabpage)|Imposta la pagina Nuova scheda come home page|
|[HomepageLocation](#homepagelocation)|Configura l'URL della home page|
|[NewTabPageAllowedBackgroundTypes](#newtabpageallowedbackgroundtypes)|Configura i tipi di sfondo consentiti per il layout della pagina Nuova scheda|
|[NewTabPageCompanyLogo](#newtabpagecompanylogo)|Imposta il logo aziendale della pagina Nuova scheda|
|[NewTabPageHideDefaultTopSites](#newtabpagehidedefaulttopsites)|Nasconde i siti principali predefiniti dalla pagina Nuova scheda|
|[NewTabPageLocation](#newtabpagelocation)|Configura l'URL della pagina Nuova scheda|
|[NewTabPageManagedQuickLinks](#newtabpagemanagedquicklinks)|Imposta i collegamenti rapidi della pagina Nuova scheda|
|[NewTabPagePrerenderEnabled](#newtabpageprerenderenabled)|Attiva il precaricamento della nuova scheda per il rendering più rapido|
|[NewTabPageSetFeedType](#newtabpagesetfeedtype)|Configura l'esperienza della pagina Nuova scheda di Microsoft Edge|
|[RestoreOnStartup](#restoreonstartup)|Azione da eseguire all'avvio|
|[RestoreOnStartupURLs](#restoreonstartupurls)|Siti da aprire all'avvio del browser|
|[ShowHomeButton](#showhomebutton)|Mostra il pulsante Home nella barra degli strumenti|
### [*Ulteriori informazioni*](#additional-policies)
|Nome criterio|Didascalia|
|-|-|
|[AddressBarMicrosoftSearchInBingProviderEnabled](#addressbarmicrosoftsearchinbingproviderenabled)|Abilita Microsoft Search nei suggerimenti di Bing nella barra degli indirizzi|
|[AdsSettingForIntrusiveAdsSites](#adssettingforintrusiveadssites)|Impostazione degli annunci per i siti con annunci intrusivi|
|[AllowDeletingBrowserHistory](#allowdeletingbrowserhistory)|Abilita l'eliminazione della cronologia di download e browser|
|[AllowFileSelectionDialogs](#allowfileselectiondialogs)|Consente le finestre di dialogo per la selezione dei file|
|[AllowPopupsDuringPageUnload](#allowpopupsduringpageunload)|Consente la visualizzazione di popup durante il caricamento di una pagina|
|[AllowSurfGame](#allowsurfgame)|Consente il gioco Surf|
|[AllowSyncXHRInPageDismissal](#allowsyncxhrinpagedismissal)|Consente alle pagine di inviare richieste XHR sincrone durante la chiusura della pagina (deprecato)|
|[AllowTokenBindingForUrls](#allowtokenbindingforurls)|Configura l'elenco dei siti con cui Microsoft Edge proverà a stabilire un binding di token|
|[AllowTrackingForUrls](#allowtrackingforurls)|Configura il monitoraggio delle eccezioni di protezione per siti specifici|
|[AlternateErrorPagesEnabled](#alternateerrorpagesenabled)|Suggerisce pagine simili quando non è possibile trovare una pagina web|
|[AlwaysOpenPdfExternally](#alwaysopenpdfexternally)|Apre sempre i file PDF esternamente|
|[AmbientAuthenticationInPrivateModesEnabled](#ambientauthenticationinprivatemodesenabled)|Abilita l'autenticazione ambientale per i profili InPrivate e Guest|
|[AppCacheForceEnabled](#appcacheforceenabled)|Consente la riabilitazione della funzionalità AppCache, anche se disabilitata per impostazione predefinita.|
|[ApplicationLocaleValue](#applicationlocalevalue)|Configura le impostazioni locali delle applicazioni|
|[AudioCaptureAllowed](#audiocaptureallowed)|Consente o blocca l'acquisizione audio|
|[AudioCaptureAllowedUrls](#audiocaptureallowedurls)|Siti che possono accedere ai dispositivi di acquisizione audio senza richiedere l'autorizzazione|
|[AudioSandboxEnabled](#audiosandboxenabled)|Consente l'esecuzione della sandbox audio|
|[AutoImportAtFirstRun](#autoimportatfirstrun)|Importa automaticamente le impostazioni e i dati di un altro browser alla prima esecuzione|
|[AutoLaunchProtocolsFromOrigins](#autolaunchprotocolsfromorigins)|Definisci un elenco di protocolli che possono avviare un'applicazione esterna da origini elencate senza chiedere conferma all'utente|
|[AutoOpenAllowedForURLs](#autoopenallowedforurls)|URL in cui è possibile applicare AutoOpenFileTypes|
|[AutoOpenFileTypes](#autoopenfiletypes)|Elenco dei tipi di file che devono essere aperti automaticamente al download|
|[AutofillAddressEnabled](#autofilladdressenabled)|Abilita il riempimento automatico per gli indirizzi|
|[AutofillCreditCardEnabled](#autofillcreditcardenabled)|Abilita il riempimento automatico per le carte di credito|
|[AutoplayAllowed](#autoplayallowed)|Consente la riproduzione automatica dei contenuti multimediali per i siti Web|
|[BackgroundModeEnabled](#backgroundmodeenabled)|App in esecuzione in background dopo la chiusura di Microsoft Edge|
|[BackgroundTemplateListUpdatesEnabled](#backgroundtemplatelistupdatesenabled)|Abilita gli aggiornamenti in background all'elenco di modelli disponibili per Raccolte e altre funzionalità che sfruttano i modelli|
|[BingAdsSuppression](#bingadssuppression)|Blocca tutti gli annunci sui risultati della ricerca di Bing|
|[BlockThirdPartyCookies](#blockthirdpartycookies)|Blocca i cookie di terze parti|
|[BrowserAddProfileEnabled](#browseraddprofileenabled)|Abilita la creazione del profilo dal menu a comparsa Identità o dalla pagina Impostazioni|
|[BrowserGuestModeEnabled](#browserguestmodeenabled)|Abilita la modalità Guest|
|[BrowserNetworkTimeQueriesEnabled](#browsernetworktimequeriesenabled)|Consente le query a un servizio Browser Network Time|
|[BrowserSignin](#browsersignin)|Impostazioni di accesso al browser|
|[BuiltInDnsClientEnabled](#builtindnsclientenabled)|Usa il client DNS predefinito|
|[BuiltinCertificateVerifierEnabled](#builtincertificateverifierenabled)|Determina se lo strumento di verifica del certificato predefinito verrà usato per la verifica dei certificati server (deprecato)|
|[CertificateTransparencyEnforcementDisabledForCas](#certificatetransparencyenforcementdisabledforcas)|Disabilita l'applicazione della trasparenza dei certificati per un elenco di hash subjectPublicKeyInfo|
|[CertificateTransparencyEnforcementDisabledForLegacyCas](#certificatetransparencyenforcementdisabledforlegacycas)|Disabilita l'applicazione della trasparenza dei certificati per un elenco di autorità di certificazione legacy|
|[CertificateTransparencyEnforcementDisabledForUrls](#certificatetransparencyenforcementdisabledforurls)|Disabilita l'applicazione della trasparenza dei certificati per URL specifici|
|[ClearBrowsingDataOnExit](#clearbrowsingdataonexit)|Cancella i dati di esplorazione alla chiusura di Microsoft Edge|
|[ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit)|Cancella le immagini e i file memorizzati nella cache alla chiusura di Microsoft Edge|
|[ClickOnceEnabled](#clickonceenabled)|Consente agli utenti di aprire i file con il protocollo ClickOnce|
|[CollectionsServicesAndExportsBlockList](#collectionsservicesandexportsblocklist)|Blocca l'accesso a un elenco specificato di servizi e di destinazioni di esportazione in Raccolte|
|[CommandLineFlagSecurityWarningsEnabled](#commandlineflagsecuritywarningsenabled)|Abilita gli avvisi di sicurezza per i contrassegni della riga di comando|
|[ComponentUpdatesEnabled](#componentupdatesenabled)|Abilita gli aggiornamenti dei componenti in Microsoft Edge|
|[ConfigureDoNotTrack](#configuredonottrack)|Configura Do Not Track|
|[ConfigureOnPremisesAccountAutoSignIn](#configureonpremisesaccountautosignin)|Configura l'accesso automatico con un account di dominio Active Directory quando non esiste un account di dominio Azure AD|
|[ConfigureOnlineTextToSpeech](#configureonlinetexttospeech)|Configura la sintesi vocale online|
|[ConfigureShare](#configureshare)|Configura l'esperienza di condivisione|
|[CustomHelpLink](#customhelplink)|Specifica il collegamento alla guida personalizzato|
|[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled)|Controlli dell'intercettazione DNS abilitati|
|[DefaultBrowserSettingEnabled](#defaultbrowsersettingenabled)|Imposta Microsoft Edge come browser predefinito|
|[DefaultSearchProviderContextMenuAccessAllowed](#defaultsearchprovidercontextmenuaccessallowed)|Consente l’accesso al menu di scelta rapida del provider di ricerca predefinito |
|[DefaultSensorsSetting](#defaultsensorssetting)|Impostazione predefinita per i sensori|
|[DefaultSerialGuardSetting](#defaultserialguardsetting)|Controlla l'uso di Serial API|
|[DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload)|Richiede che l'elenco siti in modalità Enterprise sia disponibile prima dello spostamento tramite schede.|
|[DeleteDataOnMigration](#deletedataonmigration)|Elimina i dati del browser obsoleti alla migrazione|
|[DeveloperToolsAvailability](#developertoolsavailability)|Controlla dove si possono usare gli strumenti di sviluppo|
|[DiagnosticData](#diagnosticdata)|Invia dati di diagnostica necessari e facoltativi sull'uso del browser|
|[DirectInvokeEnabled](#directinvokeenabled)|Consente agli utenti di aprire i file con il protocollo DirectInvoke|
|[Disable3DAPIs](#disable3dapis)|Disabilita il supporto per le API di grafica 3D|
|[DisableScreenshots](#disablescreenshots)|Disabilita l'acquisizione di screenshot|
|[DiskCacheDir](#diskcachedir)|Imposta la directory della cache del disco|
|[DiskCacheSize](#diskcachesize)|Imposta le dimensioni della cache del disco, in byte|
|[DnsOverHttpsMode](#dnsoverhttpsmode)|Controlla la modalità del protocollo DNS-over-HTTPS|
|[DnsOverHttpsTemplates](#dnsoverhttpstemplates)|Specifica il modello URI del resolver DNS-over-HTTPS desiderato|
|[DownloadDirectory](#downloaddirectory)|Imposta la directory di download|
|[DownloadRestrictions](#downloadrestrictions)|Consente le restrizioni per il download|
|[EdgeCollectionsEnabled](#edgecollectionsenabled)|Abilita la funzionalità Raccolte|
|[EditFavoritesEnabled](#editfavoritesenabled)|Consente agli utenti di modificare i Preferiti|
|[EnableDeprecatedWebPlatformFeatures](#enabledeprecatedwebplatformfeatures)|Riabilita le funzionalità della piattaforma Web deprecate per un periodo di tempo limitato|
|[EnableDomainActionsDownload](#enabledomainactionsdownload)|Abilita il download delle azioni di dominio da Microsoft (obsoleto)|
|[EnableOnlineRevocationChecks](#enableonlinerevocationchecks)|Abilita i controlli OCSP/CRL online|
|[EnableSha1ForLocalAnchors](#enablesha1forlocalanchors)|Consente certificati firmati SHA-1 quando sono emessi da trust anchor locali (deprecato)|
|[EnterpriseHardwarePlatformAPIEnabled](#enterprisehardwareplatformapienabled)|Consente alle estensioni gestite di usare l'API Enterprise Hardware Platform|
|[EnterpriseModeSiteListManagerAllowed](#enterprisemodesitelistmanagerallowed)|Consente l’accesso allo strumento Enterprise Mode Site List Manager|
|[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](#exemptdomainfiletypepairsfromfiletypedownloadwarnings)|Disabilita gli avvisi di download basati sull'estensione del tipo di file per i tipi di file specificati nei domini|
|[ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol)|Controlla le comunicazioni con il servizio di sperimentazione e configurazione|
|[ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox)|Mostra una casella di controllo "Sempre aperto" nella casella di controllo del protocollo esterno|
|[FamilySafetySettingsEnabled](#familysafetysettingsenabled)|Consente agli utenti di configurare la protezione per la famiglia|
|[FavoritesBarEnabled](#favoritesbarenabled)|Abilita la barra Preferiti|
|[ForceBingSafeSearch](#forcebingsafesearch)|Applica Ricerca sicura di Bing|
|[ForceCertificatePromptsOnMultipleMatches](#forcecertificatepromptsonmultiplematches)|Configura se Microsoft Edge deve selezionare automaticamente un certificato quando sono presenti più corrispondenze di certificato per un sito configurato con "AutoSelectCertificateForUrls"|
|[ForceEphemeralProfiles](#forceephemeralprofiles)|Abilita l'uso di profili temporanei|
|[ForceGoogleSafeSearch](#forcegooglesafesearch)|Applica Ricerca sicura di Google|
|[ForceLegacyDefaultReferrerPolicy](#forcelegacydefaultreferrerpolicy)|Usa un criterio di referrer predefinito di no-referrer-when-downgrade (deprecato)|
|[ForceNetworkInProcess](#forcenetworkinprocess)|Forza l'esecuzione del codice di rete nel processo del browser (obsoleto)|
|[ForceSync](#forcesync)|Forza la sincronizzazione dei dati del browser e non visualizzare la richiesta di autorizzazione di sincronizzazione|
|[ForceYouTubeRestrict](#forceyoutuberestrict)|Forza la modalità con restrizioni YouTube minima|
|[FullscreenAllowed](#fullscreenallowed)|Consente la modalità a schermo intero|
|[GloballyScopeHTTPAuthCacheEnabled](#globallyscopehttpauthcacheenabled)|Abilita la cache di autenticazione HTTP con ambito globale|
|[GoToIntranetSiteForSingleWordEntryInAddressBar](#gotointranetsiteforsinglewordentryinaddressbar)|Forza l'esplorazione del sito Intranet diretta anziché tramite la ricerca di singole parole nella barra degli indirizzi|
|[HSTSPolicyBypassList](#hstspolicybypasslist)|Configura l'elenco di nomi che ignoreranno la verifica dei criteri HSTS|
|[HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled)|Usa l'accelerazione hardware se disponibile|
|[HideFirstRunExperience](#hidefirstrunexperience)|Nasconde l'esperienza della first-run experience e la schermata iniziale|
|[ImportAutofillFormData](#importautofillformdata)|Consente l'importazione dei dati di moduli con riempimento automatico|
|[ImportBrowserSettings](#importbrowsersettings)|Consente l'importazione delle impostazioni del browser|
|[ImportCookies](#importcookies)|Consente l'importazione di cookie|
|[ImportExtensions](#importextensions)|Consente l'importazione di estensioni|
|[ImportFavorites](#importfavorites)|Consente l'importazione di Preferiti|
|[ImportHistory](#importhistory)|Consente l'importazione della cronologia esplorazioni|
|[ImportHomepage](#importhomepage)|Consente l'importazione delle impostazioni della home page|
|[ImportOpenTabs](#importopentabs)|Consente l'importazione di schede aperte|
|[ImportPaymentInfo](#importpaymentinfo)|Consente l'importazione di informazioni di pagamento|
|[ImportSavedPasswords](#importsavedpasswords)|Consente l'importazione delle password salvate|
|[ImportSearchEngine](#importsearchengine)|Consente l'importazione delle impostazioni del motore di ricerca|
|[ImportShortcuts](#importshortcuts)|Consente l'importazione di scelte rapide da tastiera|
|[InPrivateModeAvailability](#inprivatemodeavailability)|Configura la disponibilità della modalità InPrivate|
|[InsecureFormsWarningsEnabled](#insecureformswarningsenabled)|Attiva gli avvisi per i moduli non sicuri|
|[IntensiveWakeUpThrottlingEnabled](#intensivewakeupthrottlingenabled)|Controlla la funzionalità IntensiveWakeUpThrottling|
|[InternetExplorerIntegrationEnhancedHangDetection](#internetexplorerintegrationenhancedhangdetection)|Configura il rilevamento di blocchi avanzati per la modalità di Internet Explorer|
|[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)|Configurare l'integrazione Internet Explorer|
|[InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist)|Configurare l'elenco siti modalità Enterprise|
|[InternetExplorerIntegrationSiteRedirect](#internetexplorerintegrationsiteredirect)|Specifica il comportamento degli spostamenti "nella pagina" verso i siti non configurati all'avvio dalle pagine in modalità Internet Explorer|
|[InternetExplorerIntegrationTestingAllowed](#internetexplorerintegrationtestingallowed)|Consenti il test della modalità di Internet Explorer|
|[IsolateOrigins](#isolateorigins)|Abilita l'isolamento del sito per origini specifiche|
|[LocalProvidersEnabled](#localprovidersenabled)|Consente suggerimenti dai provider locali|
|[ManagedFavorites](#managedfavorites)|Configura i Preferiti|
|[ManagedSearchEngines](#managedsearchengines)|Gestisce i motori di ricerca|
|[MaxConnectionsPerProxy](#maxconnectionsperproxy)|Numero massimo di connessioni simultanee al server proxy|
|[MediaRouterCastAllowAllIPs](#mediaroutercastallowallips)|Consente a Google Cast di connettersi ai dispositivi Cast su tutti gli indirizzi IP|
|[MetricsReportingEnabled](#metricsreportingenabled)|Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali (deprecato)|
|[NativeWindowOcclusionEnabled](#nativewindowocclusionenabled)|Abilita l'occlusione della finestra nativa|
|[NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout)|Imposta un timeout per i ritardi nello spostamento tramite schede per l'elenco siti in modalità Enterprise|
|[NetworkPredictionOptions](#networkpredictionoptions)|Abilita la previsione di rete|
|[NonRemovableProfileEnabled](#nonremovableprofileenabled)|Configura l'accesso automatico di un utente con un profilo predefinito al proprio account aziendale o dell'istituto di istruzione|
|[OverrideSecurityRestrictionsOnInsecureOrigin](#overridesecurityrestrictionsoninsecureorigin)|Controlla dove si applicano le restrizioni di sicurezza per origini non sicure|
|[PaymentMethodQueryEnabled](#paymentmethodqueryenabled)|Consente ai siti Web di eseguire query per i metodi di pagamento disponibili|
|[PersonalizationReportingEnabled](#personalizationreportingenabled)|Consente la personalizzazione degli annunci, della ricerca e delle notizie con l'invio della cronologia esplorazioni a Microsoft|
|[PinningWizardAllowed](#pinningwizardallowed)|Consente la procedura guidata per Aggiungi alla barra delle applicazioni|
|[ProactiveAuthEnabled](#proactiveauthenabled)|Abilita l'autenticazione proattiva|
|[PromotionalTabsEnabled](#promotionaltabsenabled)|Abilita il contenuto promozionale di una scheda completa|
|[PromptForDownloadLocation](#promptfordownloadlocation)|Chiede dove salvare i file scaricati|
|[QuicAllowed](#quicallowed)|Consente il protocollo QUIC|
|[RelaunchNotification](#relaunchnotification)|Inviare una notifica a un utente in merito al riavvio del browser consigliato o necessario per gli aggiornamenti in sospeso|
|[RelaunchNotificationPeriod](#relaunchnotificationperiod)|Imposta il periodo di tempo per le notifiche sugli aggiornamenti|
|[RendererCodeIntegrityEnabled](#renderercodeintegrityenabled)|Abilita l'integrità del codice del renderer|
|[RequireOnlineRevocationChecksForLocalAnchors](#requireonlinerevocationchecksforlocalanchors)|Specifica se i controlli OCSP/CRL online sono necessari per i trust anchor locali|
|[ResolveNavigationErrorsUseWebService](#resolvenavigationerrorsusewebservice)|Abilita la risoluzione degli errori di spostamento con un servizio Web|
|[RestrictSigninToPattern](#restrictsignintopattern)|Limita gli account che è possibile utilizzare come account principali di Microsoft Edge|
|[RoamingProfileLocation](#roamingprofilelocation)|Imposta la directory del profilo mobile|
|[RoamingProfileSupportEnabled](#roamingprofilesupportenabled)|Abilita l'uso di copie di roaming per i dati dei profili Microsoft Edge|
|[RunAllFlashInAllowMode](#runallflashinallowmode)|Estende l'impostazione dei contenuti di Adobe Flash a tutti i contenuti|
|[SSLErrorOverrideAllowed](#sslerroroverrideallowed)|Consente agli utenti di procedere nella pagina di avviso HTTPS|
|[SSLVersionMin](#sslversionmin)|Versione TLS minima abilitata|
|[SaveCookiesOnExit](#savecookiesonexit)|Salva i cookie quando Microsoft Edge si chiude|
|[SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled)|Disattiva il salvataggio della cronologia del browser|
|[ScreenCaptureAllowed](#screencaptureallowed)|Consente o rifiuta l'acquisizione dello schermo|
|[ScrollToTextFragmentEnabled](#scrolltotextfragmentenabled)|Consente lo scorrimento al testo specificato nei frammenti di URL|
|[SearchSuggestEnabled](#searchsuggestenabled)|Abilita i suggerimenti per la ricerca|
|[SecurityKeyPermitAttestation](#securitykeypermitattestation)|Siti Web o domini che non necessitano dell'autorizzazione per usare l'attestazione della chiave di sicurezza diretta|
|[SendIntranetToInternetExplorer](#sendintranettointernetexplorer)|Invia tutti i siti Intranet a Internet Explorer|
|[SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices)|Invia informazioni sul sito per migliorare i servizi Microsoft (deprecato)|
|[SensorsAllowedForUrls](#sensorsallowedforurls)|Consenti l'accesso ai sensori in siti specifici|
|[SensorsBlockedForUrls](#sensorsblockedforurls)|Blocca l'accesso ai sensori in siti specifici|
|[SerialAskForUrls](#serialaskforurls)|Consenti API Serial in siti specifici|
|[SerialBlockedForUrls](#serialblockedforurls)|Blocca Serial API in siti specifici|
|[ShowOfficeShortcutInFavoritesBar](#showofficeshortcutinfavoritesbar)|Mostra la scelta rapida da tastiera di Microsoft Office nella barra dei Preferiti (deprecato)|
|[SignedHTTPExchangeEnabled](#signedhttpexchangeenabled)|Abilita il supporto di Signed HTTP Exchange (SXG)|
|[SitePerProcess](#siteperprocess)|Abilita l'isolamento del sito per tutte le origini|
|[SpellcheckEnabled](#spellcheckenabled)|Abilita il controllo ortografico|
|[SpellcheckLanguage](#spellchecklanguage)|Abilita lingue specifiche del controllo ortografico|
|[SpellcheckLanguageBlocklist](#spellchecklanguageblocklist)|Forza la disabilitazione delle lingue del controllo ortografico|
|[StricterMixedContentTreatmentEnabled](#strictermixedcontenttreatmentenabled)|Abilita un trattamento più rigoroso per contenuti misti (deprecato)|
|[SuppressUnsupportedOSWarning](#suppressunsupportedoswarning)|Elimina l'avviso del sistema operativo non supportato|
|[SyncDisabled](#syncdisabled)|Disabilita la sincronizzazione dei dati con i servizi di sincronizzazione di Microsoft|
|[SyncTypesListDisabled](#synctypeslistdisabled)|Configura l'elenco dei tipi esclusi dalla sincronizzazione|
|[TLS13HardeningForLocalAnchorsEnabled](#tls13hardeningforlocalanchorsenabled)|Abilita una funzionalità di sicurezza TLS 1.3 per i trust anchor locali (obsoleto)|
|[TLSCipherSuiteDenyList](#tlsciphersuitedenylist)|Specifica i pacchetti di crittografia TLS da disabilitare|
|[TabFreezingEnabled](#tabfreezingenabled)|Consente il blocco delle schede di sfondo|
|[TaskManagerEndProcessEnabled](#taskmanagerendprocessenabled)|Abilita i processi finali nel servizio di gestione attività del browser|
|[TotalMemoryLimitMb](#totalmemorylimitmb)|Imposta un limite per i megabyte di memoria che possono essere usati in un'unica istanza di Microsoft Edge|
|[TrackingPrevention](#trackingprevention)|Blocca il monitoraggio dell'attività di esplorazione sul Web degli utenti|
|[TranslateEnabled](#translateenabled)|Abilita Traduci|
|[URLAllowlist](#urlallowlist)|Definisce un elenco di URL consentiti|
|[URLBlocklist](#urlblocklist)|Blocca l'accesso a un elenco di URL|
|[UserAgentClientHintsEnabled](#useragentclienthintsenabled)|Abilita la funzionalità User-Agent Client Hints (deprecato)|
|[UserDataDir](#userdatadir)|Imposta la directory dei dati dell'utente|
|[UserDataSnapshotRetentionLimit](#userdatasnapshotretentionlimit)|Limita il numero di snapshot dei dati utente conservati per l'uso in caso di ripristino di emergenza|
|[UserFeedbackAllowed](#userfeedbackallowed)|Consente il feedback degli utenti|
|[VideoCaptureAllowed](#videocaptureallowed)|Consente o blocca l'acquisizione video|
|[VideoCaptureAllowedUrls](#videocaptureallowedurls)|Siti che possono accedere ai dispositivi di acquisizione video senza richiedere l'autorizzazione|
|[WPADQuickCheckEnabled](#wpadquickcheckenabled)|Imposta l'ottimizzazione WPAD|
|[WebAppInstallForceList](#webappinstallforcelist)|Configura l'elenco delle app Web installate forzatamente|
|[WebComponentsV0Enabled](#webcomponentsv0enabled)|Riattiva l'API v0 dei componenti Web fino a M84 (obsoleto)|
|[WebDriverOverridesIncompatiblePolicies](#webdriveroverridesincompatiblepolicies)|Consente a WebDriver di eseguire l'override dei criteri non compatibili (obsoleto)|
|[WebRtcLocalIpsAllowedUrls](#webrtclocalipsallowedurls)|Gestisce l'esposizione degli indirizzi IP locali tramite WebRTC|
|[WebRtcLocalhostIpHandling](#webrtclocalhostiphandling)|Limita l'esposizione dell'indirizzo IP locale tramite WebRTC|
|[WebRtcUdpPortRange](#webrtcudpportrange)|Limita l'intervallo di porte UDP locali usate da WebRTC|
|[WinHttpProxyResolverEnabled](#winhttpproxyresolverenabled)|Usa il resolver proxy di Windows (deprecato)|




  ## Impostazioni dei criteri di Application Guard

  [Torna all'inizio](#microsoft-edge---policies)

  ### ApplicationGuardContainerProxy
  #### Proxy contenitore di Application Guard
  
  
  #### Versioni supportate:
  - In Windows dalla versione 84 o successive

  #### Descrizione
  Configura le impostazioni del proxy per Application Guard di Microsoft Edge.
Se si abilita questo criterio, Application Guard di Microsoft Edge ignora altre fonti di configurazioni proxy.

Se non si configura il criterio, Application Guard di Microsoft Edge userà la configurazione proxy dell'host.

Questo criterio non influisce sulla configurazione proxy di Microsoft Edge al di fuori di Application Guard (nell'host).

Il campo ProxyMode consente di specificare il server proxy usato da Application Guard di Microsoft Edge.

Il campo ProxyPacUrl è un URL a un file .pac del proxy.

Il campo ProxyServer è un URL per il server proxy.

Se si sceglie il valore "direct" come "ProxyMode", tutti gli altri campi vengono ignorati.

Se si sceglie il valore "auto_detect" come "ProxyMode", tutti gli altri campi vengono ignorati.

Se si sceglie il valore "fixed_server" come "ProxyMode", viene usato il campo "ProxyServer".

Se si sceglie il valore "pac_script" come "ProxyMode", viene usato il campo "ProxyPacUrl".

Per altre informazioni su come identificare il traffico di Application Guard tramite proxy doppio, visitare [https://go.microsoft.com/fwlink/?linkid=2134653](https://go.microsoft.com/fwlink/?linkid=2134653).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ApplicationGuardContainerProxy
  - Nome Criteri di gruppo: Proxy contenitore di Application Guard
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni Application Guard
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ApplicationGuardContainerProxy
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di cast

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnableMediaRouter
  #### Abilita Google Cast
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilitare questo criterio per abilitare Google Cast. Gli utenti potranno avviarlo dal menu delle app, dai menu contestuali delle pagine, dai controlli multimediali nei siti Web abilitati a Cast e (se visualizzata) dall'icona della barra degli strumenti di Cast.

Disabilitare questo criterio per disabilitare Google Cast.

Per impostazione predefinita, Google Cast è abilitato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnableMediaRouter
  - Nome Criteri di gruppo: Abilita Google Cast
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Cast
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnableMediaRouter
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnableMediaRouter
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ShowCastIconInToolbar
  #### Mostra l'icona di cast nella barra degli strumenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impostare questo criterio su true per mostrare l'icona della barra degli strumenti di Cast nella barra degli strumenti o nel menu sulla barra di navigazione. Gli utenti non potranno rimuoverlo.

Se si disabilita o non si configura questo criterio, gli utenti possono aggiungere o rimuovere l'icona utilizzando il relativo menu contestuale.

Se è stato impostato anche il criterio [EnableMediaRouter](#enablemediarouter) su false, questo criterio viene ignorato e l'icona della barra degli strumenti non viene mostrata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ShowCastIconInToolbar
  - Nome Criteri di gruppo: Mostra l'icona di cast nella barra degli strumenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Cast
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ShowCastIconInToolbar
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ShowCastIconInToolbar
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di impostazioni di contenuto

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutoSelectCertificateForUrls
  #### Seleziona automaticamente i certificati client per questi siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  La configurazione del criterio consente di creare un elenco di pattern URL che specificano i siti per cui Microsoft Edge può selezionare automaticamente un certificato del client. Il valore è una matrice di dizionari JSON convertiti in stringa, ciascuno con la forma { "pattern": "$URL_PATTERN", "filter" : $FILTER }, dove $URL_PATTERN è un pattern di configurazione del contenuto. $FILTER limita i certificati del client che il browser seleziona automaticamente. Indipendentemente dal filtro, solo i certificati che corrispondono alla richiesta di certificato del server sono selezionati.

Esempi dell’uso della sezione $FILTER:

* Quando $FILTER è configurato su { "ISSUER": { "CN": "$ISSUER_CN" } }, solo i certificati rilasciati da certificati con il CommonName $ISSUER_CN sono selezionati.

* Quando $FILTER contiene sia la sezione "ISSUER" che la sezione "SUBJECT", sono selezionati sono i certificati del client che soddisfano entrambe le condizioni.

* Quando $FILTER contiene una sezione "SUBJECT" con il valore "O", il certificato deve avere almeno una organizzazione corrispondente al valore specificato per essere selezionata. 

* Quando $FILTER contiene una sezione "SUBJECT" con il valore "OU", il certificato ha bisogno di almeno una unità organizzativa corrispondente al valore specificato per essere selezionata.

* Quando $FILTER è configurato su {}, la selezione dei certificati del client non viene limitata automaticamente. Notare che i filtri forniti dal server web continuano ad applicarsi.

Se il criterio non viene configurato, non ci sarà alcuna selezione automatica per i siti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AutoSelectCertificateForUrls
  - Nome Criteri di gruppo: Seleziona automaticamente i certificati client per questi siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\AutoSelectCertificateForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AutoSelectCertificateForUrls\1 = "{\"pattern\":\"https://www.contoso.com\",\"filter\":{\"ISSUER\":{\"CN\":\"certificate issuer name\", \"L\": \"certificate issuer location\", \"O\": \"certificate issuer org\", \"OU\": \"certificate issuer org unit\"}, \"SUBJECT\":{\"CN\":\"certificate subject name\", \"L\": \"certificate subject location\", \"O\": \"certificate subject org\", \"OU\": \"certificate subject org unit\"}}}"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AutoSelectCertificateForUrls
  - Valore di esempio
``` xml
<array>
  <string>{"pattern":"https://www.contoso.com","filter":{"ISSUER":{"CN":"certificate issuer name", "L": "certificate issuer location", "O": "certificate issuer org", "OU": "certificate issuer org unit"}, "SUBJECT":{"CN":"certificate subject name", "L": "certificate subject location", "O": "certificate subject org", "OU": "certificate subject org unit"}}}</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CookiesAllowedForUrls
  #### Consenti i cookie in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che sono consentiti per impostare i cookie.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultCookiesSetting](#defaultcookiessetting) (se impostato) o la configurazione personale dell'utente.

Per altre informazioni, vedere i criteri [CookiesBlockedForUrls](#cookiesblockedforurls) e [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls).

Nota: non è possibile impostare modelli URL in conflitto tra questi tre criteri:

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- CookiesAllowedForUrls

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

Per non cancellare i cookie all'uscita, configura i criteri [SaveCookiesOnExit](#savecookiesonexit).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CookiesAllowedForUrls
  - Nome Criteri di gruppo: Consenti i cookie in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\CookiesAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CookiesAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CookiesBlockedForUrls
  #### Blocca i cookie in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non sono consentiti per impostare i cookie.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultCookiesSetting](#defaultcookiessetting) (se impostato) o la configurazione personale dell'utente.

Per altre informazioni, vedere i criteri [CookiesAllowedForUrls](#cookiesallowedforurls) e [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls).

Nota: non è possibile impostare modelli URL in conflitto tra questi tre criteri:

- CookiesBlockedForUrls

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CookiesBlockedForUrls
  - Nome Criteri di gruppo: Blocca i cookie in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\CookiesBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CookiesBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CookiesSessionOnlyForUrls
  #### Limita i cookie da siti Web specifici alla sessione corrente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  I cookie creati dai siti Web che corrispondono a un modello URL definito dall'utente vengono eliminati al termine della sessione (quando viene chiusa la finestra).

I cookie creati dai siti Web che non corrispondono al modello vengono controllati dal criterio [DefaultCookiesSetting](#defaultcookiessetting) (se impostato) o dalla configurazione personale dell'utente. Questo è il comportamento predefinito anche se non si configura questo criterio.

Se Microsoft Edge è in esecuzione in background, la sessione potrebbe non terminare quando viene chiusa l'ultima finestra, il che significa che i cookie non verranno eliminati quando viene chiusa la finestra. Per informazioni sulla configurazione di cosa accade quando Microsoft Edge è in esecuzione in background, vedere il criterio [BackgroundModeEnabled](#backgroundmodeenabled).

Per controllare quali siti Web possono creare cookie, è anche possibile utilizzare i criteri [CookiesAllowedForUrls](#cookiesallowedforurls) e [CookiesBlockedForUrls](#cookiesblockedforurls).

Nota: non è possibile impostare modelli URL in conflitto tra questi tre criteri:

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- CookiesSessionOnlyForUrls

Se si imposta il criterio [RestoreOnStartup](#restoreonstartup) per ripristinare gli URL di sessioni precedenti, questo criterio viene ignorato e i cookie vengono archiviati definitivamente per tali siti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CookiesSessionOnlyForUrls
  - Nome Criteri di gruppo: Limita i cookie da siti Web specifici alla sessione corrente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\CookiesSessionOnlyForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CookiesSessionOnlyForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultCookiesSetting
  #### Configura i cookie
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se i siti Web possono creare cookie nel dispositivo dell'utente. Questo criterio è di tipo tutto o niente: consente di creare cookie a tutti i siti Web o a nessuno. Non è possibile utilizzare questo criterio per abilitare i cookie di siti Web specifici.

Impostare il criterio su "SessionOnly" per eliminare i cookie al termine della sessione. Se Microsoft Edge è in esecuzione in background, la sessione potrebbe non terminare quando viene chiusa l'ultima finestra, il che significa che i cookie non verranno eliminati quando viene chiusa la finestra. Per informazioni sulla configurazione di cosa accade quando Microsoft Edge è in esecuzione in background, vedere il criterio [BackgroundModeEnabled](#backgroundmodeenabled).

Se non si configura questo criterio, viene usato quello predefinito "AllowCookies" e gli utenti possono modificare questa impostazione in Impostazioni di Microsoft Edge. Per impedire agli utenti di modificare questa impostazione, impostare il criterio.

Mapping delle opzioni del criterio:

* AllowCookies (1) = Consentire a tutti i siti di creare cookie

* BlockCookies (2) = Non consentire ad alcun sito di creare cookie

* SessionOnly (4) = Mantieni i cookie per tutta la durata della sessione, tranne quelli elencati in [SaveCookiesOnExit](#savecookiesonexit)

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultCookiesSetting
  - Nome Criteri di gruppo: Configura i cookie
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultCookiesSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultCookiesSetting
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultFileSystemReadGuardSetting
  #### Controlla l'uso dell'API file system per la lettura
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Se si imposta questo criterio su 3, i siti web possono richiedere l'accesso in lettura al filesystem del sistema operativo host attraverso l'API file System. Se si imposta questo criterio su 2, l’accesso viene negato.

Se non si imposta questo criteri, i siti web possono richiedere accesso. Gli utenti possono modificare questa impostazione.

Mapping delle opzioni del criterio:

* BlockFileSystemRead (2) = Non permette ad alcun sito di richiedere l'accesso in lettura ai file e alle directory tramite l'API file System

* AskFileSystemRead (3) = Permette ai siti di chiedere all'utente di concedere l'accesso in lettura ai file e alle directory tramite l'API file System

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultFileSystemReadGuardSetting
  - Nome Criteri di gruppo: controlla l'uso dell'API file system per la lettura
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultFileSystemReadGuardSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultFileSystemReadGuardSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultFileSystemWriteGuardSetting
  #### Controlla l'uso dell'API file system per la scrittura
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Se si imposta questo criterio su 3, i siti web possono richiedere l'accesso in scrittura al filesystem del sistema operativo host attraverso l'API file System. Se si imposta questo criterio su 2, l’accesso viene negato.

Se non si imposta questo criteri, i siti web possono richiedere accesso. Gli utenti possono modificare questa impostazione.

Mapping delle opzioni del criterio:

* BlockFileSystemWrite (2) = Non permette ad alcun sito di richiedere l'accesso in scrittura ai file e alle directory

* AskFileSystemWrite (3) = Permette ai siti di chiedere all'utente di concedere l'accesso in scrittura ai file e alle directory

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultFileSystemWriteGuardSetting
  - Nome Criteri di gruppo: controlla l'uso dell'API file system per la scrittura
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultFileSystemWriteGuardSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: DefaultFileSystemWriteGuardSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultGeolocationSetting
  #### Impostazione predefinita di georilevazione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Stabilisce se i siti Web possono tenere traccia delle posizioni fisiche degli utenti. È possibile consentire il tracciamento per impostazione predefinita (“AllowGeolocation”), negarlo per impostazione predefinita (“BlockGeolocation”) o chiedere conferma all'utente ogni volta che un sito Web richiede la posizione (“AskGeolocation”).

Se non si configura questo criterio, viene usato "AskGeolocation" e l'utente può modificarlo.

Mapping delle opzioni del criterio:

* AllowGeolocation (1) = Consentire ai siti di tenere traccia della posizione fisica degli utenti

* BlockGeolocation (2) = Non consentire ad alcun sito di tenere traccia della posizione fisica degli utenti

* AskGeolocation (3) = Chiedere conferma ogni volta che un sito Web vuole tenere traccia della posizione fisica degli utenti

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultGeolocationSetting
  - Nome Criteri di gruppo: Impostazione predefinita di georilevazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultGeolocationSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultGeolocationSetting
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultImagesSetting
  #### Impostazione predefinita per le immagini
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Stabilisce se i siti Web possono mostrare immagini. È possibile consentire (“AllowImages”) o bloccare (“BlockImages”) le immagini in tutti i siti.

Se non si configura questo criterio, le immagini sono consentite per impostazione predefinita e l'utente può modificare tale impostazione.

Mapping delle opzioni del criterio:

* AllowImages (1) = Consentire a tutti i siti di mostrare tutte le immagini

* BlockImages (2) = Non consentire ad alcun sito di mostrare le immagini

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultImagesSetting
  - Nome Criteri di gruppo: Impostazione predefinita per le immagini
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultImagesSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultImagesSetting
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultInsecureContentSetting
  #### Controlla l'uso di eccezioni di contenuti non sicuri
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Permette di specificare se gli utenti possono aggiungere eccezioni per consentire contenuti misti per siti specifici.

Questo criterio può essere ignorato per modelli URL specifici con i criteri [InsecureContentAllowedForUrls](#insecurecontentallowedforurls) e [InsecureContentBlockedForUrls](#insecurecontentblockedforurls).

Se non viene impostato questo criterio, gli utenti potranno aggiungere eccezioni per consentire i contenuti misti bloccabili e disabilitare gli aggiornamenti automatici per i contenuti misti bloccabili.

Mapping delle opzioni del criterio:

* BlockInsecureContent (2) = Non consentire ad alcun sito di caricare contenuti misti 

* AllowExceptionsInsecureContent (3) = Consentire agli utenti di aggiungere eccezioni per consentire i contenuti misti

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultInsecureContentSetting
  - Nome Criteri di gruppo: Controlla l'uso di eccezioni di contenuti non sicuri
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultInsecureContentSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultInsecureContentSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultJavaScriptSetting
  #### Impostazione predefinita di JavaScript
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Stabilisce se i siti Web possono eseguire JavaScript. È possibile consentirlo (“AllowJavaScript”) o bloccarlo (“BlockJavaScript”) per tutti i siti.

Se non si configura questo criterio, tutti i siti possono eseguire JavaScript per impostazione predefinita e l'utente può modificare tale impostazione.

Mapping delle opzioni del criterio:

* AllowJavaScript (1) = Consentire a tutti i siti di eseguire JavaScript

* BlockJavaScript (2) = Non consentire ad alcun sito di eseguire JavaScript

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultJavaScriptSetting
  - Nome Criteri di gruppo: Impostazione predefinita di JavaScript
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultJavaScriptSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultJavaScriptSetting
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultNotificationsSetting
  #### Impostazione predefinita per le notifiche
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Stabilisce se i siti Web possono mostrare le notifiche sul desktop. È possibile consentirle per impostazione predefinita (“AllowNotifications”), negarle per impostazione predefinita (“BlockNotifications”) o fare in modo che venga chiesta conferma all'utente ogni volta che un sito Web vuole mostrare una notifica (“AskNotifications”).

Se non si configura questo criterio, le notifiche sono consentite per impostazione predefinita e l'utente può modificare tale impostazione.

Mapping delle opzioni del criterio:

* AllowNotifications (1) = Consentire ai siti di mostrare le notifiche sul desktop

* BlockNotifications (2) = Non consentire ad alcun sito di mostrare le notifiche sul desktop

* AskNotifications (3) = Chiedere conferma ogni volta che un sito vuole mostrare notifiche sul desktop

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultNotificationsSetting
  - Nome Criteri di gruppo: Impostazione predefinita per le notifiche
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultNotificationsSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultNotificationsSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultPluginsSetting
  #### Impostazione predefinita di Adobe Flash
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  [PluginsAllowedForUrls](#pluginsallowedforurls) e [PluginsBlockedForUrls](#pluginsblockedforurls) vengono verificati per primi, quindi questo criterio. Le opzioni sono "ClickToPlay" e "BlockPlugins". Se si imposta questo criterio su "BlockPlugins", il plug-in viene negato per tutti i siti Web. "ClickToPlay" consente di eseguire il plug-in di Flash, ma gli utenti fanno clic sul segnaposto per avviarlo.

Se non si configura questo criterio, l'utente può modificare tale impostazione manualmente.

Nota: la riproduzione automatica è solo per i domini elencati in modo esplicito nel criterio [PluginsAllowedForUrls](#pluginsallowedforurls). Per attivare la riproduzione automatica per tutti i siti, aggiungere http://* e https://* all'elenco degli URL consentiti.

Mapping delle opzioni del criterio:

* BlockPlugins (2) = Bloccare il plug-in di Adobe Flash

* ClickToPlay (3) = Fare clic per riprodurre

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultPluginsSetting
  - Nome Criteri di gruppo: Impostazione predefinita di Adobe Flash
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultPluginsSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultPluginsSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultPopupsSetting
  #### Impostazione predefinita della finestra popup
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se i siti Web possono mostrare finestre popup. È possibile consentirle (“AllowPopups”) o bloccarle (“BlockPopups”) in tutti i siti.

Se non si configura questo criterio, le finestre popup sono bloccate per impostazione predefinita e gli utenti possono modificare tale impostazione.

Mapping delle opzioni del criterio:

* AllowPopups (1) = Consentire a tutti i siti di mostrare i popup

* BlockPopups (2) = Non consentire ad alcun sito di mostrare i popup

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultPopupsSetting
  - Nome Criteri di gruppo: Impostazione predefinita della finestra popup
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultPopupsSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultPopupsSetting
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultWebBluetoothGuardSetting
  #### Controlla l'uso dell'API Web Bluetooth
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se i siti Web possono accedere a dispositivi Bluetooth nelle vicinanze. È possibile bloccare completamente l'accesso o fare in modo che il sito chieda conferma all'utente ogni volta che vuole accedere a un dispositivo Bluetooth.

Se non si configura questo criterio, viene usato il valore predefinito (“AskWebBluetooth”, che indica che ogni volta viene chiesta conferma agli utenti) e gli utenti possono modificarlo.

Mapping delle opzioni del criterio:

* BlockWebBluetooth (2) = Non consentire ad alcun sito di richiedere l'accesso ai dispositivi Bluetooth usando l'API Web Bluetooth

* AskWebBluetooth (3) = Consentire ai siti di chiedere all'utente di autorizzare l'accesso a un dispositivo Bluetooth nelle vicinanze

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultWebBluetoothGuardSetting
  - Nome Criteri di gruppo : Controlla l'uso dell'API Web Bluetooth
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultWebBluetoothGuardSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultWebBluetoothGuardSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultWebUsbGuardSetting
  #### Controlla l'uso dell'API WebUSB
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se i siti Web possono accedere ai dispositivi USB connessi. È possibile bloccare completamente l'accesso o chiedere conferma all'utente ogni volta che un sito Web vuole accedere a dispositivi USB connessi.

È possibile sostituire questo criterio per modelli URL specifici usando i criteri [WebUsbAskForUrls](#webusbaskforurls) e [WebUsbBlockedForUrls](#webusbblockedforurls).

Se non si configura questo criterio, i siti possono chiedere agli utenti se è possibile accedere ai dispositivi USB connessi (“AskWebUsb”) per impostazione predefinita e gli utenti possono modificare questa impostazione.

Mapping delle opzioni del criterio:

* BlockWebUsb (2) = Non consentire ad alcun sito di richiedere l'accesso ai dispositivi USB tramite l'API WebUSB

* AskWebUsb (3) = Consentire ai siti di chiedere all'utente di autorizzare l'accesso a un dispositivo USB connesso

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultWebUsbGuardSetting
  - Nome Criteri di gruppo: Controlla l'uso dell'API WebUSB
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultWebUsbGuardSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultWebUsbGuardSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FileSystemReadAskForUrls
  #### Consente l'accesso in lettura con l'API file system in questi siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Impostando il criterio, è possibile elencare i modelli di URL che specificano i siti in cui è possibile chiedere agli utenti di concedere l'accesso in lettura a file o directory nel file system del sistema operativo host tramite l'API file system.

Se il criterio non viene disattivato, sta a significare che[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting) verrà applicato a tutti i siti, se è impostato. In caso contrario, si applicano le impostazioni personali degli utenti.

I modelli di URL non possono entrare in conflitto con [FileSystemReadBlockedForUrls](#filesystemreadblockedforurls). Nessuno dei criteri ha la precedenza se un URL corrisponde a entrambi.

Per informazioni dettagliate sui modelli di URL validi, vedere https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FileSystemReadAskForUrls
  - Nome Criteri di gruppo: consente l'accesso in lettura con l'API file system in questi siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: FileSystemReadAskForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FileSystemReadBlockedForUrls
  #### Consente l'accesso in lettura tramite l'API file system in questi siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Se viene impostato questo criterio, è possibile elencare i modelli di URL che specificano i siti in cui è possibile chiedere agli utenti di concedere l'accesso in lettura a file o directory nel file system del sistema operativo host tramite l'API file system.

Se non viene impostato questo criterio, [DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting) verrà applicato a tutti i siti, se è impostato. In caso contrario, si applicano le impostazioni personali degli utenti.

I modelli di URL non possono entrare in conflitto con [FileSystemReadAskForUrls](#filesystemreadaskforurls) Nessuno dei criteri ha la precedenza se un URL corrisponde a entrambi.

Per informazioni dettagliate sui modelli di URL validi, vedere https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FileSystemReadBlockedForUrls
  - Nome Criteri di gruppo: consente l'accesso in lettura tramite l'API file system in questi siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: FileSystemReadBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FileSystemWriteAskForUrls
  #### Consente l'accesso in scrittura ai file e alle cartelle in questi siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Se si imposta questo criterio, è possibile elencare i modelli di URL che specificano i siti in cui è possibile chiedere agli utenti di concedere l'accesso in lettura a file o directory nel file system del sistema operativo host.

Se non viene impostato questo criterio, [DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting) verrà applicato a tutti i siti, se è impostato. In caso contrario, si applicano le impostazioni personali degli utenti.

I modelli di URL non possono entrare in conflitto con [FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls). Nessuno dei criteri ha la precedenza se un URL corrisponde a entrambi.

Per informazioni dettagliate sui modelli di URL validi, vedere https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FileSystemWriteAskForUrls
  - Nome Criteri di gruppo: consente l'accesso in scrittura ai file e alle cartelle in questi siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: FileSystemWriteAskForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FileSystemWriteBlockedForUrls
  #### Non consente l'accesso in scrittura ai file e alle cartelle in questi siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Se viene impostato questo criterio, è possibile elencare i modelli di URL che specificano i siti in cui è possibile chiedere agli utenti di concedere l'accesso in scrittura a file o directory nel file system del sistema operativo host.

Se non viene impostato questo criterio, [DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting) verrà applicato a tutti i siti, se è impostato. In caso contrario, si applicano le impostazioni personali degli utenti.

I modelli di URL non possono entrare in conflitto con [FileSystemWriteAskForUrls](#filesystemwriteaskforurls). Nessuno dei criteri ha la precedenza se un URL corrisponde a entrambi.

Per informazioni dettagliate sui modelli di URL validi, vedere https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FileSystemWriteBlockedForUrls
  - Nome Criteri di gruppo: non consente l'accesso in scrittura ai file e alle cartelle in questi siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: FileSystemWriteBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImagesAllowedForUrls
  #### Consente le immagini in questi siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che possono mostrare immagini.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultImagesSetting](#defaultimagessetting) (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImagesAllowedForUrls
  - Nome Criteri di gruppo: Consente le immagini in questi siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ImagesAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImagesAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImagesBlockedForUrls
  #### Blocca le immagini in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non possono mostrare immagini.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultImagesSetting](#defaultimagessetting) (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImagesBlockedForUrls
  - Nome Criteri di gruppo: Blocca le immagini in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ImagesBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImagesBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InsecureContentAllowedForUrls
  #### Consente contenuti non sicuri in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Crea un elenco di modelli URL per specificare i siti che possono mostrare contenuti misti non sicuri (ovvero contenuti HTTP nei siti HTTPS).

Se non si configura questo criterio, i contenuti misti bloccabili verranno bloccati e i contenuti misti eventualmente bloccabili potranno essere aggiornati. Tuttavia, gli utenti potranno impostare eccezioni per consentire i contenuti misti non sicuri per siti specifici.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InsecureContentAllowedForUrls
  - Nome Criteri di gruppo: Consente contenuti non sicuri in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\InsecureContentAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: InsecureContentAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InsecureContentBlockedForUrls
  #### Blocca contenuti non sicuri in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Crea un elenco di modelli URL per specificare i siti che non possono mostrare contenuti misti (ovvero contenuti HTTP nei siti HTTPS) bloccabili (ossia attivi) e per quali contenuti misti eventualmente bloccabili verranno disabilitati gli aggiornamenti.

Se non si configura questo criterio, i contenuti misti bloccabili verranno bloccati e i contenuti misti eventualmente bloccabili potranno essere aggiornati. Tuttavia, gli utenti potranno impostare eccezioni per consentire i contenuti misti non sicuri per siti specifici.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InsecureContentBlockedForUrls
  - Nome Criteri di gruppo: Blocca contenuti non sicuri in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\InsecureContentBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: InsecureContentBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### JavaScriptAllowedForUrls
  #### Consente JavaScript in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che sono autorizzati a eseguire JavaScript.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultJavaScriptSetting](#defaultjavascriptsetting) (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: JavaScriptAllowedForUrls
  - Nome Criteri di gruppo: Consente JavaScript in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\JavaScriptAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: JavaScriptAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### JavaScriptBlockedForUrls
  #### Blocca JavaScript in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non sono autorizzati a eseguire JavaScript.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultJavaScriptSetting](#defaultjavascriptsetting) (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: JavaScriptBlockedForUrls
  - Nome Criteri di gruppo: Blocca JavaScript in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\JavaScriptBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: JavaScriptBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### LegacySameSiteCookieBehaviorEnabled
  #### Abilita l'impostazione di comportamento dei cookie SameSite legacy predefinita
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Consente di ripristinare il comportamento SameSite legacy per tutti i cookie. Se il comportamento legacy viene ripristinato, i cookie che non specificano un attributo SameSite sono trattati come se fossero "SameSite=None", il requisito per i cookie "SameSite=None" di avere l'attributo "Secure" viene rimosso, e la valutazione dello schema viene saltata quando si verifica se due siti siano uguali.

Se il criterio non viene configurato, il comportamento SameSite predefinito dipenderà da altre origini di configurazione per la funzionalità SameSite-by-default feature, la funzionalità Cookies-without-SameSite-must-be-secure e la funzionalità Schemeful Same-Site. Queste funzionalità possono anche essere configurate con un campo di prova o con il flag same-site-by-default-cookies, il flag cookies-without-same-site-must-be-secure, o il flag cookies-without-same-site-must-be-secure in edge://flags.

Mapping delle opzioni del criterio:

* DefaultToLegacySameSiteCookieBehavior (1) = Ripristinare il comportamento SameSite legacy per i cookie in tutti i siti

* DefaultToSameSiteByDefaultCookieBehavior (2) = Usare il comportamento SameSite per impostazione predefinita per i cookie in tutti i siti

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: LegacySameSiteCookieBehaviorEnabled
  - Nome Criteri di gruppo: Abilita l'impostazione di comportamento dei cookie SameSite legacy predefinita
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: LegacySameSiteCookieBehaviorEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: LegacySameSiteCookieBehaviorEnabled
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### LegacySameSiteCookieBehaviorEnabledForDomainList
  #### Ripristina il comportamento SameSite legacy dei cookie in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Per i cookie impostati per i domini che corrispondono a modelli specificati verrà ripristinato il comportamento SameSite legacy.

Se il comportamento legacy viene ripristinato, i cookie che non specificano un attributo SameSite sono trattati come se fossero "SameSite=None", il requisito per i cookie "SameSite=None" di avere l'attributo "Secure" viene rimosso, e la valutazione dello schema viene saltata quando si verifica se due siti siano uguali.

Se non si imposta questo criterio, verrà usato il valore predefinito globale. L'impostazione predefinita globale verrà usata anche per i cookie di domini non coperti dai modelli specificati dall'utente.

Il valore predefinito globale può essere configurato usando il criterio [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled). Se [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled) non è impostato, il valore predefinito globale si basa su altre origini di configurazione.

I modelli elencati in questo criterio vengono trattati come domini, non URL, quindi non è necessario specificare uno schema o una porta.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: LegacySameSiteCookieBehaviorEnabledForDomainList
  - Nome Criteri di gruppo: Ripristina il comportamento SameSite legacy dei cookie in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\1 = "www.example.com"
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\2 = "[*.]example.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: LegacySameSiteCookieBehaviorEnabledForDomainList
  - Valore di esempio
``` xml
<array>
  <string>www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NotificationsAllowedForUrls
  #### Consente le notifiche in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di creare un elenco di modelli di URL per specificare i siti autorizzati a visualizzare le notifiche.

Se non si imposta questo criterio, verrà usato il valore predefinito globale per tutti i siti. Il valore predefinito proviene dai criteri [DefaultNotificationsSetting](#defaultnotificationssetting), se impostato, oppure dalla configurazione personale dell'utente. Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NotificationsAllowedForUrls
  - Nome Criteri di gruppo: Consente le notifiche in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\NotificationsAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NotificationsAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NotificationsBlockedForUrls
  #### Blocca le notifiche in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di creare un elenco di modelli di URL per specificare i siti non autorizzati a visualizzare le notifiche.

Se non si imposta questo criterio, verrà usato il valore predefinito globale per tutti i siti. Il valore predefinito proviene dai criteri [DefaultNotificationsSetting](#defaultnotificationssetting), se impostato, oppure dalla configurazione personale dell'utente. Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NotificationsBlockedForUrls
  - Nome Criteri di gruppo: Blocca le notifiche in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\NotificationsBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NotificationsBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PluginsAllowedForUrls
  #### Consente il plug-in di Adobe Flash in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che possono eseguire il plug-in di Adobe Flash.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultPluginsSetting](#defaultpluginssetting) (se impostato) o la configurazione personale dell'utente.

Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322). Tuttavia, a partire da M85, i modelli con i caratteri jolly "*" e "[*.]" nell'host non sono più supportati per questo criterio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PluginsAllowedForUrls
  - Nome Criteri di gruppo: Consente il plug-in di Adobe Flash in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\PluginsAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\2 = "http://contoso.edu:8080"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PluginsAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PluginsBlockedForUrls
  #### Blocca il plug-in di Adobe Flash in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non possono eseguire Adobe Flash.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultPluginsSetting](#defaultpluginssetting) (se impostato) o la configurazione personale dell'utente.

Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322). Tuttavia, a partire da M85, i modelli con i caratteri jolly "*" e "[*.]" nell'host non sono più supportati per questo criterio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PluginsBlockedForUrls
  - Nome Criteri di gruppo: Blocca il plug-in di Adobe Flash in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\PluginsBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\2 = "http://contoso.edu:8080"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PluginsBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PopupsAllowedForUrls
  #### Consente le finestre popup in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che possono aprire finestre popup.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultPopupsSetting](#defaultpopupssetting) (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PopupsAllowedForUrls
  - Nome Criteri di gruppo: Consente le finestre popup in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\PopupsAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PopupsAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PopupsBlockedForUrls
  #### Blocca le finestre popup in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non possono aprire finestre popup.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultPopupsSetting](#defaultpopupssetting) (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PopupsBlockedForUrls
  - Nome Criteri di gruppo: Blocca le finestre popup in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\PopupsBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PopupsBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RegisteredProtocolHandlers
  #### Registra i gestori di protocollo
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impostare questo criterio (solo consigliato) per registrare un elenco di gestori di protocollo. Questo elenco viene unito a quelli registrati dall'utente ed entrambi sono disponibili per l'uso.

Per registrare un gestore di protocollo:

- Impostare la proprietà del protocollo sullo schema (ad esempio, come "mailto").
- Impostare la proprietà dell'URL sulla proprietà dell’URL dell'applicazione che gestisce lo schema specificato nel campo “protocollo”. Il modello può includere un segnaposto "%s", che verrà sostituito dall'URL gestito.

Gli utenti non possono rimuovere un gestore di protocollo registrato tramite questo criterio. Tuttavia, è possibile installare un nuovo gestore di protocollo predefinito per eseguire l'override dei gestori di protocollo esistenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: no
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RegisteredProtocolHandlers
  - Nome Criteri di gruppo: Registra i gestori di protocollo
  - Percorso Criteri di gruppo (obbligatorio): N/D
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Impostazioni contenuto
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): N/D
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: RegisteredProtocolHandlers
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [
  {
    "default": true, 
    "protocol": "mailto", 
    "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RegisteredProtocolHandlers
  - Valore di esempio
``` xml
<key>RegisteredProtocolHandlers</key>
<array>
  <dict>
    <key>default</key>
    <true/>
    <key>protocol</key>
    <string>mailto</string>
    <key>url</key>
    <string>https://mail.contoso.com/mail/?extsrc=mailto&url=%s</string>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SpotlightExperiencesAndRecommendationsEnabled
  #### Scegli se consentire agli utenti di ricevere immagini di sfondo personalizzate, testo, suggerimenti, notifiche,
e suggerimenti per i servizi Microsoft
  
  
  #### Versioni supportate:
  - In Windows dalla versione 86 o successive

  #### Descrizione
  Scegli se consentire agli utenti di ricevere immagini di sfondo personalizzate, testo, suggerimenti, notifiche e consigli per i servizi Microsoft.

Se si abilita o non si configura questa impostazione, le esperienze in evidenza e i suggerimenti vengono attivati.

Se si disabilita questa impostazione, le esperienze in evidenza e i suggerimenti vengono disattivati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco GP: SpotlightExperiencesAndRecommendationsEnabled
  - Nome GP: scegli se consentire agli utenti di ricevere immagini di sfondo personalizzate, testo, suggerimenti, notifiche e consigli per i servizi Microsoft.
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SpotlightExperiencesAndRecommendationsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebUsbAllowDevicesForUrls
  #### Concede l'accesso a siti specifici per connettersi a dispositivi USB specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di impostare un elenco di URL che specificano quali siti verranno automaticamente autorizzati ad accedere a un dispositivo USB con gli ID prodotto e fornitore specificati. Ogni voce dell'elenco deve contenere sia i dispositivi sia gli URL affinché il criterio sia valido. Ogni elemento nei dispositivi può contenere un campo per ID prodotto e ID fornitore. Gli ID che vengono omessi vengono trattati come caratteri jolly con un'eccezione, e tale eccezione è che un ID prodotto non può essere specificato senza indicare anche un ID fornitore. In caso contrario, il criterio non sarà valido e verrà ignorato.

Il modello di autorizzazione USB sfrutta l'URL del sito richiedente ("URL di richiesta") e l'URL del sito del frame principale ("URL di incorporamento") per concedere l'autorizzazione all'URL di richiesta per accedere al dispositivo USB. L'URL di richiesta potrebbe essere diverso dall'URL di incorporamento quando il sito di richiesta viene caricato in un iframe. Di conseguenza, il campo "urls" può contenere fino a due stringhe di URL delimitate da una virgola per specificare rispettivamente l'URL di richiesta e l'URL di incorporamento. Se viene specificato un solo URL, l'accesso ai dispositivi USB corrispondenti verrà concesso quando l'URL del sito di richiesta corrisponde a tale URL indipendentemente dallo stato di incorporamento. Gli URL nel campo "urls" devono essere URL validi; in caso contrario, il criterio verrà ignorato.

Se questo criterio non viene impostato, per tutti i siti verrà usato il valore predefinito globale del criterio [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) se è stato impostato, altrimenti la configurazione personale dell'utente.

I modelli URL in questo criterio non devono essere in conflitto con quelli configurati tramite [WebUsbBlockedForUrls](#webusbblockedforurls). In caso di conflitto, questo criterio avrà la precedenza rispetto a [WebUsbBlockedForUrls](#webusbblockedforurls) e [WebUsbAskForUrls](#webusbaskforurls).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebUsbAllowDevicesForUrls
  - Nome Criteri di gruppo: Concede l'accesso a siti specifici per connettersi a dispositivi USB specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WebUsbAllowDevicesForUrls
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [
  {
    "devices": [
      {
        "product_id": 5678, 
        "vendor_id": 1234
      }
    ], 
    "urls": [
      "https://contoso.com", 
      "https://fabrikam.com"
    ]
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebUsbAllowDevicesForUrls
  - Valore di esempio
``` xml
<key>WebUsbAllowDevicesForUrls</key>
<array>
  <dict>
    <key>devices</key>
    <array>
      <dict>
        <key>product_id</key>
        <integer>5678</integer>
        <key>vendor_id</key>
        <integer>1234</integer>
      </dict>
    </array>
    <key>urls</key>
    <array>
      <string>https://contoso.com</string>
      <string>https://fabrikam.com</string>
    </array>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebUsbAskForUrls
  #### Consente WebUSB in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che possono chiedere all'utente di accedere a un dispositivo USB.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) (se impostato) o la configurazione personale dell'utente.

I modelli URL definiti in questo criterio non possono essere in conflitto con quelli configurati nel criterio [WebUsbBlockedForUrls](#webusbblockedforurls): non è possibile consentire e bloccare contemporaneamente un URL. Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebUsbAskForUrls
  - Nome Criteri di gruppo: Consente WebUSB in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebUsbAskForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebUsbAskForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebUsbBlockedForUrls
  #### Blocca WebUSB in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non possono chiedere all'utente di autorizzarli ad accedere a un dispositivo USB.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) (se impostato) o la configurazione personale dell'utente.

I modelli URL in questo criterio non possono essere in conflitto con quelli configurati nel criterio [WebUsbAskForUrls](#webusbaskforurls). Non è possibile consentire e bloccare contemporaneamente un URL.  Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebUsbBlockedForUrls
  - Nome Criteri di gruppo: Blocca WebUSB in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni contenuto
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebUsbBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebUsbBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri del provider di ricerca predefinito

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderEnabled
  #### Abilita il provider di ricerca predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di usare un provider di ricerca predefinito.

Se si abilita questo criterio, un utente può cercare un termine digitando nella barra degli indirizzi (a condizione che ciò che viene digitato non sia un URL).

È possibile specificare il provider di ricerca predefinito da usare abilitando il resto dei criteri di ricerca predefiniti. Se tali criteri vengono lasciati vuoti (non configurati) o non vengono configurati correttamente, l'utente può scegliere il provider predefinito.

Se si disabilita questo criterio, l'utente non può eseguire ricerche dalla barra degli indirizzi.

Se si abilita o si disabilita questo criterio, gli utenti non possono modificarlo o sostituirlo.

Se non si configura questo criterio, il provider di ricerca predefinito è abilitato e l'utente può scegliere il provider di ricerca predefinito e impostare l'elenco di provider di ricerca.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX..

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderEnabled
  - Nome Criteri di gruppo: Abilita il provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderEncodings
  #### Codifiche del provider di ricerca predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica le codifiche di caratteri supportate dal provider di ricerca. Le codifiche sono nomi di tabelle codici come UTF-8, GB2312 e ISO-8859-1. Vengono provate nell'ordine indicato.

Questo criterio è facoltativo. Se non configurato, viene usato quello predefinito, cioè UTF-8.

Questo criterio viene applicato solo se si abilitano i criteri [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderEncodings
  - Nome Criteri di gruppo: Codifiche del provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\DefaultSearchProviderEncodings
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended\DefaultSearchProviderEncodings
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\1 = "UTF-8"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\2 = "UTF-16"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\3 = "GB2312"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\4 = "ISO-8859-1"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderEncodings
  - Valore di esempio
``` xml
<array>
  <string>UTF-8</string>
  <string>UTF-16</string>
  <string>GB2312</string>
  <string>ISO-8859-1</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderImageURL
  #### Specifica la funzionalità di ricerca per immagini per il provider di ricerca predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica l'URL per il motore di ricerca utilizzato per la ricerca delle immagini. Le richieste di ricerca vengono inviate tramite il metodo GET.

Questo criterio è facoltativo. Se non si configura, la ricerca delle immagini non è disponibile.

Specificare l'URL di Ricerca immagini Bing come: "{bing:baseURL}images/detail/search?iss=sbiupload&FORM=ANCMS1#enterInsights".

Specificare l'URL di Ricerca immagini Google come: "{google:baseURL}searchbyimage/upload".

Per completare la configurazione della ricerca di immagini, vedere il criterio [DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams).

Questo criterio viene applicato solo se si abilitano i criteri [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderImageURL
  - Nome Criteri di gruppo: Specifica la funzionalità di ricerca per immagini per il provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderImageURL
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://search.contoso.com/searchbyimage/upload"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderImageURL
  - Valore di esempio
``` xml
<string>https://search.contoso.com/searchbyimage/upload</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderImageURLPostParams
  #### Parametri per un URL immagine che usa POST
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita, questo criterio specifica i parametri utilizzati durante l'esecuzione di una ricerca di immagini che usa POST. Il criterio è costituito da coppie di valori/nomi separate da virgole. Se un valore è un parametro del modello, come {imageThumbnail} nell'esempio precedente, viene sostituito con i dati dell'anteprima dell'immagine reale. Questo criterio viene applicato solo se si abilitano i criteri [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

Specificare i parametri Post degli URL di Ricerca immagini Bing come: "imageBin={google:imageThumbnailBase64}".

Specificare i parametri Post degli URL di Ricerca immagini Google come: "encoded_image={google:imageThumbnail},image_url={google:imageURL},sbisrc={google:imageSearchSource},original_width={google:imageOriginalWidth},original_height={google:imageOriginalHeight}".

Se non si imposta questo criterio, le richieste di ricerca delle immagini vengono inviate tramite il metodo GET.

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderImageURLPostParams
  - Nome Criteri di gruppo: Parametri per un URL immagine che usa POST
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderImageURLPostParams
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"content={imageThumbnail},url={imageURL},sbisrc={SearchSource}"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderImageURLPostParams
  - Valore di esempio
``` xml
<string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderKeyword
  #### Parola chiave del provider di ricerca predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica la parola chiave, che è la scelta rapida da tastiera utilizzata nella barra degli indirizzi per attivare la ricerca per questo provider.

Questo criterio è facoltativo. Se non si configura, nessuna parola chiave attiverà il provider di ricerca.

Questo criterio viene applicato solo se si abilitano i criteri [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderKeyword
  - Nome Criteri di gruppo: Parola chiave del provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderKeyword
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"mis"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderKeyword
  - Valore di esempio
``` xml
<string>mis</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderName
  #### Nome del provider di ricerca predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica il nome del provider di ricerca predefinito.

Se si abilita questo criterio, si imposta il nome del provider di ricerca predefinito.

Se non si abilita o si lascia vuoto questo criterio, verrà usato il nome host specificato dall'URL di ricerca.

Il criterio "DefaultSearchProviderName" deve essere impostato su un provider di ricerca crittografato approvato dall'organizzazione che corrisponde al provider di ricerca crittografato impostato in DTBC-0008. Questo criterio viene applicato solo se si abilitano i criteri [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderName
  - Nome Criteri di gruppo: Nome del provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderName
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"My Intranet Search"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderName
  - Valore di esempio
``` xml
<string>My Intranet Search</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderSearchURL
  #### URL del servizio di ricerca del provider di ricerca predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica l'URL per il motore di ricerca utilizzato per una ricerca predefinita. L'URL contiene la stringa "{searchTerms}", che in fase di query viene sostituita dai termini di ricerca dell'utente.

Specificare l'URL di ricerca Bing come:

"{bing:baseURL}search?q={searchTerms}".

Specificare l'URL di ricerca Google come: "{google:baseURL}search?q={searchTerms}&{google:RLZ}{google:originalQueryForSuggestion}{google:assistedQueryStats}{google:searchFieldtrialParameter}{google:searchClient}{google:sourceId}ie={inputEncoding}".

Questo criterio è necessario quando si abilita il criterio [DefaultSearchProviderEnabled](#defaultsearchproviderenabled); in caso contrario, questo criterio viene ignorato.

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderSearchURL
  - Nome Criteri di gruppo: URL del servizio di ricerca del provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderSearchURL
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://search.contoso.com/search?q={searchTerms}"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderSearchURL
  - Valore di esempio
``` xml
<string>https://search.contoso.com/search?q={searchTerms}</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderSuggestURL
  #### URL del provider di ricerca predefinito per i suggerimenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica l'URL per il motore di ricerca utilizzato per fornire suggerimenti di ricerca. L'URL contiene la stringa "{searchTerms}", che in fase di query viene sostituita dal testo immesso dall'utente fino a quel momento.

Questo criterio è facoltativo. Se non si configura, gli utenti non vedranno i suggerimenti di ricerca; visualizzeranno suggerimenti basati sui Preferiti e sulla cronologia esplorazioni.

L'URL di suggerimento Bing può essere specificato come:

"{bing:baseURL}qbox?query={searchTerms}".

L'URL di suggerimento Google può essere specificato come: "{google:baseURL}complete/search?output=chrome&q={searchTerms}".

Questo criterio viene applicato solo se si abilitano i criteri [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato. Se l'utente ha già impostato un provider di ricerca predefinito, non verrà aggiunto all'elenco dei provider di ricerca che l'utente può scegliere. Se si tratta del comportamento desiderato, usare il criterio [ManagedSearchEngines](#managedsearchengines).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderSuggestURL
  - Nome Criteri di gruppo: URL del provider di ricerca predefinito per i suggerimenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DefaultSearchProviderSuggestURL
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://search.contoso.com/suggest?q={searchTerms}"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderSuggestURL
  - Valore di esempio
``` xml
<string>https://search.contoso.com/suggest?q={searchTerms}</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageSearchBox
  #### Configura l’esperienza della nuova scheda di casella di ricerca
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  È possibile configurare la nuova scheda della casella di ricerca per utilizzare "Casella di ricerca (consigliata)" o "Barra degli indirizzi" per cercare su nuove schede. Questo criterio funziona solo se si imposta il motore di ricerca su un valore diverso da Bing configurando i due criteri seguenti: [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl).

 Se si disabilita o non si configura questo criterio e:

- Se il motore di ricerca predefinito nella barra degli indirizzi è  Bing, la nuova scheda usa la casella di ricerca per cercare nelle nuove schede.
- Se la barra degli indirizzi predefinita non è Bing, agli utenti viene offerta una scelta aggiuntiva (usare "barra degli indirizzi") per la ricerca nelle nuove schede.


Se il criterio viene abilitato e impostato su:

- "Casella di ricerca (consigliata)" ("bing"), la nuova pagina della scheda usa la casella di ricerca per cercare nelle nuove schede.
- "Barra degli indirizzi" ("reindirizza"), nella casella di ricerca della nuova scheda viene usata la barra degli indirizzi per eseguire una ricerca nelle nuove schede.

Mapping delle opzioni del criterio:

* bing (bing) = Casella di ricerca (consigliata)

* reindirizza (reindirizza) = Barra degli indirizzi

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageSearchBox
  - Nome Criteri di gruppo: Configura l’esperienza della nuova scheda di casella di ricerca
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Provider di ricerca predefinito
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Provider di ricerca predefinito
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: NewTabPageSearchBox
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"bing"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageSetFeedType
  - Valore di esempio
``` xml
<string>bing</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri per estensioni

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExtensionAllowedTypes
  #### Configura i tipi di estensioni consentiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla i tipi di estensioni che è possibile installare e limita l'accesso al runtime.

Questa impostazione definisce i tipi di estensioni consentiti e gli host con cui possono interagire. Il valore è un elenco di stringhe, ognuna delle quali deve essere una delle seguenti: "extension", "theme", "user_script" e "hosted_app". Per altre informazioni su questi tipi, vedere la documentazione sulle estensioni di Microsoft Edge.

Tenere presente che questo criterio influisce anche sulle estensioni di cui forzare l'installazione usando il criterio [ExtensionInstallForcelist](#extensioninstallforcelist).

Se si abilita questo criterio, vengono installate solo le estensioni che corrispondono a un tipo indicato nell'elenco.

Se non si configura questo criterio, non vengono applicate restrizioni ai tipi di estensioni accettabili.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExtensionAllowedTypes
  - Nome Criteri di gruppo: Configura i tipi di estensioni consentiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Estensioni
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ExtensionAllowedTypes
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExtensionAllowedTypes\1 = "hosted_app"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExtensionAllowedTypes
  - Valore di esempio
``` xml
<array>
  <string>hosted_app</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExtensionInstallAllowlist
  #### Consente l'installazione di estensioni specifiche
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Per impostazione predefinita, tutte le estensioni sono consentite. Tuttavia, se si bloccano tutte le estensioni impostando il criterio "ExtensionInstallBlockList" su "*", gli utenti possono installare solo le estensioni definite in tale criterio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExtensionInstallAllowlist
  - Nome Criteri di gruppo: Consente l'installazione di estensioni specifiche
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Estensioni
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ExtensionInstallAllowlist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\2 = "extension_id2"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExtensionInstallAllowlist
  - Valore di esempio
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExtensionInstallBlocklist
  #### Controlla le estensioni che non è possibile installare
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Elenca estensioni specifiche che gli utenti NON possono installare in Microsoft Edge. Quando si distribuisce questo criterio, le estensioni indicate nell'elenco che sono state precedentemente installate vengono disabilitate e l'utente non può abilitarle. Se si rimuove un elemento dall'elenco di estensioni bloccate, tale estensione viene automaticamente riabilitata ovunque fosse stata già installata.

Utilizzare "*" per bloccare tutte le estensioni che non sono indicate in modo esplicito nell'elenco di estensioni consentite.

Se non si configura questo criterio, gli utenti possono installare qualsiasi estensione in Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExtensionInstallBlocklist
  - Nome Criteri di gruppo: Controlla le estensioni che non è possibile installare
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Estensioni
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ExtensionInstallBlocklist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\2 = "extension_id2"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExtensionInstallBlocklist
  - Valore di esempio
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExtensionInstallForcelist
  #### Controlla le estensioni installate automaticamente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica le estensioni che sono state installate automaticamente, senza l'interazione dell'utente, e che gli utenti non possono disinstallare o disabilitare ("installazione forzata"). Tutte le autorizzazioni richieste dalle estensioni sono concesse in modo implicito, senza l'interazione dell'utente, comprese eventuali autorizzazioni aggiuntive richieste da versioni future delle estensioni. Inoltre, sono concesse le autorizzazioni per le API enterprise.deviceAttributes ed enterprise.platformKeys extension. Queste due API sono disponibili solo per le estensioni installate in modo forzato.

Questo criterio ha la precedenza rispetto a un criterio [ExtensionInstallBlocklist](#extensioninstallblocklist) potenzialmente in conflitto. Quando si rimuove un'estensione dall'elenco di quelle con installazione forzata, l'estensione viene automaticamente disinstallata da Microsoft Edge.

L'installazione forzata si limita alle app e alle estensioni elencate nel sito Web dei componenti aggiuntivi di Microsoft Edge per le istanze diverse da quelle seguenti: istanze di Windows collegate a un dominio di Microsoft Active Directory o istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi e istanze di macOS gestite tramite MDM o collegate a un dominio tramite MCX.

Tenere presente che gli utenti possono modificare il codice sorgente di qualsiasi estensione usando gli Strumenti di sviluppo, rendendo l'estensione potenzialmente disfunzionale. Se è un problema, impostare il criterio [DeveloperToolsAvailability](#developertoolsavailability).

Per aggiungere un'estensione all'elenco, usare il formato seguente:

[extensionID];[updateURL]

- extensionID: la stringa di 32 lettere disponibile in edge://extensions in modalità sviluppatore.

- updateURL (facoltativo): l'indirizzo del documento XML del manifesto di aggiornamento per l'app o l'estensione, come descritto in [https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043). Se si vuole installare un'estensione da Chrome Web Store, specificare l'URL di aggiornamento di Chrome Web Store, https://clients2.google.com/service/update2/crx. Tenere presente che l'URL di aggiornamento impostato in questo criterio viene usato solo per l'installazione iniziale; gli aggiornamenti successivi dell'estensione usano l'URL di aggiornamento indicato nel manifesto dell'estensione. Se non si imposta updateURL, l'estensione verrà considerata ospitata in Microsoft Store e verrà usato l'URL di aggiornamento seguente (https://edge.microsoft.com/extensionwebstorebase/v1/crx).

Ad esempio, gggmmkjegpiggikcnhidnjjhmicpibll;https://edge.microsoft.com/extensionwebstorebase/v1/crx installa l'app di Microsoft Online dall'URL di aggiornamento di Microsoft Store. Per altre informazioni sull'hosting delle estensioni, vedere: [https://go.microsoft.com/fwlink/?linkid=2095044](https://go.microsoft.com/fwlink/?linkid=2095044).

Se non si configura questo criterio, le estensioni non vengono installate automaticamente e gli utenti possono disinstallare qualsiasi estensione in Microsoft Edge.

Tenere presente che questo criterio non si applica alla modalità InPrivate.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExtensionInstallForcelist
  - Nome Criteri di gruppo: Controlla le estensioni installate automaticamente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Estensioni
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ExtensionInstallForcelist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\1 = "gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\2 = "abcdefghijklmnopabcdefghijklmnop"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExtensionInstallForcelist
  - Valore di esempio
``` xml
<array>
  <string>gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx</string>
  <string>abcdefghijklmnopabcdefghijklmnop</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExtensionInstallSources
  #### Configura le origini di installazione di script utente ed estensione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce gli URL che consentono di installare estensioni e temi.

Per impostazione predefinita, gli utenti devono scaricare un file *.crx per ogni estensione o script che vogliono installare, per poi trascinarlo nella pagina delle impostazioni di Microsoft Edge. Questo criterio consente a URL specifici di installare l'estensione o lo script per l'utente.

Ogni voce di questo elenco è uno schema di corrispondenza per lo stile dell'estensione (vedere [https://go.microsoft.com/fwlink/?linkid=2095039](https://go.microsoft.com/fwlink/?linkid=2095039)). Gli utenti possono installare facilmente gli elementi da qualsiasi URL che corrisponda a una voce di questo elenco. Il percorso del file *.crx e la pagina da cui viene avviato il download (ossia, il referrer) devono essere autorizzati da questi schemi.

Il criterio [ExtensionInstallBlocklist](#extensioninstallblocklist) ha la precedenza rispetto a questo criterio. Le estensioni che si trovano nell'elenco di elementi bloccati non verranno installate, anche se provengono da un sito indicato in questo elenco.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExtensionInstallSources
  - Nome Criteri di gruppo: Configura le origini di installazione di script utente ed estensione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Estensioni
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ExtensionInstallSources
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallSources\1 = "https://corp.contoso.com/*"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExtensionInstallSources
  - Valore di esempio
``` xml
<array>
  <string>https://corp.contoso.com/*</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExtensionSettings
  #### Configura le impostazioni di gestione delle estensioni
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura le impostazioni di gestione delle estensioni per Microsoft Edge.

Questo criterio controlla più impostazioni, incluse quelle controllate dai criteri correlati all'estensione esistenti. Questo criterio sostituisce i criteri legacy se sono entrambi impostati.

Questo criterio esegue il mapping di un ID estensione o di un URL di aggiornamento alla relativa configurazione. Con un ID estensione, la configurazione viene applicata solo all'estensione specificata. Impostare una configurazione predefinita per l'ID speciale "*", da applicare a tutte le estensioni non indicate specificamente in questo criterio. Con un URL di aggiornamento, la configurazione viene applicata a tutte le estensioni con l'esatto URL di aggiornamento indicato nel manifesto di questa estensione, come descritto in [https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExtensionSettings
  - Nome Criteri di gruppo: Configura le impostazioni di gestione delle estensioni
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Estensioni
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ExtensionSettings
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {
  "*": {
    "allowed_types": [
      "hosted_app"
    ], 
    "blocked_install_message": "Custom error message.", 
    "blocked_permissions": [
      "downloads", 
      "bookmarks"
    ], 
    "install_sources": [
      "https://company-intranet/apps"
    ], 
    "installation_mode": "blocked", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ]
  }, 
  "abcdefghijklmnopabcdefghijklmnop": {
    "blocked_permissions": [
      "history"
    ], 
    "installation_mode": "allowed", 
    "minimum_version_required": "1.0.1"
  }, 
  "bcdefghijklmnopabcdefghijklmnopa": {
    "allowed_permissions": [
      "downloads"
    ], 
    "installation_mode": "force_installed", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ], 
    "update_url": "https://contoso.com/update_url"
  }, 
  "cdefghijklmnopabcdefghijklmnopab": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "fghijklmnopabcdefghijklmnopabcde": {
    "blocked_install_message": "Custom removal message.", 
    "installation_mode": "removed"
  }, 
  "update_url:https://www.contoso.com/update.xml": {
    "allowed_permissions": [
      "downloads"
    ], 
    "blocked_permissions": [
      "wallpaper"
    ], 
    "installation_mode": "allowed"
  }
}
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExtensionSettings
  - Valore di esempio
``` xml
<key>ExtensionSettings</key>
<dict>
  <key>*</key>
  <dict>
    <key>allowed_types</key>
    <array>
      <string>hosted_app</string>
    </array>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>blocked_permissions</key>
    <array>
      <string>downloads</string>
      <string>bookmarks</string>
    </array>
    <key>install_sources</key>
    <array>
      <string>https://company-intranet/apps</string>
    </array>
    <key>installation_mode</key>
    <string>blocked</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
  </dict>
  <key>abcdefghijklmnopabcdefghijklmnop</key>
  <dict>
    <key>blocked_permissions</key>
    <array>
      <string>history</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
    <key>minimum_version_required</key>
    <string>1.0.1</string>
  </dict>
  <key>bcdefghijklmnopabcdefghijklmnopa</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>installation_mode</key>
    <string>force_installed</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
    <key>update_url</key>
    <string>https://contoso.com/update_url</string>
  </dict>
  <key>cdefghijklmnopabcdefghijklmnopab</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>fghijklmnopabcdefghijklmnopabcde</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom removal message.</string>
    <key>installation_mode</key>
    <string>removed</string>
  </dict>
  <key>update_url:https://www.contoso.com/update.xml</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>blocked_permissions</key>
    <array>
      <string>wallpaper</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
  </dict>
</dict>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di autenticazione HTTP

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowCrossOriginAuthPrompt
  #### Consentire gli avvisi di autenticazione HTTP con origini multiple
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se le immagini di terza parte di una pagina possono mostrare gli avvisi di autenticazione.

In genere, questo criterio è disabilitato come protezione da phishing. Se il criterio non viene configurato, sarà disabilitato e le immagini di terza parte non potranno mostrare gli avvisi di autenticazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowCrossOriginAuthPrompt
  - Nome GP: Consentire gli avvisi di autenticazione HTTP con origine multipla
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Autenticazione HTTP
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AllowCrossOriginAuthPrompt
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowCrossOriginAuthPrompt
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AuthNegotiateDelegateAllowlist
  #### Specifica un elenco di server ai quali Microsoft Edge può delegare le credenziali utente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura l'elenco di server ai quali Microsoft Edge può delegare.

Separare più nomi di server con virgole. I caratteri jolly (*) sono consentiti.

Se non si configura questo criterio, Microsoft Edge non delegherà le credenziali utente anche se un server viene rilevato come Intranet.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AuthNegotiateDelegateAllowlist
  - Nome Criteri di gruppo: Specifica un elenco di server ai quali Microsoft Edge può delegare le credenziali utente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Autenticazione HTTP
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AuthNegotiateDelegateAllowlist
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"contoso.com"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AuthNegotiateDelegateAllowlist
  - Valore di esempio
``` xml
<string>contoso.com</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AuthSchemes
  #### Schemi di autenticazione supportati
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica gli schemi di autenticazione HTTP supportati.

È possibile configurare il criterio usando questi valori: "basic", "digest", "ntlm" e "negotiate". Separare più valori con virgole.

Se non si configura questo criterio, vengono usati i quattro schemi.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AuthSchemes
  - Nome Criteri di gruppo: Schemi di autenticazione supportati
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Autenticazione HTTP
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AuthSchemes
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"basic,digest,ntlm,negotiate"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AuthSchemes
  - Valore di esempio
``` xml
<string>basic,digest,ntlm,negotiate</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AuthServerAllowlist
  #### Configura l'elenco di server di autenticazione consentiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica i server da abilitare per l'autenticazione integrata. L'autenticazione integrata è abilitata solo quando Microsoft Edge riceve un test di autenticazione da un proxy o da un server in questo elenco.

Separare più nomi di server con virgole. I caratteri jolly (*) sono consentiti.

Se non si configura questo criterio, Microsoft Edge prova a rilevare se un server si trova nella Intranet: solo dopo risponderà alle richieste IWA. Se il server si trova su Internet, le richieste IWA da tale server vengono ignorate da Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AuthServerAllowlist
  - Nome Criteri di gruppo: Configura l'elenco di server di autenticazione consentiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Autenticazione HTTP
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AuthServerAllowlist
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"*contoso.com,contoso.com"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AuthServerAllowlist
  - Valore di esempio
``` xml
<string>*contoso.com,contoso.com</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DisableAuthNegotiateCnameLookup
  #### Disabilita la ricerca di CNAME durante la negoziazione dell'autenticazione Kerberos
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Determina se il nome SPN Kerberos generato è basato sul nome DNS canonico (CNAME) o sul nome originale immesso.

Se si abilita questo criterio, la ricerca di CNAME viene ignorata e viene usato il nome del server (come immesso).

Se si disabilita o non si configura questo criterio, viene usato il nome canonico del server.  Ciò viene determinato attraverso la ricerca di CNAME.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DisableAuthNegotiateCnameLookup
  - Nome Criteri di gruppo: Disabilita la ricerca di CNAME durante la negoziazione dell'autenticazione Kerberos
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Autenticazione HTTP
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DisableAuthNegotiateCnameLookup
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DisableAuthNegotiateCnameLookup
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnableAuthNegotiatePort
  #### Include una porta non-standard nell'SPN di Kerberos
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se il nome SPN Kerberos generato deve includere una porta non standard.

Se si abilita questo criterio e un utente include una porta non standard (una porta diversa da 80 o 443) in un URL, tale porta è inclusa nel nome SPN Kerberos generato.

Se si disabilita o non si configura questo criterio, il nome SPN Kerberos generato non includerà una porta in nessun caso.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnableAuthNegotiatePort
  - Nome Criteri di gruppo: Include una porta non-standard nell'SPN di Kerberos
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Autenticazione HTTP
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnableAuthNegotiatePort
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnableAuthNegotiatePort
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NtlmV2Enabled
  #### Controlla se è abilitata l'autenticazione NTLMv2
  
  
  #### Versioni supportate:
  - In macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se NTLMv2 è abilitato.

Tutte le versioni recenti di server Samba e Windows supportano NTLMv2. È consigliabile disabilitare NTLMv2 solo per risolvere i problemi relativi alla compatibilità con le versioni precedenti poiché riduce la sicurezza dell'autenticazione.

Se non si configura questo criterio, NTLMv2 è abilitato per impostazione predefinita.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  

  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NtlmV2Enabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri delle impostazioni della modalità tutto schermo

  [Torna all'inizio](#microsoft-edge---policies)

  ### KioskDeleteDownloadsOnExit
  #### Eliminare i file scaricati durante la sessione a tutto schermo quando Microsoft Edge si chiude
  
  
  #### Versioni supportate:
  - In Windows dalla versione 87 o successive

  #### Descrizione
  Nota: questo criterio è supportato solo quando Edge viene eseguito con il parametro da riga di comando "--edge-kiosk-type".

Se il criterio viene abilitato, i file scaricati durante le sessioni a tutto schermo sono cancellati ogni volta che Microsoft Edge viene chiuso.

Se il criterio viene disabilitato o non viene configurato, i file scaricati durante le sessioni a tutto schermo non sono cancellati ogni volta che Microsoft Edge viene chiuso. 

Per i dettagli della configurazione della modalità tutto schermo, vedere [https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco GP: KioskDeleteDownloadsOnExit
  - Nome GP: Eliminare i file scaricati durante le sessioni a tutto schermo quando Microsoft Edge si chiude
  - Percorso GP (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni modalità tutto schermo
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: KioskDeleteDownloadsOnExit
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di messaggistica nativa

  [Torna all'inizio](#microsoft-edge---policies)

  ### NativeMessagingAllowlist
  #### Controlla quali host di messaggistica nativa possono usare gli utenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Elenca host di messaggistica nativa specifici che gli utenti possono usare in Microsoft Edge.

Per impostazione predefinita, tutti gli host di messaggistica nativa sono consentiti. Se si imposta il criterio [NativeMessagingBlocklist](#nativemessagingblocklist) su *, tutti gli host di messaggistica nativa vengono bloccati e solo quelli elencati in tale criterio vengono caricati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NativeMessagingAllowlist
  - Nome Criteri di gruppo: Controlla quali host di messaggistica nativa possono usare gli utenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Messaggistica nativa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\NativeMessagingAllowlist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\2 = "com.native.messaging.host.name2"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NativeMessagingAllowlist
  - Valore di esempio
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NativeMessagingBlocklist
  #### Configura l'elenco di indirizzi bloccati per la messaggistica nativa
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica gli host di messaggistica nativa che non devono essere usati.

Utilizzare "*" per bloccare tutti gli host di messaggistica nativa se non sono indicati esplicitamente nell'elenco di quelli consentiti.

Se non si configura questo criterio, Microsoft Edge caricherà tutti gli host di messaggistica nativa installati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NativeMessagingBlocklist
  - Nome Criteri di gruppo: Configura l'elenco di indirizzi bloccati per la messaggistica nativa
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Messaggistica nativa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\NativeMessagingBlocklist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\2 = "com.native.messaging.host.name2"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NativeMessagingBlocklist
  - Valore di esempio
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NativeMessagingUserLevelHosts
  #### Consente gli host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministrazione)
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente l'installazione a livello di utente degli host di messaggistica nativa.

Se si disabilita questo criterio, Microsoft Edge userà solo gli host di messaggistica nativa installati a livello di sistema.

Per impostazione predefinita, se non si configura questo criterio, Microsoft Edge consentirà l'utilizzo degli host di messaggistica nativa a livello di utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NativeMessagingUserLevelHosts
  - Nome Criteri di gruppo: Consente gli host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministrazione)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Messaggistica nativa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NativeMessagingUserLevelHosts
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NativeMessagingUserLevelHosts
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di gestione e protezione delle password

  [Torna all'inizio](#microsoft-edge---policies)

  ### PasswordManagerEnabled
  #### Abilita il salvataggio delle password con lo strumento di gestione delle password
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente a Microsoft Edge di salvare le password utente.

Se si abilita questo criterio, gli utenti possono salvare le password in Microsoft Edge. La volta successiva che visitano un sito, Microsoft Edge immetterà la password automaticamente.

Se si disabilita questo criterio, gli utenti non possono salvare le nuove password, ma possono continuare a usare quelle salvate in precedenza.

Se si abilita o si disabilita questo criterio, gli utenti non possono modificarlo o sostituirlo in Microsoft Edge. Se non si configura questo criterio, gli utenti possono salvare le password, oltre a disattivare questa funzionalità.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PasswordManagerEnabled
  - Nome Criteri di gruppo: Abilita il salvataggio delle password con lo strumento di gestione delle password
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Gestione e protezione delle password
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Gestione e protezione delle password
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: PasswordManagerEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PasswordManagerEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PasswordMonitorAllowed
  #### Consenti agli utenti di ricevere avvisi se le loro password non sono sicure
  
  
  #### Versioni supportate:
  - In Windows dalla versione 85 o successive

  #### Descrizione
  Consenti a Microsoft Edge di monitorare le password utente.

Se si abilita questo criterio e si acconsente l’abilitazione, l'utente riceverà un avviso se una o più password archiviate in Microsoft Edge risultano non sicure. Microsoft Edge mostrerà un avviso e le informazioni saranno disponibili anche in Impostazioni > Password > Monitoraggio password.

Se si disabilita questo criterio, agli utenti non verrà chiesta l'autorizzazione per abilitare questa funzionalità. Le loro password non verranno digitalizzate e non riceveranno nessun avviso.

Se i criteri sono abilitati o non vengono configurati, gli utenti possono attivare o disattivare questa funzionalità.

Per altre informazioni sul modo in cui Microsoft Edge trova password poco sicure, vedere [https://go.microsoft.com/fwlink/?linkid=2133833](https://go.microsoft.com/fwlink/?linkid=2133833)

Istruzioni aggiuntive:

Questo criterio può essere impostato sia come consigliato sia come obbligatorio, ma con un callout importante.

Obbligatorio abilitato: dato che il consenso di un utente è una condizione preliminare per l'abilitazione di questa funzionalità per un determinato utente, questo criterio non dispone di un'impostazione obbligatoria abilitata. Se il criterio è impostato su obbligatorio abilitato, l'interfaccia utente in impostazioni non viene modificata e il messaggio di errore seguente viene visualizzato in edge://policy

Messaggio di errore di esempio: "Questo valore dei criteri viene ignorato perché il Monitoraggio password richiede il consenso del singolo utente affinché venga attivato. È possibile chiedere agli utenti dell'organizzazione di accedere a Impostazioni > Profilo > Password e attivare la funzionalità".

Consigliato abilitato: se il criterio è impostato su consigliato abilitato, l'interfaccia utente in impostazioni resterà in "disattivato". Tuttavia, accanto all'immagine verrà visualizzata un'icona a forma di valigetta, con la seguente descrizione visualizzata al passaggio del mouse: "l'organizzazione consiglia un valore specifico per questa impostazione ed è stato scelto un valore diverso".

Disabilitato e consigliato disabilitati: entrambe gli stati funzioneranno normalmente, con la consueta didascalia mostrata agli utenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PasswordMonitorAllowed
  - Nome Criteri di gruppo: consenti agli utenti di ricevere avvisi se le loro password non sono sicure
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Gestione e protezione delle password
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Gestione e protezione delle password
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: PasswordMonitorAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PasswordProtectionChangePasswordURL
  #### Configura l'URL di modifica della password
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura l'URL di modifica della password (solo schemi HTTP e HTTPS).

Il servizio della password di protezione reindirizza gli utenti a questo URL per modificare la password dopo aver visualizzato un avviso nel browser.

Se si abilita questo criterio, il servizio della password di protezione reindirizza gli utenti a questo URL per modificare la password.

Se si disabilita o non si configura questo criterio, il servizio della password di protezione non reindirizza gli utenti a un URL per la modifica della password.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PasswordProtectionChangePasswordURL
  - Nome Criteri di gruppo: Configura l'URL di modifica della password
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Gestione e protezione delle password
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PasswordProtectionChangePasswordURL
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://contoso.com/change_password.html"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PasswordProtectionChangePasswordURL
  - Valore di esempio
``` xml
<string>https://contoso.com/change_password.html</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PasswordProtectionLoginURLs
  #### Configura l'elenco di URL di accesso aziendale dove il servizio della password di protezione dovrebbe acquisire hash salati di una password
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura l'elenco di URL di accesso aziendali (solo schemi HTTP e HTTPS) dove Microsoft Edge deve acquisire gli hash salati delle password e usarli per il rilevamento del riutilizzo delle password.

Se si abilita questo criterio, il servizio della password di protezione acquisisce le impronte digitali delle password negli URL definiti.

Se si disabilita o non si configura questo criterio, non vengono acquisite le impronte digitali della password.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PasswordProtectionLoginURLs
  - Nome Criteri di gruppo: Configura l'elenco di URL di accesso aziendale dove il servizio della password di protezione dovrebbe acquisire gli hash salati di una password
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Gestione e protezione delle password
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\PasswordProtectionLoginURLs
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\1 = "https://contoso.com/login.html"
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\2 = "https://login.contoso.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PasswordProtectionLoginURLs
  - Valore di esempio
``` xml
<array>
  <string>https://contoso.com/login.html</string>
  <string>https://login.contoso.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PasswordProtectionWarningTrigger
  #### Configura il trigger di avviso per la password di protezione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di controllare quando attivare l'avviso della password di protezione. La password di protezione avvisa gli utenti quando riutilizzano la password protetta in siti potenzialmente sospetti.

È possibile usare i criteri [PasswordProtectionLoginURLs](#passwordprotectionloginurls) e [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl) per configurare le password da proteggere.

Eccezioni: le password per i siti indicati in [PasswordProtectionLoginURLs](#passwordprotectionloginurls) e [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl), oltre ai siti indicati in [SmartScreenAllowListDomains](#smartscreenallowlistdomains), non attiveranno un avviso della password di protezione.

Impostare su "PasswordProtectionWarningOff" per non mostrare gli avvisi della password di protezione.

Impostare su "PasswordProtectionWarningOnPasswordReuse" per mostrare gli avvisi della password di protezione quando l'utente riutilizza la password protetta in un sito indicato nell'elenco di quelli non consentiti.

Se si disabilita o non si configura questo criterio, il trigger di avviso non viene mostrato.

Mapping delle opzioni del criterio:

* PasswordProtectionWarningOff (0) = Avviso della password di protezione disattivato

* PasswordProtectionWarningOnPasswordReuse (1) = Avviso della password di protezione attivato dal riutilizzo della password 

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PasswordProtectionWarningTrigger
  - Nome Criteri di gruppo: Configura il trigger di avviso per la password di protezione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Gestione e protezione delle password
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PasswordProtectionWarningTrigger
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PasswordProtectionWarningTrigger
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di stampa

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultPrinterSelection
  #### Regole di selezione della stampante predefinita
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Sostituisce le regole di selezione della stampare predefinita di Microsoft Edge. Questo criterio determina le regole di selezione della stampante predefinita in Microsoft Edge, che si verifica la prima volta che un utente prova a stampare una pagina.

Quando questo criterio è impostato, Microsoft Edge tenta di trovare una stampante che corrisponda a tutti gli attributi specificati e la usa come stampante predefinita. Se sono presenti più stampanti che soddisfano i criteri specificati, viene usata la prima stampante corrispondente.

Se non si configura questo criterio o non vengono trovate stampanti corrispondenti entro l'intervallo di timeout, per impostazione predefinita viene impostata la stampante PDF integrata o non viene impostata alcuna stampante (se la stampante PDF non è disponibile).

Il valore viene analizzato come oggetto JSON, conforme allo schema seguente: { "type": "object", "properties": { "idPattern": { "description": "Regular expression to match printer id.", "type": "string" }, "namePattern": { "description": "Regular expression to match printer display name.", "type": "string" } } }

Se si omette un campo significa che tutti i valori corrispondono; ad esempio, se non si specifica la connettività, l'anteprima di stampa inizia a individuare tutti i tipi di stampanti locali. Gli schemi di espressioni regolari devono seguire la sintassi JavaScript RegExp e per le corrispondenze viene fatta distinzione tra maiuscole e minuscole.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultPrinterSelection
  - Nome Criteri di gruppo: Regole di selezione della stampante predefinita
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Stampa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultPrinterSelection
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"{ \"idPattern\": \".*public\", \"namePattern\": \".*Color\" }"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultPrinterSelection
  - Valore di esempio
``` xml
<string>{ "idPattern": ".*public", "namePattern": ".*Color" }</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PrintHeaderFooter
  #### Stampa intestazioni e piè di pagina
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Forza l'attivazione o la disattivazione di "intestazioni e piè di pagina" nella finestra di dialogo di stampa.

Se non si configura questo criterio, gli utenti possono decidere se stampare intestazioni e piè di pagina.

Se si disabilita questo criterio, gli utenti non possono stampare intestazioni e piè di pagina.

Se si abilita questo criterio, gli utenti stampano sempre intestazioni e piè di pagina.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PrintHeaderFooter
  - Nome Criteri di gruppo: Stampa intestazioni e piè di pagina
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Stampa
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Stampa
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: PrintHeaderFooter
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PrintHeaderFooter
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PrintPreviewUseSystemDefaultPrinter
  #### Imposta la stampante predefinita del sistema come stampante predefinita
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Indica a Microsoft Edge di usare la stampante predefinita di sistema come scelta predefinita nell'anteprima di stampa, anziché la stampante usata di recente.

Se si disabilita o non si configura questo criterio, l'anteprima di stampa utilizza la stampante usata di recente come scelta di destinazione predefinita.

Se si abilita questo criterio, l'anteprima di stampa utilizza la stampante predefinita del sistema operativo come scelta di destinazione predefinita.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PrintPreviewUseSystemDefaultPrinter
  - Nome Criteri di gruppo: Imposta la stampante predefinita del sistema come stampante predefinita
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Stampa
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Stampa
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: PrintPreviewUseSystemDefaultPrinter
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PrintPreviewUseSystemDefaultPrinter
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PrintingEnabled
  #### Abilita la stampa
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente la stampa in Microsoft Edge e impedisce agli utenti di modificare questa impostazione.

Se si abilita o non si configura questo criterio, gli utenti possono stampare.

Se si disabilita questo criterio, gli utenti non possono stampare da Microsoft Edge. La stampa viene disabilitata nel menu con la chiave inglese, nelle estensioni, nelle applicazioni JavaScript e così via. Gli utenti possono comunque stampare dai plug-in che ignorano Microsoft Edge durante la stampa. Ad esempio, alcune applicazioni di Adobe Flash hanno l'opzione di stampa nel menu di scelta rapida, che non è interessato da questo criterio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PrintingEnabled
  - Nome Criteri di gruppo: Abilita la stampa
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Stampa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PrintingEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PrintingEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PrintingPaperSizeDefault
  #### Dimensioni della pagina di stampa predefinite
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Sostituisce le dimensioni della pagina di stampa predefinite.

il nome deve contenere uno dei formati elencati o “personalizzato” se necessario, se non è presente nell'elenco. Se viene fornito il valore “personalizzato”, la proprietà custom_size deve essere specificata. Descrive l'altezza e la larghezza desiderate nei micrometri. In caso contrario, la proprietà custom_size non deve essere specificata. Il criterio che viola queste regole verrà ignorato.

Se le dimensioni della pagina non sono disponibili nella stampante scelta dall'utente, questi criterio verrà ignorato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PrintingPaperSizeDefault
  - Nome Criteri di gruppo: dimensioni della pagina di stampa predefinite
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Stampa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PrintingPaperSizeDefault
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {
  "custom_size": {
    "height": 297000, 
    "width": 210000
  }, 
  "name": "custom"
}
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: PrintingPaperSizeDefault
  - Valore di esempio
``` xml
<key>PrintingPaperSizeDefault</key>
<dict>
  <key>custom_size</key>
  <dict>
    <key>height</key>
    <integer>297000</integer>
    <key>width</key>
    <integer>210000</integer>
  </dict>
  <key>name</key>
  <string>custom</string>
</dict>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### UseSystemPrintDialog
  #### Stampa usando la finestra di dialogo della stampante di sistema
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Mostra la finestra di dialogo di stampa del sistema, anziché l'anteprima di stampa.

Se si abilita questo criterio, Microsoft Edge apre la finestra di dialogo di stampa del sistema, anziché l'anteprima di stampa integrata, quando un utente stampa una pagina.

Se si disabilita o non si configura questo criterio, i comandi di stampa attivano la schermata dell'anteprima di stampa di Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: UseSystemPrintDialog
  - Nome Criteri di gruppo: Stampa usando la finestra di dialogo della stampante di sistema
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Stampa
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: UseSystemPrintDialog
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: UseSystemPrintDialog
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri dei server proxy

  [Torna all'inizio](#microsoft-edge---policies)

  ### ProxyBypassList
  #### Configura le regole di esclusione di proxy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di host per i quali Microsoft Edge ignora qualsiasi proxy.

Questo criterio viene applicato solo se è stato selezionato "Usa server proxy fissi" nel criterio [ProxyMode](#proxymode). Se è stata selezionata un'altra modalità di configurazione dei criteri proxy, non abilitare o configurare questo criterio.

Se si abilita questo criterio, è possibile creare un elenco di host per i quali Microsoft Edge non usa un proxy.

Se non si configura questo criterio, non viene creato alcun elenco di host per i quali Microsoft Edge ignora un proxy. Se è stato specificato un altro metodo per l'impostazione dei criteri proxy, non configurare questo criterio.

Per esempi più dettagliati, passare a [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ProxyBypassList
  - Nome Criteri di gruppo: Configura le regole di esclusione di proxy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Server proxy
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ProxyBypassList
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://www.contoso.com, https://www.fabrikam.com"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ProxyBypassList
  - Valore di esempio
``` xml
<string>https://www.contoso.com, https://www.fabrikam.com</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ProxyMode
  #### Configura le impostazioni del server proxy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica le impostazioni del server proxy usate da Microsoft Edge. Se si abilita questo criterio, gli utenti non possono modificare le impostazioni proxy.

Se si sceglie di non usare mai un server proxy e di connettersi sempre direttamente, tutte le altre opzioni vengono ignorate.

Se si sceglie di usare le impostazioni del proxy di sistema, tutte le altre opzioni vengono ignorate.

Se si sceglie di rilevare automaticamente il server proxy, tutte le altre opzioni vengono ignorate.

Se si sceglie la modalità proxy server fisso, è possibile specificare altre opzioni in [ProxyServer](#proxyserver) e nell'elenco con valori delimitati da virgole di regole di esclusione di proxy.

Se si sceglie di usare uno script proxy PAC, è necessario specificare l'URL per lo script in "URL di un file PAC del proxy".

Per esempi dettagliati, passare a [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936).

Se si abilita questo criterio, Microsoft Edge ignorerà tutte le opzioni correlate al proxy specificate nella riga di comando.

Se non si configura questo criterio, gli utenti possono scegliere impostazioni del proxy personalizzate.

Mapping delle opzioni del criterio:

* ProxyDisabled (direct) = Non usare mai un proxy

* ProxyAutoDetect (auto_detect) = Rilevare automaticamente le impostazioni proxy

* ProxyPacScript (pac_script) = Usare uno script proxy PAC

* ProxyFixedServers (fixed_servers) = Usare server proxy fissi

* ProxyUseSystem (system) = Usare le impostazioni del proxy di sistema

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ProxyMode
  - Nome Criteri di gruppo: Configura le impostazioni del server proxy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Server proxy
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ProxyMode
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"direct"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ProxyMode
  - Valore di esempio
``` xml
<string>direct</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ProxyPacUrl
  #### Imposta l'URL del file .pac del proxy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica l'URL di un file di configurazione automatica del proxy (PAC).

Questo criterio viene applicato solo se è stato selezionato "Usa uno script del proxy con estensione pac" nel criterio [ProxyMode](#proxymode). Se è stata selezionata un'altra modalità di configurazione dei criteri proxy, non abilitare o configurare questo criterio.

Se si abilita questo criterio, è possibile specificare l'URL per un file PAC, che definisce in che modo il browser sceglie automaticamente il server proxy appropriato per il recupero di un particolare sito Web.

Se si disabilita o non si configura questo criterio, non viene specificato alcun file PAC. Se è stato specificato un altro metodo per l'impostazione dei criteri proxy, non configurare questo criterio.

Per esempi dettagliati, vedere [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ProxyPacUrl
  - Nome Criteri di gruppo: Imposta l'URL del file .pac del proxy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Server proxy
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ProxyPacUrl
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://internal.contoso.com/example.pac"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ProxyPacUrl
  - Valore di esempio
``` xml
<string>https://internal.contoso.com/example.pac</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ProxyServer
  #### Configura l'indirizzo o l'URL del server proxy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica l'URL del server proxy.

Questo criterio viene applicato solo se è stato selezionato "Usa server proxy fissi" nel criterio [ProxyMode](#proxymode). Se è stata selezionata un'altra modalità di configurazione dei criteri proxy, non abilitare o configurare questo criterio.

Se si abilita questo criterio, il server proxy configurato con questo criterio verrà usato per tutti gli URL.

Se si disabilita o non si configura questo criterio, gli utenti possono scegliere impostazioni del proxy personalizzate in questa modalità di proxy. Se è stato specificato un altro metodo per l'impostazione dei criteri proxy, non configurare questo criterio.

Per altre opzioni ed esempi dettagliati, vedere [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ProxyServer
  - Nome Criteri di gruppo: Configura l'indirizzo o l'URL del server proxy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Server proxy
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ProxyServer
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"123.123.123.123:8080"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ProxyServer
  - Valore di esempio
``` xml
<string>123.123.123.123:8080</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ProxySettings
  #### Impostazioni proxy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura le impostazioni del proxy per Microsoft Edge.

Se si abilita questo criterio, Microsoft Edge ignora tutte le opzioni correlate al proxy specificate nella riga di comando.

Se non si configura questo criterio, gli utenti possono scegliere impostazioni del proxy personalizzate.

Questo criterio sostituisce i singoli criteri seguenti:

[ProxyMode](#proxymode)
[ProxyPacUrl](#proxypacurl)
[ProxyServer](#proxyserver)
[ProxyBypassList](#proxybypasslist)

Il campo ProxyMode consente di specificare il server proxy utilizzato da Microsoft Edge e impedisce agli utenti di modificare le impostazioni proxy.

Il campo ProxyPacUrl è un URL a un file .pac del proxy.

Il campo ProxyServer è un URL per il server proxy.

Il campo ProxyBypassList è un elenco di host proxy ignorati da Microsoft Edge.

Se si sceglie il valore "direct" come "ProxyMode", un proxy non viene mai usato e tutti gli altri campi vengono ignorati.

Se si sceglie il valore "system" come "ProxyMode", viene usato il proxy di sistema e tutti gli altri campi vengono ignorati.

Se si sceglie il valore "auto_detect" come "ProxyMode", tutti gli altri campi vengono ignorati.

Se si sceglie il valore "fixed_server" come "ProxyMode", vengono usati i campi "ProxyServer" e "ProxyBypassList".

Se si sceglie il valore "pac_script" come "ProxyMode", vengono usati i campi "ProxyPacUrl" e "ProxyBypassList".

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ProxySettings
  - Nome Criteri di gruppo: Configurare Impostazioni proxy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Server proxy
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ProxySettings
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {
  "ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", 
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ProxySettings
  - Valore di esempio
``` xml
<key>ProxySettings</key>
<dict>
  <key>ProxyBypassList</key>
  <string>https://www.example1.com,https://www.example2.com,https://internalsite/</string>
  <key>ProxyMode</key>
  <string>direct</string>
  <key>ProxyPacUrl</key>
  <string>https://internal.site/example.pac</string>
  <key>ProxyServer</key>
  <string>123.123.123.123:8080</string>
</dict>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri di impostazioni di SmartScreen

  [Torna all'inizio](#microsoft-edge---policies)

  ### PreventSmartScreenPromptOverride
  #### Impedisce di ignorare i prompt di Microsoft Defender SmartScreen per i siti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  L'impostazione di questo criterio consente di decidere se gli utenti possono ignorare gli avvisi di Microsoft Defender SmartScreen sui siti Web potenzialmente dannosi.

Se si abilita questa impostazione, gli utenti non possono ignorare gli avvisi di Microsoft Defender SmartScreen e viene loro impedito di accedere al sito.

Se si disabilita o non si configura questa impostazione, gli utenti possono ignorare gli avvisi di Microsoft Defender SmartScreen e accedere al sito.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PreventSmartScreenPromptOverride
  - Nome Criteri di gruppo: Impedisce di ignorare i prompt di Microsoft Defender SmartScreen per i siti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni SmartScreen
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PreventSmartScreenPromptOverride
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PreventSmartScreenPromptOverride
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PreventSmartScreenPromptOverrideForFiles
  #### Impedisce di ignorare gli avvisi di Microsoft Defender SmartScreen sui download
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive
  - In macOS dalla versione 79 o successive

  #### Descrizione
  Questo criterio consente di determinare se gli utenti possono ignorare gli avvisi di Microsoft Defender SmartScreen relativi ai download non verificati.

Se si abilita questo criterio, gli utenti dell'organizzazione non possono ignorare gli avvisi di Microsoft Defender SmartScreen e non possono completare i download non verificati.

Se si disabilita o non si configura questo criterio, gli utenti possono ignorare gli avvisi di Microsoft Defender SmartScreen e completare i download non verificati.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PreventSmartScreenPromptOverrideForFiles
  - Nome Criteri di gruppo: Impedisce di ignorare gli avvisi di Microsoft Defender SmartScreen sui download
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni SmartScreen
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PreventSmartScreenPromptOverrideForFiles
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PreventSmartScreenPromptOverrideForFiles
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SmartScreenAllowListDomains
  #### Configura l'elenco di domini per i quali Microsoft Defender SmartScreen non attiva gli avvisi
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura l'elenco di domini attendibili di Microsoft Defender SmartScreen. Ciò significa che Microsoft Defender SmartScreen non controlla l'eventuale presenza di risorse potenzialmente dannose, come software di phishing e altri malware, se gli URL di origine corrispondono a questi domini.
Il servizio di protezione di download Microsoft Defender SmartScreen non controllerà i download ospitati in questi domini.

Se si abilita questo criterio, Microsoft Defender SmartScreen considera attendibili questi domini.
Se si disabilita o non si imposta questo criterio, la protezione di Microsoft Defender SmartScreen predefinita viene applicata a tutte le risorse.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.
Si noti inoltre che questo criterio non viene applicato se l'organizzazione ha abilitato Microsoft Defender Advanced Threat Protection. È necessario configurare gli elenchi di indirizzi consentiti e bloccati in Microsoft Defender Security Center.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SmartScreenAllowListDomains
  - Nome Criteri di gruppo: Configura l'elenco di domini per i quali Microsoft Defender SmartScreen non attiva gli avvisi
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni SmartScreen
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\SmartScreenAllowListDomains
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\2 = "myuniversity.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SmartScreenAllowListDomains
  - Valore di esempio
``` xml
<array>
  <string>mydomain.com</string>
  <string>myuniversity.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SmartScreenEnabled
  #### Configura Microsoft Defender SmartScreen
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  L'impostazione di questo criterio consente di configurare se attivare Microsoft Defender SmartScreen. Microsoft Defender SmartScreen genera messaggi di avviso per proteggere gli utenti da potenziali tentativi di phishing e software dannoso. Per impostazione predefinita, Microsoft Defender SmartScreen è attivato.

Se si abilita questa impostazione, Microsoft Defender SmartScreen è attivato.

Se si disabilita questa impostazione, Microsoft Defender SmartScreen è disattivato.

Se non si configura questa impostazione, gli utenti possono scegliere se usare Microsoft Defender SmartScreen.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SmartScreenEnabled
  - Nome Criteri di gruppo: Configura Microsoft Defender SmartScreen
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni SmartScreen
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Impostazioni SmartScreen
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: SmartScreenEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SmartScreenEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SmartScreenForTrustedDownloadsEnabled
  #### Forza i controlli di Microsoft Defender SmartScreen sui download da origini attendibili
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Questo criterio consente di configurare se Microsoft Defender SmartScreen controlla la reputazione dei download da un'origine attendibile.

Se si abilita o non si configura questa impostazione, Microsoft Defender SmartScreen controlla la reputazione del download indipendentemente dall'origine.

Se si disabilita questa impostazione, Microsoft Defender SmartScreen non controlla la reputazione del download quando si scaricano contenuti da un'origine attendibile.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft, alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SmartScreenForTrustedDownloadsEnabled
  - Nome Criteri di gruppo: Forza i controlli di Microsoft Defender SmartScreen sui download da origini attendibili
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni SmartScreen
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Impostazioni SmartScreen
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: SmartScreenForTrustedDownloadsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SmartScreenPuaEnabled
  #### Configura Microsoft Defender SmartScreen per bloccare le applicazioni potenzialmente indesiderate
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  L'impostazione di questo criterio consente di configurare se attivare il blocco di app potenzialmente indesiderate con Microsoft Defender SmartScreen. Il blocco di app potenzialmente indesiderate con Microsoft Defender SmartScreen fornisce messaggi di avviso per proteggere gli utenti da adware, coin miner, bundleware e altre app di scarsa reputazione ospitate dai siti Web. Il blocco di app potenzialmente indesiderate con Microsoft Defender SmartScreen è disattivato per impostazione predefinita.

Se si abilita questa impostazione, il blocco di app potenzialmente indesiderate con Microsoft Defender SmartScreen è attivato.

Se si disabilita questa impostazione, il blocco di app potenzialmente indesiderate con Microsoft Defender SmartScreen è disattivato.

Se non si configura questa impostazione, gli utenti possono scegliere se usare il blocco di app potenzialmente indesiderate con Microsoft Defender SmartScreen.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SmartScreenPuaEnabled
  - Nome Criteri di gruppo: Configura Microsoft Defender SmartScreen per bloccare le applicazioni potenzialmente indesiderate
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Impostazioni SmartScreen
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Impostazioni SmartScreen
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: SmartScreenPuaEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SmartScreenPuaEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Criteri per avvio&comma; home page e pagina Nuova scheda

  [Torna all'inizio](#microsoft-edge---policies)

  ### HomepageIsNewTabPage
  #### Imposta la pagina Nuova scheda come home page
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura la home page predefinita in Microsoft Edge. È possibile impostare la home page su un URL specificato dall'utente o sulla pagina Nuova scheda.

Se si abilita questo criterio, la pagina Nuova scheda viene sempre usata per la home page e il percorso dell'URL della home page viene ignorato.

Se si disabilita questo criterio, la home page dell'utente non può essere la pagina Nuova scheda, a meno che l'URL non sia impostato su "edge://newtab".

Se non si configura questo criterio, gli utenti possono scegliere se la pagina Nuova scheda è la home page.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: HomepageIsNewTabPage
  - Nome Criteri di gruppo: Imposta la pagina Nuova scheda come home page
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: HomepageIsNewTabPage
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: HomepageIsNewTabPage
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### HomepageLocation
  #### Configura l'URL della home page
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura l'URL della home page predefinita in Microsoft Edge.

La home page è la pagina aperta dal pulsante Home. Le pagine che si aprono all'avvio sono controllate dai criteri [RestoreOnStartup](#restoreonstartup).

È possibile impostare un URL qui o impostare la home page per aprire la pagina Nuova scheda. Se si sceglie di aprire la pagina Nuova scheda, questo criterio non avrà effetto.

Se si abilita questo criterio, gli utenti non possono cambiare l'URL della home page, ma possono scegliere di usare la pagina Nuova scheda come home page.

Se si disabilita o non si configura questo criterio, gli utenti possono scegliere la propria home page, a condizione che il criterio [HomepageIsNewTabPage](#homepageisnewtabpage) non sia abilitato.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: HomepageLocation
  - Nome Criteri di gruppo: Configura l'URL della home page
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: HomepageLocation
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://www.contoso.com"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: HomepageLocation
  - Valore di esempio
``` xml
<string>https://www.contoso.com</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageAllowedBackgroundTypes
  #### Configura i tipi di sfondo consentiti per il layout della pagina Nuova scheda
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  È possibile configurare i tipi di immagine di sfondo consentiti per il layout della pagina Nuova scheda in Microsoft Edge.

Se non si configura questo criterio, vengono abilitati tutti i tipi di immagine di sfondo della pagina Nuova scheda.

Mapping delle opzioni del criterio:

* DisableImageOfTheDay (1) = Disabilitare il tipo di immagine di sfondo giornaliero

* DisableCustomImage (2) = Disabilitare il tipo di immagine di sfondo personalizzato

* DisableAll (3) = Disabilitare tutti i tipi di immagine di sfondo 

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageAllowedBackgroundTypes
  - Nome Criteri di gruppo: Configura i tipi di sfondo consentiti per il layout della pagina Nuova scheda
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NewTabPageAllowedBackgroundTypes
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageAllowedBackgroundTypes
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageCompanyLogo
  #### Imposta il logo aziendale della pagina Nuova scheda
  
  >OBSOLETO: questo criterio è obsoleto e non funziona dopo Microsoft Edge 85.
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79, fino alla versione 85

  #### Descrizione
  Questa politica non ha funzionato come previsto a causa di cambiamenti nei requisiti operativi. Di conseguenza, è obsoleto e non deve essere usato.

Specifica il logo aziendale da usare nella pagina Nuova scheda in Microsoft Edge.

Il criterio deve essere configurato come una stringa che esprime il o i logo in formato JSON. Ad esempio: { "default_logo": { "url": "https://www.contoso.com/logo.png", "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29" }, "light_logo": { "url": "https://www.contoso.com/light_logo.png", "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737" } }

Questo criterio si configura specificando l'URL dal quale Microsoft Edge può scaricare il logo e il suo hash crittografico (SHA-256), che viene usato per verificare l'integrità del download. Il logo deve essere in formato PNG o SVG e le dimensioni del relativo file non devono superare i 16 MB. Il logo viene scaricato e memorizzato nella cache e verrà riscaricato ogni volta che l'URL o l'hash cambia. L'URL deve essere accessibile senza l'autenticazione.

È necessario usare l'elemento "default_logo", che verrà utilizzato quando non è presente un'immagine di sfondo. Se viene fornito l'elemento "light_logo", verrà usato quando la pagina Nuova scheda dell'utente avrà un'immagine di sfondo. È consigliabile usare un logo orizzontale con uno sfondo trasparente allineato a sinistra e centrato verticalmente. Il logo deve avere un'altezza minima di 32 pixel e proporzioni da 1:1 a 4:1. L'elemento "default_logo" deve avere un contrasto corretto su uno sfondo bianco/nero, mentre l'elemento "light_logo" deve avere un contrasto corretto su un'immagine di sfondo.

Se si abilita questo criterio, Microsoft Edge scarica e mostra il logo specificato nella pagina Nuova scheda. Gli utenti non possono ignorare o nascondere il logo.

Se si disabilita o non si configura questo criterio, Microsoft Edge non mostrerà alcun logo aziendale né un logo Microsoft nella pagina Nuova scheda.

Per informazioni sulla determinazione dell'hash SHA-256, vedere https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageCompanyLogo
  - Nome Criteri di gruppo: imposta il logo aziendale della pagina Nuova scheda (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NewTabPageCompanyLogo
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {
  "default_logo": {
    "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", 
    "url": "https://www.contoso.com/logo.png"
  }, 
  "light_logo": {
    "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", 
    "url": "https://www.contoso.com/light_logo.png"
  }
}
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageCompanyLogo
  - Valore di esempio
``` xml
<key>NewTabPageCompanyLogo</key>
<dict>
  <key>default_logo</key>
  <dict>
    <key>hash</key>
    <string>cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29</string>
    <key>url</key>
    <string>https://www.contoso.com/logo.png</string>
  </dict>
  <key>light_logo</key>
  <dict>
    <key>hash</key>
    <string>517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737</string>
    <key>url</key>
    <string>https://www.contoso.com/light_logo.png</string>
  </dict>
</dict>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageHideDefaultTopSites
  #### Nasconde i siti principali predefiniti dalla pagina Nuova scheda
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Nasconde i siti principali predefiniti dalla pagina Nuova scheda in Microsoft Edge.

Se si imposta questo criterio su true, i riquadri dei siti principali predefiniti vengono nascosti.

Se si imposta questo criterio su false o non lo si configura, i riquadri dei siti principali predefiniti rimangono visibili.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageHideDefaultTopSites
  - Nome Criteri di gruppo: Nasconde i siti principali predefiniti dalla pagina Nuova scheda
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NewTabPageHideDefaultTopSites
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageHideDefaultTopSites
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageLocation
  #### Configura l'URL della pagina Nuova scheda
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura l'URL predefinito della pagina Nuova scheda.

Questo criterio determina la pagina che viene aperta quando vengono create nuove schede (incluso quando vengono aperte nuove finestre). Influisce anche sulla pagina di avvio se è impostata per aprire la pagina Nuova scheda.

Questo criterio non determina quale pagina viene aperta all'avvio; ciò è controllato dal criterio [RestoreOnStartup](#restoreonstartup). Inoltre, non influisce sulla home page se è impostata per aprire la pagina Nuova scheda.

Se non si configura questo criterio, viene utilizzata la pagina Nuova scheda predefinita.

Se si configura questo criterio *e* il criterio [NewTabPageSetFeedType](#newtabpagesetfeedtype), questo criterio ha la precedenza.

Se viene fornito un URL non valido, verranno aperte nuove schede del tipo about://blank.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageLocation
  - Nome Criteri di gruppo: Configura l'URL della pagina Nuova scheda
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: NewTabPageLocation
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://www.fabrikam.com"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageLocation
  - Valore di esempio
``` xml
<string>https://www.fabrikam.com</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageManagedQuickLinks
  #### Imposta i collegamenti rapidi della pagina Nuova scheda
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Per impostazione predefinita, Microsoft Edge mostra collegamenti rapidi nella pagina Nuova scheda dalle scelte rapide da tastiera aggiunte dall'utente e i siti principali in base alla cronologia esplorazioni. Con questo criterio, è possibile configurare fino a tre riquadri per collegamenti rapidi nella pagina Nuova scheda, espressi come oggetto JSON:

[ { "url": "https://www.contoso.com", "title": "Contoso Portal", "pinned": true/false }, ... ]

Il campo "url" è obbligatorio; "title" e "pinned" sono facoltativi. Se non viene fornito il campo "title", l'URL verrà usato come titolo predefinito. Se non viene fornito il campo "pinned", il valore predefinito è false.

Microsoft Edge presenta questi campi nell'ordine indicato, da sinistra a destra, con tutti i riquadri aggiunti visualizzati prima di quelli non aggiunti.

Se il criterio è impostato come obbligatorio, il campo "pinned" verrà ignorato e verranno aggiunti tutti i riquadri. I riquadri non possono essere eliminati dall'utente e verranno sempre visualizzati all'inizio dell'elenco dei collegamenti rapidi.

Se il criterio è impostato come consigliato, i riquadri aggiunti rimarranno nell'elenco, ma l'utente può modificarli ed eliminarli. I riquadri dei collegamenti rapidi non aggiunti si comportano come i siti principali predefiniti e vengono rimossi dall'elenco se altri siti Web vengono visitati più di frequente. Quando si applicano collegamenti non aggiunti a un profilo di browser esistente tramite questo criterio, i collegamenti potrebbero non essere visualizzati, a seconda di come sono classificati rispetto alla cronologia esplorazioni dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageManagedQuickLinks
  - Nome Criteri di gruppo: Imposta i collegamenti rapidi della pagina Nuova scheda
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: NewTabPageManagedQuickLinks
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [
  {
    "pinned": true, 
    "title": "Contoso Portal", 
    "url": "https://contoso.com"
  }, 
  {
    "title": "Fabrikam", 
    "url": "https://fabrikam.com"
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageManagedQuickLinks
  - Valore di esempio
``` xml
<key>NewTabPageManagedQuickLinks</key>
<array>
  <dict>
    <key>pinned</key>
    <true/>
    <key>title</key>
    <string>Contoso Portal</string>
    <key>url</key>
    <string>https://contoso.com</string>
  </dict>
  <dict>
    <key>title</key>
    <string>Fabrikam</string>
    <key>url</key>
    <string>https://fabrikam.com</string>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPagePrerenderEnabled
  #### Attiva il precaricamento della nuova scheda per il rendering più rapido
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Se si configurano questi criteri, è possibile precaricare la pagina Nuova scheda e per gli utenti non sarà possibile cambiare questa impostazione. Se non si configura questo criterio, il precaricamento è abilitato e l'utente sarà in grado di modificare tale impostazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPagePrerenderEnabled
  - Nome Criteri di gruppo: attiva il precaricamento della nuova scheda per il rendering più rapido
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: NewTabPagePrerenderEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: NewTabPagePrerenderEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NewTabPageSetFeedType
  #### Configura l'esperienza della pagina Nuova scheda di Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Consente di scegliere l'esperienza del feed di Microsoft News o Office 365 per la pagina Nuova scheda.

Se si imposta questo criterio su “News”, gli utenti vedranno l'esperienza del feed di Microsoft News nella pagina Nuova scheda.

Se si imposta questo criterio su “Office”, gli utenti con accesso al browser di Azure Active Directory vedranno l'esperienza del feed di Office 365 nella pagina Nuova scheda.

Se si disabilita o non si configura questo criterio:

- Gli utenti con accesso al browser di Azure Active Directory ottengono l'esperienza del feed della pagina Nuova scheda di Office 365, oltre all'esperienza del feed della pagina Nuova scheda standard.

- Gli utenti che non hanno accesso al browser di Azure Active Directory vedranno l'esperienza della pagina Nuova scheda standard.

Se si configura questo criterio *e* il criterio [NewTabPageLocation](#newtabpagelocation), il criterio [NewTabPageLocation](#newtabpagelocation) ha la precedenza.

Impostazione predefinita: disabilitato o non configurato.

Mapping delle opzioni del criterio:

* News (0) = Esperienza del feed di Microsoft News

* Office (1) = Esperienza del feed di Office 365

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NewTabPageSetFeedType
  - Nome Criteri di gruppo: Configura l'esperienza della pagina Nuova scheda di Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: NewTabPageSetFeedType
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NewTabPageSetFeedType
  - Valore di esempio
``` xml
<integer>0</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RestoreOnStartup
  #### Azione da eseguire all'avvio
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica il comportamento di Microsoft Edge all'avvio.

Se si desidera che all'avvio si apra sempre una nuova scheda, scegliere "RestoreOnStartupIsNewTabPage”.

Se si desidera riaprire gli URL che erano stati aperti l'ultima volta che è stato chiuso Microsoft Edge, scegliere "RestoreOnStartupIsLastSession”. L'ultima sessione di esplorazione verrà ripristinata. Questa opzione disabilita alcune impostazioni che si basano sulle sessioni o che eseguono azioni all'uscita (ad esempio, Cancella i dati di esplorazione all'uscita o i cookie di sessione).

Se si desidera aprire un set specifico di URL, scegliere "RestoreOnStartupIsURLs".

La disabilitazione di questa impostazione equivale a non configurarla. Gli utenti potranno modificarla in Microsoft Edge.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

Mapping delle opzioni del criterio:

* RestoreOnStartupIsNewTabPage (5) = Aprire una nuova scheda

* RestoreOnStartupIsLastSession (1) = Ripristinare l'ultima sessione

* RestoreOnStartupIsURLs (4) = Aprire un elenco di URL

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RestoreOnStartup
  - Nome Criteri di gruppo: Azione da eseguire all'avvio
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: RestoreOnStartup
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000004
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RestoreOnStartup
  - Valore di esempio
``` xml
<integer>4</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RestoreOnStartupURLs
  #### Siti da aprire all'avvio del browser
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica un elenco di siti Web da aprire automaticamente all'avvio del browser. Se non si configura questo criterio, non viene aperto alcun sito all'avvio.

Questo criterio funziona solo se si imposta anche il criterio [RestoreOnStartup](#restoreonstartup) su "Apri un elenco di URL" (4).

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RestoreOnStartupURLs
  - Nome Criteri di gruppo: Siti da aprire all'avvio del browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\RestoreOnStartupURLs
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Consigliato\RestoreOnStartupURLs
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\1 = "https://contoso.com"
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\2 = "https://www.fabrikam.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RestoreOnStartupURLs
  - Valore di esempio
``` xml
<array>
  <string>https://contoso.com</string>
  <string>https://www.fabrikam.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ShowHomeButton
  #### Mostra il pulsante Home nella barra degli strumenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Mostra il pulsante Home nella barra degli strumenti di Microsoft Edge.

Abilitare questo criterio per mostrare sempre il pulsante Home. Disabilitarlo per non mostrare mai il pulsante.

Se non si configura il criterio, gli utenti possono scegliere se mostrare il pulsante Home.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ShowHomeButton
  - Nome Criteri di gruppo: Mostra il pulsante Home nella barra degli strumenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/Avvio, home page e pagina Nuova scheda
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/Avvio, home page e pagina Nuova scheda
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ShowHomeButton
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ShowHomeButton
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ## Altri criteri

  [Torna all'inizio](#microsoft-edge---policies)

  ### AddressBarMicrosoftSearchInBingProviderEnabled
  #### Abilita Microsoft Search nei suggerimenti di Bing nella barra degli indirizzi
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Consente la visualizzazione dei suggerimenti rilevanti di Bing per Microsoft Search nell'elenco di suggerimenti della barra degli indirizzi quando l'utente digita una stringa di ricerca nella barra degli indirizzi. Se si abilita o non si configura questo criterio, gli utenti possono visualizzare i risultati interni forniti da Microsoft Search in Bing nell'elenco di suggerimenti della barra degli indirizzi di Microsoft Edge. Per vedere i risultati di Microsoft Search in Bing, l'utente deve accedere a Microsoft Edge con il proprio account di Azure AD per l'organizzazione.
Se si disabilita questo criterio, gli utenti non possono visualizzare i risultati interni nell'elenco di suggerimenti della barra degli indirizzi di Microsoft Edge.
Se è stato abilitato il set di criteri che forza un provider di ricerca predefinito ([DefaultSearchProviderEnabled](#defaultsearchproviderenabled), [DefaultSearchProviderName](#defaultsearchprovidername) e [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)) e il provider di ricerca specificato non è Bing, questo criterio non è applicabile e non saranno disponibili suggerimenti di Microsoft Search in Bing nell'elenco di suggerimenti della barra degli indirizzi.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AddressBarMicrosoftSearchInBingProviderEnabled
  - Nome Criteri di gruppo: Abilita Microsoft Search nei suggerimenti di Bing nella barra degli indirizzi
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AddressBarMicrosoftSearchInBingProviderEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AddressBarMicrosoftSearchInBingProviderEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AdsSettingForIntrusiveAdsSites
  #### Impostazione degli annunci per i siti con annunci intrusivi
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Controlla se gli annunci sono bloccati nei siti con annunci intrusivi.

Mapping delle opzioni del criterio:

* AllowAds (1) = Consentire gli annunci in tutti i siti

* BlockAds (2) = Bloccare gli annunci nei siti con annunci intrusivi. (Valore predefinito)

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AdsSettingForIntrusiveAdsSites
  - Nome Criteri di gruppo: Impostazione degli annunci per i siti con annunci intrusivi
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AdsSettingForIntrusiveAdsSites
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AdsSettingForIntrusiveAdsSites
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowDeletingBrowserHistory
  #### Abilita l'eliminazione della cronologia di download e browser
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di eliminare la cronologia del browser e la cronologia dei download, oltre a impedire agli utenti di modificare questa impostazione.

Anche con questo criterio disabilitato, non è garantita la conservazione della cronologia di esplorazione e dei download: gli utenti possono modificare o eliminare direttamente i file del database della cronologia e il browser stesso potrebbe rimuovere (in base al periodo di scadenza) o archiviare alcuni o tutti gli elementi della cronologia in qualsiasi momento.

Se si abilita o non si configura questo criterio, gli utenti possono eliminare la cronologia di esplorazione e dei download.

Se si disabilita questo criterio, gli utenti non possono eliminare la cronologia di esplorazione e dei download.

Se si abilita questo criterio, non abilitare il criterio [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) poiché entrambi sono associati all'eliminazione dei dati. Se si abilitano entrambi, il criterio [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) ha la precedenza ed elimina tutti i dati quando si chiude Microsoft Edge, indipendentemente da come è configurato tale criterio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowDeletingBrowserHistory
  - Nome Criteri di gruppo: Abilita l'eliminazione della cronologia di download e browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AllowDeletingBrowserHistory
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowDeletingBrowserHistory
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowFileSelectionDialogs
  #### Consente le finestre di dialogo per la selezione dei file
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente l'accesso ai file locali facendo in modo che Microsoft Edge mostri finestre di dialogo per la selezione dei file.

Se si abilita o non si configura questo criterio, gli utenti possono aprire le finestre di dialogo per la selezione dei file come di consueto.

Se si disabilita questo criterio, ogni volta che l'utente esegue un'azione che attiva una finestra di dialogo per la selezione dei file (come l'importazione dei preferiti, il caricamento dei file o il salvataggio dei collegamenti), viene invece visualizzato un messaggio e si presume che l'utente abbia selezionato Annulla nella finestra di dialogo per la selezione dei file.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowFileSelectionDialogs
  - Nome Criteri di gruppo: Consente le finestre di dialogo per la selezione dei file
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AllowFileSelectionDialogs
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowFileSelectionDialogs
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowPopupsDuringPageUnload
  #### Consente la visualizzazione di popup durante il caricamento di una pagina
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Questo criterio consente a un amministratore di specificare che una pagina può mostrare popup durante il suo scaricamento.

Se il criterio è abilitato, le pagine possono mostrare popup mentre vengono scaricate.

Se il criterio è disabilitato o non configurato, le pagine non possono mostrare popup mentre vengono scaricate. Ciò è definito dalle specifiche: https://html.spec.whatwg.org/#apis-for-creating-and-navigating-browsing-contexts-by-name).

Questo criterio verrà rimosso in futuro.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowPopupsDuringPageUnload
  - Nome Criteri di gruppo: Consente la visualizzazione di popup durante il caricamento di una pagina
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AllowPopupsDuringPageUnload
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowPopupsDuringPageUnload
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowSurfGame
  #### Consente il gioco Surf
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Se si disabilita questo criterio, gli utenti non saranno in grado di avviare il gioco Surf quando il dispositivo è offline o se l'utente accede a edge://surf.

Se si abilita o non si configura questo criterio, gli utenti possono avviare il gioco Surf.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowSurfGame
  - Nome Criteri di gruppo: Consente il gioco Surf
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AllowSurfGame
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowSurfGame
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowSyncXHRInPageDismissal
  #### Consente alle pagine di inviare richieste XHR sincrone durante la chiusura della pagina (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Questo criterio è deprecato perché è solo un meccanismo a breve termine che offre alle aziende più tempo per aggiornare i contenuti Web se e quando viene rilevata incompatibilità con la modifica per impedire le richieste XHR sincrone durante la chiusura della pagina. Non funzionerà in Microsoft Edge versione 88.

Questo criterio consente di specificare che una pagina può inviare richieste XHR sincrone durante la chiusura della pagina.

Se si abilita questo criterio, le pagine possono inviare richieste XHR sincrone durante la chiusura della pagina.

Se si disabilita o non si configura questo criterio, le pagine non possono inviare richieste XHR sincrone durante la chiusura della pagina.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowSyncXHRInPageDismissal
  - Nome Criteri di gruppo: Consente alle pagine di inviare richieste XHR sincrone durante la chiusura della pagina (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AllowSyncXHRInPageDismissal
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowSyncXHRInPageDismissal
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowTokenBindingForUrls
  #### Configura l'elenco dei siti con cui Microsoft Edge proverà a stabilire un binding di token
  
  
  #### Versioni supportate:
  - In Windows dalla versione 83 o successive

  #### Descrizione
  Configura l'elenco di modelli URL per i siti in cui il browser tenterà di eseguire il protocollo di binding di token.
Per i domini in questo elenco, il browser invierà il messaggio ClientHello di binding di token nell'handshake TLS (vedere https://tools.ietf.org/html/rfc8472).
Se il server risponde con una risposta ServerHello valida, il browser creerà e invierà messaggi di binding di token nelle successive richieste HTTPS. Per altre informazioni, vedere https://tools.ietf.org/html/rfc8471.

Se questo elenco è vuoto, il binding di token verrà disabilitato.

Questo criterio è disponibile solo nei dispositivi Windows 10 con la funzionalità Modalità protetta virtuale.

A partire da Microsoft Edge 86, questo criterio non supporta più l'aggiornamento dinamico.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowTokenBindingForUrls
  - Nome Criteri di gruppo: Configura l'elenco dei siti con cui Microsoft Edge proverà a stabilire un binding di token.
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\AllowTokenBindingForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\2 = "[*.]mydomain2.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\3 = "[*.].mydomain2.com"

```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AllowTrackingForUrls
  #### Configura il monitoraggio delle eccezioni di protezione per siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Configura l'elenco di modelli URL esclusi dalla prevenzione del rilevamento.

Se si configura questo criterio, l'elenco dei modelli URL configurati è escluso dalla prevenzione del rilevamento.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio "Blocca il monitoraggio dell'attività di esplorazione sul Web degli utenti" (se impostato) o la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AllowTrackingForUrls
  - Nome Criteri di gruppo: Configura il monitoraggio delle eccezioni di protezione per siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\AllowTrackingForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AllowTrackingForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AlternateErrorPagesEnabled
  #### Suggerisce pagine simili quando non è possibile trovare una pagina web
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Consente a Microsoft Edge di rilasciare una connessione a un servizio Web per generare suggerimenti di ricerca e URL per problemi di connettività come gli errori DNS.

Se si abilita questo criterio, un servizio Web viene usato per generare suggerimenti di ricerca e URL per errori di rete.

Se si disabilita questo criterio, non vengono effettuate chiamate al servizio Web e viene visualizzata una pagina di errore standard.

Se non si configura questo criterio, Microsoft Edge rispetta le preferenze degli utenti impostate in Servizi in edge://settings/privacy.
In particolare, è presente l'opzione **Suggerisci pagine simili quando non è possibile trovare una pagina Web**, che può essere attivata o disattivata dall'utente. Se viene abilitato questo criterio (AlternateErrorPagesEnabled), l'impostazione Suggerisci pagine simili quando non è possibile trovare una pagina Web è attivata, ma l'utente non potrà modificarla tramite l’interruttore. Se si disabilita questo criterio, l'impostazione Suggerisci pagine simili quando non è possibile trovare una pagina Web è disattivata e l'utente non potrà modificarla tramite l’interruttore.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AlternateErrorPagesEnabled
  - Nome Criteri di gruppo: Suggerisce pagine simili quando non è possibile trovare una pagina Web
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: AlternateErrorPagesEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AlternateErrorPagesEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AlwaysOpenPdfExternally
  #### Apre sempre i file PDF esternamente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disabilita il visualizzatore PDF interno in Microsoft Edge.

Se si abilita questo criterio, Microsoft Edge considera i file PDF come download e consente agli utenti di aprirli con l'applicazione predefinita.

Se si disabilita o non si configura questo criterio, Microsoft Edge aprirà i file PDF (a meno che l'utente non lo impedisca).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AlwaysOpenPdfExternally
  - Nome Criteri di gruppo: Apre sempre i file PDF esternamente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AlwaysOpenPdfExternally
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AlwaysOpenPdfExternally
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AmbientAuthenticationInPrivateModesEnabled
  #### Abilita l'autenticazione ambientale per i profili InPrivate e Guest
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Configurare questo criterio per consentire/impedire l'autenticazione ambientale per i profili InPrivate e Guest in Microsoft Edge.

L'autenticazione ambientale è l'autenticazione HTTP con le credenziali predefinite quando non vengono fornite le credenziali esplicite tramite gli schemi NTLM/Kerberos/Test Negotiate/risposta.

Se si imposta il criterio su “RegularOnly”, consente l'autenticazione ambientale solo per le sessioni regolari. L'autenticazione ambientale per le sessioni InPrivate e Guest non sarà consentita.

Se si imposta il criterio su” InPrivateAndRegular”, consente l'autenticazione ambientale per le sessioni InPrivate e regolari. L'autenticazione ambientale per le sessioni Guest non sarà consentita.

Se si imposta il criterio su “GuestAndRegular”, consente l'autenticazione ambientale per le sessioni Guest e regolari. L'autenticazione ambientale per le sessioni InPrivate non sarà consentita.

Se si imposta il criterio su “All”, consente l'autenticazione ambientale per tutte le sessioni.

Nota: l'autenticazione ambientale è sempre consentita sui profili regolari.

In Microsoft Edge versione 81 e successive, se il criterio non viene impostato, l'autenticazione ambientale sarà abilitata solo per le sessioni regolari.

Mapping delle opzioni del criterio:

* RegularOnly (0) = Abilitare l'autenticazione ambientale solo nelle sessioni regolari

* InPrivateAndRegular (1) = Abilitare l'autenticazione ambientale nelle sessioni InPrivate e regolari

* GuestAndRegular (2) = Abilitare l'autenticazione ambientale nelle sessioni Guest e regolari

* All (3) = Abilitare l'autenticazione ambientale nelle sessioni regolari, InPrivate e Guest

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AmbientAuthenticationInPrivateModesEnabled
  - Nome Criteri di gruppo: Abilita l'autenticazione ambientale per i profili InPrivate e Guest
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AmbientAuthenticationInPrivateModesEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AmbientAuthenticationInPrivateModesEnabled
  - Valore di esempio
``` xml
<integer>0</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AppCacheForceEnabled
  #### Consente la riabilitazione della funzionalità AppCache, anche se disabilitata per impostazione predefinita.
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 84 o successive

  #### Descrizione
  Se si imposta questo criterio su true, AppCache è abilitato, anche se AppCache in Microsoft Edge non è disponibile per impostazione predefinita.

Se si imposta questo criterio su false o non lo si imposta, AppCache seguirà le impostazioni predefinite di Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AppCacheForceEnabled
  - Nome Criteri di gruppo: consente la riabilitazione della funzionalità AppCache, anche se disabilitata per impostazione predefinita
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AppCacheForceEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: AppCacheForceEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ApplicationLocaleValue
  #### Configura le impostazioni locali delle applicazioni
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Configura le impostazioni locali delle applicazioni in Microsoft Edge e impedisce agli utenti di modificarle.

Se si abilita questo criterio, Microsoft Edge usa le impostazioni locali specificate. Se le impostazioni locali configurate non sono supportate, verrà usato "en-US".

Se si disabilita o non si configura questa impostazione, Microsoft Edge usa le impostazioni locali preferite specificate dall'utente (se configurate) o le impostazioni locali di fallback "en-US".

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ApplicationLocaleValue
  - Nome Criteri di gruppo: Configura le impostazioni locali delle applicazioni
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ApplicationLocaleValue
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"en"
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AudioCaptureAllowed
  #### Consente o blocca l'acquisizione audio
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di specificare se un utente deve concedere l'accesso a un sito Web al proprio dispositivo di acquisizione audio. Questo criterio si applica a tutti gli URL, ad eccezione di quelli configurati nell'elenco [AudioCaptureAllowedUrls](#audiocaptureallowedurls).

Se si abilita o non si configura (impostazione predefinita) questo criterio, all'utente viene chiesto l'accesso all'acquisizione audio, ad eccezione degli URL nell'elenco [AudioCaptureAllowedUrls](#audiocaptureallowedurls). Questi URL elencati sono autorizzati ad accedere senza richiedere la conferma dell'utente.

Se si disabilita questo criterio, all'utente non viene inviata alcuna richiesta e l'acquisizione audio è accessibile solo per gli URL configurati in [AudioCaptureAllowedUrls](#audiocaptureallowedurls).

Questo criterio influisce su tutti i tipi di input audio, non solo sul microfono predefinito.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AudioCaptureAllowed
  - Nome Criteri di gruppo: Consente o blocca l'acquisizione audio
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AudioCaptureAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AudioCaptureAllowed
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AudioCaptureAllowedUrls
  #### Siti che possono accedere ai dispositivi di acquisizione audio senza richiedere l'autorizzazione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica i siti Web, in base ai modelli URL, che possono usare i dispositivi di acquisizione audio senza chiedere l'autorizzazione all'utente. I modelli in questo elenco vengono confrontati con l'origine di sicurezza dell'URL di richiesta. In caso di corrispondenza, al sito viene automaticamente concesso l'accesso ai dispositivi di acquisizione audio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AudioCaptureAllowedUrls
  - Nome Criteri di gruppo: Siti che possono accedere ai dispositivi di acquisizione audio senza richiedere l'autorizzazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\AudioCaptureAllowedUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AudioCaptureAllowedUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AudioSandboxEnabled
  #### Consente l'esecuzione della sandbox audio
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Questo criterio controlla la sandbox del processo audio.

Se si abilita questo criterio, il processo audio verrà eseguito in modalità sandbox.

Se si disabilita questo criterio, il processo audio non verrà eseguito in modalità sandbox e il modulo di elaborazione audio WebRTC verrà eseguito nel processo del renderer.
Questo lascia gli utenti esposti ai rischi per la sicurezza correlati all'esecuzione del sottosistema audio non in modalità sandbox.

Se non si configura questo criterio, per la sandbox audio verrà usata la configurazione predefinita, che potrebbe variare a seconda della piattaforma.

Questo criterio è pensato per offrire alle aziende la possibilità di disabilitare la sandbox audio se usano configurazioni di software per la sicurezza che interferiscono con la sandbox.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AudioSandboxEnabled
  - Nome Criteri di gruppo: Consente l'esecuzione della sandbox audio
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AudioSandboxEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AudioSandboxEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutoImportAtFirstRun
  #### Importa automaticamente le impostazioni e i dati di un altro browser alla prima esecuzione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita questo criterio, tutti i tipi di dati e le impostazioni supportati del browser specificato verranno importati automaticamente alla prima esecuzione. Durante la first-run experience, la sezione di importazione verrà ignorata.

I dati del browser della Versione legacy di Microsoft Edge saranno sempre migrati automaticamente nella first-run experience, indipendentemente dal valore di questo criterio.

Se questo criterio è impostato su “FromDefaultBrowser”, i tipi di dati corrispondenti al browser predefinito nel dispositivo gestito verranno importati.

Se il browser specificato come valore di questo criterio non è presente nel dispositivo gestito, Microsoft Edge ignorerà l'importazione senza inviare alcuna notifica all'utente.

Se si imposta questo criterio su "DisabledAutoImport", la sezione di importazione della first-run experience viene interamente ignorata e Microsoft Edge non importa i dati e le impostazioni del browser automaticamente.

Se questo criterio è impostato sul valore di “FromInternetExplorer”, i seguenti tipi di dati verranno importati da Internet Explorer:
1. Preferiti o segnalibri
2. Password salvate
3. Motori di ricerca
4. Cronologia esplorazioni
5. Home page

Se questo criterio è impostato sul valore di “FromGoogleChrome”, i seguenti tipi di dati verranno importati da Google Chrome:
1. Preferiti
2. Password salvate
3. Indirizzi e altro
4. Informazioni di pagamento
5. Cronologia esplorazioni
6. Impostazioni
7. Schede aggiunte e aperte
8. Extensions
9. Cookie

Nota: per altri dettagli su cosa viene importato da Google Chrome, vedere [https://go.microsoft.com/fwlink/?linkid=2120835](https://go.microsoft.com/fwlink/?linkid=2120835)

Se questo criterio è impostato sul valore di “FromSafari”, i dati degli utenti non vengono più importati in Microsoft Edge. Ciò è dovuto al modo in cui l'accesso completo al disco funziona sul Mac.
In macOS Mojave e versioni successive, non è più possibile avere l'importazione automatica dei dati di Safari in Microsoft Edge.

A partire da Microsoft Edge versione 83, se questo criterio è impostato sul valore di “FromMozillaFirefox”, i seguenti tipi di dati verranno importati da Mozilla Firefox:
1. Preferiti o segnalibri
2. Password salvate
3. Indirizzi e altro
4. Cronologia esplorazioni

Se si desidera limitare l'importazione di tipi di dati specifici nei dispositivi gestiti, è possibile utilizzare questo criterio con altri criteri come [ImportAutofillFormData](#importautofillformdata), [ImportBrowserSettings](#importbrowsersettings), [ImportFavorites](#importfavorites) e così via.

Mapping delle opzioni del criterio:

* FromDefaultBrowser (0) = Importa automaticamente tutti i tipi di dati e le impostazioni supportati dal browser predefinito

* FromInternetExplorer (1) = Importa automaticamente tutti i tipi di dati e le impostazioni supportati da Internet Explorer

* FromGoogleChrome (2) = Importa automaticamente tutti i tipi di dati e le impostazioni supportati da Google Chrome

* FromSafari (3) = Importa automaticamente tutti i tipi di dati e le impostazioni supportati da Safari

* DisabledAutoImport (4) = Disabilita l'importazione automatica e la sezione di importazione della first-run experience viene ignorata

* FromMozillaFirefox (5) = Importa automaticamente tutti i tipi di dati e le impostazioni supportati da Mozilla Firefox

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AutoImportAtFirstRun
  - Nome Criteri di gruppo: Importa automaticamente le impostazioni e i dati di un altro browser alla prima esecuzione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AutoImportAtFirstRun
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AutoImportAtFirstRun
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutoLaunchProtocolsFromOrigins
  #### Definisci un elenco di protocolli che possono avviare un'applicazione esterna da origini elencate senza chiedere conferma all'utente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Consente di impostare un elenco di protocolli e, per ciascun protocollo, un elenco associato di modelli di origine consentiti, che può avviare un'applicazione esterna senza richiedere all'utente. Il separatore finale non deve essere incluso nell'elenco del protocollo. Ad esempio, inserisci “skype” invece di “skype:” o “skype://”.

Se si configura questo criterio, è possibile usare un protocollo solo per avviare un'applicazione esterna senza richiedere consenso in base al criterio se:

- il protocollo è elencato

- l'origine del sito che tenta di avviare il protocollo corrisponde a uno dei modelli di origine nell'elenco allowed_origins di tale protocollo.

Se una delle due condizioni è falsa, il prompt di avvio del protocollo esterno non verrà omesso in base al criterio.

Se non si configura questo criterio, non è possibile avviare alcun protocollo senza un prompt. Gli utenti possono rifiutare esplicitamente i prompt in base al protocollo/sito a meno che il criterio [ ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox) sia impostato su disabilitato. Questo criterio non ha alcun impatto sulle esenzioni di prompt per protocollo/sito impostate dagli utenti.

I modelli di corrispondenza di origine usano un formato simile a quelli per il criterio [URLBlocklist](#urlblocklist), documentati su [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

Tuttavia, i modelli di corrispondenza di origine per questo criterio non possono contenere elementi come “/path” o “@query”. Qualsiasi modello che contiene un elemento “/path” o “@query” verrà ignorato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AutoLaunchProtocolsFromOrigins
  - Nome Criteri di gruppo: definisci un elenco di protocolli che possono avviare un'applicazione esterna da origini elencate senza chiedere conferma all'utente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AutoLaunchProtocolsFromOrigins
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [
  {
    "allowed_origins": [
      "example.com", 
      "http://www.example.com:8080"
    ], 
    "protocol": "spotify"
  }, 
  {
    "allowed_origins": [
      "https://example.com", 
      "https://.mail.example.com"
    ], 
    "protocol": "teams"
  }, 
  {
    "allowed_origins": [
      "*"
    ], 
    "protocol": "outlook"
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: AutoLaunchProtocolsFromOrigins
  - Valore di esempio
``` xml
<key>AutoLaunchProtocolsFromOrigins</key>
<array>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>example.com</string>
      <string>http://www.example.com:8080</string>
    </array>
    <key>protocol</key>
    <string>spotify</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>https://example.com</string>
      <string>https://.mail.example.com</string>
    </array>
    <key>protocol</key>
    <string>teams</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>*</string>
    </array>
    <key>protocol</key>
    <string>outlook</string>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutoOpenAllowedForURLs
  #### URL in cui è possibile applicare AutoOpenFileTypes
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Un elenco di URL a cui [AutoOpenFileTypes](#autoopenfiletypes) verrà applicato. Questo criterio non ha alcun effetto sul modo in cui i valori aperti automaticamente impostati dagli utenti tramite la barra di download ... > Voce del menu “Apri sempre file di questo tipo”.

Se si impostano gli URL in questo criterio, i file verranno aperti automaticamente in base al criterio, se l'URL fa parte del set e il tipo di file è elencato in [AutoOpenFileTypes](#autoopenfiletypes). Se una delle due condizioni è falsa, il download non si aprirà automaticamente in base ai criteri.

Se non si impostano questo criterio, tutti i download in cui il tipo di file è presente in [AutoOpenFileTypes](#autoopenfiletypes) si aprirà automaticamente.

Un modello di URL deve essere formattato in base a [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AutoOpenAllowedForURLs
  - Nome Criteri di gruppo: URL in cui è possibile applicare AutoOpenFileTypes
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\AutoOpenAllowedForURLs
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\1 = "example.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\5 = ".exact.hostname.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: AutoOpenAllowedForURLs
  - Valore di esempio
``` xml
<array>
  <string>example.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutoOpenFileTypes
  #### Elenco dei tipi di file che devono essere aperti automaticamente al download
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Questo criterio imposta un elenco dei tipi di file che devono essere aperti automaticamente al download. Nota: quando si elenca il tipo di file, non è necessario includere il separatore iniziale, quindi inserisci “txt” al posto di “.txt”.

Per impostazione predefinita, questi tipi di file verranno aperti automaticamente in tutti gli URL. È possibile usare il criterio [AutoOpenAllowedForURLs](#autoopenallowedforurls) per limitare gli URL di cui questi tipi di file verranno aperti automaticamente.

I file con tipi che devono essere aperti automaticamente continueranno a essere soggetti ai controlli abilitati di Microsoft Defender SmartScreen e non verranno aperti se non superano tali controlli.

I tipi di file che un utente ha già specificato per l'apertura automatica continueranno a essere scaricati automaticamente. L'utente continuerà a essere in grado di specificare altri tipi di file da aprire automaticamente.

Se non si imposta questo criterio, solo i tipi di file che un utente ha già specificato per l'apertura automatica verranno aperto al download.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri del gruppo: AutoOpenFileTypes
  - Nome Criteri di gruppo: elenco dei tipi di file che devono essere aperti automaticamente al download
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\AutoOpenFileTypes
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\1 = "exe"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\2 = "txt"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AutoOpenFileTypes
  - Valore di esempio
``` xml
<array>
  <string>exe</string>
  <string>txt</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutofillAddressEnabled
  #### Abilita il riempimento automatico per gli indirizzi
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilita la funzionalità di riempimento automatico e consente agli utenti di completare automaticamente le informazioni relative all'indirizzo nei moduli Web usando le informazioni archiviate in precedenza.

Se si disabilita questo criterio, la funzionalità di riempimento automatico non suggerisce o compila mai le informazioni sull'indirizzo, né salva informazioni sull'indirizzo aggiuntive che l'utente potrebbe aver inviato durante l'esplorazione del Web.

Se si abilita o non si configura questo criterio, gli utenti possono controllare la funzionalità di riempimento automatico per gli indirizzi nell'interfaccia utente.

Se si disabilita questo criterio, si interrompe anche tutta l'attività per tutti i moduli Web, ad eccezione dei moduli relativi a password e pagamenti. Non vengono salvate altre voci e Microsoft Edge non suggerisce o compila automaticamente eventuali voci precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AutofillAddressEnabled
  - Nome Criteri di gruppo: Abilita il riempimento automatico per gli indirizzi
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: AutofillAddressEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AutofillAddressEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutofillCreditCardEnabled
  #### Abilita il riempimento automatico per le carte di credito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilita la funzionalità di riempimento automatico di Microsoft Edge e consente agli utenti di completare automaticamente le informazioni relative alla carta di credito nei moduli Web usando le informazioni archiviate in precedenza.

Se si disabilita questo criterio, la funzionalità di riempimento automatico non suggerisce o compila mai le informazioni sulla carta di credito, né salva informazioni sulla carta di credito aggiuntive che gli utenti potrebbero aver inviato durante l'esplorazione del Web.

Se si abilita o non si configura questo criterio, gli utenti possono controllare la funzionalità di riempimento automatico per le carte di credito.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome Criteri di gruppo: AutofillCreditCardEnabled
  - Nome Criteri di gruppo: Abilita il riempimento automatico per le carte di credito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: AutofillCreditCardEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AutofillCreditCardEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### AutoplayAllowed
  #### Consente la riproduzione automatica dei contenuti multimediali per i siti Web
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Questo criterio imposta i criteri di riproduzione automatica di contenuti multimediali per i siti Web.

L'impostazione predefinita, "Non configurato", rispetta le impostazioni di riproduzione automatica di contenuti multimediali correnti e consente agli utenti di configurare le proprie impostazioni di riproduzione automatica.

Se si abilita questo criterio, la riproduzione automatica di contenuti multimediali è consentita.  Tutti i siti Web possono riprodurre contenuti multimediali. Gli utenti non possono eseguire l'override del criterio.

Se si disabilita questo criterio, la riproduzione automatica di contenuti multimediali è bloccata.  Nessun sito Web può riprodurre contenuti multimediali. Gli utenti non possono eseguire l'override del criterio.

Per applicare il criterio, è necessario chiudere e riaprire una scheda.


  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: AutoplayAllowed
  - Nome Criteri di gruppo: Consente la riproduzione automatica dei contenuti multimediali per i siti Web
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: AutoplayAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: AutoplayAllowed
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BackgroundModeEnabled
  #### App in esecuzione in background dopo la chiusura di Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Consente l'avvio dei processi di Microsoft Edge all'accesso al sistema operativo e li mantiene in esecuzione dopo la chiusura dell'ultima finestra del browser. In questo scenario, le app in background e la sessione di esplorazione corrente rimangono attive, inclusi i cookie di sessione. Un processo in background aperto visualizza un'icona nell'area di notifica e può sempre essere chiuso da lì.

Se si abilita questo criterio, la modalità in background è attivata.

Se si disabilita questo criterio, la modalità in background è disattivata.

Se non si configura questo criterio, inizialmente la modalità in background è disattivata, ma può essere configurata dall'utente in edge://settings/system.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BackgroundModeEnabled
  - Nome Criteri di gruppo: App in esecuzione in background dopo la chiusura di Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: BackgroundModeEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BackgroundTemplateListUpdatesEnabled
  #### Abilita gli aggiornamenti in background all'elenco di modelli disponibili per Raccolte e altre funzionalità che sfruttano i modelli
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Consente di abilitare o disabilitare gli aggiornamenti in background all'elenco di modelli disponibili per Raccolte e altre funzionalità che sfruttano i modelli.  I modelli vengono usati per estrarre metadati complessi da una pagina Web quando la pagina viene salvata come raccolta.

Se si abilita o non si configura questa impostazione, l'elenco di modelli disponibili verrà scaricato in background da un servizio Microsoft ogni 24 ore.

Se si disabilita questa impostazione, l'elenco di modelli disponibili verrà scaricato su richiesta. Questo tipo di download può influire leggermente sulle prestazioni di Raccolte e altre funzionalità.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BackgroundTemplateListUpdatesEnabled
  - Nome Criteri di gruppo: Abilita gli aggiornamenti in background all'elenco di modelli disponibili per Raccolte e altre funzionalità che sfruttano i modelli
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BackgroundTemplateListUpdatesEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BackgroundTemplateListUpdatesEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BingAdsSuppression
  #### Blocca tutti gli annunci sui risultati della ricerca di Bing
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Fornisce un'esperienza di ricerca senza pubblicità su Bing.com

Se si abilita questo criterio, un utente può eseguire ricerche su bing.com senza pubblicità. Contemporaneamente, l'impostazione Ricerca sicura verrà impostata su "Strict" e non potrà essere modificata dall'utente.

Se non si configura questo criterio, l'esperienza predefinita mostrerà pubblicità nei risultati della ricerca su bing.com. Ricerca sicura sarà impostata su "Moderate" per impostazione predefinita e potrà essere modificata dall'utente.

Questo criterio è disponibile solo per le SKU K-12 identificate come tenant EDU da Microsoft.

Consultare [https://go.microsoft.com/fwlink/?linkid=2119711](https://go.microsoft.com/fwlink/?linkid=2119711) per altre informazioni su questo criterio o se si verificano gli scenari seguenti:

* Si dispone di un tenant EDU, ma il criterio non funziona.

* L'IP è stato inserito nell'elenco elementi consentiti per avere un'esperienza di ricerca senza pubblicità.

* Si è verificata un'esperienza di ricerca senza pubblicità nella Versione legacy di Microsoft Edge e si desidera eseguire l'aggiornamento alla nuova versione di Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BingAdsSuppression
  - Nome Criteri di gruppo: Blocca tutti gli annunci sui risultati della ricerca di Bing
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BingAdsSuppression
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BingAdsSuppression
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BlockThirdPartyCookies
  #### Blocca i cookie di terze parti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impedisce agli elementi di una pagina Web che non fanno parte del dominio che si trova nella barra degli indirizzi di impostare i cookie.

Se si abilita questo criterio, gli elementi della pagina Web che non fanno parte del dominio che si trova nella barra degli indirizzi non possono impostare cookie

Se si disabilita questo criterio, gli elementi della pagina Web di un dominio diverso da quello nella barra degli indirizzi possono impostare cookie.

Se non si configura questo criterio, i cookie di terze parti sono abilitati, ma gli utenti possono modificare questa impostazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BlockThirdPartyCookies
  - Nome Criteri di gruppo: Blocca i cookie di terze parti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: BlockThirdPartyCookies
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BlockThirdPartyCookies
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BrowserAddProfileEnabled
  #### Abilita la creazione del profilo dal menu a comparsa Identità o dalla pagina Impostazioni
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di creare nuovi profili, usando l'opzione **Aggiungi profilo**.
Se si abilita o non si configura questo criterio, Microsoft Edge consente agli utenti di usare **Aggiungi profilo** nel menu a comparsa Identità o nella pagina Impostazioni per creare nuovi profili.

Se si disabilita questo criterio, gli utenti non potranno aggiungere nuovi profili dal menu a comparsa Identità o dalla pagina Impostazioni.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BrowserAddProfileEnabled
  - Nome Criteri di gruppo: Abilita la creazione del profilo dal menu a comparsa Identità o dalla pagina Impostazioni
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BrowserAddProfileEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BrowserAddProfileEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BrowserGuestModeEnabled
  #### Abilita la modalità Guest
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilita l'opzione per consentire l'utilizzo di profili guest in Microsoft Edge. In un profilo guest, il browser non importa i dati di esplorazione da profili esistenti ed elimina i dati di esplorazione quando tutti i profili guest sono chiusi.

Se si abilita o non si configura questo criterio, Microsoft Edge consente agli utenti di esplorare nei profili guest.

Se si disabilita questo criterio, Microsoft Edge non consente agli utenti di esplorare nei profili guest.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BrowserGuestModeEnabled
  - Nome Criteri di gruppo: Abilita la modalità Guest
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BrowserGuestModeEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BrowserGuestModeEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BrowserNetworkTimeQueriesEnabled
  #### Consente le query a un servizio Browser Network Time
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impedisce a Microsoft Edge di inviare occasionalmente query a un servizio Browser Network Time per recuperare un timestamp preciso.

Se si disabilita questo criterio, Microsoft Edge interromperà l'invio di query a un servizio Browser Network Time.

Se si abilita o non si configura questo criterio, Microsoft Edge invierà occasionalmente query a un servizio Browser Network Time.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BrowserNetworkTimeQueriesEnabled
  - Nome Criteri di gruppo: Consente le query a un servizio Browser Network Time
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BrowserNetworkTimeQueriesEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BrowserNetworkTimeQueriesEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BrowserSignin
  #### Impostazioni di accesso al browser
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se un utente può accedere a Microsoft Edge con il proprio account e usare i servizi correlati all'account come la sincronizzazione e Single Sign-On. Per controllare la disponibilità della sincronizzazione, usare invece il criterio [SyncDisabled](#syncdisabled).

Se si imposta questo criterio su "Disabilita", assicurarsi di disabilitare anche il criterio [NonRemovableProfileEnabled](#nonremovableprofileenabled) poiché [NonRemovableProfileEnabled](#nonremovableprofileenabled) disabilita la creazione di un profilo di accesso automatico al browser. Se entrambi i criteri sono impostati, Microsoft Edge userà il criterio "Disabilita l'accesso al browser" e si comporterà come se [NonRemovableProfileEnabled](#nonremovableprofileenabled) fosse disabilitato.

Se si imposta questo criterio su "Abilita", gli utenti possono accedere al browser. L'accesso al browser non implica che la sincronizzazione sia attivata per impostazione predefinita; per usare questa funzionalità, l'utente deve acconsentire esplicitamente.

Se si imposta questo criterio su "Forza", gli utenti devono accedere a un profilo per usare il browser. Per impostazione predefinita, questo consentirà all'utente di scegliere se sincronizzare il proprio account, a meno che la sincronizzazione non sia disabilitata dall'amministratore di dominio o con il criterio [SyncDisabled](#syncdisabled). Il valore predefinito del criterio [BrowserGuestModeEnabled](#browserguestmodeenabled) è impostato su false.

Se non si configura questo criterio, gli utenti possono decidere se abilitare l'opzione di accesso al browser e usarla secondo necessità.

Mapping delle opzioni del criterio:

* Disabilita (0) = Disabilita l'accesso al browser

* Abilita (1) = Abilita l'accesso al browser

* Forza (2) = Forza gli utenti ad accedere per usare il browser

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BrowserSignin
  - Nome Criteri di gruppo: Impostazioni di accesso al browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BrowserSignin
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BrowserSignin
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BuiltInDnsClientEnabled
  #### Usa il client DNS predefinito
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se usare il client DNS predefinito.

Ciò non influisce su quali server DNS vengono usati, ma solo sullo stack del software utilizzato per comunicare con essi. Ad esempio, se il sistema operativo è configurato per usare un server DNS aziendale, tale server verrà usato dal client DNS predefinito. Tuttavia, è possibile che il client DNS predefinito gestisca i server in modi diversi tramite protocolli correlati al DNS più moderni, come DNS-over-TLS.

Se si abilita questo criterio, viene usato il client DNS predefinito, se disponibile.

Se si disabilita questo criterio, il client non viene mai usato.

Se non si configura questo criterio, il client DNS predefinito è abilitato per impostazione predefinita su MacOS e gli utenti possono decidere se usare il client DNS predefinito modificando edge://flags o specificando un contrassegno della riga di comando.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: BuiltInDnsClientEnabled
  - Nome Criteri di gruppo: Usa il client DNS predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: BuiltInDnsClientEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BuiltInDnsClientEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### BuiltinCertificateVerifierEnabled
  #### Determina se lo strumento di verifica del certificato predefinito verrà usato per la verifica dei certificati server (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In macOS dalla versione 83 o successive

  #### Descrizione
  Questo criterio è deprecato perché serve solo come meccanismo a breve termine per offrire alle aziende più tempo per aggiornare i propri ambienti e segnalare problemi se risultano incompatibili con lo strumento di verifica predefinito.

Non funzionerà in Microsoft Edge versione 87, quando è prevista la rimozione dello strumento di verifica del certificato legacy in Mac OS X.


  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  

  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: BuiltinCertificateVerifierEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForCas
  #### Disabilita l'applicazione della trasparenza dei certificati per un elenco di hash subjectPublicKeyInfo
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disabilita l'applicazione dei requisiti di trasparenza dei certificati per un elenco di hash subjectPublicKeyInfo.

Questo criterio consente di disabilitare i requisiti di divulgazione della trasparenza dei certificati per le catene di certificati che contengono certificati con uno degli hash subjectPublicKeyInfo specificati. In questo modo, è possibile continuare a usare per gli host aziendali i certificati che altrimenti potrebbero non essere considerati attendibili perché non divulgati in modo adeguato.

Per disabilitare l'applicazione della trasparenza dei certificati quando è impostato questo criterio, è necessario soddisfare uno dei seguenti set di condizioni:
1. L'hash è di un subjectPublicKeyInfo del certificato del server.
2. L'hash è di un subjectPublicKeyInfo che compare in un certificato di firma nella catena di certificati, tale certificato di firma è vincolato tramite l'estensione X.509v3 nameConstraints, uno o più directoryName nameConstraints sono presenti in permittedSubtrees e directoryName contiene un attributo organizationName.
3. L'hash è di un subjectPublicKeyInfo che compare in un certificato di firma nella catena di certificati, il certificato di firma ha uno o più attributi organizationName nell'oggetto del certificato e il certificato del server contiene lo stesso numero di attributi organizationName, nello stesso ordine e con valori identici byte per byte.

Un hash subjectPublicKeyInfo viene specificato concatenando il nome dell'algoritmo hash, il carattere "/" e la codifica Base64 di tale algoritmo hash applicata al subjectPublicKeyInfo con codifica DER del certificato specificato. La codifica Base64 è nello stesso formato di un SPKI Fingerprint, come definito in RFC 7469, Sezione 2.4. Gli algoritmi hash non riconosciuti vengono ignorati. L'unico algoritmo hash supportato al momento è "sha256".

Se si disabilita o non si configura questo criterio, i certificati che devono essere divulgati con la trasparenza dei certificati verranno considerati non attendibili se la loro divulgazione non è conforme al criterio di trasparenza dei certificati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CertificateTransparencyEnforcementDisabledForCas
  - Nome Criteri di gruppo: Disabilita l'applicazione della trasparenza dei certificati per un elenco di hash subjectPublicKeyInfo
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\2 = "sha256//////////////////////w=="

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CertificateTransparencyEnforcementDisabledForCas
  - Valore di esempio
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForLegacyCas
  #### Disabilita l'applicazione della trasparenza dei certificati per un elenco di autorità di certificazione legacy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disabilita l'applicazione dei requisiti di trasparenza dei certificati per un elenco di autorità di certificazione legacy.

Questo criterio consente di disabilitare i requisiti di divulgazione della trasparenza dei certificati per le catene di certificati che contengono certificati con uno degli hash subjectPublicKeyInfo specificati. In questo modo, è possibile continuare a usare per gli host aziendali i certificati che altrimenti potrebbero non essere considerati attendibili perché non divulgati in modo adeguato.

Per disabilitare l'applicazione della trasparenza dei certificati, è necessario impostare l'hash su un subjectPublicKeyInfo che compare in un certificato di firma riconosciuto come autorità di certificazione legacy. Un'autorità di certificazione legacy è un'autorità di certificazione considerata pubblicamente attendibile per impostazione predefinita da uno o più sistemi operativi supportati da Microsoft Edge.

Un hash subjectPublicKeyInfo viene specificato concatenando il nome dell'algoritmo hash, il carattere "/" e la codifica Base64 di tale algoritmo hash applicata al subjectPublicKeyInfo con codifica DER del certificato specificato. La codifica Base64 è nello stesso formato di un SPKI Fingerprint, come definito in RFC 7469, Sezione 2.4. Gli algoritmi hash non riconosciuti vengono ignorati. L'unico algoritmo hash supportato al momento è "sha256".

Se non si configura questo criterio, i certificati che devono essere divulgati con la trasparenza dei certificati verranno considerati non attendibili se la loro divulgazione non è conforme al criterio di trasparenza dei certificati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CertificateTransparencyEnforcementDisabledForLegacyCas
  - Nome Criteri di gruppo: Disabilita l'applicazione della trasparenza dei certificati per un elenco di autorità di certificazione legacy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\2 = "sha256//////////////////////w=="

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CertificateTransparencyEnforcementDisabledForLegacyCas
  - Valore di esempio
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForUrls
  #### Disabilita l'applicazione della trasparenza dei certificati per URL specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disabilita l'applicazione dei requisiti di trasparenza dei certificati per gli URL elencati.

Questo criterio consente di non divulgare i certificati per i nomi host negli URL specificati tramite la trasparenza dei certificati. In questo modo, è possibile usare i certificati che altrimenti verrebbero considerati non attendibili, perché non sono stati divulgati in modo adeguato, ma è più difficile rilevare i certificati emessi in modo errato per tali host.

Creare il modello URL in base a [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322). Poiché i certificati sono validi per un determinato nome host, indipendentemente dallo schema, dalla porta o dal percorso, solo la parte del nome host dell'URL viene considerata. Gli host con caratteri jolly non sono supportati.

Se non si configura questo criterio, i certificati che dovrebbero essere divulgati con la trasparenza dei certificati vengono considerati non attendibili se non vengono divulgati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CertificateTransparencyEnforcementDisabledForUrls
  - Nome Criteri di gruppo: Disabilita l'applicazione della trasparenza dei certificati per URL specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\2 = ".contoso.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CertificateTransparencyEnforcementDisabledForUrls
  - Valore di esempio
``` xml
<array>
  <string>contoso.com</string>
  <string>.contoso.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ClearBrowsingDataOnExit
  #### Cancella i dati di esplorazione alla chiusura di Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Microsoft Edge non cancella i dati di esplorazione per impostazione predefinita quando viene chiuso. I dati di esplorazione includono le informazioni inserite nei moduli, le password e persino i siti Web visitati.

Se si abilita questo criterio, tutti i dati di esplorazione vengono eliminati ogni volta che Microsoft Edge viene chiuso. Tenere presente che, se si abilita questo criterio, ha la precedenza rispetto a come è stato configurato [DefaultCookiesSetting](#defaultcookiessetting).

Se si disabilita o non si configura questo criterio, gli utenti possono configurare l'opzione Cancella dati delle esplorazioni in Impostazioni.

Se si abilita questo criterio, non configurare il criterio [AllowDeletingBrowserHistory](#allowdeletingbrowserhistory) o [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) perché gestiscono tutti l'eliminazione dei dati di esplorazione. Se si configurano i criteri precedenti e questo criterio, tutti i dati di esplorazione vengono eliminati quando Microsoft Edge viene chiuso, indipendentemente da come è stato configurato [AllowDeletingBrowserHistory](#allowdeletingbrowserhistory) o [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit).

Per non cancellare i cookie all'uscita, configura i criteri [SaveCookiesOnExit](#savecookiesonexit).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ClearBrowsingDataOnExit
  - Nome Criteri di gruppo: Cancella i dati di esplorazione alla chiusura di Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ClearBrowsingDataOnExit
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ClearBrowsingDataOnExit
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ClearCachedImagesAndFilesOnExit
  #### Cancella le immagini e i file memorizzati nella cache alla chiusura di Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Microsoft Edge non cancella i file e le immagini memorizzati nella cache per impostazione predefinita quando viene chiuso.

Se si abilita questo criterio, i file e le immagini memorizzati nella cache vengono eliminati ogni volta che Microsoft Edge viene chiuso.

Se si disabilita questo criterio, gli utenti non possono configurare l'opzione dei file e delle immagini memorizzati nella cache in edge://settings/clearBrowsingDataOnClose.

Se non si configura questo criterio, gli utenti possono scegliere se cancellare i file e le immagini memorizzati nella cache all'uscita.

Se si disabilita questo criterio, non abilitare il criterio [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) poiché entrambi sono associati all'eliminazione dei dati. Se si configurano entrambi, il criterio [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) ha la precedenza ed elimina tutti i dati quando si chiude Microsoft Edge, indipendentemente da come è configurato [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ClearCachedImagesAndFilesOnExit
  - Nome Criteri di gruppo: Cancella le immagini e i file memorizzati nella cache alla chiusura di Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ClearCachedImagesAndFilesOnExit
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ClearCachedImagesAndFilesOnExit
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ClickOnceEnabled
  #### Consente agli utenti di aprire i file con il protocollo ClickOnce
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Consente agli utenti di aprire i file con il protocollo ClickOnce. Il protocollo ClickOnce consente ai siti Web di richiedere che il browser apra i file da un URL specifico usando il gestore di file ClickOnce nel dispositivo o nel computer dell'utente.

Se si abilita questo criterio, gli utenti possono aprire i file usando il protocollo ClickOnce. Questo criterio sostituisce l'impostazione ClickOnce dell'utente nella pagina edge://flags/.

Se si disabilita questo criterio, gli utenti non possono aprire i file usando il protocollo ClickOnce. Al contrario, il file verrà salvato nel file system tramite il browser. Questo criterio sostituisce l'impostazione ClickOnce dell'utente nella pagina edge://flags/.

Se non si configura questo criterio, gli utenti con versioni di Microsoft Edge precedenti a Microsoft Edge 87 non possono aprire i file usando il protocollo ClickOnce per impostazione predefinita. Tuttavia, essi hanno la possibilità di abilitare l'uso del protocollo ClickOnce con la pagina edge://flags/. Gli utenti con versioni di Microsoft Edge dalla 87 e successive possono aprire i file usando il protocollo ClickOnce, ma hanno la possibilità di disabilitare il protocollo ClickOnce con la pagina edge://flags/.

La disabilitazione di ClickOnce potrebbe impedire l'avvio corretto delle applicazioni ClickOnce (file con estensione .application).

Per altre informazioni su ClickOnce, vedere [https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872) e [https://go.microsoft.com/fwlink/?linkid=2099880](https://go.microsoft.com/fwlink/?linkid=2099880).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ClickOnceEnabled
  - Nome Criteri di gruppo: Consente agli utenti di aprire i file con il protocollo ClickOnce
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ClickOnceEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CollectionsServicesAndExportsBlockList
  #### Blocca l'accesso a un elenco specificato di servizi e di destinazioni di esportazione in Raccolte
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Elenca servizi specifici e destinazioni di esportazione a cui gli utenti non possono accedere nella funzionalità Raccolte in Microsoft Edge. Include anche la visualizzazione di dati aggiuntivi da Bing e l’esportazione di raccolte verso prodotti Microsoft o partner esterni.

Se si abilita questo criterio, i servizi e le destinazioni di esportazione corrispondenti all'elenco specificato vengono bloccati.

Se non si configura questo criterio, non vengono applicate restrizioni ai servizi e destinazioni di esportazione accettabili.

Mapping delle opzioni del criterio:

* pinterest_suggestions (pinterest_suggestions) = Suggerimenti di Pinterest

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CollectionsServicesAndExportsBlockList
  - Nome Criteri di gruppo: Blocca l'accesso a un elenco specificato di servizi e destinazioni di esportazione in Raccolte
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft Edge\CollectionsServicesAndExportsBlockList
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\1 = "pinterest_suggestions"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CollectionsServicesAndExportsBlockList
  - Valore di esempio
``` xml
<array>
  <string>pinterest_suggestions</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CommandLineFlagSecurityWarningsEnabled
  #### Abilita gli avvisi di sicurezza per i contrassegni della riga di comando
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Se disabilitato, questo criterio impedisce la visualizzazione degli avvisi di sicurezza all'avvio di Microsoft Edge con contrassegni della riga di comando potenzialmente pericolosi.

Se abilitato o non configurato, gli avvisi di sicurezza vengono visualizzati quando tali contrassegni della riga di comando vengono usati per avviare Microsoft Edge.

Ad esempio, il contrassegno --disable-gpu-sandbox genera un avviso che informa che è in uso un contrassegno della riga di comando non supportato: --disable-gpu-sandbox. Questo comporta rischi di stabilità e sicurezza.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CommandLineFlagSecurityWarningsEnabled
  - Nome Criteri di gruppo: Abilita gli avvisi di sicurezza per i contrassegni della riga di comando
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: CommandLineFlagSecurityWarningsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CommandLineFlagSecurityWarningsEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ComponentUpdatesEnabled
  #### Abilita gli aggiornamenti dei componenti in Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita o non si configura questo criterio, gli aggiornamenti dei componenti sono abilitati in Microsoft Edge.

Se si disabilita o si imposta su false questo criterio, gli aggiornamenti dei componenti sono disabilitati per tutti i componenti in Microsoft Edge.

Tuttavia, alcuni componenti sono esclusi da questo criterio. Sono inclusi i componenti che non contengono codice eseguibile, che non alterano in modo significativo il comportamento del browser o che sono fondamentali per la sicurezza. In altri termini, gli aggiornamenti che sono considerati "critici per la sicurezza" vengono comunque applicati anche se si disabilita questo criterio.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ComponentUpdatesEnabled
  - Nome Criteri di gruppo: Abilita gli aggiornamenti dei componenti in Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ComponentUpdatesEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ComponentUpdatesEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ConfigureDoNotTrack
  #### Configura Do Not Track
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se inviare richieste Do Not Track ai siti Web che richiedono informazioni di monitoraggio. Le richieste Do Not Track consentono ai siti Web visitati di sapere che l'utente non vuole tenere traccia dell'attività di esplorazione. Per impostazione predefinita, Microsoft Edge non invia richieste Do Not Track, ma gli utenti possono attivare questa funzionalità per inviarle.

Se si abilita questo criterio, vengono sempre inviate richieste Do Not Track ai siti Web che richiedono informazioni di monitoraggio.

Se si disabilita questo criterio, le richieste non vengono mai inviate.

Se non si configura questo criterio, gli utenti possono scegliere se inviare tali richieste.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ConfigureDoNotTrack
  - Nome Criteri di gruppo: Configura Do Not Track
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ConfigureDoNotTrack
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ConfigureDoNotTrack
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ConfigureOnPremisesAccountAutoSignIn
  #### Configura l'accesso automatico con un account di dominio Active Directory quando non esiste un account di dominio Azure AD
  
  
  #### Versioni supportate:
  - In Windows dalla versione 81 o successive

  #### Descrizione
  Abilita l'uso degli account Active Directory per l'accesso automatico se i computer degli utenti sono aggiunti a un dominio e se l'ambiente non è aggiunto ad Azure AD ibrido. Se invece si desidera che gli utenti accedano automaticamente con l'account Azure Active Directory, aggiungere l'ambiente ad Azure AD (vedere [https://go.microsoft.com/fwlink/?linkid=2118197](https://go.microsoft.com/fwlink/?linkid=2118197) per altre informazioni) o ad Azure AD ibrido (vedere [https://go.microsoft.com/fwlink/?linkid=2118365](https://go.microsoft.com/fwlink/?linkid=2118365) per altre informazioni).

Se il criterio [BrowserSignin](#browsersignin) è disabilitato, questo criterio non avrà alcun effetto.

Se si abilita questo criterio e lo si imposta su "SignInAndMakeDomainAccountNonRemovable”, Microsoft Edge eseguirà automaticamente l’accesso degli utenti che usano computer aggiunti al dominio tramite gli account Active Directory.

Se si imposta questo criterio su “Disabilitato” o non lo si imposta, Microsoft Edge non eseguirà automaticamente l’accesso degli utenti che usano computer aggiunti al dominio con account Active Directory.

Mapping delle opzioni del criterio:

* Disabilitato (0) = Disabilitato

* SignInAndMakeDomainAccountNonRemovable (1) = Accede e rende l’account di dominio non rimovibile

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ConfigureOnPremisesAccountAutoSignIn
  - Nome Criteri di gruppo: Configura l'accesso automatico con un account di dominio Active Directory quando non esiste un account di dominio Azure AD
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ConfigureOnPremisesAccountAutoSignIn
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ConfigureOnlineTextToSpeech
  #### Configura la sintesi vocale online
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Indica se il browser può sfruttare i caratteri voce della sintesi vocale online, parte dei Servizi cognitivi Azure. Questi caratteri voce sono di qualità superiore rispetto ai caratteri voce di sistema predefiniti.

Se si abilita o non si configura questo criterio, le applicazioni basate sul Web che usano l'API SpeechSynthesis possono utilizzare i caratteri voce della sintesi vocale online.

Se si disabilita questo criterio, i caratteri voce non sono disponibili.

Sono disponibili altre informazioni su questa funzionalità qui: API SpeechSynthesis: [https://go.microsoft.com/fwlink/?linkid=2110038](https://go.microsoft.com/fwlink/?linkid=2110038) Servizi cognitivi: [https://go.microsoft.com/fwlink/?linkid=2110141](https://go.microsoft.com/fwlink/?linkid=2110141)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ConfigureOnlineTextToSpeech
  - Nome Criteri di gruppo: Configura la sintesi vocale online
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ConfigureOnlineTextToSpeech
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ConfigureOnlineTextToSpeech
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ConfigureShare
  #### Configura l'esperienza di condivisione
  
  
  #### Versioni supportate:
  - In Windows dalla versione 83 o successive

  #### Descrizione
  Se si imposta questo criterio su "ShareAllowed" (impostazione predefinita), gli utenti potranno accedere all'esperienza di condivisione di Windows 10 da Impostazioni e dal menu Altro in Microsoft Edge per condividere contenuti con altre app nel sistema.

Se si imposta questo criterio su "ShareDisallowed", gli utenti non potranno accedere all'esperienza di condivisione di Windows 10. Se il pulsante Condividi è nella barra degli strumenti, verrà nascosto.

Mapping delle opzioni del criterio:

* ShareAllowed (0) = Consentire di usare l'esperienza di condivisione

* ShareDisallowed (1) = Non consentire di usare l'esperienza di condivisione

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ConfigureShare
  - Nome Criteri di gruppo: Configura l'esperienza di condivisione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ConfigureShare
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### CustomHelpLink
  #### Specifica il collegamento alla guida personalizzato
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Specifica un collegamento per il menu ? o il tasto F1.

Se si abilita questo criterio, un amministratore può specificare un collegamento per il menu ? o il tasto F1.

Se si disabilita o non si configura questo criterio, viene usato il collegamento predefinito per il menu ? o il tasto F1.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: CustomHelpLink
  - Nome Criteri di gruppo: Specifica il collegamento alla guida personalizzato
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: CustomHelpLink
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://go.microsoft.com/fwlink/?linkid=2080734"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: CustomHelpLink
  - Valore di esempio
``` xml
<string>https://go.microsoft.com/fwlink/?linkid=2080734</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DNSInterceptionChecksEnabled
  #### Controlli dell'intercettazione DNS abilitati
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Questo criterio configura un interruttore locale che consente di disabilitare i controlli di intercettazione DNS. Questi controlli tentano di individuare se il browser si trova dietro un proxy che reindirizza nomi host sconosciuti.

Questo rilevamento potrebbe non essere necessario in un ambiente aziendale in cui la configurazione di rete è nota. Può essere disabilitato per evitare ulteriore traffico DNS e HTTP all'avvio e a ogni modifica della configurazione del DNS.

Se si abilita o non si imposta questo criterio, i controlli di intercettazione DNS vengono eseguiti.

Se si disabilita questo criterio, i controlli di intercettazione DNS non vengono eseguiti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DNSInterceptionChecksEnabled
  - Nome Criteri di gruppo: Controlli dell'intercettazione DNS abilitati
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DNSInterceptionChecksEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DNSInterceptionChecksEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultBrowserSettingEnabled
  #### Imposta Microsoft Edge come browser predefinito
  
  
  #### Versioni supportate:
  - In Windows 7 e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita questo criterio su true, Microsoft Edge controlla sempre se si tratta del browser predefinito all’avvio e, se possibile, lo registra automaticamente.

Se si imposta questo criterio su falso, Microsoft Edge non controlla se si tratta dell'impostazione predefinita e disattiva i controlli utente per questa opzione.

Se non si imposta questo criterio, Microsoft Edge consente agli utenti di controllare se si tratta dell'impostazione predefinita e, in caso contrario, se devono essere visualizzate le notifiche degli utenti.

Nota per gli amministratori di Windows: questo criterio funziona solo per i PC che eseguono Windows 7. Per le versioni più recenti di Windows, è necessario distribuire un file di "associazioni delle applicazioni predefinite" che rende Microsoft Edge il gestore per i protocolli HTTPS e HTTP (e, facoltativamente, il protocollo ftp e i formati di file come .html, .htm, .pdf, .svg, .webp). Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2094932](https://go.microsoft.com/fwlink/?linkid=2094932).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultBrowserSettingEnabled
  - Nome Criteri di gruppo: Imposta Microsoft Edge come browser predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultBrowserSettingEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultBrowserSettingEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSearchProviderContextMenuAccessAllowed
  #### Consente l’accesso al menu di scelta rapida del provider di ricerca predefinito 
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Consente di usare un provider di ricerca predefinito nel menu di scelta rapida.

Se si imposta questo criterio su disabilitato, la voce del menu di scelta rapida che si basa sul provider di ricerca predefinito e sulla ricerca della barra laterale non sarà disponibile.

Se questo criterio è impostato su abilitato o non impostato, la voce del menu di scelta rapida per il provider di ricerca predefinito e per la ricerca della barra laterale sarà disponibile.

Il valore del criterio viene applicato solo quando il criterio [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) è abilitato; in caso contrario, non è applicabile.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSearchProviderContextMenuAccessAllowed
  - Nome Criteri di gruppo: consente l’accesso al menu di scelta rapida del provider di ricerca predefinito
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultSearchProviderContextMenuAccessAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSearchProviderContextMenuAccessAllowed
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSensorsSetting
  #### Impostazione predefinita per i sensori
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Specificare se i siti Web possono accedere e usare sensori come i sensori di movimento e di luce. È possibile bloccare o consentire completamente l'accesso dei siti Web ai sensori.

Impostando il criterio su 1 si consente ai siti Web di accedere ai sensori e usarli. Impostando il criterio su 2 si nega l'accesso ai sensori.

È possibile sostituire questo criterio per modelli URL specifici usando i criteri [SensorsAllowedForUrls](#sensorsallowedforurls) e [SensorsBlockedForUrls](#sensorsblockedforurls).

Se non si configura questo criterio, i siti Web possono accedere ai sensori e usarli e gli utenti possono modificare tale impostazione. Questo è il valore globale predefinito per [SensorsAllowedForUrls](#sensorsallowedforurls) e [SensorsBlockedForUrls](#sensorsblockedforurls).

Mapping delle opzioni del criterio:

* AllowSensors (1) = consenti ai siti di accedere ai sensori

* BlockSensors (2) = non consentire ad alcun sito di accedere ai sensori

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultPopupsSetting
  - Nome Criteri di gruppo: Impostazione predefinita per i sensori
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultSensorsSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSensorsSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DefaultSerialGuardSetting
  #### Controlla l'uso di Serial API
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Specificare se i siti Web possono accedere alle porte seriali. È possibile bloccare completamente l'accesso o chiedere conferma all'utente ogni volta che un sito Web vuole accedere a una porta seriale.

L'impostazione del criterio su 3 consente ai siti Web di richiedere l'accesso alle porte seriali. Impostando il criterio su 2 si nega l'accesso alle porte seriali.

È possibile sostituire questo criterio per modelli URL specifici usando i criteri [SerialAskForUrls](#serialaskforurls) and [SerialBlockedForUrls](#serialblockedforurls).

Se non si configura questo criterio, per impostazione predefinita i siti possono chiedere agli utenti se è possibile accedere a una porta seriale e gli utenti possono modificare questa impostazione.

Mapping delle opzioni del criterio:

* BlockSerial (2) = non consentire ad alcun sito di richiedere l'accesso alle porte seriali tramite Serial API

* AskSerial (3) = consenti ai siti di richiedere l'autorizzazione dell'utente per accedere a una porta seriale

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DefaultSerialGuardSetting
  - Nome Criteri di gruppo: controlla l'uso di Serial API
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DefaultSerialGuardSetting
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DefaultSerialGuardSetting
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DelayNavigationsForInitialSiteListDownload
  #### Richiede che l'elenco siti in modalità Enterprise sia disponibile prima dello spostamento tramite schede.
  
  
  #### Versioni supportate:
  - In Windows dalla versione 84 o successive

  #### Descrizione
  Consente di specificare se le schede Microsoft Edge attendono lo spostamento finché il browser non avrà scaricato l'elenco iniziale dei siti in modalità Enterprise. Questa opzione viene usata in scenari in cui la Home page del browser deve essere caricata in modalità Internet Explorer ed è importante che venga prima eseguita nel browser dopo l'abilitazione della modalità Internet Explorer. Se questo scenario non esiste, è consigliabile non abilitare questa opzione perché può influire negativamente sulle prestazioni del caricamento della Home page. L'impostazione viene applicata solo se Microsoft Edge non dispone di un elenco dei siti in modalità aziendale memorizzato nella cache, ad esempio quando si esegue il primo browser dopo l'abilitazione della modalità Internet Explorer.

Questa impostazione funziona in combinazione con i criteri: [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) impostato su "IEMode e [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist), in cui l'elenco ha almeno una voce.

Il comportamento di timeout di questo criterio può essere configurato con il criterio [NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout).

Se si imposta questo criterio su “All”, quando Microsoft Edge non dispone di una versione memorizzata nella cache dell'elenco dei siti in modalità Enterprise, le tabulazioni ritarderanno lo spostamento finché il browser non avrà scaricato l'elenco dei siti. I siti configurati per l'apertura in modalità Internet Explorer dall'elenco dei siti vengono caricati in modalità di Internet Explorer, anche durante la navigazione iniziale del browser. Siti che non possono essere configurati per l'apertura in Internet Explorer, come siti con uno schema diverso da http:, https:, file:, or ftp: non ritardare l'esplorazione e il caricamento immediato in modalità Microsoft Edge.

Se si imposta questo criterio su “None” o non lo si configura, quando Microsoft Edge non dispone di una versione memorizzata nella cache dell'elenco dei siti in modalità Enterprise, le tabulazioni verranno spostate immediatamente e non attenderanno che il browser scarichi l'elenco dei siti in modalità Enterprise. I siti configurati per l'apertura in modalità di Internet Explorer dall'elenco sito verranno aperti in modalità Microsoft Edge finché il browser non avrà terminato il download dell'elenco dei siti in modalità Enterprise.

Mapping delle opzioni del criterio:

* None (0) = Nessuno

* All (1) = Tutti gli spostamenti idonei

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DelayNavigationsForInitialSiteListDownload
  - Nome Criteri di gruppo: richiede che l'elenco siti in modalità Enterprise sia disponibile prima dello spostamento tramite schede.
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DelayNavigationsForInitialSiteListDownload
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DeleteDataOnMigration
  #### Elimina i dati del browser obsoleti alla migrazione
  
  
  #### Versioni supportate:
  - In Windows dalla versione 83 o successive

  #### Descrizione
  Questo criterio determina se i dati di esplorazione dell'utente della Versione legacy di Microsoft Edge verranno eliminati dopo la migrazione a Microsoft Edge versione 81 o successiva.

Se si imposta questo criterio su "Abilitato", tutti i dati di esplorazione della Versione legacy di Microsoft Edge dopo la migrazione a Microsoft Edge versione 81 o successiva verranno eliminati. Questo criterio deve essere impostato prima della migrazione a Microsoft Edge versione 81 o successiva per avere effetti sui dati di esplorazione esistenti.

Se si imposta questo criterio su "Disabilitato" o se il criterio non viene configurato, i dati di esplorazione dell'utente non vengono eliminati dopo la migrazione a Microsoft Edge versione 83 o successiva.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DeleteDataOnMigration
  - Nome Criteri di gruppo: Elimina i dati del browser obsoleti alla migrazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DeleteDataOnMigration
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DeveloperToolsAvailability
  #### Controlla dove si possono usare gli strumenti di sviluppo
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla dove si possono usare gli strumenti di sviluppo.

Se si imposta questo criterio su "DeveloperToolsDisallowedForForceInstalledExtensions" (impostazione predefinita), gli utenti possono accedere agli strumenti di sviluppo e alla console di JavaScript in generale, ma non nel contesto delle estensioni installate dai criteri aziendali.

Se si imposta questo criterio su "DeveloperToolsAllowed", gli utenti possono accedere agli strumenti di sviluppo e alla console di JavaScript in qualsiasi contesto, comprese le estensioni installate dai criteri aziendali.

Se si imposta questo criterio su "DeveloperToolsDisallowed", gli utenti non possono accedere agli strumenti di sviluppo o esaminare gli elementi del sito Web. I menu e i tasti di scelta rapida o le voci di menu a comparsa che aprono gli strumenti di sviluppo o la console di JavaScript sono disabilitati.

Mapping delle opzioni del criterio:

* DeveloperToolsDisallowedForForceInstalledExtensions (0) = Bloccare gli strumenti di sviluppo nelle estensioni installate da criteri aziendali, consentirli in altri contesti

* DeveloperToolsAllowed (1) = Consentire di usare gli strumenti di sviluppo

* DeveloperToolsDisallowed (2) = Non consentire di usare gli strumenti di sviluppo

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DeveloperToolsAvailability
  - Nome Criteri di gruppo: Controlla dove si possono usare gli strumenti di sviluppo
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DeveloperToolsAvailability
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DeveloperToolsAvailability
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DiagnosticData
  #### Invia dati di diagnostica necessari e facoltativi sull'uso del browser
  
  
  #### Versioni supportate:
  - In Windows 7 e macOS dalla versione 86 o successive

  #### Descrizione
  Questo criterio controlla l'invio a Microsoft dei dati di diagnostica necessari e facoltativi relativi all'utilizzo del browser.

I dati di diagnostica necessari raccolti fanno in modo che Microsoft Edge rimanga sicuro, aggiornato e funzioni come previsto.

I dati di diagnostica facoltativi includono i dati sull'uso del browser, i siti Web visitati e i report di arresto anomalo di Microsoft in modo da migliorare il prodotto e il servizio.

Questo criterio non è supportato nei dispositivi Windows 10. Per controllare la raccolta di dati in Windows 10, gli amministratori IT devono usare i criteri di gruppo dati di diagnostica Windows. Questo criterio può essere sia "Consenti telemetria" o "Consenti dati di diagnostica", a seconda della versione di Windows in uso. Ulteriori informazioni sulla raccolta dei dati di diagnostica Windows 10: [https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

Per configurare il criterio, usa una delle opzioni seguenti:

“Disattivato” disattiva la raccolta di dati diagnostica obbligatoria e facoltativa. Questa opzione non è consigliata.

"RequiredData" invia i dati di diagnostica necessari, ma disattiva la raccolta di dati diagnostica facoltativa. Microsoft Edge invia i dati di diagnostica necessari in modo che Microsoft Edge rimanga sicuro, aggiornato e funzioni come previsto.

"OptionalData" invia i dati di diagnostica facoltativi includendo i dati sull'utilizzo del browser, i siti Web visitati, i report di arresto anomalo inviati a Microsoft per migliorare il prodotto e il servizio.

In Windows 7/macOS questo criterio controlla l'invio di dati obbligatori e facoltativi a Microsoft.

Se non configuri o disattivi questo criterio, Microsoft Edge lo applicherà come impostazione predefinita per le preferenze degli utenti.

Mapping delle opzioni del criterio:

* Disattivato (0) = disattivato (non consigliato)

* RequiredData (1) = dati obbligatori

* OptionalData (2) = dati facoltativi

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco GP: DiagnosticData
  - Nome criteri di gruppo: Invia dati di diagnostica necessari e facoltativi sull'uso del browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DiagnosticData
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: DiagnosticData
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DirectInvokeEnabled
  #### Consente agli utenti di aprire i file con il protocollo DirectInvoke
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Consente agli utenti di aprire i file con il protocollo DirectInvoke. Il protocollo DirectInvoke consente ai siti Web di richiedere che il browser apra i file da un URL specifico usando un gestore di file specifico nel dispositivo o nel computer dell'utente.

Se si abilita o non si configura questo criterio, gli utenti possono aprire i file usando il protocollo DirectInvoke.

Se si disabilita questo criterio, gli utenti non possono aprire i file usando il protocollo DirectInvoke. Al contrario, il file verrà salvato nel file system.

Nota: la disabilitazione di DirectInvoke potrebbe impedire il corretto funzionamento di alcune funzionalità di Microsoft SharePoint Online.

Per altre informazioni su DirectInvoke, vedere [https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872) e [https://go.microsoft.com/fwlink/?linkid=2099871](https://go.microsoft.com/fwlink/?linkid=2099871).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DirectInvokeEnabled
  - Nome Criteri di gruppo: Consente agli utenti di aprire i file con il protocollo DirectInvoke
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DirectInvokeEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### Disable3DAPIs
  #### Disabilita il supporto per le API di grafica 3D
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impedisce alle pagine Web di accedere all'unità di elaborazione grafica (GPU). In particolare, le pagine Web non possono accedere all'API WebGL e i plug-in non possono usare l'API Pepper 3D.

Se si disabilita o non si configura questo criterio, è possibile che le pagine Web utilizzino l'API WebGL e che i plug-in utilizzino l'API Pepper 3D. Per impostazione predefinita, Microsoft Edge potrebbe continuare a richiedere argomenti della riga di comando per utilizzare queste API.

Se il criterio [HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled) è impostato su false, l'impostazione per il criterio "Disable3DAPIs" viene ignorata (equivale all'impostazione del criterio "Disable3DAPIs" su true).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: Disable3DAPIs
  - Nome Criteri di gruppo: Disabilita il supporto per le API di grafica 3D
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: Disable3DAPIs
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: Disable3DAPIs
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DisableScreenshots
  #### Disabilita l'acquisizione di screenshot
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se l'utente può acquisire screenshot della pagina del browser.

Se abilitato, l'utente non può acquisire screenshot tramite i tasti di scelta rapida o le API delle estensioni.

Se si disabilita o non si configura questo criterio, gli utenti possono acquisire screenshot.

Tenere presente che questo criterio controlla gli screenshot acquisiti all'interno del browser. Anche se si abilita questo criterio, gli utenti potrebbero comunque acquisire screenshot attraverso dei metodi esterni al browser (come l'uso di una funzionalità del sistema operativo o di un'altra applicazione).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DisableScreenshots
  - Nome Criteri di gruppo: Disabilita l'acquisizione di screenshot
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DisableScreenshots
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DisableScreenshots
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DiskCacheDir
  #### Imposta la directory della cache del disco
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura la directory da usare per archiviare i file memorizzati nella cache.

Se si abilita questo criterio, Microsoft Edge usa la directory fornita indipendentemente dal fatto che l'utente abbia specificato il contrassegno "--disk-cache-dir". Per evitare perdite di dati o altri errori imprevisti, non configurare questo criterio su una directory radice di un volume o su una directory utilizzata per altri scopi, perché Microsoft Edge ne gestisce il contenuto.

Per un elenco delle variabili che è possibile usare quando si specificano directory e percorsi, vedere [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041).

Se non si configura questo criterio, viene usata la directory della cache predefinita e gli utenti possono ignorare tale impostazione predefinita con il contrassegno della riga di comando "--disk-cache-dir".

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DiskCacheDir
  - Nome Criteri di gruppo: Imposta la directory della cache del disco
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DiskCacheDir
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"${user_home}/Edge_cache"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DiskCacheDir
  - Valore di esempio
``` xml
<string>${user_home}/Edge_cache</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DiskCacheSize
  #### Imposta le dimensioni della cache del disco, in byte
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura le dimensioni della cache, in byte, utilizzata per archiviare i file nel disco.

Se si abilita questo criterio, Microsoft Edge usa le dimensioni della cache fornite indipendentemente dal fatto che l'utente abbia specificato il contrassegno "--disk-cache-size". Il valore specificato in questo criterio non è un limite rigido, ma piuttosto un suggerimento per il sistema di memorizzazione nella cache; qualsiasi valore inferiore ad alcuni megabyte è troppo basso e verrà arrotondato per eccesso a un minimo ragionevole.

Se si imposta il valore di questo criterio su 0, vengono usate le dimensioni della cache predefinite e gli utenti non possono modificarle.

Se non si configura questo criterio, vengono usate le dimensioni predefinite, ma gli utenti possono ignorarle con il contrassegno "--disk-cache-size".

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DiskCacheSize
  - Nome Criteri di gruppo: Imposta le dimensioni della cache del disco, in byte
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DiskCacheSize
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x06400000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DiskCacheSize
  - Valore di esempio
``` xml
<integer>104857600</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DnsOverHttpsMode
  #### Controlla la modalità del protocollo DNS-over-HTTPS
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Controlla la modalità del resolver DNS-over-HTTPS. Questo criterio imposta la modalità predefinita solo per ogni query. La modalità può essere ignorata per tipi di query speciali, ad esempio richieste di risolvere un nome host del server DNS-over-HTTPS.

La modalità "off" disabilita DNS-over-HTTPS.

La modalità "automatic" invia prima query DNS-over-HTTPS se un server DNS-over-HTTPS è disponibile e potrebbe eseguire il fallback per l'invio di query non protette in caso di errore.

La modalità "secure" invia solo query DNS-over-HTTPS e non risolve in caso di errore.

Se non si configura questo criterio, il browser potrebbe inviare richieste DNS-over-HTTPS a un resolver associato al resolver di sistema configurato dell'utente.

Mapping delle opzioni del criterio:

* off (off) = Disabilita DNS-over-HTTPS

* automatic (automatic) = Abilita DNS-over-HTTPS con fallback insicuro

* secure (secure) = Abilita DNS-over-HTTPS senza fallback insicuro

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DnsOverHttpsMode
  - Nome Criteri di gruppo: Controlla la modalità del protocollo DNS-over-HTTPS
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DnsOverHttpsMode
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"off"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DnsOverHttpsMode
  - Valore di esempio
``` xml
<string>off</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DnsOverHttpsTemplates
  #### Specifica il modello URI del resolver DNS-over-HTTPS desiderato
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Specifica il modello URI del resolver DNS-over-HTTPS desiderato. Per specificare più resolver DNS-over-HTTPS, separare i modelli URI corrispondenti con spazi.

Se si imposta [DnsOverHttpsMode](#dnsoverhttpsmode) su "secure", questo criterio deve essere impostato e non può rimanere vuoto.

Se si imposta [DnsOverHttpsMode](#dnsoverhttpsmode) su "automatic" e questo criterio è impostato, verranno usati i modelli URI specificati. Se non si imposta questo criterio, i mapping hardcoded verranno usati per tentare di aggiornare il resolver DNS corrente dell'utente su un resolver DoH gestito dallo stesso provider.

Se il modello URI contiene una variabile dns, le richieste al resolver useranno GET; in caso contrario, le richieste useranno POST.

I modelli formattati in modo non corretto verranno ignorati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DnsOverHttpsTemplates
  - Nome Criteri di gruppo: Specifica il modello URI del resolver DNS-over-HTTPS desiderato
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: DnsOverHttpsTemplates
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://dns.example.net/dns-query{?dns}"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DnsOverHttpsTemplates
  - Valore di esempio
``` xml
<string>https://dns.example.net/dns-query{?dns}</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DownloadDirectory
  #### Imposta la directory di download
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura la directory da usare quando si scaricano i file.

Se si abilita questo criterio, Microsoft Edge usa la directory fornita indipendentemente dal fatto che l'utente ne abbia specificata una o abbia scelto di dover specificare ogni volta il percorso di download. Per un elenco delle variabili che è possibile usare, vedere [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041).

Se si disabilita o non si configura questo criterio, viene usata la directory di download predefinita e l'utente può modificarla.

Se si imposta un percorso non valido, per impostazione predefinita Microsoft Edge userà la directory di download predefinita dell'utente.

Se la cartella specificata dal percorso non esiste, il download attiverà una richiesta che chiede all'utente dove desidera salvare il download.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DownloadDirectory
  - Nome Criteri di gruppo: Imposta la directory di download
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DownloadDirectory
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"\n      Linux-based OSes (including Mac): /home/${user_name}/Downloads\n      Windows: C:\\Users\\${user_name}\\Downloads"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DownloadDirectory
  - Valore di esempio
``` xml
<string>
      Linux-based OSes (including Mac): /home/${user_name}/Downloads
      Windows: C:\Users\${user_name}\Downloads</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### DownloadRestrictions
  #### Consente le restrizioni per il download
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura il tipo di download che Microsoft Edge blocca completamente, senza consentire agli utenti di ignorare la decisione relativa alla sicurezza.

Impostare "BlockDangerousDownloads" per consentire tutti i download tranne quelli che attivano avvisi di Microsoft Defender SmartScreen.

Impostare "BlockPotentiallyDangerousDownloads” per consentire tutti i download tranne quelli che attivano avvisi di Microsoft Defender SmartScreen per download potenzialmente pericolosi o indesiderati.

Impostare "BlockAllDownloads" per bloccare tutti i download.

Se non si configura questo criterio o si imposta l'opzione "DefaultDownloadSecurity”, i download vengono sottoposti alle solite restrizioni di sicurezza in base ai risultati dell'analisi di Microsoft Defender SmartScreen.

Queste restrizioni si applicano ai download dal contenuto delle pagine Web, oltre all'opzione di menu a comparsa "Collegamento di download...". Queste restrizioni non si applicano al salvataggio o al download della pagina attualmente visualizzata, né si applicano all'opzione Salva come PDF dalle opzioni di stampa.

Per altre informazioni su Microsoft Defender SmartScreen, vedere [https://go.microsoft.com/fwlink/?linkid=2094934](https://go.microsoft.com/fwlink/?linkid=2094934).

Mapping delle opzioni del criterio:

* DefaultDownloadSecurity (0) = Nessuna speciale restrizione

* BlockDangerousDownloads (1) = Bloccare download pericolosi

* BlockPotentiallyDangerousDownloads (2) = Bloccare download potenzialmente pericolosi o indesiderati

* BlockAllDownloads (3) = Bloccare tutti i download

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: DownloadRestrictions
  - Nome Criteri di gruppo: Consente le restrizioni per il download
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: DownloadRestrictions
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: DownloadRestrictions
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EdgeCollectionsEnabled
  #### Abilita la funzionalità Raccolte
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Permette di consentire agli utenti di accedere alla funzionalità Raccolte, dove è possibile raccogliere, organizzare, condividere ed esportare contenuti in modo più efficiente e con l'integrazione di Office.

Se si abilita o non si configura questo criterio, gli utenti possono accedere alla funzionalità Raccolte in Microsoft Edge.

Se si disabilita questo criterio, gli utenti non possono accedere a Raccolte in Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EdgeCollectionsEnabled
  - Nome Criteri di gruppo: Abilita la funzionalità Raccolte
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EdgeCollectionsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EdgeCollectionsEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EditFavoritesEnabled
  #### Consente agli utenti di modificare i Preferiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilitare questo criterio per consentire agli utenti di aggiungere, rimuovere e modificare i Preferiti. Questo è il comportamento predefinito se non si configura questo criterio.

Disabilitare questo criterio per impedire agli utenti di aggiungere, rimuovere o modificare i Preferiti. Possono continuare a usare i Preferiti esistenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EditFavoritesEnabled
  - Nome Criteri di gruppo: Consente agli utenti di modificare i Preferiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EditFavoritesEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EditFavoritesEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnableDeprecatedWebPlatformFeatures
  #### Riabilita le funzionalità della piattaforma Web deprecate per un periodo di tempo limitato
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica un elenco di funzionalità della piattaforma Web deprecate da riabilitare temporaneamente.

Questo criterio consente di riabilitare le funzionalità della piattaforma Web deprecate per un periodo di tempo limitato. Le funzionalità sono identificate da un contrassegno stringa.

Se non si configura questo criterio, se l'elenco è vuoto o se una funzionalità non corrisponde a uno dei contrassegni stringa supportati, tutte le funzionalità della piattaforma Web deprecate rimangono disabilitate.

Il criterio è supportato nelle piattaforme di cui sopra, ma la funzionalità da abilitare potrebbe non essere disponibile in tutte quelle piattaforme. Non tutte le funzionalità della piattaforma Web deprecate possono essere riabilitate. Solo quelle indicate in modo esplicito di seguito possono essere riabilitate e solo per un periodo di tempo limitato, che varia a seconda della funzionalità. È possibile rivedere l'intento alla base delle modifiche alle funzionalità della piattaforma Web qui: https://bit.ly/blinkintents.

Il formato generale del contrassegno stringa è [DeprecatedFeatureName]_EffectiveUntil[yyyymmdd].

Mapping delle opzioni del criterio:

* ExampleDeprecatedFeature (ExampleDeprecatedFeature_EffectiveUntil20080902) = Abilitare l'API ExampleDeprecatedFeature fino al 02/09/2008

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnableDeprecatedWebPlatformFeatures
  - Nome Criteri di gruppo: Riabilita le funzionalità della piattaforma Web deprecate per un periodo di tempo limitato
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures\1 = "ExampleDeprecatedFeature_EffectiveUntil20080902"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnableDeprecatedWebPlatformFeatures
  - Valore di esempio
``` xml
<array>
  <string>ExampleDeprecatedFeature_EffectiveUntil20080902</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnableDomainActionsDownload
  #### Abilita il download delle azioni di dominio da Microsoft (obsoleto)
  
  >OBSOLETO: questo criterio è obsoleto e non funziona dopo Microsoft Edge 84.
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77, fino alla versione 84

  #### Descrizione
  Questo criterio non funziona perché è consigliabile evitare stati conflittuali. Questo criterio è usato per abilitare/disabilitare il download dell'elenco di azioni del dominio, ma non sempre consentiva di ottenere lo stato desiderato. Il servizio di sperimentazione e configurazione, che gestisce il download, ha il proprio criterio per configurare cosa viene scaricato dal servizio. Usare invece il criterio [ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol).

In Microsoft Edge, le azioni del dominio rappresentano una serie di funzionalità di compatibilità che consentono al browser di funzionare correttamente sul Web.

Microsoft conserva un elenco di azioni da eseguire in determinati domini per motivi di compatibilità. Ad esempio, il browser potrebbe ignorare la stringa agente utente in un sito Web se tale sito Web è interrotto a causa della nuova stringa agente utente in Microsoft Edge. Ognuna di queste azioni deve essere temporanea mentre Microsoft tenta di risolvere il problema con il proprietario del sito.

Quando il browser viene avviato e poi periodicamente, il browser contatterà il servizio di sperimentazione e configurazione che contiene l'elenco più aggiornato delle azioni di compatibilità da eseguire. Questo elenco viene salvato in locale dopo che viene recuperato in modo che le richieste successive aggiornino l'elenco solo se la copia del server è cambiata.

Se si abilita questo criterio, l'elenco delle azioni del dominio continuerà a essere scaricato dal servizio di sperimentazione e configurazione.

Se si disabilita questo criterio, l'elenco delle azioni del dominio non verrà più scaricato dal servizio di sperimentazione e configurazione.

Se non si configura questo criterio, l'elenco delle azioni del dominio continuerà a essere scaricato dal servizio di sperimentazione e configurazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnableDomainActionsDownload
  - Nome Criteri di gruppo: Abilita il download delle azioni di dominio da Microsoft (obsoleto)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnableDomainActionsDownload
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnableDomainActionsDownload
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnableOnlineRevocationChecks
  #### Abilita i controlli OCSP/CRL online
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  I controlli di revoca online non forniscono vantaggi significativi per la sicurezza e sono disabilitati per impostazione predefinita.

Se si abilita questo criterio, Microsoft Edge eseguirà controlli online OCSP/CRL "soft-fail". "Soft fail" significa che, se il server di revoca non può essere raggiunto, il certificato verrà considerato valido.

Se si disabilita o non si configura il criterio, Microsoft Edge non eseguirà i controlli di revoca online.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnableOnlineRevocationChecks
  - Nome Criteri di gruppo: Abilita i controlli OCSP/CRL online
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnableOnlineRevocationChecks
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnableOnlineRevocationChecks
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnableSha1ForLocalAnchors
  #### Consente certificati firmati SHA-1 quando sono emessi da trust anchor locali (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Se questa impostazione è abilitata, Microsoft Edge consente le connessioni protette da certificati firmati SHA-1, purché il certificato sia concatenato a un certificato radice installato localmente e sia altrimenti valido. 

Si noti che questo criterio dipende dallo stack di verifica dei certificati del sistema operativo (OS) che consente le firme SHA-1. Se un aggiornamento del sistema operativo modifica la gestione dei certificati SHA-1 da parte del sistema operativo, questo criterio potrebbe non avere più effetto.  Inoltre, questo criterio è inteso come soluzione alternativa temporanea per dare alle organizzazioni più tempo per allontanarsi da SHA-1. Questo criterio verrà rimosso al rilascio di Microsoft Edge 92 a metà 2021.

Se non si imposta questo criterio o lo si imposta su falso, oppure se il certificato SHA-1 è concatenato a una radice del certificato pubblicamente attendibile, Microsoft Edge non consentirà i certificati firmati SHA-1.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnableSha1ForLocalAnchors
  - Nome Criteri di gruppo: Consente certificati firmati SHA-1 quando sono emessi da trust anchor locali (deprecato) 
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnableSha1ForLocalAnchors
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnableSha1ForLocalAnchors
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnterpriseHardwarePlatformAPIEnabled
  #### Consente alle estensioni gestite di usare l'API Enterprise Hardware Platform
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Quando questo criterio è abilitato, le estensioni installate dai criteri aziendali possono utilizzare l'API Enterprise Hardware Platform.
Quando questo criterio è disabilitato o non impostato, nessuna estensione potrà usare l'API Enterprise Hardware Platform.
Questo criterio si applica anche alle estensioni del componente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnterpriseHardwarePlatformAPIEnabled
  - Nome Criteri di gruppo: Consente alle estensioni gestite di usare l'API Enterprise Hardware Platform
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnterpriseHardwarePlatformAPIEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: EnterpriseHardwarePlatformAPIEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### EnterpriseModeSiteListManagerAllowed
  #### Consente l’accesso allo strumento Enterprise Mode Site List Manager
  
  
  #### Versioni supportate:
  - In Windows dalla versione 86 o successive

  #### Descrizione
  Consente di impostare se Enterprise Mode Site List Manager è disponibile per gli utenti.

Se si abilita questo criterio, gli utenti possono visualizzare il pulsante di spostamento di Enterprise Mode Site List Manager sulla pagina edge://compat, passare allo strumento e usarlo.

Se si disabilita o non si configura questo criterio, gli utenti non visualizzeranno il pulsante di spostamento di Enterprise Mode Site List Manager e non saranno in grado di usarlo.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: EnterpriseModeSiteListManagerAllowed
  - Nome Criteri di gruppo: Consente l’accesso allo strumento Enterprise Mode Site List Manager
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: EnterpriseModeSiteListManagerAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  #### Disabilita gli avvisi di download basati sull'estensione del tipo di file per i tipi di file specificati nei domini
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  È possibile abilitare questo criterio per creare un dizionario di estensioni di file con un elenco di domini corrispondente che verrà escluso dagli avvisi di download basati sull'estensione del tipo di file. In questo modo gli amministratori dell'organizzazione possono bloccare gli avvisi di download basati sulle estensioni dei file associati a un dominio elencato. Ad esempio, se l'estensione “jnlp” è associata a "website1.com", gli utenti non vedranno un avviso durante il download di file “jnlp” da “website1.com”, ma l'avviso di download viene visualizzato quando si scaricano i file “jnlp” da “website2.com”.

I file con estensioni specificate per i domini identificati da questo criterio continueranno a essere soggetti agli avvisi di sicurezza basati sulle estensioni dei tipi di file, ad esempio avvisi per il download di contenuti misti e avvisi di Microsoft Defender SmartScreen.

Se si disabilitano il criterio o non lo si configura, i tipi di file che generano avvisi per il download basato su estensione mostreranno avvisi all'utente.

Se il criterio viene abilitato:

* Il modello di URL deve essere formattato in base a [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).
* L'estensione del tipo di file immessa deve essere in formato ASCII in minuscolo. Quando si elenca il tipo di file, non è necessario includere il separatore iniziale, pertanto deve essere insertito “jnlp” invece di “.jnlp”.

Esempio:

Il valore di esempio seguente impedirebbe il download di avvisi basati su estensioni di file in swf, exe e jnlp per i domini *. contoso.com. Mostrerà all'utente un avviso per il download basato su estensione di un tipo di file in qualsiasi altro dominio per i file exe e jnlp, ma non per i file swf.

[ { "file_extension": "jnlp", "domains": ["contoso.com"] }, { "file_extension": "exe", "domains": ["contoso.com"] }, { "file_extension": "swf", "domains": ["*"] } ]

Si noti che mentre nell'esempio precedente viene mostrata la soppressione degli avvisi di download basati sulle estensioni di file per i file "swf" per tutti i domini, l'applicazione della soppressione di tali avvisi per tutti i domini per qualsiasi estensione di file pericoloso non è consigliata a causa di problemi di sicurezza. Nell'esempio è indicato solo per dimostrare la possibilità di eseguire questa operazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - Nome Criteri di gruppo: disabilita gli avvisi di download basati sull'estensione del tipo di file per i tipi di file specificati nei domini
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\1 = {"domains": ["https://contoso.com", "contoso2.com"], "file_extension": "jnlp"}
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\2 = {"domains": ["*"], "file_extension": "swf"}

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - Valore di esempio
``` xml
<array>
  <string>{'domains': ['https://contoso.com', 'contoso2.com'], 'file_extension': 'jnlp'}</string>
  <string>{'domains': ['*'], 'file_extension': 'swf'}</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExperimentationAndConfigurationServiceControl
  #### Controlla le comunicazioni con il servizio di sperimentazione e configurazione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  In Microsoft Edge, il servizio di sperimentazione e configurazione viene usato per distribuire il payload di sperimentazione e configurazione.

Il payload di sperimentazione è costituito da un elenco di funzionalità di distribuzione che Microsoft sta sottoponendo a test e feedback.

Il payload di configurazione è costituito da un elenco di impostazioni che Microsoft desidera distribuire a Microsoft Edge per ottimizzare l'esperienza utente. Ad esempio, il payload di configurazione può specificare la frequenza con cui Microsoft Edge invia richieste al servizio di sperimentazione e configurazione per recuperare il payload più recente.

Inoltre, il payload di configurazione contiene un elenco di azioni da eseguire in determinati domini per motivi di compatibilità. Ad esempio, il browser potrebbe ignorare la stringa agente utente in un sito Web se tale sito Web è interrotto a causa della nuova stringa agente utente in Microsoft Edge. Ognuna di queste azioni deve essere temporanea mentre Microsoft tenta di risolvere il problema con il proprietario del sito.

Se si imposta questo criterio su “FullMode”, viene scaricato il payload completo dal servizio di sperimentazione e configurazione. Sono inclusi i payload di sperimentazione e configurazione.

Se si imposta questo criterio su “ConfigurationsOnlyMode”, viene fornito solo il payload di configurazione.

Se si imposta questo criterio su "RestrictedMode", la comunicazione con il servizio di sperimentazione e configurazione viene bloccata completamente.

Se non si configura questo criterio, in un dispositivo gestito in canali Stable e Beta il comportamento è uguale a quello della modalità “ConfigurationsOnlyMode”.

Se non si configura questo criterio, in un dispositivo non gestito il comportamento è uguale a quello della modalità “FullMode".

Mapping delle opzioni del criterio:

* FullMode (2) = Recuperare configurazioni ed esperimenti

* ConfigurationsOnlyMode (1) = Recuperare solo le configurazioni

* RestrictedMode (0) = Disabilitare la comunicazione con il servizio di sperimentazione e configurazione

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExperimentationAndConfigurationServiceControl
  - Nome Criteri di gruppo: Controlla le comunicazioni con il servizio di sperimentazione e configurazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ExperimentationAndConfigurationServiceControl
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExperimentationAndConfigurationServiceControl
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ExternalProtocolDialogShowAlwaysOpenCheckbox
  #### Mostra una casella di controllo "Sempre aperto" nella casella di controllo del protocollo esterno
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Questo criterio controlla se la casella di controllo "Consenti sempre a questo sito di aprire collegamenti di questo tipo" viene visualizzata nelle richieste di conferma per l'avvio del protocollo esterno. Questo criterio si applica solo ai collegamenti https://.

Se viene abilitato questo criterio, quando viene visualizzata una richiesta di conferma del protocollo esterno, l'utente può selezionare "Consenti sempre" per ignorare tutte le richieste di conferma future per il protocollo in tale sito.

Se si disabilita questo criterio, la casella di controllo "Consenti sempre" non viene visualizzata. All'utente verrà richiesta una conferma ogni volta che viene richiamato un protocollo esterno.

Nelle versioni di Microsoft Edge precedenti alla 83, se non si configura questo criterio la casella di controllo "Consenti sempre" non viene visualizzata. All'utente verrà richiesta una conferma ogni volta che viene richiamato un protocollo esterno.

In Microsoft Edge 83, se non si configura questo criterio la visibilità della casella di controllo è controllata dal contrassegno "Abilita la memorizzazione delle preferenze di richiesta per l'avvio del protocollo" in edge://flags

Da Microsoft Edge versione 84, se non si configura questo criterio, quando viene visualizzata una richiesta di conferma del protocollo esterno, l'utente può selezionare "Consenti sempre" per ignorare tutte le richieste di conferma future per il protocollo in tale sito.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - Nome Criteri di gruppo: Mostra una casella di controllo "Sempre aperto" nella casella di controllo del protocollo esterno
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ExternalProtocolDialogShowAlwaysOpenCheckbox
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FamilySafetySettingsEnabled
  #### Consente agli utenti di configurare la protezione per la famiglia
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Questo criterio disabilita e nasconde completamente la pagina relativa alla protezione per la famiglia in Impostazioni. Non sarà possibile accedere nemmeno a edge://settings/familysafety. La pagina relativa alla protezione per la famiglia descrive le funzionalità disponibili per i gruppi familiari e come iscriversi a un gruppo familiare. Altre informazioni sulla protezione per la famiglia sono disponibili qui: ([https://go.microsoft.com/fwlink/?linkid=2098432](https://go.microsoft.com/fwlink/?linkid=2098432)).

Se si abilita o non si configura questo criterio, la pagina relativa alla protezione per la famiglia viene visualizzata.

Se si disabilita questo criterio, la pagina relativa alla protezione per la famiglia non verrà visualizzata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FamilySafetySettingsEnabled
  - Nome Criteri di gruppo: Consente agli utenti di configurare la protezione per la famiglia
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: FamilySafetySettingsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: FamilySafetySettingsEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FavoritesBarEnabled
  #### Abilita la barra Preferiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilita o disabilita la barra dei Preferiti.

Se si abilita questo criterio, gli utenti vedranno la barra dei Preferiti.

Se si disabilita questo criterio, gli utenti non vedranno la barra dei Preferiti.

Se non si configura questo criterio, l'utente può decidere di usare o meno la barra dei Preferiti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FavoritesBarEnabled
  - Nome Criteri di gruppo: Abilita la barra Preferiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: FavoritesBarEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: FavoritesBarEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceBingSafeSearch
  #### Applica Ricerca sicura di Bing
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Garantisce che le query nella ricerca Web di Bing vengano effettuate con Ricerca sicura impostata sul valore specificato. Questa impostazione non può essere modificata dagli utenti.

Se si configura questo criterio su "BingSafeSearchNoRestrictionsMode”, Ricerca sicura di Bing ritornerà al valore di bing.com.

Se si configura questo criterio su "BingSafeSearchModerateMode", viene usata l'impostazione moderata in Ricerca sicura. L'impostazione moderata filtra video e immagini per adulti, ma non il testo dei risultati della ricerca.

Se si configura questo criterio su "BingSafeSearchStrictMode", viene usata l'impostazione con restrizioni in Ricerca sicura. L'impostazione con restrizioni filtra testo, immagini e video per adulti.

Se si disabilita o non si configura questo criterio, Ricerca sicura di Bing non viene applicata e gli utenti possono impostare il valore che desiderano su bing.com.

Mapping delle opzioni del criterio:

* BingSafeSearchNoRestrictionsMode (0) = Non configurare le restrizioni della ricerca in Bing

* BingSafeSearchModerateMode (1) = Configurare restrizioni della ricerca moderate in Bing

* BingSafeSearchStrictMode (2) = Configurare restrizioni della ricerca rigide in Bing

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceBingSafeSearch
  - Nome Criteri di gruppo: Applica Ricerca sicura di Bing
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceBingSafeSearch
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceBingSafeSearch
  - Valore di esempio
``` xml
<integer>0</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceCertificatePromptsOnMultipleMatches
  #### Configura se Microsoft Edge deve selezionare automaticamente un certificato quando sono presenti più corrispondenze di certificato per un sito configurato con "AutoSelectCertificateForUrls"
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Determina se agli utenti viene richiesto di selezionare un certificato se sono presenti più certificati disponibili e un sito è configurato con [AutoSelectCertificateForUrls](#autoselectcertificateforurls). Se non si configura [AutoSelectCertificateForUrls](#autoselectcertificateforurls) per un sito, all'utente verrà sempre chiesto di selezionare un certificato.

Se si imposta questo criterio su True, Microsoft Edge richiederà a un utente di selezionare un certificato per i siti nell'elenco definiti in [AutoSelectCertificateForUrls](#autoselectcertificateforurls) solo e soltanto se sono presenti più certificati.

Se si imposta questo criterio su False o non lo si configura, Microsoft Edge selezionerà automaticamente un certificato anche se sono presenti più corrispondenze per un certificato. All'utente non verrà richiesto di selezionare un certificato per i siti nell'elenco definito in [AutoSelectCertificateForUrls](#autoselectcertificateforurls).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceCertificatePromptsOnMultipleMatches
  - Nome Criteri di gruppo: Configura se Microsoft Edge deve selezionare automaticamente un certificato quando sono presenti più corrispondenze di certificato per un sito configurato con "AutoSelectCertificateForUrls"
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceCertificatePromptsOnMultipleMatches
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceCertificatePromptsOnMultipleMatches
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceEphemeralProfiles
  #### Abilita l'uso di profili temporanei
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se i profili utente vengono convertiti in modalità temporanea. Un profilo temporaneo viene creato all'avvio di una sessione, viene eliminato al termine della sessione e viene associato al profilo originale dell'utente.

Se si abilita questo criterio, i profili vengono eseguiti in modalità temporanea. Questo consente agli utenti di lavorare dai propri dispositivi senza salvare i dati di esplorazione in tali dispositivi. Se si abilita questo criterio come criterio del sistema operativo (usando l'oggetto Criteri di gruppo in Windows, ad esempio), si applica a tutti i profili nel sistema.

Se si disabilita o non si configura questo criterio, gli utenti ottengono i loro normali profili quando accedono al browser.

In modalità temporanea, i dati dei profili vengono salvati nel disco solo per la durata della sessione utente. Le funzionalità come la cronologia del browser, le estensioni e i relativi dati, i dati Web come i cookie e i database Web non vengono salvati dopo la chiusura del browser. Questo non impedisce a un utente di scaricare manualmente i dati nel disco, di salvare o stampare pagine. Se l'utente ha abilitato la sincronizzazione, tutti i dati vengono conservati nei loro account di sincronizzazione, esattamente come con i profili normali. Gli utenti possono anche usare l'esplorazione InPrivate in modalità temporanea, a meno che non venga disabilitata esplicitamente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceEphemeralProfiles
  - Nome Criteri di gruppo: Abilita l'uso di profili temporanei
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceEphemeralProfiles
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceEphemeralProfiles
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceGoogleSafeSearch
  #### Applica Ricerca sicura di Google
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impone l'esecuzione di query nella ricerca Web Google con Ricerca sicura attivata e impedisce agli utenti di modificare questa impostazione.

Se si abilita questo criterio, Ricerca sicura in Google Search sarà sempre attiva.

Se si disabilita o non si configura questo criterio, Ricerca sicura in Google Search non viene applicata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceGoogleSafeSearch
  - Nome Criteri di gruppo: Applica Ricerca sicura di Google
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceGoogleSafeSearch
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceGoogleSafeSearch
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceLegacyDefaultReferrerPolicy
  #### Usa un criterio di referrer predefinito di no-referrer-when-downgrade (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Questo criterio è deprecato perché è solo un meccanismo a breve termine che offre alle aziende più tempo per aggiornare i contenuti Web se e quando viene rilevata incompatibilità con il criterio di referrer predefinito corrente. Non funzionerà in Microsoft Edge versione 88.

Il criterio di referrer predefinito di Microsoft Edge sta per essere rafforzato dal suo valore corrente di no-referrer-when-downgrade a quello più sicuro di strict-origin-when-cross-origin attraverso un'implementazione graduale.

Prima dell'implementazione, questo criterio aziendale non avrà alcun effetto. Dopo l'implementazione, quando questo criterio aziendale viene abilitato, il criterio di referrer predefinito di Microsoft Edge verrà impostato sul valore precedente di no-referrer-when-downgrade.

Questo criterio aziendale è disabilitato per impostazione predefinita.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceLegacyDefaultReferrerPolicy
  - Nome Criteri di gruppo: Usa un criterio di referrer predefinito di no-referrer-when-downgrade.
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceLegacyDefaultReferrerPolicy
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceLegacyDefaultReferrerPolicy
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceNetworkInProcess
  #### Forza l'esecuzione del codice di rete nel processo del browser (obsoleto)
  
  >OBSOLETO: questo criterio è obsoleto e non funziona dopo Microsoft Edge 83.
  #### Versioni supportate:
  - In Windows dalla versione 78 a 83

  #### Descrizione
  Questo criterio non funziona perché era solo un meccanismo a breve termine che offre alle aziende più tempo per eseguire la migrazione a software di terze parti che non dipendono dalle API di rete collegate. Sono consigliati server proxy con LSP e patch dell'API Win32.

Questo criterio forza l'esecuzione del codice di rete nel processo del browser.

Questo criterio è disabilitato per impostazione predefinita. Se abilitato, gli utenti sono esposti a problemi di sicurezza quando il processo di rete è in modalità sandbox.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceNetworkInProcess
  - Nome Criteri di gruppo: forza l'esecuzione del codice di rete nel processo del browser (obsoleto)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceNetworkInProcess
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceSync
  #### Forza la sincronizzazione dei dati del browser e non visualizzare la richiesta di autorizzazione di sincronizzazione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Forza la sincronizzazione dei dati in Microsoft Edge. Questo criterio impedisce anche all'utente di disattivare la sincronizzazione.

Se non si configura questo criterio, gli utenti potranno attivare o disattivare la sincronizzazione. Se si abilita questo criterio, gli utenti non potranno disattivare la sincronizzazione.

Affinché il criterio funzioni come previsto, il criterio [BrowserSignin](#browsersignin) non deve essere configurato o deve essere impostati su abilitato. Se [BrowserSignin](#browsersignin) è disabilitato, [ForceSync](#forcesync) non avrà effetto.

[SyncDisabled](#syncdisabled) non deve essere configurato o deve essere impostato su False. Se è impostato su True, [ForceSync](#forcesync) non avrà effetto.

0 = non avviare automaticamente la sincronizzazione e visualizzare il consenso di sincronizzazione (impostazione predefinita) 1 = forza l'attivazione della sincronizzazione per il profilo utente di Azure AD/Azure AD - danneggiato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceSync
  - Nome Criteri di gruppo: forza la sincronizzazione dei dati del browser e non visualizzare la richiesta di autorizzazione di sincronizzazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceSync
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceSync
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ForceYouTubeRestrict
  #### Forza la modalità con restrizioni YouTube minima
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Impone una modalità con restrizioni minime su YouTube e impedisce agli utenti di selezionare una modalità con restrizioni meno rigide.

Si imposta su “Strict” per applicare la modalità con restrizioni rigide su YouTube.

Si imposta su “Moderate” per imporre all'utente di usare solo la modalità con restrizioni moderate e la modalità con restrizioni rigide su YouTube. Non è possibile disabilitare la modalità con restrizioni.

Si imposta su “Off” o non si configura questo criterio per non imporre la modalità con restrizioni su YouTube. I criteri esterni, come quelli di YouTube, potrebbero applicare la modalità con restrizioni.

Mapping delle opzioni del criterio:

* Off (0) = Non applicare la modalità con restrizioni su YouTube

* Moderate (1) = Applicare almeno la modalità con restrizioni moderate su YouTube

* Strict (2) = Applicare la modalità con restrizioni rigide su YouTube

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ForceYouTubeRestrict
  - Nome Criteri di gruppo: Forza la modalità con restrizioni YouTube minima
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ForceYouTubeRestrict
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ForceYouTubeRestrict
  - Valore di esempio
``` xml
<integer>0</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### FullscreenAllowed
  #### Consente la modalità a schermo intero
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Imposta la disponibilità della modalità a schermo intero: tutta l'interfaccia utente di Microsoft Edge viene nascosta e sono visibili solo i contenuti Web.

Se si abilita o non si configura questo criterio, l'utente, le app e le estensioni con le autorizzazioni appropriate possono attivare la modalità a schermo intero.

Se si disabilita questo criterio, gli utenti, le app e le estensioni non potranno attivare la modalità a schermo intero.

L'apertura di Microsoft Edge in modalità tutto schermo con la riga di comando non è disponibile quando la modalità a schermo intero è disabilitata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: FullscreenAllowed
  - Nome Criteri di gruppo: Consente la modalità a schermo intero
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: FullscreenAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### GloballyScopeHTTPAuthCacheEnabled
  #### Abilita la cache di autenticazione HTTP con ambito globale
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Questo criterio configura una singola cache per profilo globale con le credenziali di autenticazione del server HTTP.

Se si disabilita o non si imposta questo criterio, il browser userà il comportamento predefinito dell'autenticazione cross-site che, a partire dalla versione 80, sarà quello di definire l'ambito delle credenziali di autenticazione del server HTTP per il sito principale. Quindi, se due siti usano risorse dello stesso dominio di autenticazione, le credenziali dovranno essere fornite in modo indipendente nel contesto di entrambi i siti. Le credenziali del proxy memorizzato nella cache verranno riutilizzate in più siti.

Se si abilita questo criterio, le credenziali di autenticazione HTTP inserite nel contesto di un sito verranno automaticamente usate nel contesto di un altro sito.

L'abilitazione di questo criterio lascia i siti esposti ad alcuni tipi di attacchi cross-site e consente agli utenti di essere rintracciati nei siti anche senza i cookie, aggiungendo voci alla cache di autenticazione HTTP con le credenziali incorporate negli URL.

Questo criterio ha lo scopo di offrire alle aziende, a seconda del comportamento legacy, la possibilità di aggiornare le procedure di accesso e verrà rimosso in futuro.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: GloballyScopeHTTPAuthCacheEnabled
  - Nome Criteri di gruppo: Abilita la cache di autenticazione HTTP con ambito globale
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: GloballyScopeHTTPAuthCacheEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: GloballyScopeHTTPAuthCacheEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### GoToIntranetSiteForSingleWordEntryInAddressBar
  #### Forza l'esplorazione del sito Intranet diretta anziché tramite la ricerca di singole parole nella barra degli indirizzi
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Se si abilita questo criterio, il risultato di suggerimento automatico principale nell'elenco di suggerimenti della barra degli indirizzi reindirizza ai siti Intranet se il testo inserito nella barra degli indirizzi è una singola parola senza punteggiatura.

L'esplorazione predefinita quando si digita una singola parola senza punteggiatura reindirizzerà l'utente a un sito Intranet corrispondente al testo inserito.

Se si abilita questo criterio, il secondo risultato di suggerimento automatico nell'elenco di suggerimenti della barra degli indirizzi eseguirà una ricerca sul Web esattamente come è stato immesso il testo, purché tale testo sia una singola parola senza punteggiatura. Verrà usato il provider di ricerca predefinito se non è abilitato anche un criterio che impedisce la ricerca sul Web.

Ecco due effetti derivanti dall'abilitazione di questo criterio:

Lo spostamento nei siti in risposta a query formate da una singola parola che in genere vengono risolte in un elemento della cronologia non sarà più possibile. Al contrario, il browser tenterà di passare a siti interni che potrebbero non esistere nell'Intranet di un'organizzazione. Il risultato sarà un errore 404.

Per i termini di ricerca più diffusi formati da una singola parola, è necessario selezionare manualmente i suggerimenti per eseguire la ricerca correttamente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: GoToIntranetSiteForSingleWordEntryInAddressBar
  - Nome Criteri di gruppo: Forza l'esplorazione del sito Intranet diretta anziché tramite la ricerca di singole parole nella barra degli indirizzi
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: GoToIntranetSiteForSingleWordEntryInAddressBar
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: GoToIntranetSiteForSingleWordEntryInAddressBar
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### HSTSPolicyBypassList
  #### Configura l'elenco di nomi che ignoreranno la verifica dei criteri HSTS
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  I nomi host specificati in questo elenco saranno esclusi dalla verifica dei criteri HSTS che potrebbe aggiornare le richieste da "http://" a "https://". In questo criterio sono consentiti solo i nomi host con etichetta singola. I nomi host devono essere in forma canonica. Gli IDN devono essere convertiti nel formato con etichetta A e tutte le lettere devono essere minuscole. Questo criterio si applica solo ai nomi host specifici; non si applica ai sottodomini dei nomi nell'elenco.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: HSTSPolicyBypassList
  - Nome Criteri di gruppo: Configura l'elenco di nomi che ignoreranno la verifica dei criteri HSTS
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\HSTSPolicyBypassList
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\HSTSPolicyBypassList\1 = "meet"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: HSTSPolicyBypassList
  - Valore di esempio
``` xml
<array>
  <string>meet</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### HardwareAccelerationModeEnabled
  #### Usa l'accelerazione hardware se disponibile
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica di usare l'accelerazione hardware, se disponibile. Se si abilita o non si configura questo criterio, l'accelerazione hardware è abilitata a meno che non venga esplicitamente bloccata una funzionalità della GPU.

Se si disabilita questo criterio, l'accelerazione hardware è disabilitata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: HardwareAccelerationModeEnabled
  - Nome Criteri di gruppo: Usa l'accelerazione hardware se disponibile
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: HardwareAccelerationModeEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: HardwareAccelerationModeEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### HideFirstRunExperience
  #### Nasconde l'esperienza della first-run experience e la schermata iniziale
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Se si abilita questo criterio, la first-run experience e la schermata iniziale non verranno mostrate agli utenti quando eseguono Microsoft Edge per la prima volta.

Le opzioni di configurazione predefinite mostrate nella first-run experience del browser saranno le seguenti:

- Nella pagina Nuova scheda, il tipo di feed sarà impostato su MSN Notizie e il layout su Ispirato.

- L'utente continuerà ad accedere automaticamente a Microsoft Edge se l'account Windows è del tipo MSA o Azure AD.

- La sincronizzazione non è abilitata per impostazione predefinita, e agli utenti viene chiesto di specificare se vogliono eseguire la sincronizzazione all'avvio del browser. È possibile usare i criteri [ForceSync](#forcesync) o [SyncDisabled](#syncdisabled) per configurare la sincronizzazione e la richiesta di consenso per la sincronizzazione.

Se si disabilita o non si configura questo criterio, la first-run experience e la schermata iniziale verranno mostrate.

Nota: le opzioni di configurazione specifiche mostrate all'utente nella first-run experience possono essere gestite anche usando altri criteri specifici. È possibile usare il criterio HideFirstRunExperience in combinazione con questi criteri per configurare un'esperienza di browser specifica nei dispositivi gestiti. Ecco alcuni di questi altri criteri:

-[AutoImportAtFirstRun](#autoimportatfirstrun)

-[NewTabPageLocation](#newtabpagelocation)

-[NewTabPageSetFeedType](#newtabpagesetfeedtype)

-[ForceSync](#forcesync)

-[SyncDisabled](#syncdisabled)

-[BrowserSignin](#browsersignin)

-[NonRemovableProfileEnabled](#nonremovableprofileenabled)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: HideFirstRunExperience
  - Nome Criteri di gruppo: Nasconde l'esperienza della prima esecuzione e la schermata iniziale
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: HideFirstRunExperience
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: HideFirstRunExperience
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportAutofillFormData
  #### Consente l'importazione dei dati di moduli con riempimento automatico
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare i dati di moduli con riempimento automatico da un altro browser in Microsoft Edge.

Se si abilita questo criterio, viene selezionata automaticamente l'opzione per l'importazione manuale dei dati di riempimento automatico.

Se si disabilita questo criterio, i dati di moduli con riempimento automatico non vengono importati nella first-run experience e gli utenti non possono importarli manualmente.

Se non si configura questo criterio, i dati di riempimento automatico vengono importati nella first-run experience e gli utenti possono scegliere se importare questi dati manualmente durante le sessioni di esplorazione successive.

È possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà i dati di riempimento automatico nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa ai **dati di riempimento automatico** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione dai browser Google Chrome (in Windows 7, 8 e 10 e in macOS) e Mozilla Firefox (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportAutofillFormData
  - Nome Criteri di gruppo: Consente l'importazione dei dati di moduli con riempimento automatico
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportAutofillFormData
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportAutofillFormData
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportBrowserSettings
  #### Consente l'importazione delle impostazioni del browser
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Consente agli utenti di importare le impostazioni del browser da un altro browser in Microsoft Edge.

Se si abilita questo criterio, la casella di controllo **Impostazioni browser** viene automaticamente selezionata nella finestra di dialogo **Importa dati del browser**.

Se si disabilita questo criterio, le impostazioni del browser non vengono importate alla prima esecuzione e gli utenti non possono importarle manualmente.

Se non si configura questo criterio, le impostazioni del browser vengono importate alla prima esecuzione e gli utenti possono scegliere se importarle manualmente durante le sessioni di esplorazione successive.

È anche possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà le impostazioni nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa alle **impostazioni del browser** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione da Google Chrome (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportBrowserSettings
  - Nome Criteri di gruppo: Consente l'importazione delle impostazioni del browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportBrowserSettings
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportBrowserSettings
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportCookies
  #### Consente l'importazione di cookie
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Consente agli utenti di importare i cookie da un altro browser in Microsoft Edge.

Se si disabilita questo criterio, i cookie non vengono importati nella first-run experience.

Se non si configura questo criterio, i cookie vengono importati alla prima esecuzione.

È anche possibile impostare questo criterio come suggerimento. Ciò significa che Microsoft Edge importa i cookie nella first-run experience.

**Nota**: al momento questo criterio gestisce l'importazione da Google Chrome (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportCookies
  - Nome Criteri di gruppo: Consente l'importazione di cookie
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportCookies
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportCookies
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportExtensions
  #### Consente l'importazione di estensioni
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Consente agli utenti di importare le estensioni da un altro browser in Microsoft Edge.

Se si abilita questo criterio, la casella di controllo **Estensioni** viene automaticamente selezionata nella finestra di dialogo **Importa dati del browser**.

Se si disabilita questo criterio, le estensioni non vengono importate nella first-run experience e gli utenti non possono importarle manualmente.

Se non si configura questo criterio, le estensioni vengono importate nella first-run experience e gli utenti possono scegliere se importarle manualmente durante le sessioni di esplorazione successive.

È anche possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà le estensioni nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa ai **preferiti** durante l'importazione manuale.

**Nota**: al momento questo criterio supporta solo l'importazione da Google Chrome (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportExtensions
  - Nome Criteri di gruppo: Consente l'importazione di estensioni
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportExtensions
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportExtensions
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportFavorites
  #### Consente l'importazione di Preferiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare i preferiti da un altro browser in Microsoft Edge.

Se si abilita questo criterio, la casella di controllo **Preferiti** viene automaticamente selezionata nella finestra di dialogo **Importa dati del browser**.

Se si disabilita questo criterio, i preferiti non vengono importati alla prima esecuzione e gli utenti non possono importarli manualmente.

Se non si configura questo criterio, i preferiti vengono importati alla prima esecuzione e gli utenti possono scegliere se importarli manualmente durante le sessioni di esplorazione successive.

È anche possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà i preferiti nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa ai **preferiti** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione dai browser Internet Explorer (in Windows 7, 8 e 10), Google Chrome (in Windows 7, 8 e 10 e in macOS), Mozilla Firefox (in Windows 7, 8 e 10 e in macOS) e Apple Safari (in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportFavorites
  - Nome Criteri di gruppo: Consente l'importazione di Preferiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportFavorites
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportFavorites
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportHistory
  #### Consente l'importazione della cronologia esplorazioni
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare la cronologia esplorazioni da un altro browser in Microsoft Edge.

Se si abilita questo criterio, la casella di controllo **Cronologia esplorazioni** viene automaticamente selezionata nella finestra di dialogo **Importa dati del browser**.

Se si disabilita questo criterio, i dati della cronologia esplorazioni non vengono importati alla prima esecuzione e gli utenti non possono importare tali dati manualmente.

Se non si configura questo criterio, i dati della cronologia esplorazioni vengono importati alla prima esecuzione e gli utenti possono scegliere se importarli manualmente durante le sessioni di esplorazione successive.

È anche possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà la cronologia esplorazioni nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa alla **cronologia** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione dai browser Internet Explorer (in Windows 7, 8 e 10), Google Chrome (in Windows 7, 8 e 10 e in macOS), Mozilla Firefox (in Windows 7, 8 e 10 e in macOS) e Apple Safari (macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportHistory
  - Nome Criteri di gruppo: Consente l'importazione della cronologia esplorazioni
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportHistory
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportHistory
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportHomepage
  #### Consente l'importazione delle impostazioni della home page
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare l'impostazione della home page da un altro browser in Microsoft Edge.

Se si abilita questo criterio, viene selezionata automaticamente l'opzione per l'importazione manuale dell'impostazione della home page.

Se si disabilita questo criterio, l'impostazione della home page non viene importata alla prima esecuzione e gli utenti non possono importarla manualmente.

Se non si configura questo criterio, l'impostazione della home page viene importata alla prima esecuzione e gli utenti possono scegliere se importare questi dati manualmente durante le sessioni di esplorazione successive.

È possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà l'impostazione della home page nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa alla **home page** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione da Internet Explorer (in Windows 7, 8 e 10).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportHomepage
  - Nome Criteri di gruppo: Consente l'importazione delle impostazioni della home page
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ImportHomepage
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportHomepage
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportOpenTabs
  #### Consente l'importazione di schede aperte
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Consente agli utenti di importare le schede aperte e aggiunte da un altro browser in Microsoft Edge.

Se si abilita questo criterio, la casella di controllo **Schede aperte** viene automaticamente selezionata nella finestra di dialogo **Importa dati del browser**.

Se si disabilita questo criterio, le schede aperte non vengono importate nella first-run experience e gli utenti non possono importarle manualmente.

Se non si configura questo criterio, le schede aperte vengono importate nella first-run experience e gli utenti possono scegliere se importarle manualmente durante le sessioni di esplorazione successive.

È anche possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà le schede aperte nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa alle **schede aperte** durante l'importazione manuale.

**Nota**: al momento questo criterio supporta solo l'importazione da Google Chrome (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportOpenTabs
  - Nome Criteri di gruppo: Consente l'importazione di schede aperte
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportOpenTabs
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportOpenTabs
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportPaymentInfo
  #### Consente l'importazione di informazioni di pagamento
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare le informazioni di pagamento da un altro browser in Microsoft Edge.

Se si abilita questo criterio, la casella di controllo **Informazioni di pagamento** viene automaticamente selezionata nella finestra di dialogo **Importa dati del browser**.

Se si disabilita questo criterio, le informazioni di pagamento non vengono importate alla prima esecuzione e gli utenti non possono importarle manualmente.

Se non si configura questo criterio, le informazioni di pagamento vengono importate alla prima esecuzione e gli utenti possono scegliere se importarle manualmente durante le sessioni di esplorazione successive.

È anche possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà le informazioni di pagamento nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa alle **informazioni di pagamento** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione da Google Chrome (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportPaymentInfo
  - Nome Criteri di gruppo: Consente l'importazione di informazioni di pagamento
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportPaymentInfo
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportPaymentInfo
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportSavedPasswords
  #### Consente l'importazione delle password salvate
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare le password salvate da un altro browser in Microsoft Edge.

Se si abilita questo criterio, viene selezionata automaticamente l'opzione per l'importazione manuale delle password salvate.

Se si disabilita questo criterio, le password salvate non vengono importate nella first-run experience e gli utenti non possono importarle manualmente.

Se non si configura questo criterio, le password salvate vengono importate nella first-run experience e gli utenti possono scegliere se importarle manualmente durante le sessioni di esplorazione successive.

È possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà le password salvate nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa alle **password** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione dai browser Internet Explorer (in Windows 7, 8 e 10), Google Chrome (in Windows 7, 8 e 10 e in macOS) e Mozilla Firefox (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportSavedPasswords
  - Nome Criteri di gruppo: Consente l'importazione delle password salvate
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportSavedPasswords
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportSavedPasswords
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportSearchEngine
  #### Consente l'importazione delle impostazioni del motore di ricerca
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente agli utenti di importare le impostazioni del motore di ricerca da un altro browser in Microsoft Edge.

Se si abilita questo criterio, viene selezionata automaticamente l'opzione per l'importazione delle impostazioni del motore di ricerca.

Se si disabilita questo criterio, le impostazioni del motore di ricerca non vengono importate alla prima esecuzione e gli utenti non possono importarle manualmente.

Se non si configura questo criterio, le impostazioni del motore di ricerca vengono importate alla prima esecuzione e gli utenti possono scegliere se importare questi dati manualmente durante le sessioni di esplorazione successive.

È possibile impostare questo criterio come suggerimento. Questo significa che Microsoft Edge importerà le impostazioni del motore di ricerca nella first-run experience, ma gli utenti possono selezionare o deselezionare l'opzione relativa al **motore di ricerca** durante l'importazione manuale.

**Nota**: al momento questo criterio gestisce l'importazione da Internet Explorer (in Windows 7, 8 e 10).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportSearchEngine
  - Nome Criteri di gruppo: Consente l'importazione delle impostazioni del motore di ricerca
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportSearchEngine
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportSearchEngine
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ImportShortcuts
  #### Consente l'importazione di scelte rapide da tastiera
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Consente agli utenti di importare i tasti di scelta rapida da un altro browser in Microsoft Edge.

Se si disabilita questo criterio, le scelte rapide da tastiera non vengono importate nella first-run experience.

Se non si configura questo criterio, i tasti di scelta rapida vengono importate alla prima esecuzione.

È anche possibile impostare questo criterio come suggerimento. Ciò significa che Microsoft Edge importa le scelte rapide da tastiera nella first-run experience.

**Nota**: al momento questo criterio gestisce l'importazione da Google Chrome (in Windows 7, 8 e 10 e in macOS).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ImportShortcuts
  - Nome Criteri di gruppo: Consente l'importazione di scelte rapide da tastiera
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ImportShortcuts
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ImportShortcuts
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InPrivateModeAvailability
  #### Configura la disponibilità della modalità InPrivate
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se l'utente può aprire le pagine in modalità InPrivate in Microsoft Edge.

Se questo criterio non viene configurato o viene impostato su "Abilitato", gli utenti possono aprire le pagine in modalità InPrivate.

Impostare questo criterio su "Disabilitato" per impedire agli utenti di usare la modalità InPrivate.

Impostare questo criterio su "Forzato" per usare sempre la modalità InPrivate.

Mapping delle opzioni del criterio:

* Abilitato (0) = Modalità InPrivate disponibile

* Disabilitato (1) = Modalità InPrivate disabilitata

* Forzato (2) = Modalità InPrivate forzata

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InPrivateModeAvailability
  - Nome Criteri di gruppo: Configura la disponibilità della modalità InPrivate
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InPrivateModeAvailability
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: InPrivateModeAvailability
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InsecureFormsWarningsEnabled
  #### Attiva gli avvisi per i moduli non sicuri
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Questo criterio controlla la gestione di moduli non protetti (moduli inviati tramite HTTP) incorporati in siti di sicurezza (HTTPS) nel browser.
Se si abilita questo criterio o non lo si imposta, viene visualizzato un avviso a pagina intera quando viene inviato un modulo non protetto. Inoltre, viene visualizzata una bolla di avviso accanto ai campi del modulo quando sono evidenziati e la funzione riempimento automatico viene disabilitata per tali moduli.
Se si disabilitano i criteri, gli avvisi non verranno visualizzati per i moduli non sicuri e il riempimento automatico funzionerà normalmente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InsecureFormsWarningsEnabled
  - Nome Criteri di gruppo: attiva gli avvisi per i moduli non sicuri
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InsecureFormsWarningsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: InsecureFormsWarningsEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### IntensiveWakeUpThrottlingEnabled
  #### Controlla la funzionalità IntensiveWakeUpThrottling
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Quando la funzionalità IntensiveWakeUpThrottling è abilitata, questa fa sì che i timer JavaScript nelle schede di sfondo vengano aggressivamente limitati e uniti, funzionando non più di una volta al minuto dopo che una pagina è stata fatta passare in background per 5 minuti o più.

Si tratta di una caratteristica conforme agli standard Web, ma può infrangere le funzionalità di alcuni siti web causando il ritardo di determinate azioni per un massimo di un minuto. Tuttavia, se abilitata, comporta un notevole risparmio di CPU e batteria.  Per ulteriori informazioni, vedere https://bit.ly/30b1XR4.

Se si abilita questo criterio, l’attivazione della funzione verrà forzata e gli utenti non saranno in grado di eseguire l'override di questa impostazione.
Se si disabilita questo criterio, la disattivazione della funzione verrà forzata e gli utenti non saranno in grado di eseguire l'override di questa impostazione.
Se non si configura questo criterio, la funzione sarà controllata dalla relativa logica interna. Gli utenti possono configurare manualmente questa opzione.

Il criterio viene applicato per processo di rendering, con il valore più recente dell'impostazione del criterio in vigore all'avvio di un processo di rendering. Per garantire che tutte le schede caricate ricevano un'impostazione coerente dei criteri, è necessario riavviare il sistema. I processi in esecuzione con valori diversi da questo criterio non comportano alcun rischio.


  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: IntensiveWakeUpThrottlingEnabled
  - Nome Criteri di gruppo: controlla la funzionalità IntensiveWakeUpThrottling
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: IntensiveWakeUpThrottlingEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: IntensiveWakeUpThrottlingEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InternetExplorerIntegrationEnhancedHangDetection
  #### Configura il rilevamento di blocchi avanzati per la modalità di Internet Explorer
  
  
  #### Versioni supportate:
  - In Windows dalla versione 84 o successive

  #### Descrizione
  Il rilevamento di eventi di blocco avanzati offre un approccio più granulare per il rilevamento di pagine Web bloccate in modalità Internet Explorer, rispetto a quello che utilizza Internet Explorer in modo autonomo. Quando viene rilevata una pagina web bloccata, il browser applica un’azione di prevenzione per evitare che il resto del browser si blocchi a sua volta.

Questa opzione consente di configurare l'uso del rilevamento di eventi di blocco avanzato nel caso in cui si verificano problemi incompatibili con qualsiasi sito web. È consigliabile disabilitare questo criterio solo se vengono visualizzate notifiche come "(sito Web) non risponde" in modalità Internet Explorer, ma non in Internet Explorer in modo autonomo.

Questa impostazione funziona in combinazione con i criteri: [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) impostato su "IEMode e [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist), in cui l'elenco ha almeno una voce.

Se si imposta questo criterio su "Abilitato" o non lo si configura, i siti Web in esecuzione in modalità Internet Explorer useranno il rilevamento di eventi di blocco avanzato.

Se si imposta questo criterio su "Disabilitato", il rilevamento di eventi di blocco avanzato viene disabilitato e per gli utenti sarà disponibile il rilevamento di eventi di blocco di base di Internet Explorer.

Per altre informazioni sulla modalità Internet Explorer, vedere [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

Mapping delle opzioni del criterio:

* Disabilitato (0) = Rilevamento di eventi di blocco avanzato disabilitato

* Abilitato (1) = Rilevamento di eventi di blocco avanzato abilitato

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InternetExplorerIntegrationEnhancedHangDetection
  - Nome Criteri di gruppo: configura il rilevamento di blocchi avanzati per la modalità Internet Explorer
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InternetExplorerIntegrationEnhancedHangDetection
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InternetExplorerIntegrationLevel
  #### Configurare l'integrazione Internet Explorer
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Per istruzioni sulla configurazione dell'esperienza ottimale per la modalità di Internet Explorer, vedere [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

Mapping delle opzioni del criterio:

* None (0) = Nessuno

* IEMode (1) = Modalità Internet Explorer

* NeedIE (2) = Internet Explorer 11

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InternetExplorerIntegrationLevel
  - Nome Criteri di gruppo: Configurare l'integrazione Internet Explorer
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InternetExplorerIntegrationLevel
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InternetExplorerIntegrationSiteList
  #### Configurare l'elenco siti modalità Enterprise
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Per istruzioni sulla configurazione dell'esperienza ottimale per la modalità di Internet Explorer, vedere [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InternetExplorerIntegrationSiteList
  - Nome Criteri di gruppo: Configurare l'elenco siti modalità Enterprise
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InternetExplorerIntegrationSiteList
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://internal.contoso.com/sitelist.xml"
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InternetExplorerIntegrationSiteRedirect
  #### Specifica il comportamento degli spostamenti "nella pagina" verso i siti non configurati all'avvio dalle pagine in modalità Internet Explorer
  
  
  #### Versioni supportate:
  - In Windows dalla versione 81 o successive

  #### Descrizione
  Lo spostamento nella pagina viene avviato da un collegamento, uno script o una maschera nella pagina corrente. Può essere anche avviato da un reindirizzamento lato server di un precedente tentativo di spostamento nella pagina. Al contrario un utente può avviare uno spostamento che non sia nella pagina, e indipendentemente dalla pagina corrente, in diversi modi usando i controlli del browser. Ad esempio, usando la barra degli indirizzi, il pulsante Indietro o un collegamento preferito.

Questa impostazione consente di specificare se gli spostamenti dalle pagine caricate in modalità Internet Explorer a siti non configurati (che non sono configurati nell'elenco di siti in modalità Enterprise) reindirizzano a Microsoft Edge o rimangono in modalità Internet Explorer.

Questa impostazione funziona in combinazione con i criteri: [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) impostato su "IEMode e [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist), in cui l'elenco ha almeno una voce.

Se si disabilita o non si configura questo criterio, solo i siti configurati per l'apertura in modalità Internet Explorer verranno aperti in questa modalità. I siti non configurati per l'apertura in modalità Internet Explorer verranno reindirizzati a Microsoft Edge.

Se si imposta questo criterio su “Predefinito”, solo i siti configurati per l'apertura in modalità Internet Explorer verranno aperti in questa modalità. I siti non configurati per l'apertura in modalità Internet Explorer verranno reindirizzati a Microsoft Edge.

Se si imposta questo criterio su “AutomaticNavigationsOnly”, si ottiene l'esperienza predefinita tranne gli spostamenti automatici (ad esempio reindirizzamenti 302) ai siti non configurati in modalità Internet Explorer.

Se si imposta questo criterio su “AllInPageNavigations”, tutti gli spostamenti dalle pagine caricate in modalità IE verso siti non configurati vengono mantenuti in modalità Internet Explorer (scelta meno consigliata).

Per altre informazioni sulla modalità Internet Explorer, vedere [https://go.microsoft.com/fwlink/?linkid=2105106](https://go.microsoft.com/fwlink/?linkid=2105106)

Mapping delle opzioni del criterio:

* Predefinito (0) = Predefinito

* AutomaticNavigationsOnly (1) = Mantenere gli spostamenti automatici in modalità Internet Explorer

* AllInPageNavigations (2) = Mantenere tutti gli spostamenti nella pagina in modalità Internet Explorer

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InternetExplorerIntegrationSiteRedirect
  - Nome Criteri di gruppo: Specifica il comportamento degli spostamenti "nella pagina" verso i siti non configurati all'avvio dalle pagine in modalità Internet Explorer
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InternetExplorerIntegrationSiteRedirect
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### InternetExplorerIntegrationTestingAllowed
  #### Consenti il test della modalità di Internet Explorer
  
  
  #### Versioni supportate:
  - In Windows dalla versione 86 o successive

  #### Descrizione
  Questo criterio sostituisce il criterio di contrassegno del test della modalità ie. Consente agli utenti di aprire una scheda in modalità Internet Explorer dal menu dell'interfaccia utente.

Questa impostazione funziona in combinazione con i criteri: [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) impostato su "IEMode e [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist), in cui l'elenco ha almeno una voce.

Se si abilita questo criterio, gli utenti possono aprire la scheda modalità IE dall'interfaccia utente ed esplorare il sito corrente in modalità Internet Explorer.

Se si disabilita questo criterio, gli utenti non potranno vedere direttamente l'opzione dell'interfaccia utente nel menu.

Se non si configura questo criterio, è possibile configurare manualmente il contrassegno del test della modalità ie.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: InternetExplorerIntegrationTestingAllowed
  - Nome Criteri di gruppo: consenti test della modalità Internet Explorer
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: InternetExplorerIntegrationTestingAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### IsolateOrigins
  #### Abilita l'isolamento del sito per origini specifiche
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica le origini da eseguire in isolamento, nel relativo processo.

Inoltre, questo processo isola le origini denominate dai sottodomini (ad esempio, specificando https://contoso.com/, https://foo.contoso.com/ verrà isolato come parte del sito https://contoso.com/.

Se il criterio è abilitato, ognuna delle origini denominate in un elenco con valori separati da virgole verrà eseguita in un processo specifico.

Se si disabilita questo criterio, vengono disabilitate entrambe le funzionalità "IsolateOrigins" e "SitePerProcess". Gli utenti possono comunque abilitare il criterio "IsolateOrigins" manualmente, tramite i contrassegni della riga di comando.

Se non si configura il criterio, l'utente può modificare tale impostazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: IsolateOrigins
  - Nome Criteri di gruppo: Abilita l'isolamento del sito per origini specifiche
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: IsolateOrigins
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"https://contoso.com/,https://fabrikam.com/"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: IsolateOrigins
  - Valore di esempio
``` xml
<string>https://contoso.com/,https://fabrikam.com/</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### LocalProvidersEnabled
  #### Consente suggerimenti dai provider locali
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Consente i suggerimenti dai provider di suggerimenti nel dispositivo (provider locali), ad esempio, Preferiti e Cronologia esplorazioni, nell'elenco dei suggerimenti automatici e nella barra degli indirizzi di Microsoft Edge.

Se si abilita questo criterio, vengono usati i suggerimenti dei provider locali.

Se si disabilita questo criterio, i suggerimenti dei provider locali non vengono mai usati. I suggerimenti relativi a cronologia e preferiti locali non verranno visualizzati.

Se non si configura questo criterio, i suggerimenti dei provider locali sono consentiti, ma l'utente può modificarli con l'interruttore delle impostazioni.

Alcune funzionalità potrebbero non essere disponibili se è stato applicato un criterio per disabilitare questa caratteristica. Ad esempio, i suggerimenti della cronologia esplorazioni non sono disponibili se si abilita il criterio [SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled).

Questo criterio richiede il riavvio del browser per completare l'applicazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: LocalProvidersEnabled
  - Nome Criteri di gruppo: Consente suggerimenti dai provider locali
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: LocalProvidersEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: LocalProvidersEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ManagedFavorites
  #### Configura i Preferiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura un elenco di preferiti gestiti.

Il criterio crea un elenco di preferiti. Ogni preferito contiene le chiavi "name" e "url", che includono il nome e la destinazione del preferito. È possibile configurare una sottocartella definendo un preferito senza una chiave "url" ma con una chiave "children" aggiuntiva che contiene un elenco di preferiti come descritto in precedenza (alcuni dei quali potrebbero essere delle cartelle). Microsoft Edge modifica gli URL incompleti come se fossero stati immessi tramite la barra degli indirizzi, ad esempio "microsoft.com" diventa "https://microsoft.com/".

Questi preferiti vengono inseriti in una cartella che non può essere modificata dall'utente (ma l'utente può scegliere di nasconderla dalla barra dei preferiti). Per impostazione predefinita, il nome della cartella è "Preferiti gestiti" ma è possibile modificarla aggiungendo all'elenco dei preferiti un dizionario contenente la chiave "toplevel_name" con il nome della cartella desiderato come valore.

I preferiti gestiti non vengono sincronizzati con l'account utente e non possono essere modificati dalle estensioni.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ManagedFavorites
  - Nome Criteri di gruppo: Configura i Preferiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ManagedFavorites
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [
  {
    "toplevel_name": "My managed favorites folder"
  }, 
  {
    "name": "Microsoft", 
    "url": "microsoft.com"
  }, 
  {
    "name": "Bing", 
    "url": "bing.com"
  }, 
  {
    "children": [
      {
        "name": "Microsoft Edge Insiders", 
        "url": "www.microsoftedgeinsider.com"
      }, 
      {
        "name": "Microsoft Edge", 
        "url": "www.microsoft.com/windows/microsoft-edge"
      }
    ], 
    "name": "Microsoft Edge links"
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ManagedFavorites
  - Valore di esempio
``` xml
<key>ManagedFavorites</key>
<array>
  <dict>
    <key>toplevel_name</key>
    <string>My managed favorites folder</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Microsoft</string>
    <key>url</key>
    <string>microsoft.com</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Bing</string>
    <key>url</key>
    <string>bing.com</string>
  </dict>
  <dict>
    <key>children</key>
    <array>
      <dict>
        <key>name</key>
        <string>Microsoft Edge Insiders</string>
        <key>url</key>
        <string>www.microsoftedgeinsider.com</string>
      </dict>
      <dict>
        <key>name</key>
        <string>Microsoft Edge</string>
        <key>url</key>
        <string>www.microsoft.com/windows/microsoft-edge</string>
      </dict>
    </array>
    <key>name</key>
    <string>Microsoft Edge links</string>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ManagedSearchEngines
  #### Gestisce i motori di ricerca
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di configurare un elenco di massimo 10 motori di ricerca, uno dei quali deve essere contrassegnato come predefinito.
Non è necessario specificare la codifica. A partire da Microsoft Edge 80, i parametri suggest_url e image_search_url sono facoltativi. Il parametro facoltativo image_search_post_params (costituito da coppie nome/valore separate da virgole) è disponibile a partire da Microsoft Edge 80.

A partire da Microsoft Edge 83, è possibile abilitare l'individuazione del motore di ricerca con il parametro facoltativo allow_search_engine_discovery. Questo parametro deve essere il primo elemento nell'elenco. Se allow_search_engine_discovery non è specificato, l'individuazione del motore di ricerca verrà disabilitata per impostazione predefinita. A partire dalla versione 84 di Microsoft Edge, è possibile impostare questo criterio come consigliato per consentire l'individuazione dei provider di ricerca. Non è necessario aggiungere il parametro facoltativo allow_search_engine_discovery.

Se si abilita questo criterio, gli utenti non possono aggiungere, rimuovere o modificare i motori di ricerca nell'elenco. Gli utenti possono impostare il motore di ricerca predefinito su qualsiasi motore di ricerca nell'elenco.

Se si disabilita o non si configura questo criterio, gli utenti possono modificare l'elenco dei motori di ricerca nel modo desiderato.

Se il criterio [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) è impostato, questo criterio (ManagedSearchEngines) viene ignorato. Per terminare l'applicazione del criterio, l'utente deve riavviare il browser.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ManagedSearchEngines
  - Nome Criteri di gruppo: Gestisce i motori di ricerca
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ManagedSearchEngines
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [
  {
    "allow_search_engine_discovery": true
  }, 
  {
    "is_default": true, 
    "keyword": "example1.com", 
    "name": "Example1", 
    "search_url": "https://www.example1.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"
  }, 
  {
    "image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", 
    "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", 
    "keyword": "example2.com", 
    "name": "Example2", 
    "search_url": "https://www.example2.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"
  }, 
  {
    "encoding": "UTF-8", 
    "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", 
    "keyword": "example3.com", 
    "name": "Example3", 
    "search_url": "https://www.example3.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"
  }, 
  {
    "keyword": "example4.com", 
    "name": "Example4", 
    "search_url": "https://www.example4.com/search?q={searchTerms}"
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ManagedSearchEngines
  - Valore di esempio
``` xml
<key>ManagedSearchEngines</key>
<array>
  <dict>
    <key>allow_search_engine_discovery</key>
    <true/>
  </dict>
  <dict>
    <key>is_default</key>
    <true/>
    <key>keyword</key>
    <string>example1.com</string>
    <key>name</key>
    <string>Example1</string>
    <key>search_url</key>
    <string>https://www.example1.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example1.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>image_search_post_params</key>
    <string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
    <key>image_search_url</key>
    <string>https://www.example2.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example2.com</string>
    <key>name</key>
    <string>Example2</string>
    <key>search_url</key>
    <string>https://www.example2.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example2.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>encoding</key>
    <string>UTF-8</string>
    <key>image_search_url</key>
    <string>https://www.example3.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example3.com</string>
    <key>name</key>
    <string>Example3</string>
    <key>search_url</key>
    <string>https://www.example3.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example3.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>keyword</key>
    <string>example4.com</string>
    <key>name</key>
    <string>Example4</string>
    <key>search_url</key>
    <string>https://www.example4.com/search?q={searchTerms}</string>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### MaxConnectionsPerProxy
  #### Numero massimo di connessioni simultanee al server proxy
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica il numero massimo di connessioni simultanee al server proxy.

Alcuni server proxy non possono gestire un numero elevato di connessioni simultanee per client; è possibile risolvere questo problema impostando questo criterio su un valore più basso.

Il valore di questo criterio deve essere inferiore a 100 e superiore a 6. Il valore predefinito è 32.

Alcune app Web sono note per l'utilizzo di molte connessioni con GET: ridurre le connessioni massime sotto 32 potrebbe provocare interruzioni della rete del browser se è aperto un numero eccessivo di questo tipo di app Web.

Se non si configura questo criterio, viene utilizzato il valore predefinito (32).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: MaxConnectionsPerProxy
  - Nome Criteri di gruppo: Numero massimo di connessioni simultanee al server proxy
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: MaxConnectionsPerProxy
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000020
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: MaxConnectionsPerProxy
  - Valore di esempio
``` xml
<integer>32</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### MediaRouterCastAllowAllIPs
  #### Consente a Google Cast di connettersi ai dispositivi Cast su tutti gli indirizzi IP
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilitare questo criterio per consentire a Google Cast di connettersi a dispositivi Cast su tutti gli indirizzi IP, non solo sugli indirizzi privati RFC1918/RFC4193.

Disabilitare questo criterio per limitare Google Cast ai dispositivi Cast negli indirizzi privati RFC1918/RFC4193.

Se non si configura questo criterio, Google Cast si connette solo ai dispositivi Cast negli indirizzi privati RFC1918/RFC4193, a meno che non si abiliti la funzionalità CastAllowAllIPs.

Se il criterio [EnableMediaRouter](#enablemediarouter) è disabilitato, questo criterio non ha alcun effetto.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: MediaRouterCastAllowAllIPs
  - Nome Criteri di gruppo: Consente a Google Cast di connettersi ai dispositivi Cast su tutti gli indirizzi IP
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: MediaRouterCastAllowAllIPs
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: MediaRouterCastAllowAllIPs
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### MetricsReportingEnabled
  #### Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  questa impostazione è deprecata. È attualmente supportato, ma diventerà obsoleto in Microsoft Edge 89. Questo criterio è stato sostituito dal nuovo criterio:  [DiagnosticData](#diagnosticdata)per Windows 7, Windows 8 e macOS. Questo criterio è stato sostituito da Consenti telemetria per il rientro su Windows 10 ([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)).

Questi criteri abilitano l'invio di report a Microsoft sui dati sull'uso e sull'arresto anomalo di Microsoft Edge.

Abilita questo criterio per inviare a Microsoft report di dati sull'uso e sull'arresto anomalo. Disabilita questi criteri se non vuoi inviare questi dati a Microsoft. In entrambi i casi, gli utenti non possono modificare né sovrascrivere l'impostazione.

In Windows 10, se non si configura questo criterio, Microsoft Edge per impostazione predefinita userà i dati di diagnostica Windows. Se si abilita questo criterio, Microsoft Edge invierà solo i dati sull'utilizzo se l'impostazione dati di diagnostica Windows è impostata su Avanzato o Completo. Se si disabilita questo criterio, Microsoft Edge non invierà i dati sull'utilizzo. I dati relativi agli arresti anomali vengono inviati in base all'impostazione dei dati di diagnostica Windows. Per altre informazioni sulle impostazioni dei dati di diagnostica Windows, vedere [https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

In Windows 7, Windows 8 e macOS questo criterio controlla l'invio di dati relativi all'utilizzo e all'arresto anomalo. Se non si configura questo criterio, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.

Per abilitare questo criterio,[ SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) deve essere impostato su abilitato. Se [MetricsReportingEnabled](#metricsreportingenabled) o [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) non è configurato o disabilitato, i dati non verranno inviati a Microsoft.

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi, o istanze macOS gestite via MDM o collegate a un dominio via MCX.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: MetricsReportingEnabled
  - Nome Criteri di gruppo: Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: MetricsReportingEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: MetricsReportingEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NativeWindowOcclusionEnabled
  #### Abilita l'occlusione della finestra nativa
  
  
  #### Versioni supportate:
  - In Windows dalla versione 84 o successive

  #### Descrizione
  Abilita l'occlusione della finestra nativa in Microsoft Edge.

Se si abilita questa impostazione, per ridurre il consumo di energia e CPU, Microsoft Edge rileverà quando una finestra è coperta da altre finestre e sospenderà i pixel di disegno.

Se si disabilita questa impostazione, Microsoft Edge non rileverà quando una finestra è coperta da altre finestre.

Se non viene impostato questo criterio, il rilevamento delle finestre nascoste sarà abilitato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NativeWindowOcclusionEnabled
  - Nome Criteri di gruppo: Abilita l'occlusione della finestra nativa
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NativeWindowOcclusionEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NavigationDelayForInitialSiteListDownloadTimeout
  #### Imposta un timeout per i ritardi nello spostamento tramite schede per l'elenco siti in modalità Enterprise
  
  
  #### Versioni supportate:
  - In Windows dalla versione 84 o successive

  #### Descrizione
  Consente di impostare un timeout, in secondi, se le schede Microsoft Edge attendono lo spostamento finché il browser non avrà scaricato l'elenco iniziale dei siti in modalità Enterprise.

Questa impostazione funziona in combinazione con i criteri: [InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) impostato su “IEMode” e [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist), in cui l'elenco ha almeno una voce, e [DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload) impostato su “Tutti gli spostamenti idonei” (1).

Le schede non attenderanno più tempo del timeout per il download dell'elenco dei siti in modalità Enterprise. Se il browser non ha ancora terminato il download dell'elenco di siti in modalità Enterprise al termine del timeout, le schede Microsoft Edge continueranno comunque a navigare. Il valore del timeout non deve essere superiore a 20 secondi e non meno di un secondo.

Se si imposta il timeout in questo criterio su un valore maggiore del valore predefinito di 2 secondi, dopo 2 secondi viene visualizzata una barra informazioni. Nella barra delle informazioni è presente un pulsante che consente all'utente di interrompere il completamento del download dell'elenco dei siti in modalità Enterprise.

Se non si configura questo criterio, viene usato il timeout predefinito di 2 secondi. Questa impostazione predefinita è soggetta a modifiche in futuro.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NavigationDelayForInitialSiteListDownloadTimeout
  - Nome Criteri di gruppo: imposta un timeout per i ritardi nello spostamento tramite schede per l'elenco siti in modalità Enterprise
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NavigationDelayForInitialSiteListDownloadTimeout
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x0000000a
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NetworkPredictionOptions
  #### Abilita la previsione di rete
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente la previsione di rete e impedisce agli utenti di modificare questa impostazione.

Questo criterio controlla la prelettura DNS, la preconnessione TCP e SSL e il prerendering delle pagine Web.

Se non si configura questo criterio, la previsione di rete è abilitata ma l'utente può modificarla.

Mapping delle opzioni del criterio:

* NetworkPredictionAlways (0) = Prevedere le azioni di rete in qualsiasi connessione di rete

* NetworkPredictionWifiOnly (1) = Non supportato, se si usa questo valore, verrà considerato come se fosse impostato “Prevedi le azioni di rete su qualsiasi connessione di rete” (0).

* NetworkPredictionNever (2) = Non prevedere le azioni di rete in qualsiasi connessione di rete

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NetworkPredictionOptions
  - Nome Criteri di gruppo: Abilita la previsione di rete
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: NetworkPredictionOptions
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: NetworkPredictionOptions
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### NonRemovableProfileEnabled
  #### Configura l'accesso automatico di un utente con un profilo predefinito al proprio account aziendale o dell'istituto di istruzione
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Questo criterio determina se un utente può rimuovere il profilo di Microsoft Edge con accesso automatico con un account aziendale o dell'istituto di istruzione di un utente.

Se si abilita questo criterio, verrà creato un profilo non rimovibile con l'account aziendale o dell'istituto di istruzione dell'utente in Windows. Questo profilo non può essere disconnesso o rimosso.

Se si disabilita o non si configura questo criterio, il profilo con accesso automatico con un account aziendale o dell'istituto di istruzione di un utente in Windows può essere disconnesso o rimosso dall'utente.

Se si desidera configurare l'accesso al browser, usare il criterio [BrowserSignin](#browsersignin).

Questo criterio è disponibile solo nelle istanze Windows aggiunte a un dominio di Active Directory di Microsoft, alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: NonRemovableProfileEnabled
  - Nome Criteri di gruppo: Configura l'accesso automatico di un utente con un profilo predefinito al proprio account aziendale o dell'istituto di istruzione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: NonRemovableProfileEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### OverrideSecurityRestrictionsOnInsecureOrigin
  #### Controlla dove si applicano le restrizioni di sicurezza per origini non sicure
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica un elenco di origini (URL) o modelli di nomi host (come "*.contoso.com") per cui non si applicano restrizioni di sicurezza per le origini non sicure.

Questo criterio consente di specificare le origini consentite per le applicazioni legacy che non possono distribuire TLS o configurare un server di gestione temporanea per lo sviluppo Web interno, in modo che gli sviluppatori possano testare le funzionalità che richiedono contesti sicuri senza dover distribuire TLS nel server di gestione temporanea. Questo criterio impedisce anche che l'origine venga etichettata come "non sicura" in omnibox.

L'impostazione di un elenco di URL in questo criterio ha lo stesso effetto dell'impostazione del contrassegno della riga di comando "--unsafely-treat-insecure-origin-as-secure" su un elenco degli stessi URL separati da virgole. Se si abilita questo criterio, sostituisce il contrassegno della riga di comando.

Per altre informazioni sui contesti sicuri, vedere https://www.w3.org/TR/secure-contexts/.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: OverrideSecurityRestrictionsOnInsecureOrigin
  - Nome Criteri di gruppo: Controlla dove si applicano le restrizioni di sicurezza per origini non sicure
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\1 = "http://testserver.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\2 = "*.contoso.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: OverrideSecurityRestrictionsOnInsecureOrigin
  - Valore di esempio
``` xml
<array>
  <string>http://testserver.contoso.com/</string>
  <string>*.contoso.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PaymentMethodQueryEnabled
  #### Consente ai siti Web di eseguire query per i metodi di pagamento disponibili
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Consente di specificare se i siti Web possono verificare che l'utente disponga di metodi di pagamento salvati.

Se si disabilita questo criterio, i siti Web che usano l'API PaymentRequest.canMakePayment o PaymentRequest.hasEnrolledInstrument verranno informati che non sono disponibili metodi di pagamento.

Se si abilita o non si configura questo criterio, i siti Web possono verificare se l'utente ha metodi di pagamento salvati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PaymentMethodQueryEnabled
  - Nome Criteri di gruppo: Consente ai siti Web di eseguire query per i metodi di pagamento disponibili
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PaymentMethodQueryEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PaymentMethodQueryEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PersonalizationReportingEnabled
  #### Consente la personalizzazione degli annunci, della ricerca e delle notizie con l'invio della cronologia esplorazioni a Microsoft
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Questo criterio impedisce a Microsoft di raccogliere la cronologia esplorazioni di Microsoft Edge di un utente per personalizzare pubblicità, ricerca, notizie e altri servizi Microsoft.

Questa impostazione è disponibile solo per gli utenti con un account Microsoft. Questa impostazione non è disponibile per gli account per bambini o gli account aziendali.

Se si disabilita questo criterio, gli utenti non possono modificare o sostituire l'impostazione. Se questo criterio è abilitato o non viene configurato, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PersonalizationReportingEnabled
  - Nome Criteri di gruppo: Consente la personalizzazione degli annunci, della ricerca e delle notizie con l'invio della cronologia esplorazioni a Microsoft
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PersonalizationReportingEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PersonalizationReportingEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PinningWizardAllowed
  #### Consente la procedura guidata per Aggiungi alla barra delle applicazioni
  
  
  #### Versioni supportate:
  - In Windows dalla versione 80 o successive

  #### Descrizione
  Microsoft Edge usa la procedura guidata Aggiungi alla barra delle applicazioni per aiutare gli utenti ad aggiungere i siti suggeriti alla barra delle applicazioni. La funzionalità della procedura guidata Aggiungi alla barra delle applicazioni è abilitata per impostazione predefinita e gli utenti possono accedervi tramite Impostazioni e il menu Altro.

Se si abilita o non si configura questo criterio, gli utenti possono accedere alla procedura guidata Aggiungi alla barra delle applicazioni da Impostazioni o dal menu Altro. La procedura guidata può anche essere attivata tramite l'avvio di un protocollo.

Se si disabilita questo criterio, la procedura guidata Aggiungi alla barra delle applicazioni viene disabilitata nel menu e non può essere attivata tramite l'avvio di un protocollo.

Le impostazioni utente per abilitare o disabilitare la procedura guidata Aggiungi alla barra delle applicazioni non sono disponibili.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PinningWizardAllowed
  - Nome Criteri di gruppo: Consente la procedura guidata per Aggiungi alla barra delle applicazioni
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PinningWizardAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ProactiveAuthEnabled
  #### Abilita l'autenticazione proattiva
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di configurare se attivare l'autenticazione proattiva.

Se si abilita questo criterio, Microsoft Edge tenta di autenticare in modo proattivo l'utente connesso con i servizi Microsoft. A intervalli regolari, Microsoft Edge verifica con un servizio online la disponibilità di un manifesto aggiornato che contiene la configurazione che determina come eseguire questa operazione.

Se si disabilita questo criterio, Microsoft Edge non tenta di autenticare in modo proattivo l'utente connesso con i servizi Microsoft. Microsoft Edge non verifica più con un servizio online la disponibilità di un manifesto aggiornato che contiene la configurazione che determina come eseguire questa operazione.

Se non si configura questo criterio, l'autenticazione proattiva è attivata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ProactiveAuthEnabled
  - Nome Criteri di gruppo: Abilita l'autenticazione proattiva
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ProactiveAuthEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ProactiveAuthEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PromotionalTabsEnabled
  #### Abilita il contenuto promozionale di una scheda completa
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla la presentazione di contenuti promozionali o didattici di schede complete. Questa impostazione controlla la presentazione di pagine di benvenuto che consentono agli utenti di accedere a Microsoft Edge, scegliere il browser predefinito o scoprire di più sulle funzionalità dei prodotti.

Se si abilita (impostato su true) o non si configura questo criterio, Microsoft Edge può mostrare contenuti di schede complete agli utenti per fornire informazioni sui prodotti.

Se si disabilita (impostato su false) questo criterio, Microsoft Edge non può mostrare contenuti di schede complete agli utenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PromotionalTabsEnabled
  - Nome Criteri di gruppo: Abilita il contenuto promozionale di una scheda completa
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PromotionalTabsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PromotionalTabsEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### PromptForDownloadLocation
  #### Chiede dove salvare i file scaricati
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica se chiedere dove salvare un file prima di scaricarlo.

Se si abilita questo criterio, all'utente viene chiesto dove salvare ogni file prima di scaricarlo. Se non si configura questo criterio, i file vengono salvati automaticamente nella posizione predefinita, senza chiedere conferma all'utente.

Se non si configura questo criterio, l'utente può modificare tale impostazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: PromptForDownloadLocation
  - Nome Criteri di gruppo: Chiede dove salvare i file scaricati
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: PromptForDownloadLocation
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: PromptForDownloadLocation
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### QuicAllowed
  #### Consente il protocollo QUIC
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di utilizzare il protocollo QUIC in Microsoft Edge.

Se si abilita o non si configura questo criterio, il protocollo QUIC è consentito.

Se si disabilita questo criterio, il protocollo QUIC viene bloccato.

QUIC è un protocollo di rete a livello trasporto che può migliorare le prestazioni delle applicazioni Web che attualmente usano TCP.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: QuicAllowed
  - Nome Criteri di gruppo: Consente il protocollo QUIC
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: QuicAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: QuicAllowed
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RelaunchNotification
  #### Inviare una notifica a un utente in merito al riavvio del browser consigliato o necessario per gli aggiornamenti in sospeso
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Comunica agli utenti che è necessario riavviare Microsoft Edge per applicare un aggiornamento in sospeso.

Se non si configura questo criterio, Microsoft Edge aggiunge un'icona del cestino a destra della barra dei menu superiore per chiedere agli utenti di riavviare il browser per applicare l'aggiornamento.

Se si abilita questo criterio e lo si imposta su "Consigliato”, un avviso ricorrente informa gli utenti che è consigliato un riavvio. Gli utenti possono ignorare l'avviso e rinviare il riavvio.

Se si imposta il criterio su "Obbligatorio", un avviso ricorrente informa gli utenti che il browser verrà riavviato automaticamente al termine del periodo di notifica. Il periodo predefinito è sette giorni. È possibile configurare questo periodo con il criterio [RelaunchNotificationPeriod](#relaunchnotificationperiod).

La sessione dell'utente viene ripristinata al riavvio del browser.

Mapping delle opzioni del criterio:

* Consigliato (1) = Consigliato: mostra un avviso ricorrente all'utente che indica che è consigliato un riavvio

* Obbligatorio (2) = Obbligatorio: mostra un avviso ricorrente all'utente che indica che è necessario un riavvio

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RelaunchNotification
  - Nome Criteri di gruppo: Invia una notifica a un utente in merito al riavvio del browser consigliato o necessario per gli aggiornamenti in sospeso
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RelaunchNotification
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RelaunchNotification
  - Valore di esempio
``` xml
<integer>1</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RelaunchNotificationPeriod
  #### Imposta il periodo di tempo per le notifiche sugli aggiornamenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di impostare il periodo di tempo, in millisecondi, in cui gli utenti vengono informati che Microsoft Edge deve essere riavviato per applicare un aggiornamento in sospeso.

Durante questo periodo di tempo, l'utente verrà ripetutamente informato della necessità di un aggiornamento. In Microsoft Edge, il menu dell'app cambia per indicare che è necessario un riavvio una volta trascorso un terzo del periodo di notifica. Questa notifica cambia colore una volta trascorsi due terzi del periodo di notifica e cambierà ancora una volta al termine dell'intero periodo di notifica. Le notifiche aggiuntive abilitate dal criterio [RelaunchNotification](#relaunchnotification) seguono questa stessa pianificazione.

Se non impostato, viene usato il periodo predefinito di 604800000 millisecondi (una settimana).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RelaunchNotificationPeriod
  - Nome Criteri di gruppo: Imposta il periodo di tempo per le notifiche sugli aggiornamenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RelaunchNotificationPeriod
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x240c8400
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RelaunchNotificationPeriod
  - Valore di esempio
``` xml
<integer>604800000</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RendererCodeIntegrityEnabled
  #### Abilita l'integrità del codice del renderer
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Se si abilita o non si configura questo criterio, l'integrità del codice del renderer è abilitata. Questo criterio deve essere disabilitato solo se si verificano problemi di compatibilità con software di terze parti che devono essere eseguiti all'interno dei processi del renderer di Microsoft Edge.

La disabilitazione di questo criterio ha un effetto dannoso sulla stabilità e sulla sicurezza di Microsoft Edge perché il codice sconosciuto e potenzialmente ostile potrà essere caricato all'interno dei processi del renderer di Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RendererCodeIntegrityEnabled
  - Nome Criteri di gruppo: Abilita l'integrità del codice del renderer
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RendererCodeIntegrityEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RequireOnlineRevocationChecksForLocalAnchors
  #### Specifica se i controlli OCSP/CRL online sono necessari per i trust anchor locali
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Controlla se sono necessari controlli di revoca online (controlli OCSP/CRL). Se Microsoft Edge non è in grado di ottenere informazioni sullo stato di revoca, questi certificati vengono considerati come revocati ("hard-fail").

Se si abilita questo criterio, Microsoft Edge esegue sempre il controllo della revoca di certificati del server che sono stati convalidati e sono firmati da certificati di firma installati in locale.

Se si disabilita o non si configura questo criterio, Microsoft Edge usa le impostazioni di controllo della revoca online esistenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RequireOnlineRevocationChecksForLocalAnchors
  - Nome Criteri di gruppo: Specifica se i controlli OCSP/CRL online sono necessari per i trust anchor locali
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RequireOnlineRevocationChecksForLocalAnchors
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ResolveNavigationErrorsUseWebService
  #### Abilita la risoluzione degli errori di spostamento con un servizio Web
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente a Microsoft Edge di rilasciare una connessione senza dati per un servizio Web per testare le reti per la connettività in casi come i Wi-Fi di alberghi e aeroporti.

Se si abilita questo criterio, viene usato un servizio Web per i test di connettività di rete.

Se si disabilita questo criterio, Microsoft Edge usa le API native per provare a risolvere i problemi di connettività di rete e di spostamento.

**Nota**: ad eccezione di Windows 8 e versioni successive di Windows, Microsoft Edge usa *sempre* API native per risolvere i problemi di connettività.

Se non si configura questo criterio, Microsoft Edge rispetta le preferenze degli utenti impostate in Servizi in edge://settings/privacy.
In particolare, è presente un'opzione **Usare un servizio Web per consentire di risolvere errori di spostamento**, che può essere attivata o disattivata dall'utente. Tenere presente che se è stato abilitato questo criterio (ResolveNavigationErrorsUseWebService), l'impostazione **Usare un servizio Web per consentire di risolvere errori di spostamento** è attivata, ma l'utente non può modificare tale impostazione usando il relativo interruttore. Se questo criterio è stato disabilitato, l'impostazione **Usare un servizio Web per consentire di risolvere errori di spostamento** è disattivata e l'utente non può modificarla usando il relativo interruttore.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ResolveNavigationErrorsUseWebService
  - Nome Criteri di gruppo: Abilita la risoluzione degli errori di spostamento con un servizio Web
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: ResolveNavigationErrorsUseWebService
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ResolveNavigationErrorsUseWebService
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RestrictSigninToPattern
  #### Limita gli account che è possibile utilizzare come account principali di Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Determina quali account possono essere impostati come account principali del browser in Microsoft Edge (l'account che viene scelto durante la procedura di consenso esplicito per la sincronizzazione).

Se un utente prova a configurare un account principale del browser con un nome utente che non corrisponde a questo modello, tale utente viene bloccato e visualizza un messaggio di errore. È possibile configurare questo criterio in modo che corrisponda a più account usando un'espressione regolare Perl per il modello. Si noti che le corrispondenze con il modello supportano la distinzione tra maiuscole e minuscole. Per altre informazioni sulle regole delle espressioni regolari usate, fare riferimento ahttps://go.microsoft.com/fwlink/p/?linkid=2133903.

Se non si configura o si lascia vuoto questo criterio, gli utenti possono impostare qualsiasi account come account principale del browser in Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RestrictSigninToPattern
  - Nome Criteri di gruppo: Limita gli account che è possibile utilizzare come account principali di Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RestrictSigninToPattern
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
".*@contoso.com"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RestrictSigninToPattern
  - Valore di esempio
``` xml
<string>.*@contoso.com</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RoamingProfileLocation
  #### Imposta la directory del profilo mobile
  
  
  #### Versioni supportate:
  - In Windows dalla versione 85 o successive

  #### Descrizione
  Configura la directory da usare per archiviare la copia dei profili mobile.

Se si abilita questo criterio, Microsoft Edge usa la directory specificata per archiviare una copia dei profili mobile, purché sia stato abilitato anche il criterio [RoamingProfileSupportEnabled](#roamingprofilesupportenabled). Se si disabilita il criterio [ o non lo si configura, il valore archiviato in questo criterio non verrà usato.](#roamingprofilesupportenabled)

Per un elenco delle variabili che è possibile usare, vedere [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041).

Se non si configura questo criterio, verrà usato il percorso predefinito del profilo mobile.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RoamingProfileLocation
  - Nome Criteri di gruppo: imposta la directory del profilo mobile
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RoamingProfileLocation
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"${roaming_app_data}\\edge-profile"
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RoamingProfileSupportEnabled
  #### Abilita l'uso di copie di roaming per i dati dei profili Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows dalla versione 85 o successive

  #### Descrizione
  Abilita questo criterio per usare i profili mobile in Windows. Le impostazioni archiviate nei profili Microsoft Edge (preferite e preferenze) vengono salvate anche in un file archiviato nella cartella del profilo utente mobile (o nel percorso specificato dall'amministratore tramite il criterio [RoamingProfileLocation](#roamingprofilelocation)).

Se si disabilita questo criterio o non lo si configura, vengono usati solo i normali profili locali.

Il criterio [SyncDisabled](#syncdisabled) disabilita tutta la sincronizzazione dati, eseguendo l’override del criterio.

Per altre informazioni sull'uso dei profili utente mobile, vedere https://docs.microsoft.com/windows-server/storage/folder-redirection/deploy-roaming-user-profiles.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RoamingProfileSupportEnabled
  - Nome Criteri di gruppo: abilita l'uso di copie di roaming per i dati dei profili Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RoamingProfileSupportEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### RunAllFlashInAllowMode
  #### Estende l'impostazione dei contenuti di Adobe Flash a tutti i contenuti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita questo criterio, tutti i contenuti di Adobe Flash incorporati nei siti Web che sono impostati per consentire Adobe Flash nelle impostazioni relative ai contenuti (configurate dall'utente o da criteri aziendali) verranno eseguiti. Sono inclusi i contenuti provenienti da origini e/o contenuti di piccole dimensioni.

Per controllare quali siti Web possono eseguire Adobe Flash, vedere le specifiche nei criteri [DefaultPluginsSetting](#defaultpluginssetting), [PluginsAllowedForUrls](#pluginsallowedforurls) e [PluginsBlockedForUrls](#pluginsblockedforurls).

Se si disabilita o non si configura questo criterio, i contenuti di Adobe Flash provenienti da altre origini (da siti che non sono specificati nei tre criteri sopra indicati) o i contenuti di piccole dimensioni potrebbero essere bloccati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: RunAllFlashInAllowMode
  - Nome Criteri di gruppo: Estende l'impostazione dei contenuti di Adobe Flash a tutti i contenuti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: RunAllFlashInAllowMode
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: RunAllFlashInAllowMode
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SSLErrorOverrideAllowed
  #### Consente agli utenti di procedere nella pagina di avviso HTTPS
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Microsoft Edge mostra una pagina di avviso quando gli utenti visitano siti con errori SSL.

Se si abilita o non si configura (impostazione predefinita) questo criterio, gli utenti possono fare clic su tali pagine di avviso.

Se si disabilita questo criterio, gli utenti non potranno fare clic su una qualsiasi pagina di avviso.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SSLErrorOverrideAllowed
  - Nome Criteri di gruppo: Consente agli utenti di procedere nella pagina di avviso HTTPS
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SSLErrorOverrideAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SSLErrorOverrideAllowed
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SSLVersionMin
  #### Versione TLS minima abilitata
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Configura la versione minima supportata del protocollo TLS. Se non si configura questo criterio, Microsoft Edge usa la versione minima predefinita, TLS 1.0.

Se il criterio viene abilitato, Microsoft Edge non userà alcuna versione di SSL/TLS più vecchia di quella specificata. Qualsiasi valore non riconosciuto viene ignorato.

Mapping delle opzioni del criterio:

* TLSv1 (tls1) = TLS 1.0

* TLSv1.1 (tls1.1) = TLS 1.1

* TLSv1.2 (tls1.2) = TLS 1.2

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SSLVersionMin
  - Nome Criteri di gruppo: Versione TLS minima abilitata
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SSLVersionMin
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"tls1"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SSLVersionMin
  - Valore di esempio
``` xml
<string>tls1</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SaveCookiesOnExit
  #### Salva i cookie quando Microsoft Edge si chiude
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Quando questo criterio è abilitato, quando il browser viene chiuso, il set specificato di cookie è esente dall'eliminazione. Questo criterio è efficace solo quando:
- L’interruttore "cookie e altri dati del sito" sono configurati in impostazioni/privacy e servizi/cancellazione dei dati per la navigazione in chiusura o
- Il criterio [ ClearBrowsingDataOnExit](#clearbrowsingdataonexit) è abilitato o
- Il criterio [DefaultCookiesSetting](#defaultcookiessetting) è impostato su “Mantieni cookie per la durata della sessione”.

È possibile definire un elenco dei siti, in base ai modelli di URL, che consentiranno di mantenere i cookie nelle varie sessioni.

Nota: gli utenti possono continuare a modificare l'elenco dei siti dei cookie aggiungendo o rimuovendo URL. Tuttavia, gli URL aggiunti da un amministratore non possono essere rimossi.

Se abiliti questo criterio, l'elenco dei cookie non sarà deselezionato quando il browser viene chiuso.

Se non disabiliti o configuri questo criterio, verrà usata la configurazione personale dell'utente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco GP: SaveCookiesOnExit
  - Nome Criteri di gruppo: Salva i cookie quando Microsoft Edge viene chiude
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\SpellcheckLanguage
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: SaveCookiesOnExit
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SavingBrowserHistoryDisabled
  #### Disattiva il salvataggio della cronologia del browser
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disabilita il salvataggio della cronologia del browser e impedisce agli utenti di modificare questa impostazione.

Se si abilita questo criterio, la cronologia esplorazioni non viene salvata. Viene disabilitata anche la sincronizzazione delle schede.

Se si disabilita o non si configura questo criterio, la cronologia esplorazioni viene salvata.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SavingBrowserHistoryDisabled
  - Nome Criteri di gruppo: Disattiva il salvataggio della cronologia del browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SavingBrowserHistoryDisabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SavingBrowserHistoryDisabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ScreenCaptureAllowed
  #### Consente o rifiuta l'acquisizione dello schermo
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Se si abilita o non si configura questo criterio, una pagina Web può usare le API di condivisione dello schermo (ad esempio, getDisplayMedia() o l'API Desktop Capture extension) per acquisire lo schermo.
Se si disabilita questo criterio, le chiamate alle API di condivisione dello schermo avranno esito negativo. Ad esempio, se si usa una riunione online basata sul Web, la condivisione di video o schermate non funzionerà.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ScreenCaptureAllowed
  - Nome Criteri di gruppo: Consente o rifiuta l'acquisizione dello schermo
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ScreenCaptureAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ScreenCaptureAllowed
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ScrollToTextFragmentEnabled
  #### Consente lo scorrimento al testo specificato nei frammenti di URL
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Questa funzionalità consente a collegamenti ipertestuali e URL della barra degli indirizzi di reindirizzare a testo specifico in una pagina Web, che verrà visualizzato al termine del caricamento della pagina Web.

Se si abilita o non si configura questo criterio, verranno visualizzati specifici frammenti di testo nella pagina Web tramite un URL.

Se si disabilita questo criterio, non verranno visualizzati specifici frammenti di testo nella pagina Web tramite un URL.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ScrollToTextFragmentEnabled
  - Nome Criteri di gruppo: Consente lo scorrimento al testo specificato nei frammenti di URL
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ScrollToTextFragmentEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ScrollToTextFragmentEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SearchSuggestEnabled
  #### Abilita i suggerimenti per la ricerca
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilita i suggerimenti per la ricerca sul Web nell'elenco dei suggerimenti automatici e nella barra degli indirizzi di Microsoft Edge e impedisce agli utenti di modificare questo criterio.

Se si abilita questo criterio, vengono usati i suggerimenti per la ricerca sul Web.

Se si disabilita questo criterio, i suggerimenti per la ricerca sul Web non vengono mai usati, ma vengono visualizzati i suggerimenti relativi alla cronologia e ai preferiti locali. Se si disabilita questo criterio, i caratteri digitati e gli URL visitati non verranno inclusi nella telemetria di Microsoft.

Se il criterio non è impostato, i suggerimenti per la ricerca sono abilitati, ma l'utente può modificare tale impostazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SearchSuggestEnabled
  - Nome Criteri di gruppo: Abilita i suggerimenti per la ricerca
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: SearchSuggestEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SearchSuggestEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SecurityKeyPermitAttestation
  #### Siti Web o domini che non necessitano dell'autorizzazione per usare l'attestazione della chiave di sicurezza diretta
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica i siti Web e i domini che non necessitano dell'autorizzazione esplicita dell'utente quando sono richiesti certificati di attestazione dalle chiavi di sicurezza. Inoltre, alla chiave di sicurezza viene inviato un segnale che indica che è possibile usare un'attestazione specifica. Se non si esegue questa operazione, gli utenti vengono informati ogni volta che un sito richiede l'attestazione di chiavi di sicurezza.

I siti (come https://contoso.com/some/path)) corrispondono solo come U2F appIDs. I domini (come contoso.com) corrispondono solo come webauthn RP IDs. Per includere sia le API U2F sia le API webauthn per un determinato sito, è necessario elencare il dominio e l'URL dell'appID.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SecurityKeyPermitAttestation
  - Nome Criteri di gruppo: Siti Web o domini che non necessitano dell'autorizzazione per usare l'attestazione della chiave di sicurezza diretta
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\SecurityKeyPermitAttestation
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SecurityKeyPermitAttestation\1 = "https://contoso.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SecurityKeyPermitAttestation
  - Valore di esempio
``` xml
<array>
  <string>https://contoso.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SendIntranetToInternetExplorer
  #### Invia tutti i siti Intranet a Internet Explorer
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Per istruzioni sulla configurazione dell'esperienza ottimale per la modalità di Internet Explorer, vedere [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SendIntranetToInternetExplorer
  - Nome Criteri di gruppo: Invia tutti i siti Intranet a Internet Explorer
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SendIntranetToInternetExplorer
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SendSiteInfoToImproveServices
  #### Invia informazioni sul sito per migliorare i servizi Microsoft (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  questa impostazione è deprecata. È attualmente supportato, ma diventerà obsoleto in Microsoft Edge 89. Questo criterio è stato sostituito dal nuovo criterio:  [DiagnosticData](#diagnosticdata)per Windows 7, Windows 8 e macOS. Questo criterio è stato sostituito da Consenti telemetria per il rientro su Windows 10 ([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)).

Questo criterio consente di inviare informazioni sui siti Web visitati in Microsoft Edge a Microsoft per migliorare i servizi, ad esempio la ricerca.

Abilitare questo criterio per inviare a Microsoft le informazioni sui siti Web visitati in Microsoft Edge. Disabilitare questo criterio per non inviare a Microsoft le informazioni sui siti Web visitati in Microsoft Edge. In entrambi i casi, gli utenti non possono modificare né sovrascrivere l'impostazione.

In Windows 10, se non si configura questo criterio, Microsoft Edge per impostazione predefinita userà i dati di diagnostica Windows. Se questi criteri sono abilitati, Microsoft Edge invierà solo le informazioni sui siti Web visitati in MIcrosoft Edge se l'impostazione dei dati di diagnostica Windows è impostata su Completo. Se questi criteri sono disabilitati, Microsoft Edge non invierà le informazioni sui siti Web visitati. Per altre informazioni sulle impostazioni dei dati di diagnostica Windows, vedere [https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

In Windows 7, Windows 8 e Mac, questo criterio controlla l'invio di informazioni sui siti Web visitati. Se non si configura questo criterio, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.

Per abilitare questo criterio, [MetricsReportingEnabled](#metricsreportingenabled) deve essere impostato su Abilitato. Se [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) o [MetricsReportingEnabled](#metricsreportingenabled) non è configurato o disabilitato, i dati non verranno inviati a Microsoft.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SendSiteInfoToImproveServices
  - Nome Criteri di gruppo: Invia informazioni sul sito per migliorare i servizi Microsoft (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SendSiteInfoToImproveServices
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SendSiteInfoToImproveServices
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SensorsAllowedForUrls
  #### Consenti l'accesso ai sensori in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Definisci un elenco di siti in base ai modelli di URL, che possono accedere a e usare sensori come il sensore di movimento di luce.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultSensorsSetting](#defaultsensorssetting) (se impostato) o la configurazione personale dell'utente.

Per i modelli di URL che non corrispondono a questo criterio, viene usato l'ordine di precedenza seguente: il criterio [SensorsBlockedForUrls](#sensorsblockedforurls) (se è presente una corrispondenza), il criterio [DefaultSensorsSetting](#defaultsensorssetting) (se impostato) oppure le impostazioni personali dell'utente.

I modelli di URL definiti in questo criterio non possono essere in conflitto con quelli configurati nel criterio [SensorsBlockedForUrls](#sensorsblockedforurls). Non è possibile consentire e bloccare un URL.

Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SensorsAllowedForUrls
  - Nome Criteri di gruppo: consenti l'accesso ai sensori in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SensorsAllowedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SensorsBlockedForUrls
  #### Blocca l'accesso ai sensori in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Definisci un elenco di siti in base ai modelli di URL, che possono accedere a sensori come il sensore di movimento di luce.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultSensorsSetting](#defaultsensorssetting) (se impostato) o la configurazione personale dell'utente.

Per i modelli di URL che non corrispondono a questo criterio, viene usato l'ordine di precedenza seguente: il criterio [SensorsAllowedForUrls](#sensorsallowedforurls) (se è presente una corrispondenza), il criterio [DefaultSensorsSetting](#defaultsensorssetting) (se impostato) oppure le impostazioni personali dell'utente.

I modelli di URL definiti in questo criterio non possono essere in conflitto con quelli configurati nel criterio [SensorsAllowedForUrls](#sensorsallowedforurls). Non è possibile consentire e bloccare un URL.

Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SensorsBlockedForUrls
  - Nome Criteri di gruppo: blocca l'accesso ai sensori in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SensorsBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SerialAskForUrls
  #### Consenti API Serial in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che possono chiedere all'utente di accedere a una porta seriale.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultSerialGuardSetting](#defaultserialguardsetting) (se impostato) o la configurazione personale dell'utente.

Per i modelli di URL che non corrispondono a questo criterio, viene usato l'ordine di precedenza seguente: il criterio [SerialBlockedForUrls](#serialblockedforurls) (se è presente una corrispondenza), il criterio [DefaultSerialGuardSetting](#defaultserialguardsetting) (se impostato) oppure le impostazioni personali dell'utente.

I modelli di URL definiti in questo criterio non possono essere in conflitto con quelli configurati nel criterio [SerialBlockedForUrls](#serialblockedforurls). Non è possibile consentire e bloccare un URL.

Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SerialAskForUrls
  - Nome Criteri di gruppo: consenti Serial API in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SerialAskForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SerialBlockedForUrls
  #### Blocca Serial API in siti specifici
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che non possono chiedere all'utente di autorizzarli ad accedere a una porta seriale.

Se non si configura questo criterio, per tutti i siti si usa il valore predefinito globale del criterio [DefaultSerialGuardSetting](#defaultserialguardsetting) (se impostato) o la configurazione personale dell'utente.

Per i modelli di URL che non corrispondono a questo criterio, viene usato l'ordine di precedenza seguente: il criterio [SerialAskForUrls](#serialaskforurls) (se è presente una corrispondenza), il criterio [DefaultSerialGuardSetting](#defaultserialguardsetting) (se impostato) oppure le impostazioni personali dell'utente.

I modelli di URL in questo criterio non possono essere in conflitto con quelli configurati nel criterio [SerialAskForUrls](#serialaskforurls). Non è possibile consentire e bloccare un URL.

Per informazioni dettagliate sui modelli di URL validi, vedere [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SerialBlockedForUrls
  - Nome Criteri di gruppo: blocca Serial API in siti specifici
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\2 = "[*.]contoso.edu"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SerialBlockedForUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### ShowOfficeShortcutInFavoritesBar
  #### Mostra la scelta rapida da tastiera di Microsoft Office nella barra dei Preferiti (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Questa politica non ha funzionato come previsto a causa di cambiamenti nei requisiti operativi. Therefore it's deprecated and should not be used.

Specifica se includere un collegamento a Office.com nella barra Preferiti. For users signed into Microsoft Edge the shortcut takes users to their Microsoft Office apps and docs. If you enable or don't configure this policy, users can choose whether to see the shortcut by changing the toggle in the favorites bar context menu.
Se si disabilita questo criterio, il collegamento non viene mostrato.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: ShowOfficeShortcutInFavoritesBar
  - Nome Criteri di gruppo: mostra il collegamento a Microsoft Office nella barra dei Preferiti (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: ShowOfficeShortcutInFavoritesBar
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: ShowOfficeShortcutInFavoritesBar
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SignedHTTPExchangeEnabled
  #### Abilita il supporto di Signed HTTP Exchange (SXG)
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Abilita il supporto per Signed HTTP Exchange (SXG).

Se questo criterio non è impostato o abilitato, Microsoft Edge accetta i contenuti Web serviti come Signed HTTP Exchange.

Se questo criterio è disabilitato, non è possibile caricare Signed HTTP Exchange.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SignedHTTPExchangeEnabled
  - Nome Criteri di gruppo: Abilita il supporto di Signed HTTP Exchange (SXG)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SignedHTTPExchangeEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SignedHTTPExchangeEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SitePerProcess
  #### Abilita l'isolamento del sito per tutte le origini
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Il criterio "SitePerProcess" può essere usato per impedire agli utenti di rifiutare esplicitamente il comportamento predefinito dell'isolamento di tutti i siti. È anche possibile usare il criterio [IsolateOrigins](#isolateorigins) per isolare altre origini più specifiche.

Se si abilita questo criterio, gli utenti non possono rifiutare esplicitamente il comportamento predefinito in cui ogni sito viene eseguito nel relativo processo specifico.

Se si disabilita o non si configura questo criterio, un utente può rifiutare esplicitamente l'isolamento del sito.  Ad esempio, usando la voce "Disabilitare l'isolamento del sito" entry in edge://flags. Se si disabilita o non si configura il criterio, l'isolamento del sito non viene disattivato.


  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SitePerProcess
  - Nome Criteri di gruppo: Abilita l'isolamento del sito per tutte le origini
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SitePerProcess
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SitePerProcess
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SpellcheckEnabled
  #### Abilita il controllo ortografico
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita o non si configura questo criterio, l'utente può usare il controllo ortografico.

Se si disabilita questo criterio, l'utente non può usare il controllo ortografico e i criteri [SpellcheckLanguage](#spellchecklanguage) e [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) sono disabilitati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SpellcheckEnabled
  - Nome Criteri di gruppo: Abilita il controllo ortografico
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SpellcheckEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SpellcheckEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SpellcheckLanguage
  #### Abilita lingue specifiche del controllo ortografico
  
  
  #### Versioni supportate:
  - In Windows dalla versione 77 o successive

  #### Descrizione
  Abilita lingue diverse per il controllo ortografico. Tutte le lingue specificate dall'utente che non sono riconosciute verranno ignorate.

Se si abilita questo criterio, il controllo ortografico è abilitato per le lingue specificate, oltre che per tutte le lingue abilitate dall'utente.

Se si disabilita o non si configura questo criterio, non viene apportata alcuna modifica alle preferenze del controllo ortografico dell'utente.

Se il criterio [SpellcheckEnabled](#spellcheckenabled) è disabilitato, questo criterio non avrà alcun effetto.

Se una lingua è inclusa nel criterio "SpellcheckLanguage" e nel criterio [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist), la lingua del controllo ortografico è abilitata.

Le lingue supportate sono: af, bg, ca, cs, cy, da, de, el, en-AU, en-CA, en-GB, en-US, es, es-419, es-AR, es-ES, es-MX, es-US, et, fa, fo, fr, he, hi, hr, hu, id, it, ko, lt, lv, nb, nl, pl, pt-BR, pt-PT, ro, ru, sh, sk, sl, sq, sr, sv, ta, tg, tr, uk, vi.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SpellcheckLanguage
  - Nome Criteri di gruppo: Abilita lingue specifiche del controllo ortografico
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\SpellcheckLanguage
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\2 = "es"

```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SpellcheckLanguageBlocklist
  #### Forza la disabilitazione delle lingue del controllo ortografico
  
  
  #### Versioni supportate:
  - In Windows dalla versione 78 o successive

  #### Descrizione
  Forza la disabilitazione delle lingue del controllo ortografico. Le lingue non riconosciute nell'elenco verranno ignorate.

Se si abilita questo criterio, il controllo ortografico verrà disabilitato per le lingue specificate. L'utente può comunque abilitare o disabilitare il controllo ortografico per le lingue non presenti nell'elenco.

Se si disabilita o non si configura questo criterio, non viene apportata alcuna modifica alle preferenze del controllo ortografico dell'utente.

Se il criterio [SpellcheckEnabled](#spellcheckenabled) è disabilitato, questo criterio non avrà alcun effetto.

Se una lingua è inclusa nel criterio [SpellcheckLanguage](#spellchecklanguage) e nel criterio "SpellcheckLanguageBlocklist", la lingua del controllo ortografico è abilitata.

Le lingue attualmente supportate sono: af, bg, ca, cs, da, de, el, en-AU, en-CA, en-GB, en-US, es, es-419, es-AR, es-ES, es-MX, es-US, et, fa, fo, fr, he, hi, hr, hu, id, it, ko, lt, lv, nb, nl, pl, pt-BR, pt-PT, ro, ru, sh, sk, sl, sq, sr, sv, ta, tg, tr, uk, vi.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SpellcheckLanguageBlocklist
  - Nome Criteri di gruppo: Forza la disabilitazione delle lingue del controllo ortografico
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\SpellcheckLanguageBlocklist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\2 = "es"

```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### StricterMixedContentTreatmentEnabled
  #### Abilita un trattamento più rigoroso per contenuti misti (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81 o successive

  #### Descrizione
  Questo criterio è deprecato perché è solo un meccanismo a breve termine che offre alle aziende più tempo per aggiornare i contenuti Web se e quando viene rilevata incompatibilità con un trattamento più rigoroso dei contenuti misti. Non funzionerà in Microsoft Edge versione 85.

Questo criterio controlla il trattamento per i contenuti misti (contenuti HTTP in siti HTTPS) nel browser.

Se si imposta questo criterio su true o non si configura, i contenuti audio e video misti verranno automaticamente aggiornati a HTTPS (ovvero, l'URL verrà riscritto come HTTPS, senza un fallback se la risorsa non è disponibile su HTTPS) e verrà visualizzato l'avviso "Non sicuro" nella barra degli URL per i contenuti misti di immagini.

Se si imposta il criterio su false, gli aggiornamenti automatici verranno disabilitati per i contenuti audio e video e non verranno visualizzati avvisi per le immagini.

Questo criterio non influisce su altri tipi di contenuti misti diversi da audio, video e immagini.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: StricterMixedContentTreatmentEnabled
  - Nome Criteri di gruppo: Abilita un trattamento più rigoroso per contenuti misti (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: StricterMixedContentTreatmentEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: StricterMixedContentTreatmentEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SuppressUnsupportedOSWarning
  #### Elimina l'avviso del sistema operativo non supportato
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disattiva l'avviso che viene visualizzato quando Microsoft Edge è in esecuzione in un computer o un sistema operativo non più supportato.

Se il criterio è impostato su false o non è configurato, verranno visualizzati degli avvisi in tali computer o sistemi operativi non supportati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SuppressUnsupportedOSWarning
  - Nome Criteri di gruppo: Elimina l'avviso del sistema operativo non supportato
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: SuppressUnsupportedOSWarning
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SuppressUnsupportedOSWarning
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SyncDisabled
  #### Disabilita la sincronizzazione dei dati con i servizi di sincronizzazione di Microsoft
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Disabilita la sincronizzazione dei dati in Microsoft Edge. Questo criterio impedisce anche che venga visualizzata la richiesta di consenso per la sincronizzazione.

Se il criterio non viene impostato o lo si applica come consigliato, gli utenti potranno attivare o disattivare la sincronizzazione. Se si applica questo criterio come obbligatorio, gli utenti non potranno attivare la sincronizzazione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SyncDisabled
  - Nome Criteri di gruppo: Disabilita la sincronizzazione dei dati con i servizi di sincronizzazione di Microsoft
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: SyncDisabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SyncDisabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### SyncTypesListDisabled
  #### Configura l'elenco dei tipi esclusi dalla sincronizzazione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 83 o successive

  #### Descrizione
  Se si abilita questo criterio, tutti i tipi di dati specificati verranno esclusi dalla sincronizzazione. Questo criterio può essere usato per limitare il tipo di dati caricati nel servizio di sincronizzazione di Microsoft Edge.

È possibile specificare uno dei tipi di dati seguenti per questo criterio: “preferiti”, “impostazioni”, “password", “addressesAndMore”, “estensioni”, “cronologia”, “openTabs” e “raccolte”. Si noti che i nomi dei tipi di dati fanno distinzione tra maiuscole e minuscole.

Gli utenti non potranno eseguire l'override dei tipi di dati disabilitati.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: SyncTypesListDisabled
  - Nome Criteri di gruppo: Configura l'elenco dei tipi esclusi dalla sincronizzazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\SyncTypesListDisabled
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\SyncTypesListDisabled\1 = "favorites"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: SyncTypesListDisabled
  - Valore di esempio
``` xml
<array>
  <string>favorites</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TLS13HardeningForLocalAnchorsEnabled
  #### Abilita una funzionalità di sicurezza TLS 1.3 per i trust anchor locali (obsoleto)
  
  >OBSOLETO: questo criterio è obsoleto e non funziona dopo Microsoft Edge 85.
  #### Versioni supportate:
  - In Windows e macOS dalla versione 81, fino alla versione 85

  #### Descrizione
  Questo criterio non funziona perché doveva essere solo un meccanismo a breve termine per dare alle aziende più tempo per aggiornare i proxy interessati.

Questo criterio controlla una funzionalità di sicurezza in TLS 1.3 che protegge le connessioni dagli attacchi di downgrade. È compatibile con le versioni precedenti e non influisce sulle connessioni ai server o ai proxy conformi a TLS 1.2. Tuttavia, nelle versioni meno recenti di alcuni proxy di intercettazione TLS sono presenti difetti di implementazione che le rendono non compatibili.

Se si abilita o non si imposta questo criterio, Microsoft Edge consentirà tali protezioni per tutte le connessioni.

Se si disabilita questo criterio, Microsoft Edge disabiliterà queste protezioni per le connessioni autenticate con certificati di firma installati in locale. Queste protezioni sono sempre abilitate per le connessioni autenticate con certificati di firma pubblicamente attendibili.

Questo criterio può essere usato per testare l'eventuale presenza di proxy interessati e aggiornarli. I proxy interessati causeranno un esito negativo per le connessioni con un codice errore di ERR_TLS13_DOWNGRADE_DETECTED.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TLS13HardeningForLocalAnchorsEnabled
  - Nome Criteri di gruppo: Abilita una funzionalità di sicurezza TLS 1.3 per i trust anchor locali
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: TLS13HardeningForLocalAnchorsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: TLS13HardeningForLocalAnchorsEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TLSCipherSuiteDenyList
  #### Specifica i pacchetti di crittografia TLS da disabilitare
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 85 o successive

  #### Descrizione
  Configura l'elenco dei pacchetti di crittografia disabilitati per connessioni TLS.

Se si configura questo criterio, l'elenco dei pacchetti di crittografia configurati non verranno usati per stabilire connessioni TLS.

Se non si configura questo criterio, il browser sceglierà i pacchetti crittografici TLS da usare.

I valori dei pacchetti di crittografia da disabilitare sono specificati come valori esadecimali a 16 bit. I valori sono assegnati dal registro di sistema IANA (Internet Assigned Numbers Authority).

Il pacchetto di crittografia 1.3 TLS TLS_AES_128_GCM_SHA256 (0x1301) è obbligatorio per TLS 1,3 e non può essere disabilitato con questo criterio.

Questo criterio non influisce sulle connessioni basate su QUIC. QUIC può essere disattivato tramite il criterio [QuicAllowed](#quicallowed).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TLSCipherSuiteDenyList
  - Nome Criteri di gruppo: Specifica i pacchetti di crittografia TLS da disabilitare
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\TLSCipherSuiteDenyList
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\1 = "0x1303"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\2 = "0xcca8"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\3 = "0xcca9"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave preferenza: TLSCipherSuiteDenyList
  - Valore di esempio
``` xml
<array>
  <string>0x1303</string>
  <string>0xcca8</string>
  <string>0xcca9</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TabFreezingEnabled
  #### Consente il blocco delle schede di sfondo
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 79 o successive

  #### Descrizione
  Controlla se Microsoft Edge può bloccare le schede in background per almeno 5 minuti.

Il blocco delle schede riduce l'utilizzo della CPU, della batteria e della memoria. Microsoft Edge usa funzionalità euristiche per evitare il blocco delle schede utili in background, come la visualizzazione delle notifiche, la riproduzione di contenuti audio e lo streaming di contenuti video.

Se si abilita o non si configura questo criterio, le schede che sono state in background per almeno 5 minuti potrebbero essere bloccate.

Se si disabilita questo criterio, non verrà bloccata nessuna scheda.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TabFreezingEnabled
  - Nome Criteri di gruppo: Consente il blocco delle schede di sfondo
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: TabFreezingEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: TabFreezingEnabled
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TaskManagerEndProcessEnabled
  #### Abilita i processi finali nel servizio di gestione attività del browser
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Se si abilita o non si configura questo criterio, gli utenti possono terminare i processi nella gestione attività del browser. Se viene disabilitato, gli utenti non possono terminare i processi e il pulsante Termina processo viene disabilitato nella gestione attività del browser.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TaskManagerEndProcessEnabled
  - Nome Criteri di gruppo: Abilita i processi finali nel servizio di gestione attività del browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: TaskManagerEndProcessEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: TaskManagerEndProcessEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TotalMemoryLimitMb
  #### Imposta un limite per i megabyte di memoria che possono essere usati in un'unica istanza di Microsoft Edge
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Configura la quantità di memoria che una singola istanza di Microsoft Edge può usare prima che le schede vengano eliminate per risparmiare memoria. La memoria usata dalla scheda verrà liberata e sarà necessario ricaricare la scheda quando verrà aperta di nuovo.

Se si abilita questo criterio, il browser inizierà a rimuovere le schede per risparmiare memoria dopo il superamento del limite. Tuttavia, non ci sono garanzie che il browser sia in esecuzione sempre sotto il limite. Qualsiasi valore inferiore a 1024 verrà arrotondato per eccesso a 1024.

Se non si imposta questo criterio, il browser tenterà di risparmiare memoria solo dopo che viene rilevata una quantità di memoria fisica del computer in uso insufficiente.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TotalMemoryLimitMb
  - Nome Criteri di gruppo: Imposta un limite per i megabyte di memoria che possono essere usati in un'unica istanza di Microsoft Edge
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: TotalMemoryLimitMb
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000800
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: TotalMemoryLimitMb
  - Valore di esempio
``` xml
<integer>2048</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TrackingPrevention
  #### Blocca il monitoraggio dell'attività di esplorazione sul Web degli utenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 78 o successive

  #### Descrizione
  Consente di decidere se impedire ai siti Web di tenere traccia delle attività di esplorazione del Web degli utenti.

Se si disabilita o non si configura questo criterio, gli utenti possono impostare il proprio livello di prevenzione del rilevamento.

Mapping delle opzioni del criterio:

* TrackingPreventionOff (0) = Disattivato (nessuna prevenzione del rilevamento)

* TrackingPreventionBasic (1) = Di base (blocca i tracker dannosi, contenuti e annunci verranno personalizzati)

* TrackingPreventionBalanced (2) = Bilanciato (blocca i tracker dannosi e i tracker di siti non visitati dall'utente; contenuti e annunci saranno meno personalizzati)

* TrackingPreventionStrict (3) = Con restrizioni (blocca i tracker dannosi e la maggior parte dei tracker di tutti i siti; contenuti e annunci avranno una personalizzazione minima. alcune parti dei siti potrebbero non funzionare)

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TrackingPrevention
  - Nome Criteri di gruppo: Blocca il monitoraggio dell'attività di esplorazione sul Web degli utenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: TrackingPrevention
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000002
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: TrackingPrevention
  - Valore di esempio
``` xml
<integer>2</integer>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### TranslateEnabled
  #### Abilita Traduci
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Abilita il servizio di traduzione Microsoft integrato in Microsoft Edge.

Se si abilita questo criterio, Microsoft Edge offre funzionalità di traduzione all'utente mostrando un riquadro a comparsa di traduzione integrato, se necessario, e un'opzione di traduzione nel menu di scelta rapida selezionabile con il pulsante destro del mouse.

Disabilitare questo criterio per disabilitare tutte le funzionalità di traduzione integrate.

Se non si configura il criterio, gli utenti possono scegliere se usare o meno la funzionalità di traduzione.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: sì
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: TranslateEnabled
  - Nome Criteri di gruppo: Abilita Traduci
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): Modelli amministrativi/Microsoft Edge - Impostazioni predefinite (gli utenti possono eseguire l'override)/
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): SOFTWARE\Criteri\Microsoft\Edge\Recommended
  - Nome valore: TranslateEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: TranslateEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### URLAllowlist
  #### Definisce un elenco di URL consentiti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente l'accesso agli URL indicati, come eccezioni rispetto all'elenco di URL bloccati.

Formattare il modello URL in base a [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

È possibile usare questo criterio per aprire eccezioni degli elenchi di indirizzi bloccati restrittivi. Ad esempio, è possibile includere "*" nell'elenco di indirizzi bloccati per bloccare tutte le richieste e quindi usare questo criterio per consentire l'accesso a un elenco limitato di URL. È possibile usare questo criterio per aprire eccezioni a determinati schemi, sottodomini di altri domini, porte o percorsi specifici.

Il filtro più specifico determina se un URL è bloccato o consentito. L'elenco di indirizzi consentiti avrà la precedenza sull'elenco di quelli bloccati.

Questo criterio è limitato a 1.000 voci; le voci successive vengono ignorate.

Questo criterio consente anche al browser di richiamare automaticamente applicazioni esterne registrate come gestori protocollo per protocolli come “tel:” o “ssh:”.

Se non si configura questo criterio, non sono presenti eccezioni rispetto all'elenco di indirizzi bloccati nel criterio [URLBlocklist](#urlblocklist).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: URLAllowlist
  - Nome Criteri di gruppo: Definisce un elenco di URL consentiti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\URLAllowlist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\5 = ".exact.hostname.com"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: URLAllowlist
  - Valore di esempio
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### URLBlocklist
  #### Blocca l'accesso a un elenco di URL
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Definisce un elenco di siti, in base ai modelli URL, che sono bloccati (gli utenti non possono caricarli).

Formattare il modello URL in base a [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322).

È possibile definire eccezioni nel criterio [URLAllowlist](#urlallowlist). Questi criteri sono limitati a 1.000 voci; le voci successive vengono ignorate.

Tenere presente che non è consigliabile bloccare gli URL "edge://*" interni: ciò potrebbe comportare errori imprevisti.

Questo criterio non impedisce l'aggiornamento dinamico della pagina con JavaScript. Ad esempio, se si blocca "contoso.com/abc", gli utenti potrebbero comunque visitare "contoso.com" e fare clic su un collegamento per accedere a "contoso.com/abc", a condizione che la pagina non venga aggiornata.

Se non si configura questo criterio, non viene bloccato nessun URL.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: URLBlocklist
  - Nome Criteri di gruppo: Blocca l'accesso a un elenco di URL
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\URLBlocklist
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\3 = "hosting.com/bad_path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\5 = ".exact.hostname.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\6 = "file://*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\7 = "custom_scheme:*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\8 = "*"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: URLBlocklist
  - Valore di esempio
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/bad_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
  <string>file://*</string>
  <string>custom_scheme:*</string>
  <string>*</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### UserAgentClientHintsEnabled
  #### Abilita la funzionalità User-Agent Client Hints (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 86 o successive

  #### Descrizione
  Questo criterio è deprecato perché è solo un meccanismo a breve termine che offre alle aziende più tempo per aggiornare i contenuti Web se e quando viene rilevata incompatibilità con la funzione suggerimenti client agente utente. Non funzionerà in Microsoft Edge versione 89.

Quando viene abilitata, la funzionalità User-Agent Client Hints invia intestazioni della richiesta granulari che forniscono informazioni sul browser utente (ad esempio, la versione dl browser) e sull’ambiente (ad esempio, l’architettura del sistema).

Si tratta di una funzionalità aggiuntiva, ma le nuove intestazioni potrebbero interrompere alcuni siti Web che limitano i caratteri che le richieste potrebbero contenere. 

Se si abilita o non si configura questo criterio, la funzionalità User-Agent Client Hints viene abilitata. Se si disabilita questo criterio, questa funzionalità non è disponibile.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: UserAgentClientHintsEnabled
  - Nome Criteri di gruppo: Abilita la funzionalità User-Agent Client Hints (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: UserAgentClientHintsEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: UserAgentClientHintsEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### UserDataDir
  #### Imposta la directory dei dati dell'utente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Imposta la directory da usare per archiviare i dati degli utenti.

Se si abilita questo criterio, Microsoft Edge usa la directory specificata indipendentemente dal fatto che l'utente abbia impostato il contrassegno della riga di comando "--user-data-dir".

Se non si abilita questo criterio, viene usato il percorso del profilo predefinito, ma l'utente può sostituirlo usando il contrassegno "--user-data-dir". Gli utenti possono trovare la directory del profilo in edge://version/ nel percorso del profilo.

Per evitare perdite di dati o altri errori, non configurare questo criterio su una directory radice di un volume o su una directory utilizzata per altri scopi, perché Microsoft Edge ne gestisce il contenuto.

Per un elenco delle variabili che è possibile usare, vedere [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: UserDataDir
  - Nome Criteri di gruppo: Imposta la directory dei dati dell'utente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: UserDataDir
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"${users}/${user_name}/Edge"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: UserDataDir
  - Valore di esempio
``` xml
<string>${users}/${user_name}/Edge</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### UserDataSnapshotRetentionLimit
  #### Limita il numero di snapshot dei dati utente conservati per l'uso in caso di ripristino di emergenza
  
  
  #### Versioni supportate:
  - In Windows dalla versione 86 o successive

  #### Descrizione
  Dopo ogni aggiornamento della versione principale, Microsoft Edge creerà uno snapshot delle parti dei dati di esplorazione dell'utente da usare in caso di emergenza successiva che richieda un ripristino dello stato precedente temporaneo della versione. Se è stato eseguito un ripristino dello stato precedente temporaneo a una versione per cui un utente dispone di uno snapshot corrispondente, i dati dello snapshot vengono ripristinati. Questo consente agli utenti di mantenere impostazioni quali segnalibri e dati di riempimento automatico.

Se non si imposta questo criterio, verrà usato il valore predefinito di 3 snapshot.

Se si imposta questo criterio, i vecchi snapshot vengono eliminati in base alle esigenze per rispettare il limite impostato. Se si imposta questo criterio su 0, non viene eseguita alcuno snapshot.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Numero intero

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: UserDataSnapshotRetentionLimit
  - Nome Criteri di gruppo: limita il numero di snapshot dei dati utente conservati per l'uso in caso di ripristino dello stato precedente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: UserDataSnapshotRetentionLimit
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000003
```


  

  [Torna all'inizio](#microsoft-edge---policies)

  ### UserFeedbackAllowed
  #### Consente il feedback degli utenti
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Microsoft Edge usa la funzionalità di feedback (abilitata per impostazione predefinita) per consentire agli utenti di inviare feedback, suggerimenti o questionari dei clienti e di segnalare eventuali problemi riscontrati con il browser. Inoltre, per impostazione predefinita, gli utenti non possono disabilitare (disattivare) la funzionalità di feedback di Edge.

Se si abilita o non si configura questo criterio, gli utenti possono richiamare la funzionalità di feedback di Edge.

Se si disabilita questo criterio, gli utenti non possono richiamare la funzionalità di feedback di Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: UserFeedbackAllowed
  - Nome Criteri di gruppo: Consente il feedback degli utenti
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: UserFeedbackAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: UserFeedbackAllowed
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### VideoCaptureAllowed
  #### Consente o blocca l'acquisizione video
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Controlla se i siti possono acquisire video.

Se abilitato o non configurato (impostazione predefinita), all'utente verrà chiesto se accedere all'acquisizione video per tutti i siti tranne quelli con gli URL configurati nell'elenco del criterio [VideoCaptureAllowedUrls](#videocaptureallowedurls), ai quali verrà fornito l'accesso senza richiedere conferma.

Se si disabilita questo criterio, all'utente non viene inviata alcuna richiesta e l'acquisizione video è disponibile solo per gli URL configurati nel criterio [VideoCaptureAllowedUrls](#videocaptureallowedurls).

Questo criterio influisce su tutti i tipi di input video, non solo sulla fotocamera predefinita.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: VideoCaptureAllowed
  - Nome Criteri di gruppo: Consente o blocca l'acquisizione video
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: VideoCaptureAllowed
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000000
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: VideoCaptureAllowed
  - Valore di esempio
``` xml
<false/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### VideoCaptureAllowedUrls
  #### Siti che possono accedere ai dispositivi di acquisizione video senza richiedere l'autorizzazione
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Specifica i siti Web, in base ai modelli URL, che possono usare i dispositivi di acquisizione video senza chiedere l'autorizzazione all'utente. I modelli in questo elenco vengono confrontati con l'origine di sicurezza dell'URL di richiesta. In caso di corrispondenza, al sito viene automaticamente concesso l'accesso ai dispositivi di acquisizione video.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: VideoCaptureAllowedUrls
  - Nome Criteri di gruppo: Siti che possono accedere ai dispositivi di acquisizione video senza richiedere l'autorizzazione
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\VideoCaptureAllowedUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: VideoCaptureAllowedUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WPADQuickCheckEnabled
  #### Imposta l'ottimizzazione WPAD
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di disattivare l'ottimizzazione WPAD (Web Proxy AutoDiscovery) in Microsoft Edge.

Se si disabilita questo criterio, l'ottimizzazione WPAD è disabilitata, cosa che farà attendere il browser più a lungo per i server WPAD basati su DNS.

Se si abilita o non si configura il criterio, l'ottimizzazione WPAD è abilitata.

Indipendentemente dall'abilitazione di questo criterio, l'impostazione di ottimizzazione WPAD non può essere modificata dagli utenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WPADQuickCheckEnabled
  - Nome Criteri di gruppo: Imposta l'ottimizzazione WPAD
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WPADQuickCheckEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WPADQuickCheckEnabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebAppInstallForceList
  #### Configura l'elenco delle app Web installate forzatamente
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Configurare il criterio per specificare un elenco di app web che si installano silenziosamente, senza l'intervento dell'utente, e gli utenti che possono disinstallarle o disattivarle.

Ogni voce dell'elenco del criterio è un oggetto con un numero obbligatorio: url (l'URL dell'app web da installare) e 2 membri facoltativi: default_launch_container (specifica la modalità della finestra in cui l'app web si apre, il predefinito è una nuova scheda) e create_desktop_shortcut (true se si vuole creare dei collegamenti sul desktop per Linux e Windows).

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### Tipo:
  - Dictionary

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebAppInstallForceList
  - Nome Criteri di gruppo: Configura l'elenco delle app Web installate forzatamente
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WebAppInstallForceList
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [
  {
    "create_desktop_shortcut": true, 
    "default_launch_container": "window", 
    "url": "https://www.contoso.com/maps"
  }, 
  {
    "default_launch_container": "tab", 
    "url": "https://app.contoso.edu"
  }
]
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebAppInstallForceList
  - Valore di esempio
``` xml
<key>WebAppInstallForceList</key>
<array>
  <dict>
    <key>create_desktop_shortcut</key>
    <true/>
    <key>default_launch_container</key>
    <string>window</string>
    <key>url</key>
    <string>https://www.contoso.com/maps</string>
  </dict>
  <dict>
    <key>default_launch_container</key>
    <string>tab</string>
    <key>url</key>
    <string>https://app.contoso.edu</string>
  </dict>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebComponentsV0Enabled
  #### Riattiva l'API v0 dei componenti Web fino a M84 (obsoleto)
  
  >OBSOLETO: questo criterio è obsoleto e non funziona dopo Microsoft Edge 84.
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80, fino alla versione 84

  #### Descrizione
  Questo criterio non funziona perché queste funzionalità sono consentite per la riabilitazione selettiva di Microsoft Edge versione 85. Le API dei componenti Web v0 (Shadow DOM v0, Custom Elements v0 e HTML Imports) sono state deprecate nel 2018 e sono state disabilitate per impostazione predefinita a partire da Microsoft Edge versione 80.

Se si imposta questo criterio su True, le funzionalità dei componenti Web v0 verranno abilitate per tutti i siti.

Se si imposta questo criterio su False o non si imposta questo criterio, le funzionalità dei componenti Web v0 saranno disabilitate per impostazione predefinita, a partire da Microsoft Edge versione 80.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebComponentsV0Enabled
  - Nome Criteri di gruppo: Riattiva l'API v0 dei componenti Web fino a M84 (obsoleto)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WebComponentsV0Enabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebComponentsV0Enabled
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebDriverOverridesIncompatiblePolicies
  #### Consente a WebDriver di eseguire l'override dei criteri non compatibili (obsoleto)
  
  >OBSOLETO: questo criterio è obsoleto e non funziona dopo Microsoft Edge 84.
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77, fino alla versione 84

  #### Descrizione
  Questo criterio non funziona perché WebDriver ora è compatibile con tutti i criteri esistenti.

Questo criterio consente agli utenti della funzionalità WebDriver di ignorare i criteri che possono interferire con il suo funzionamento.

Al momento, questo criterio disabilita i criteri [SitePerProcess](#siteperprocess) e [IsolateOrigins](#isolateorigins).

Se il criteri è abilitato, WebDriver sarà in grado di ignorare i criteri non compatibili.
Se il criterio è disabilitato o non configurato, WebDriver non sarà in grado di ignorare i criteri non compatibili.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebDriverOverridesIncompatiblePolicies
  - Nome Criteri di gruppo: Consente a WebDriver di eseguire l'override dei criteri non compatibili (obsoleto)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WebDriverOverridesIncompatiblePolicies
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebDriverOverridesIncompatiblePolicies
  - Valore di esempio
``` xml
<true/>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebRtcLocalIpsAllowedUrls
  #### Gestisce l'esposizione degli indirizzi IP locali tramite WebRTC
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 80 o successive

  #### Descrizione
  Specifica un elenco di origini (URL) o modelli di nomi host (come "*contoso.com*") per cui l'indirizzo IP locale deve essere esposto da WebRTC.

Se si abilita questo criterio e si imposta un elenco di origini (URL) o modelli di nomi host, quando edge://flags/#enable-webrtc-hide-local-ips-with-mdns è abilitato, WebRTC espone l'indirizzo IP locale per i casi che corrispondono ai modelli nell'elenco.

Se si disabilita o non si configura questo criterio e edge://flags/#enable-webrtc-hide-local-ips-with-mdns è abilitato, WebRTC non espone gli indirizzi IP locali. L'indirizzo IP locale è nascosto con un nome host mDNS.

Se si abilita, si disabilita o non si configura questo criterio e edge://flags/#enable-webrtc-hide-local-ips-with-mdns è disabilitato, WebRTC espone gli indirizzi IP locali.

Tenere presente che questo criterio indebolisce la protezione degli indirizzi IP locali che potrebbero essere necessari agli amministratori.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Elenco di stringhe

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebRtcLocalIpsAllowedUrls
  - Nome Criteri di gruppo: Gestisce l'esposizione degli indirizzi IP locali tramite WebRTC
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebRtcLocalIpsAllowedUrls
  - Percorso (consigliato): N/D
  - Nome valore: 1, 2, 3, ...
  - Tipo valore: elenco di REG_SZ
  ##### Valore di esempio
```
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\2 = "*contoso.com*"

```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebRtcLocalIpsAllowedUrls
  - Valore di esempio
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>*contoso.com*</string>
</array>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebRtcLocalhostIpHandling
  #### Limita l'esposizione dell'indirizzo IP locale tramite WebRTC
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Consente di specificare se WebRTC espone o meno l'indirizzo IP locale dell'utente.

Se si imposta questo criterio su "AllowAllInterfaces" o su "AllowPublicAndPrivateInterfaces", WebRTC espone l'indirizzo IP locale.

Se si imposta questo criterio su "AllowPublicInterfaceOnly" o su "DisableNonProxiedUdp", WebRTC non espone l'indirizzo IP locale.

Se si disabilita o non si imposta questo criterio, WebRTC espone l'indirizzo IP locale.

Mapping delle opzioni del criterio:

* AllowAllInterfaces (impostazione predefinita) = Consentire tutte le interfacce. Espone l'indirizzo IP locale

* AllowPublicAndPrivateInterfaces (default_public_and_private_interfaces) = Sono consentite le interfacce pubbliche e private sulla route predefinita http. Espone l'indirizzo IP locale

* AllowPublicInterfaceOnly (default_public_interface_only) = È consentita l'interfaccia pubblica sulla route predefinita http. Non espone l'indirizzo IP locale

* DisableNonProxiedUdp (disable_non_proxied_udp) = Usare TCP a meno che il server proxy non supporti UDP. Non espone l'indirizzo IP locale

Durante la configurazione di questo criterio, utilizzare le informazioni precedenti.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebRtcLocalhostIpHandling
  - Nome Criteri di gruppo: Limita l'esposizione dell'indirizzo IP locale tramite WebRTC
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WebRtcLocalhostIpHandling
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"default"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebRtcLocalhostIpHandling
  - Valore di esempio
``` xml
<string>default</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WebRtcUdpPortRange
  #### Limita l'intervallo di porte UDP locali usate da WebRTC
  
  
  #### Versioni supportate:
  - In Windows e macOS dalla versione 77 o successive

  #### Descrizione
  Restringe l'intervallo di porte UDP utilizzato da WebRTC a un intervallo di porte specifico (endpoint inclusi).

Configurando questo criterio, si specifica l'intervallo di porte UDP locali che può essere usato da WebRTC.

Se non si configura questo criterio o se lo si imposta su una stringa vuota o un intervallo di porte non valido, WebRTC potrà usare qualsiasi porta UDP locale disponibile.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Stringa

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WebRtcUdpPortRange
  - Nome Criteri di gruppo: Limita l'intervallo di porte UDP locali usate da WebRTC
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WebRtcUdpPortRange
  - Tipo valore: REG_SZ
  ##### Valore di esempio
```
"10000-11999"
```


  #### Informazioni e impostazioni Mac
  - Nome chiave di preferenza: WebRtcUdpPortRange
  - Valore di esempio
``` xml
<string>10000-11999</string>
```
  

  [Torna all'inizio](#microsoft-edge---policies)

  ### WinHttpProxyResolverEnabled
  #### Usa il resolver proxy di Windows (deprecato)
  >DEPRECATO: questo criterio è deprecato. È attualmente supportato, ma diventerà obsoleto in una versione futura.
  
  #### Versioni supportate:
  - In Windows dalla versione 84 o successive

  #### Descrizione
  Questo criterio è deprecato perché verrà sostituito da una funzione simile in una versione futura, vedere https://crbug.com/1032820.

Usa Windows per risolvere i proxy per tutta la rete di browser anziché il resolver proxy incorporato in Microsoft Edge. Il resolver proxy di Windows abilita le funzionalità di proxy di Windows, ad esempio DirectAccess/NRPT.

Questo criterio include i problemi descritti da https://crbug.com/644030. Questo comporta il recupero e l’esecuzione dei file PAC dal codice di Windows, inclusi i file PAC impostati tramite il criterio [.](#proxypacurl) Poiché i recuperi di rete per il file PAC avvengono tramite Windows anziché tramite il codice di Microsoft Edge, i criteri di rete come [DnsOverHttpsMode](#dnsoverhttpsmode) non si applicano ai recuperi di rete per un file PAC.

Se questo criterio viene abilitato, verrà usato il resolver proxy di Windows.

Se si disabilitano o non si configura questo criterio, verrà usato il resolver proxy Microsoft Edge.

  #### Funzionalità supportate:
  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: no - Richiede il riavvio del browser

  #### Tipo:
  - Booleano

  #### Informazioni e impostazioni di Windows
  ##### Info su Criteri di gruppo (ADMX)
  - Nome univoco Criteri di gruppo: WinHttpProxyResolverEnabled
  - Nome Criteri di gruppo: usa il resolver proxy di Windows (deprecato)
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge/
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdge.admx
  ##### Impostazioni del Registro di sistema di Windows
  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge
  - Percorso (consigliato): N/D
  - Nome valore: WinHttpProxyResolverEnabled
  - Tipo valore: REG_DWORD
  ##### Valore di esempio
```
0x00000001
```


  

  [Torna all'inizio](#microsoft-edge---policies)


## Vedere anche
- [Configurazione di Microsoft Edge](configure-microsoft-edge.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Blog sulle basi di riferimento della sicurezza di Microsoft](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)