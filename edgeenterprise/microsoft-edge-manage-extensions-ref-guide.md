---
title: Guida dettagliata al criterio ExtensionSettings
ms.author: aspoddar
author: dan-wesley
manager: balajek
ms.date: 03/31/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Guida di riferimento dettagliata per la configurazione delle estensioni di Microsoft Edge tramite il criterio ExtensionSettings.
ms.openlocfilehash: 89ff329d6e209a4e658907385ec24fd0d2f1d1c2
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618159"
---
# <a name="detailed-guide-to-the-extensionsettings-policy"></a>Guida dettagliata al criterio ExtensionSettings

Microsoft Edge offre diverse modalità di gestione delle estensioni. Una modalità comune consiste nell'impostare più criteri in un unico posto con una stringa JSON nell'Editor Criteri di gruppo di Windows o nel Registro di sistema di Windows tramite il criterio [ExtensionSettings.](/deployedge/microsoft-edge-policies#extensionsettings)

> [!NOTE]
> Questo articolo riguarda Microsoft Edge versione 77 o successiva.

## <a name="before-you-begin"></a>Prima di iniziare

Puoi decidere se impostare tutte le opzioni di gestione delle estensioni qui o impostare i controlli tramite altri criteri.
  
Il criterio ExtensionSettings può sovrascrivere altri criteri impostati altrove nei Criteri di gruppo, inclusi i criteri seguenti:

- [ExtensionAllowedTypes](/DeployEdge/microsoft-edge-policies#extensionallowedtypes)
- [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist)
- [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ExtensionInstallSources](/DeployEdge/microsoft-edge-policies#extensioninstallsources)
- [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallsources)

## <a name="extensionsettings-policy-fields"></a>Campi del criterio ExtensionSettings

Questo criterio può controllare le impostazioni, ad esempio l'URL di aggiornamento da cui verrà scaricata l'estensione per l'installazione iniziale e le autorizzazioni bloccate, o le autorizzazioni la cui esecuzione non è consentita. I campi dei criteri disponibili sono descritti nella tabella seguente.

| &nbsp; | Descrizione |
|--|--|
| **allowed_types** | Può essere usato solo per impostare la configurazione predefinita, *. Specifica i tipi di app o estensioni che gli utenti possono installare in Microsoft Edge. Il valore è costituito da un elenco di stringhe, ognuna delle quali deve essere del tipo seguente: "extension", "theme", "user_script" e "hosted_app"   |
| **blocked_install_message**| Se non consenti agli utenti di installare determinate estensioni, puoi creare un messaggio personalizzato da visualizzare nel browser nel caso gli utenti provino a installarle.<br>Aggiungi un testo al messaggio di errore generico visualizzato nel sito Web Componenti aggiuntivi di Microsoft Edge. Ad esempio, puoi indicare agli utenti come contattare il reparto IT o perché un determinato interno non è disponibile. Il messaggio non può superare i 1.000 caratteri.   |
|**blocked_permissions**  | Non consente agli utenti di installare ed eseguire estensioni che richiedono determinate autorizzazioni API non consentite dall'organizzazione. Ad esempio, puoi bloccare le estensioni che accedono ai cookie. Se un'estensione richiede un'autorizzazione che hai bloccato in precedenza, l'utente non può installarla. Se gli utenti hanno installato in precedenza l'estensione, non verrà più caricata. Se un'estensione contiene un'autorizzazione bloccata come requisito facoltativo, viene installata come al solito. Pertanto, se l'estensione è in esecuzione, le autorizzazioni bloccate vengono automaticamente rifiutate.<br>Per un elenco di autorizzazioni disponibili, vedere [Dichiarare le autorizzazioni](/microsoft-edge/extensions-chromium/enterprise/declare-permissions).   |
| **installation_mode**| Controlla se e il modo in cui le estensioni specificate vengono aggiunte a Microsoft Edge. Puoi impostare la modalità di installazione su una delle opzioni seguenti:<br>- allowed: gli utenti possono installare l'estensione. Se non viene definita alcuna modalità di installazione, questa è l'impostazione predefinita.<br>- blocked: gli utenti non possono installare l'estensione.<br>- force_installed: installa automaticamente l'estensione senza interazione dell'utente. Gli utenti non possono rimuoverla. È possibile anche definire il percorso di download dell'estensione tramite update_url. **Nota:** non puoi usare l'impostazione contrassegnata da * perché Microsoft Edge non saprebbe quale estensione installare automaticamente.<br>- normal_installed: installa automaticamente l'estensione senza interazione dell'utente. Gli utenti possono disabilitarla. È possibile anche definire il percorso di download dell'estensione tramite update_url. **Nota:** non puoi usare l'impostazione contrassegnata da * perché Microsoft Edge non saprebbe quale estensione installare automaticamente.<br>- removed: gli utenti non possono installare l'estensione. Se gli utenti hanno installato in precedenza l'estensione, Microsoft Edge la rimuoverà. |  |
| **install_sources** | Può essere utilizzato solo per configurare la configurazione predefinita, *. Specifica gli URL consentiti per l'installazione delle estensioni. Sia il percorso del file *.crx che la pagina da cui viene avviato il download (il referrer) devono essere consentiti da tali modelli. Per gli esempi di modelli di URL, vedi i [modelli di corrispondenza.](/microsoft-edge/extensions-chromium/enterprise/match-patterns)  |
| **minimum_version_required** |Microsoft Edge disabilita le estensioni, tra cui le estensioni installate forzatamente, con una versione precedente alla versione minima specificata.<br>Il formato della stringa della versione è lo stesso utilizzato nel manifesto dell'estensione.     |
| **update_url** | Si applica solo a force_installed e normal_installed. Specifica la posizione da cui Microsoft Edge deve scaricare un'estensione. Se l'estensione è ospitata nel sito Web Componenti aggiuntivi di Microsoft Edge, utilizzare la posizione seguente: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.<br>Microsoft Edge usa l'URL specificato per l'installazione iniziale dell'estensione. Per i successivi aggiornamenti delle estensioni, Microsoft Edge l'URL nel manifesto dell'estensione.   |
| **runtime_allowed_hosts**| Consente alle estensioni di interagire con siti Web specificati, anche se sono definiti in runtime_blocked_hosts. Puoi specificare fino a 100 voci. Le voci aggiuntive vengono ignorate.<br>Il formato del modello host è simile ai  [modelli di corrispondenza,](/microsoft-edge/extensions-chromium/enterprise/match-patterns)  ad eccezione del fatto che non è possibile definire il percorso. Ad esempio:<br>- *://*.example.com<br>- *://example.*: sono supportati i caratteri jolly eTLD     |
| **runtime_blocked_hosts**| Impedisce alle estensioni di interagire con i siti Web specificati o di modificarli. Le modifiche includono il blocco dell'inserimento di JavaScript, l'accesso ai cookie e le modifiche alle richieste Web.<br>Puoi specificare fino a 100 voci. Le voci aggiuntive vengono ignorate.<br>Il formato del modello host è simile ai modelli di corrispondenza, ad eccezione del fatto che non è possibile definire il percorso. Ad esempio:<br>- *://*.example.com<br>- *://example.*: sono supportati i caratteri jolly eTLD   |


## <a name="configure-using-a-json-string-in-windows-group-policy-editor"></a>Configurazione con una stringa JSON nell'Editor dei Criteri di gruppo di Windows

La procedura per usare i criteri delle impostazioni delle estensioni con l'oggetto Criteri di gruppo presuppone che si sia già importato ADM/ADMX per i criteri di Microsoft Edge.

1. Apri l'Editor Criteri di gruppo e passa a Microsoft Edge > **Estensioni > Configura i criteri per le impostazione di gestione delle estensioni**.
2. Abilita i criteri e immetti i relativi dati JSON (JavaScript Object Notation) compatti nella casella di testo su una singola riga senza interruzioni.
3. Per convalidare i criteri e compattarli in una singola riga, usa uno strumento di compressione JSON.

### <a name="properly-format-json-for-the-extension-settings-policy"></a>Formatta correttamente JSON per i criteri delle impostazioni delle estensioni

È necessario comprendere le due parti di questo criterio: l'ambito predefinito e l'ambito individuale. L'ambito predefinito è un catch-all per le estensioni senza un proprio ambito. L'ambito individuale viene applicato solo a tale estensione.  

L'ambito predefinito è identificato da un asterisco (*). L'esempio seguente definisce un ambito predefinito e un ambito individuale dell'estensione.

```json
{ 
   “*”: {}, 
   “nckgahadagoaajjgafhacjanaoiihapd”: {} 
} 
```

Un'estensione ottiene le impostazioni da un solo ambito. Se è disponibile un ambito individuale per tale estensione, si tratta delle impostazioni applicate a tale estensione. Se non è disponibile alcun ambito individuale, l'estensione utilizzerà l'ambito predefinito.  

L'esempio JSON successivo blocca l'esecuzione di qualsiasi estensione in `.example.com` e qualsiasi estensione che richieda l'autorizzazione "USB".

```json
{ 
  "*": { 
    "runtime_blocked_hosts": ["*://*.example.com"], 
    "blocked_permissions": ["usb"] 
  } 
} 
```

**JSON compatto**

```json
{"*":{"runtime_blocked_hosts":["*://*.example.com"],"blocked_permissions":["usb"]}} 
```

### <a name="a-few-more-json-examples-for-extension-settings"></a>Altri esempi di JSON per le impostazioni delle estensioni

#### <a name="using-installation_mode-property-to-allow-and-block-extensions"></a>Utilizzo della proprietà installation_mode per consentire e bloccare le estensioni

- L'utente può installare tutte le estensioni per impostazione predefinita 

  `{ "*": {"installation_mode": "allowed" }}`
- L'utente non può installare le estensioni.  

  `{ "*": {"installation_mode": "blocked" }}`

- Specifica un messaggio personalizzato da visualizzare quando l'installazione è bloccata.

   `{"*": {"blocked_install_message": ["Call IT(408 - 555 - 1234) for an exception"]}}`

#### <a name="using-installation_mode-property-to-force-install-extensions"></a>Utilizzo della proprietà installation_mode per forzare l'installazione delle estensioni

Quando si usa installation_mode come "force_installed", l'estensione viene installata automaticamente senza interazione dell'utente. L'utente non può disabilitare o rimuovere l'estensione. Se l'installazione di un'estensione è "normal" o "forced", è necessario definire anche il campo **update_url**. Il campo punta alla posizione da cui è possibile installare l'estensione. Utilizza le posizioni seguenti per il campo **update_url**:

- Se l'estensione che stai scaricando è ospitata nello store Componenti aggiuntivi di Microsoft Edge, usa [https://edge.microsoft.com/extensionwebstorebase/v1/crx](https://edge.microsoft.com/extensionwebstorebase/v1/crx).
- Se l'estensione che stai scaricando è ospitata in Chrome Web Store, usa [https://clients2.google.com/service/update2/crx](https://clients2.google.com/service/update2/crx).
- Se l'estensione è ospitata nel tuo server, usa l'URL da cui Microsoft Edge può scaricare il pacchetto dell'estensione (file .crx). Esempio JSON:

   `{"nckgahadagoaajjgafhacjanaoiihapd": {"installation_mode": "force_installed","update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"}}`
  
Nell'esempio precedente se anziché usare "force_installed", si usa "normal_installed", l'estensione viene installata automaticamente senza interazione dell'utente che può invece disabilitarla.  

   > [!TIP]
   > La formattazione corretta di una stringa JSON può essere complicata. Esegui un controllo JSON prima di implementare il criterio. Oppure prova una versione precedente dello [Strumento per la generazione di impostazioni per le estensioni](https://microsoft.github.io/edge-extension-settings-generator/minimal)

## <a name="configure-using-the-windows-registry"></a>Configurazione utilizzando il Registro di sistema di Windows

Il criterio ExtensionSettings deve essere scritto nel Registro di sistema della chiave seguente:

`HKLM\Software\Policies\Microsoft\Edge\`

> [!NOTE]
> È possibile usare HKCU anziché HKLM. Il percorso equivalente può essere configurato con l'oggetto Criteri di gruppo.  

Per Microsoft Edge, tutte le impostazioni verranno avviate in questa chiave:

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\`

La chiave successiva che verrà creata è l'ID di estensione per l'ambito individuale o un asterisco (*) per l'ambito predefinito. Ad esempio, se usi la posizione seguente per le impostazioni di Google Hangouts:

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\nckgahadagoaajjgafhacjanaoiihapd`

Per le impostazioni applicate all'ambito predefinito, utilizza questo percorso:

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\*`

Impostazioni diverse richiederanno formati diversi, a seconda che si tratti di una stringa o di una matrice di stringhe. I valori della matrice richiedono [＂value＂]. I valori stringa possono essere immessi così come sono. L'elenco seguente mostra quali impostazioni sono matrici o stringhe:

- Installation_mode = Stringa
- update_url = Stringa
- blocked_permissions = Matrice di stringhe
- allowed_permissions = Matrice di stringhe
- minimum_version_required = Stringa
- runtime_blocked_hosts = Matrice di stringhe
- runtime_allowed_hosts = Matrice di stringhe
- blocked_install_message = Stringa


## <a name="see-also"></a>Vedi anche

- [Gestire le estensioni di Microsoft Edge nell'organizzazione](microsoft-edge-manage-extensions.md)
- [Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge](microsoft-edge-manage-extensions-policies.md)
- [Domande frequenti sulle estensioni di Microsoft Edge](microsoft-edge-manage-extensions-faq.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
