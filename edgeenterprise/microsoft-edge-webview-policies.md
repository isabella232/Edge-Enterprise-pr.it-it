---
title: Documentazione sui criteri di Microsoft Edge WebView2
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 09/26/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione di Windows e Mac per tutti i criteri supportati dal browser Microsoft Edge
ms.openlocfilehash: b27443995e0caecf30bc74036b85cb702ba5c3fc
ms.sourcegitcommit: 884bdb6ef9484ed3b080b4c5ab091f5f29ba2928
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "12056742"
---
# <a name="microsoft-edge-webview2---policies"></a>Criteri: Microsoft Edge WebView2

La versione più recente di Microsoft Edge WebView2 include i criteri riportati di seguito. È possibile usare questi criteri per configurare la modalità di esecuzione di Microsoft Edge WebView2 nell'organizzazione.

Sono disponibili informazioni su un set aggiuntivo di criteri usati per controllare come e quando viene aggiornato Microsoft Edge WebView2 nell'articolo [Informazioni di riferimento sui criteri dell'aggiornamento di Microsoft Edge](microsoft-edge-update-policies.md).


> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 87 o successiva.

## <a name="available-policies"></a>Criteri disponibili

In queste tabelle sono elencati tutti i criteri di gruppo disponibili in questa versione di Microsoft Edge WebView2. Usa i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.

- [Impostazioni di override del caricatore](#loader-override-settings)


### [*<a name="loader-override-settings"></a>Impostazioni di override del caricatore*](#loader-override-settings-policies)

|Nome criterio|Didascalia|
|-|-|
|[BrowserExecutableFolder](#browserexecutablefolder)|Configura il percorso della cartella eseguibile del browser|
|[ReleaseChannelPreference](#releasechannelpreference)|Imposta la preferenza dell'ordine di ricerca del canale di rilascio|




  ## <a name="loader-override-settings-policies"></a>Criteri delle impostazioni di override del caricatore

  [Torna all'inizio](#microsoft-edge-webview2---policies)

  ### <a name="browserexecutablefolder"></a>BrowserExecutableFolder

  #### <a name="configure-the-location-of-the-browser-executable-folder"></a>Configura il percorso della cartella eseguibile del browser

  
  
  #### <a name="supported-versions"></a>Versioni supportate:

  - In Windows dalla versione 87 o successive

  #### <a name="description"></a>Descrizione

  Questo criterio configura le applicazioni WebView2 per l’uso di WebView2 Runtime nel percorso specificato. La cartella deve contenere i file seguenti: msedgewebview2.exe, msedge.dll, and così via.

Per impostare il valore per il percorso della cartella, specifica il Nome del valore e la Coppia valori. Imposta il nome del valore sull'ID modello utente dell'applicazione o sul nome del file eseguibile. È possibile usare il carattere jolly "*" come nome del valore da applicare a tutte le applicazioni.

  #### <a name="supported-features"></a>Funzionalità supportate:

  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### <a name="data-type"></a>Tipo:

  - Elenco di stringhe

  #### <a name="windows-information-and-settings"></a>Informazioni e impostazioni di Windows

  ##### <a name="group-policy-admx-info"></a>Info su Criteri di gruppo (ADMX)

  - Nome Criteri di gruppo univoco: BrowserExecutableFolder
  - Nome Criteri di gruppo: configura il percorso della cartella eseguibile del browser
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge WebView2/Impostazioni di override del caricatore
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Impostazioni del Registro di sistema di Windows

  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebView2\browserExecutableFolder
  - Percorso (consigliato): N/D
  - Nome valore: elenco di REG_SZ
  - Tipo valore: elenco di REG_SZ

  ##### <a name="example-value"></a>Valore di esempio

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [Torna all'inizio](#microsoft-edge-webview2---policies)

  ### <a name="releasechannelpreference"></a>ReleaseChannelPreference

  #### <a name="set-the-release-channel-search-order-preference"></a>Imposta la preferenza dell'ordine di ricerca del canale di rilascio

  
  
  #### <a name="supported-versions"></a>Versioni supportate:

  - In Windows dalla versione 87 o successive

  #### <a name="description"></a>Descrizione

  L'ordine di ricerca del canale predefinito è WebView2 Runtime, Beta, Dev, and Canary.

Per invertire l'ordine di ricerca predefinito, imposta questo criterio su 1.

Per impostare il valore per la preferenza del canale di rilascio, specifica il Nome del valore e la Coppia valori. Imposta il nome del valore sull'ID modello utente dell'applicazione o sul nome del file eseguibile. È possibile usare il carattere jolly "*" come nome del valore da applicare a tutte le applicazioni.

  #### <a name="supported-features"></a>Funzionalità supportate:

  - Può essere obbligatorio: sì
  - Può essere consigliato: no
  - Aggiornamento dei criteri dinamici: sì

  #### <a name="data-type"></a>Tipo:

  - Elenco di stringhe

  #### <a name="windows-information-and-settings"></a>Informazioni e impostazioni di Windows

  ##### <a name="group-policy-admx-info"></a>Info su Criteri di gruppo (ADMX)

  - Nome Criteri di gruppo univoco: ReleaseChannelPreference
  - Nome Criteri di gruppo: imposta la preferenza dell'ordine di ricerca del canale di rilascio
  - Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge WebView2/Impostazioni di override del caricatore
  - Percorso Criteri di gruppo (consigliato): N/D
  - Nome file ADMX Criteri di gruppo: MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Impostazioni del Registro di sistema di Windows

  - Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebView2\releaseChannelPreference
  - Percorso (consigliato): N/D
  - Nome valore: elenco di REG_SZ
  - Tipo valore: elenco di REG_SZ

  ##### <a name="example-value"></a>Valore di esempio

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference = "Name: *, Value: 1"

```

  

  [Torna all'inizio](#microsoft-edge-webview2---policies)


## <a name="see-also"></a>Vedere anche

- [Configurazione di Microsoft Edge](configure-microsoft-edge.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Blog sulle basi di riferimento della sicurezza di Microsoft](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)