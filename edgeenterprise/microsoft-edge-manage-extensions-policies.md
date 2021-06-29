---
title: Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge all’interno della grande impresa
ms.openlocfilehash: a633b036c1733716dfb257b4711bca57bd6721f0
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618160"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a>Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge

In questo articolo vengono descritte le opzioni e i passaggi per la gestione delle estensioni tramite criteri di gruppo. Queste opzioni presuppongono che si abbia già gestito Microsoft Edge per gli utenti. Se Microsoft Edge non è statp già gestito per gli utenti, seguire il collegamento seguente.

- [Gestire le estensioni di Microsoft Edge nella grande impresa](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> L’articolo riguarda Microsoft Edge versione 77 o successiva.

## <a name="block-extensions-based-on-their-permissions"></a>Bloccare le estensioni a seconda delle relative autorizzazioni

È possibile controllare le estensioni che gli utenti possono installare a seconda delle autorizzazioni tramite il criterio [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings). Un'estensione installata non verrà eseguita se necessita di un'autorizzazione bloccata. L'estensione non viene rimossa, ma solo disabilitata.

> [!NOTE]
> Le impostazioni relative alle autorizzazioni bloccate possono essere configurate solo tramite il criterio Impostazioni estensione.  

Utilizzare i passaggi seguenti come riferimento per bloccare un’estensione.

1. Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**,  quindi selezionare **Configura impostazioni di gestione delle estensioni**.
2. Abilitare il criterio, quindi specificare le autorizzazioni che si desidera consentire o bloccare utilizzando una stringa JSON che andrà compressa. La schermata successiva mostra come bloccare un'estensione che utilizza l'autorizzazione "USB".

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="Configurare i criteri di gruppo per bloccare un'estensione.":::

L'esempio seguente mostra l’utilizzo di JSON per bloccare qualsiasi estensione che richiede l'uso dell'autorizzazione "USB" e della relativa stringa compressa.

### <a name="json-example"></a>Esempio di JSON

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > Per bloccare tutte le estensioni che utilizzano l'autorizzazione, utilizzare un asterisco per l'ID di estensione, come illustrato nell'esempio precedente. Se si specifica un ID di estensione, il criterio verrà applicato solo a tale estensione. È possibile bloccare più di un’estensione, ma queste devono essere voci separate.

## <a name="prevent-extensions-from-altering-web-pages"></a>Impedire alle estensioni di modificare le pagine Web

Questa impostazione impedisce alle estensioni di leggere e modificare i dati sensibili di siti Web e domini. Il blocco delle azioni indesiderate viene eseguito bloccando azioni quali l'inserimento di script nei siti Web, la lettura dei cookie o la modifica delle richieste Web. Questa impostazione non impedisce agli utenti di installare o rimuovere estensioni, ma impedisce alle estensioni di modificare i siti Web specificati. 
  
> [!NOTE]
> Le impostazioni agli host di runtime consenti/bloccati bloccate possono essere configurate solo tramite il criterio Impostazioni estensione.  

È possibile configurare le impostazioni seguenti tramite il criterio ExtensionSettings per impedire (o consentire) di apportare modifiche a siti Web o domini:

- **Runtime_blocked_hosts**. Questa impostazione impedisce alle estensioni di apportare modifiche o leggere i dati dei siti Web specificati.
- **Runtime_allowed_hosts**. Questa impostazione consente alle estensioni di apportare modifiche o leggere i dati dei siti Web specificati. Il formato seguente viene usato per specificare i siti nella stringa JSON all’interno del criterio:

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` le sezioni sono obbligatorie, ma la sezione `[subdomain|*]` è facoltativa.

La tabella seguente mostra esempi di modelli host e di corrispondenza validi.

|Modelli host validi|Corrisponde|Non corrisponde|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | Tutti gli URL  |   |

Utilizzare i passaggi seguenti come riferimento per bloccare o consentire alle estensioni di accedere a un sito Web o a un dominio.

1. Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Configura impostazioni di gestione delle estensioni**.  
2. Abilitare il criterio, quindi specificare le autorizzazioni che si desidera consentire o bloccare comprimendole a una singola stringa JSON.

Gli esempi seguenti mostrano come bloccare le estensioni su un nome host e uno stesso dominio.

### <a name="json-example-to-block-hostname"></a>Esempio di JSON per bloccare il nome host

Questo esempio mostra la stringa JSON e quella JSON compressa per impedire a qualsiasi estensione di accedere al `www.microsoft.com` nome host.

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> Per impedire a tutte le estensioni di accedere alla pagina Web, utilizzare un asterisco per l'ID di estensione, come illustrato nell'esempio precedente.  Se si specifica un ID di estensione invece che un asterisco, il criterio verrà applicato solo a tale estensione. È possibile bloccare più di un’estensione, ma queste devono essere voci separate.

### <a name="json-example-to-block-extensions-on-same-domain"></a>Esempio di JSON per bloccare le estensioni per lo stesso dominio

Questo esempio mostra la stringa JSON e quella JSON compressa per bloccare l'esecuzione di estensioni specifiche nello stesso dominio, "importantwebsite".

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a>Consentire o bloccare le estensioni nei criteri di gruppo

È possibile usare i criteri [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) e [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) per controllare le estensioni bloccate o consentite. Utilizzare i passaggi seguenti come riferimento per consentire tutte le estensioni ad eccezione di quelle che si desidera bloccare.

1. Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Controlla quali estensioni non è possibile installare**.
2. Seleziona **Abilitato**.
3. Fai clic su **Mostra**.
4. Immettere l'ID app delle estensioni che si desidera bloccare. Per aggiungere più ID app, utilizzare una riga separata per ogni ID.
5. Per bloccare tutte le estensioni, digitare **\*** nel criterio per impedire l'installazione di eventuali estensioni. È possibile utilizzare quest’ultimo insieme al criterio "Consenti l'installazione di estensioni specifiche" per consentire solo l'installazione di determinate estensioni. La schermata successiva mostra un'estensione che verrà bloccata in base all'ID app fornito.

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="Usare l'ID app per bloccare un'estensione.":::

   > [!TIP]
   > Se non è possibile trovare l'ID app di un'estensione, cercare l'estensione nel sito Web Componenti aggiuntivi di Microsoft Edge. Trovare l'estensione specifica. L'ID app verrà visualizzato nella parte finale dell'URL nell'omnibox.

> [!NOTE]
> È possibile aggiungere un'estensione già installata sul computer di un utente all'elenco di estensioni bloccate. Ciò disabiliterà l'estensione e impedirà all'utente di riattivarla. Questa non verrà disinstallata, ma soltanto disabilitata.

## <a name="force-install-an-extension"></a>Forzare l'installazione di un'estensione

Usare il criterio [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) per controllare le estensioni bloccate o consentite. Utilizzare i passaggi seguenti come riferimento per forzare l’installazione di un’estensione.

1. Nell'editor Criteri di gruppo, passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Controlla le estensioni installate automaticamente**.
2. Seleziona **Abilitato**.  
3. Fai clic su **Mostra**.
4. Immettere l'app ID o gli ID dell’estensione o delle estensioni per cui forzare l'installazione.  

L'estensione verrà installata automaticamente senza necessità di interazione da parte dell’utente. L'utente non potrà inoltre disinstallare o disabilitare l'estensione. Questa impostazione sovrascriverà i criteri dell'elenco abilitato di estensioni bloccate.

> [!NOTE]
> Per le estensioni ospitate nel Chrome Web Store utilizzare una stringa, come ad esempio: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`.

## <a name="block-extensions-from-a-specific-store-or-update-url"></a>Bloccare le estensioni da uno Store o un URL di aggiornamento specifico

Per bloccare le estensioni di un determinato Store o URL, è sufficiente bloccare *update_url* per tale store utilizzando il criterio [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings).

Utilizzare i passaggi seguenti come riferimento per bloccare le estensioni da un determinato Store o URL.

1. Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Configura impostazioni di gestione delle estensioni**.  
2. Abilitare il criterio, quindi specificare le autorizzazioni che si desidera consentire o bloccare comprimendole a una singola stringa JSON.

L'esempio seguente mostra la stringa JSON e quella JSON compressa per il blocco delle estensioni dal Chrome Web Store tramite il relativo URL di aggiornamento (`https://clients2.google.com/service/update2/crx`).

### <a name="json-example-for-blocking-on-update-url"></a>Esempio di JSON per il blocco dell'URL di aggiornamento

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> È ancora possibile usare ** ExtensionInstallForceList** e **ExtensionInstallAllowList** per consentire/forzare l'installazione di estensioni specifiche tramite JSON nell'esempio precedente, anche se lo Store è bloccato.

## <a name="see-also"></a>Consultare anche

- [Gestire le estensioni di Microsoft Edge nella grande impresa](microsoft-edge-manage-extensions.md)
- [Creare un archivio Web per ospitare le estensioni di Microsoft Edge](microsoft-edge-manage-extensions-webstore.md)
- [Guida di riferimento per i criteri ExtensionSettings](microsoft-edge-manage-extensions-ref-guide.md)
- [Domande frequenti sulle estensioni di Microsoft Edge](microsoft-edge-manage-extensions-faq.md)
- [Pagina di destinazione di Microsoft Edge per le aziende](https://aka.ms/EdgeEnterprise)
