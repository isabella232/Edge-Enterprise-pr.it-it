---
title: Microsoft Edge e Siti configurabili nella modalità IE
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge e Siti configurabili nella modalità IE
ms.openlocfilehash: 0248ecd394acee5773751c0685969e3d40940431
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979988"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a>Altre informazioni su Siti configurabili nella modalità IE

Questo articolo descrive la funzionalità Siti configurabili nell'Elenco siti modalità Enterprise durante l'uso di Internet Explorer in Microsoft Edge.

## <a name="prerequisites"></a>Prerequisiti

- Aggiornamenti di Windows

  - Windows 10 versione 1909, Windows Server versione 1909 – KB4550945  o successive
  - Windows 10 versione 1903, Windows Server versione 1903 – KB4550945  o successive
  - Windows 10 versione 1809, Windows Server versione 1809, e Windows Server 2019 - KB4550969 o successive
  - Windows 10 versione 1803 – KB4550944 o successive
  - Windows 10 versione 1607, Windows Server 2016 - KB4556826 o successive
  - Windows 10 versione iniziale, luglio 2015 - KB4550947 o successive
  - Windows 8.1 - KB4556798 o successive

- Microsoft Edge version 83 o successive
- [Modalità IE](./edge-ie-mode.md) configurata con l'Elenco siti modalità Enterprise

## <a name="overview"></a>Panoramica

La configurazione dei siti che hanno bisogno della modalità IE nell'Elenco siti modalità Enterprise funziona bene per gran parte degli ambienti con applicazioni legacy. Tuttavia, in alcuni casi questo approccio non è il modo migliore di configurare un sottogruppi di siti da aprire nella modalità IE senza eseguire il rendering di un intero dominio nella modalità IE. Ad esempio, quando l'ambiente include sia applicazioni moderne che applicazioni che sono eseguite su singoli server, e si vuole avere la flessibilità di eseguire il rendering solo delle applicazioni legacy nella modalità IE, eseguendo il rendering delle altre applicazioni nella modalità Microsoft Edge.

La soluzione è usare la funzionalità Siti configurabili nell'Elenco siti modalità Enterprise. Quando la funzionalità è abilitata, Microsoft Edge consente ai siti contrassegnati con il tag "configurabile" di essere inclusi nella determinazione del modulo della modalità IE.

## <a name="how-configurable-sites-works"></a>Funzionamento di Siti configurabili

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a>Passare automaticamente dal motore di Microsoft Edge a quello di Internet Explorer

Per usare la funzionalità Siti configurabili, è necessario che uno o più siti dell'Elenco siti modalità enterprise abbiano l'opzione `<open-in>Configurable</open-in>`.

Esempio:

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

Quando la funzionalità Siti configurabili è abilitata, Edge si comporta in questo modo:

1. Quando viene inviata una richiesta a un sito configurabile, Microsoft Edge invia l'intestazione della richiesta HTTP "`X-InternetExplorerModeConfigurable: 1`".
2. Un sito configurabile potrebbe inviare una risposta di reindirizzamento (ad esempio, HTTP 302) con l'intestazione della risposta HTTP "`X-InternetExplorerMode: 1`" in modo da richiedere a Microsoft Edge di cariare il sito nella modalità IE.
3. Anche la destinazione del reindirizzamento (ossia il valore dell'intestazione della risposta di **Location**) deve essere un sito **Configurabile** o **Neutro**, altrimenti l'intestazione della risposta della modalità IE sarà ignorata. Ci si attende che la destinazione del reindirizzamento sia di norma uguale all'URL originale. Ma non deve essere necessariamente così.

   > [!NOTE]
   > La risposta di reindirizzamento viene memorizzata nella cache in base al comportamento normale di memorizzazione nella cache dei reindirizzamenti di Microsoft Edge.

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a>Tornare al Microsoft Edge dal motore Internet Explorer

L'abilitazione dei siti configurabili in Microsoft Edge determina l'abilitazione automatica dei seguenti comportamenti nella modalità IE:

1. Quando viene inviata una richiesta a un sito configurabile, le schede della modalità IE inviano l'intestazione della richiesta HTTP "`X-InternetExplorerModeConfigurable: 1`", la stessa delle schede di Microsoft Edge.
2. Un sito configurabile potrebbe inviare una risposta di reindirizzamento (ad esempio, HTTP 302) con l'intestazione della risposta HTTP "`X-InternetExplorerMode: 0`" in modo da richiedere di ritornare alla modalità di navigazione di Microsoft Edge.
3. Anche la destinazione del reindirizzamento (ossia il valore dell'intestazione della risposta di **Location**) deve essere un sito **Configurabile** o **Neutro**, altrimenti l'intestazione della risposta della modalità IE sarà ignorata. Ci si attende che la destinazione del reindirizzamento sia di norma uguale all'URL originale. Ma non deve essere necessariamente così.

   > [!NOTE]
   > La risposta di reindirizzamento viene memorizzata nella cache in base al comportamento normale di memorizzazione nella cache dei reindirizzamenti di Microsoft Edge.

> [!TIP]
> Entrambi i motori di ricerca inviano la stessa intestazione di richiesta "`X-InternetExplorerModeConfigurable: 1`" a Siti configurabili. Si consiglia di usare lestazione di richiesta Utente-Agente per distinguere le richieste della modalità Microsoft Edge da quelle della modalità IE, ed evitare il reindirizzamento quando il sito è già caricato dal motore corretto.

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)