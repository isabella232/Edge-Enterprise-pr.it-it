---
title: Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 05/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge
ms.openlocfilehash: 5b0d2f58318b10538d0470b644d346b5b9b9489b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980240"
---
# Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge

A partire dalla versione 83 di Microsoft Edge, Microsoft effettuerà distribuzioni progressive degli aggiornamenti principali del canale Stable di Microsoft Edge nel corso di pochi giorni. La distribuzione progressiva ci consente di controllare gli aggiornamenti e aggiornare in modo sicuro il browser in tutta l'organizzazione.

> [!NOTE]
> Questo si applica alla versione 83 di Microsoft Edge sul canale Stable, o successive.

## Perché è necessaria la distribuzione progressiva?

Monitorando l'attentamente integrità dei nostri aggiornamenti e distribuendo gli aggiornamenti nel corso di alcuni giorni, possiamo limitare l'impatto dei problemi che possono verificarsi con il nuovo aggiornamento. Con la versione 83 di Microsoft Edge, le distribuzioni progressive saranno abilitate per tutte le versioni di Microsoft Edge per Windows 7, Windows 8 e 8.1, e Windows 10. Microsoft Edge per Mac sarà supportato non appena possibile.

## Come funzionano gli aggiornamenti?

A ogni installazione di Microsoft Edge viene assegnato un valore di aggiornamento. Quando la distribuzione incrementale viene avviata, l'aggiornamento viene mostrato quando il valore del dispositivo rientra nell'intervallo di valori dell'aggiornamento. Durante il progresso della distribuzione (entro un paio di giorni), tutti gli utenti avranno eseguito l'aggiornamento. Gli aggiornamenti del browser che apportano correzioni critiche per la sicurezza avranno una cadenza di distribuzione più rapida di quelli che non le apportano. Ciò è fatto per garantire la tempestiva protezione delle vulnerabilità.

## Come sono condizionate le imprese da tutto questo?

Gli artefatti Microsoft Edge sono distribuiti alle organizzazioni tramite meccanismi multipli, come Microsoft Intune, Windows Server Update Services (WSUS) e Gestione configurazione. Questi strumenti di distribuzione si comportano in modo diverso rispetto alle distribuzioni progressive:

- le organizzazioni che gestiscono la distribuzione tramite Microsoft Intune sono registrate per gli aggiornamenti automatici. Viene usata la distribuzione progressiva, e tutti gli utenti vedono un aggiornamento entro pochi giorni.
- Le organizzazioni che gestiscono la distribuzione con WSUS (Windows Server Update Services) o con Gestione configurazione non sono registrate per gli aggiornamenti automatici. Gli amministratori gestiscono e applicano gli aggiornamenti che saranno disponibili fin da subito. La distribuzione progressiva non influisce su questo processo.

Si prega di condividere il proprio prezioso feedback usando l'utente, il pulsante del feedback nell'app, o sotto nei commenti in caso di domande o dubbi.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
