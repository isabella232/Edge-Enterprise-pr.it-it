---
title: Panoramica dei canali di Microsoft Edge
ms.author: srugh
author: srugh
manager: seanlynd
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Panoramica dei canali di Microsoft Edge
ms.openlocfilehash: 7d1fb72b458569cb4e4c6f44a6d89be7f65984df
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641992"
---
# <a name="overview-of-the-microsoft-edge-channels"></a>Panoramica dei canali di Microsoft Edge

Uno dei vantaggi della versione successiva di Microsoft Edge è che Microsoft può fornire le nuove funzionalità su base regolare. Tuttavia, in qualità di amministratore che distribuisce Microsoft Edge agli utenti dell'organizzazione potresti volere un controllo maggiore sulla frequenza con cui gli utenti scaricano queste nuove funzionalità. Microsoft offre quattro opzioni, denominate canali, per controllare la frequenza con cui Microsoft Edge viene aggiornato con le nuove funzionalità. Ecco una panoramica delle quattro opzioni.

Per altre informazioni sul supporto per ciascun canale, vedi: [Ciclo di vita di Microsoft Edge](/deployedge/microsoft-edge-support-lifecycle)
  
> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="channel-overview"></a>Panoramica dei canali

|Canale|Scopo principale|Frequenza di aggiornamento con le nuove funzionalità|Con supporto?|
|:---:|---|:---:|:---:|
|[Stable](#stable-channel)|Distribuzione ampia|~6 settimane|Sì|
|[Beta](#beta-channel)|Convalida rappresentativa nell'organizzazione|~6 settimane|Sì|
|[Dev](#dev-channel)|Pianificazione e sviluppo|Ogni settimana|No|
|[Canary](#canary-channel)|Contenuto rischioso|Ogni giorno|No|

Il canale di aggiornamento che decidi di distribuire agli utenti dipende da diversi fattori, ad esempio il numero di applicazioni line-of-business sfruttate dall'utente e che devi testare ogni volta che gli utenti hanno una versione aggiornata di Microsoft Edge. Per prendere questa decisione, esamina le informazioni che seguono sui quattro canali di aggiornamento disponibili per Microsoft Edge.

### <a name="stable-channel"></a>Canale Stable

Il canale Stable è progettato per la distribuzione generale nell'organizzazione ed è il canale in cui la maggior parte degli utenti deve essere attiva. È il più stabile dei canali ed è il risultato della stabilizzazione del set disponibile di funzionalità nella versione precedente del canale Beta. Le nuove funzionalità vengono fornite ogni sei settimane. Gli aggiornamenti della sicurezza e della qualità vengono forniti in base alle esigenze. Viene fornito il supporto per una versione del canale Stable fino a quando non è disponibile la versione successiva del canale.

### <a name="beta-channel"></a>Canale Beta

Il canale Beta è destinato alla distribuzione della produzione dell'organizzazione a un campione rappresentativo di utenti. Si tratta di una versione con supporto e ogni versione Beta verrà supportata fino a quando non sarà disponibile la versione successiva di questo canale. Si tratta di una buona opportunità per verificare che le operazioni funzionino come previsto nell'ambiente in uso e se si verifica un problema, è necessario porvi rimedio prima di pubblicare la versione nel canale Stable. Le nuove funzionalità vengono fornite ogni sei settimane. Gli aggiornamenti della sicurezza e della qualità vengono forniti in base alle esigenze.

### <a name="dev-channel"></a>Canale Dev

Il canale Dev intende aiutarti a pianificare e sviluppare con le funzionalità più recenti di Microsoft Edge, ma con una qualità superiore a quella del canale Canary. Questa è la tua opportunità per dare un'occhiata in anteprima alle novità in arrivo e per prepararti per la prossima versione Beta.

### <a name="canary-channel"></a>Canale Canary

Il canale Canary viene distribuito ogni giorno ed è il più rischioso di tutti i canali. Se vuoi accedere agli investimenti più recenti, questi verranno prima di tutto visualizzati qui. A causa della natura di questa frequenza, nel tempo si verificheranno problemi, quindi potresti desiderare che un altro canale sia installato affiancato se usi le versioni Canary.

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Download di canali](https://aka.ms/EdgeEnterprise)
