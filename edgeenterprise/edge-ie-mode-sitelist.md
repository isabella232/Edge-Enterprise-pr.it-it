---
title: Configurare i siti nell'elenco di siti in modalità Enterprise
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare l'elenco di siti in modalità Enterprise
ms.openlocfilehash: 969a4f6001dbe08a51c26ecf35812b101d315a59
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980269"
---
# Configurare i siti nell'elenco di siti in modalità Enterprise

Questo articolo descrive le modifiche apportate all'elenco di siti in modalità Enterprise che supportano la configurazione della modalità IE per Microsoft Edge versione 77 e successive.

Per altre informazioni sullo schema per il file XML dell'elenco di siti in modalità Enterprise, vedere [Indicazioni per lo schema v.2 della modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).

> [!NOTE]
> Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.

## Elementi dello schema aggiornati

La tabella seguente descrive l'elemento \<open-in app\> aggiunto allo schema v.2 della modalità Enterprise:

| **Elemento** | **Descrizione** |
| --- | --- |
| \<open-in app="**true**"\> | Un elemento figlio che controlla il browser usato per i siti. Questo elemento è obbligatorio per i siti che devono essere **aperti in IE11**.|

**Esempio:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

La tabella seguente indica i valori possibili dell'elemento \<open-in\>:

| **Value** | **Descrizione** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Apre il sito in modalità IE o in una finestra a schermo intero di IE11. Per abilitare la modalità IE, vedere [Configurare i criteri della modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Apre il sito in una finestra a schermo intero di IE11 |
| **\<open-in\>MSEdge\</open-in\>** | Apre il sito in Microsoft Edge |
| **\<open-in\>Nessuno o non specificato.\</open-in\>** | Apre il sito nel browser predefinito o nel browser in cui l'utente ha avviato la navigazione. |
|**\<open-in\>Configurabile\</open-in\>** | Consente al sito di partecipare alla determinazione del motore in modalità Internet Explorer. Per altre informazioni, vedere [Informazioni sui siti configurabili in modalità Internet Explorer](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> L'attributo app=**"true"** viene riconosciuto solo quando è associato a _'open-in' IE11_. Se lo si aggiunge agli altri elementi 'open-in', il comportamento del browser non cambia.   

## Configurare i siti neutri

Per il corretto funzionamento della modalità IE, i server di autenticazione e Single Sign-On devono essere configurati in modo esplicito come siti neutri. In caso contrario, le pagine in modalità IE tenteranno di reindirizzare a Microsoft Edge e l'autenticazione avrà esito negativo.

Quando viene avviata la navigazione, un sito neutrale usa il browser Microsoft Edge o la modalità IE. La configurazione dei siti neutri garantisce che le applicazioni che usano tali server di autenticazione, moderni e legacy, continuino a funzionare.

È possibile configurare i siti neutri impostando l'elenco a discesa *Apri in* su 'Nessuno' nello strumento Enterprise Mode Site List Manager o aggiornando direttamente il file XML dell'elenco siti:

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

Per identificare i server di autenticazione, analizzare il traffico di rete da un'applicazione che usa gli strumenti di sviluppo di IE11. Se serve più tempo per identificare i server di autenticazione, è possibile configurare un criterio in modo che tutti gli spostamenti nella pagina rimangano in modalità IE. Per ridurre al minimo l'uso della modalità IE, disabilitare questa impostazione dopo aver identificato e aggiunto i server di autenticazione all'elenco dei siti. Per altre informazioni, vedere [Configurare gli spostamenti nella pagina per rimanere in modalità IE](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect).

>[!NOTE]
   >Lo schema per la modalità Enterprise v.1 non è supportato per l'integrazione della modalità Internet Explorer. Se attualmente usi lo schema v.1 con Internet Explorer 11, devi eseguire l'aggiornamento allo schema v.2. Per altre informazioni, vedi [Indicazioni per lo schema v.2 della modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [Informazioni aggiuntive sulla modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)