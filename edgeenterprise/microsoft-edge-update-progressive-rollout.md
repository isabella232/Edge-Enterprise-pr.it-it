---
title: Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge
ms.openlocfilehash: bdcefdc118125d67057fa77513bd732cff6882e3
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980248"
---
# <a name="progressive-rollouts-for-microsoft-edge-stable-channel-updates"></a>Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge

A partire dalla versione 83 di Microsoft Edge, Microsoft effettuerà distribuzioni progressive degli aggiornamenti principali del canale Stable di Microsoft Edge nel corso di pochi giorni. La distribuzione progressiva ci consente di controllare gli aggiornamenti e aggiornare in modo sicuro il browser in tutta l'organizzazione.

> [!NOTE]
> Questo si applica alla versione 83 di Microsoft Edge sul canale Stable, o successive.

## <a name="why-do-we-need-progressive-rollout"></a>Perché è necessaria la distribuzione progressiva?

Monitorando l'attentamente integrità dei nostri aggiornamenti e distribuendo gli aggiornamenti nel corso di alcuni giorni, possiamo limitare l'impatto dei problemi che possono verificarsi con il nuovo aggiornamento. Con la versione 83 di Microsoft Edge, le distribuzioni progressive saranno abilitate per tutte le versioni di Microsoft Edge per Windows 7, Windows 8 e 8.1, e Windows 10. Microsoft Edge per Mac sarà supportato non appena possibile.

## <a name="how-will-the-updates-work"></a>Come funzionano gli aggiornamenti?

A ogni installazione di Microsoft Edge viene assegnato un valore di aggiornamento. Quando la distribuzione incrementale viene avviata, l'aggiornamento viene mostrato quando il valore del dispositivo rientra nell'intervallo di valori dell'aggiornamento. Durante il progresso della distribuzione (entro un paio di giorni), tutti gli utenti avranno eseguito l'aggiornamento. Gli aggiornamenti del browser che apportano correzioni critiche per la sicurezza avranno una cadenza di distribuzione più rapida di quelli che non le apportano. Ciò è fatto per garantire la tempestiva protezione delle vulnerabilità.

## <a name="how-does-this-affect-enterprises"></a>Come sono condizionate le imprese da tutto questo?

Gli artefatti Microsoft Edge sono distribuiti alle organizzazioni tramite meccanismi multipli, come Microsoft Intune, Windows Server Update Services (WSUS) e Gestione configurazione. Questi strumenti di distribuzione si comportano in modo diverso rispetto alle distribuzioni progressive:

- le organizzazioni che gestiscono la distribuzione tramite Microsoft Intune sono registrate per gli aggiornamenti automatici. Viene usata la distribuzione progressiva, e tutti gli utenti vedono un aggiornamento entro pochi giorni.
- Le organizzazioni che gestiscono la distribuzione con WSUS (Windows Server Update Services) o con Gestione configurazione non sono registrate per gli aggiornamenti automatici. Gli amministratori gestiscono e applicano gli aggiornamenti che saranno disponibili fin da subito. La distribuzione progressiva non influisce su questo processo.

Si prega di condividere il proprio prezioso feedback usando l'utente, il pulsante del feedback nell'app, o sotto nei commenti in caso di domande o dubbi.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
