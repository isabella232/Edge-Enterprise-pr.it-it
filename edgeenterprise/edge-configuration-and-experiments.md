---
title: Configurazioni e sperimentazione di Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Configurazioni e sperimentazione di Microsoft Edge
ms.openlocfilehash: d6aee10133b5cbc0f7a784fab561864303d3dc6eb4e1cb6547562b9e6107961a
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726169"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a>Configurazioni e sperimentazione di Microsoft Edge

Questo articolo descrive l'interazione tra Microsoft Edge e il servizio di sperimentazione e configurazione. Microsoft Edge comunica con questo servizio per richiedere e ricevere diversi tipi di payload. Questi payload includono configurazioni, implementazioni di funzionalità ed esperimenti.

> [!IMPORTANT]
> Assicurarsi che i client possano accedere a `https://config.edge.skype.com` in modo da poter ricevere i payload.

> [!NOTE]
> Si applica a Microsoft Edge versione 77 o successiva.

## <a name="configurations"></a>Configurazioni

Le configurazioni sono il payload destinato a garantire l'integrità, la sicurezza e la conformità alla privacy del prodotto e hanno lo stesso valore per tutti gli utenti (in base a piattaforme e canali). Ciò potrebbe essere usato per abilitare un flag di funzionalità per un'azione di dominio e anche per disabilitare un flag di funzionalità nel caso di un bug.

## <a name="controlled-feature-rollout"></a>Implementazione controllata delle funzionalità

L'implementazione controllata della funzionalità è una procedura per aumentare lentamente le dimensioni del gruppo di utenti che riceve una funzionalità. Distribuendo una nuova funzionalità a un sottoinsieme selezionato in modo casuale della popolazione degli utenti, è possibile confrontare il feedback degli utenti con un gruppo di controllo di dimensioni uguali senza la possibilità per misurare l'impatto della funzionalità.

## <a name="experiments"></a>Esperimenti

Nelle build di Microsoft Edge sono presenti funzionalità ancora in fase di sviluppo o sperimentali. Gli esperimenti sono simili alla procedura di implementazione controllata delle funzionalità, ma le dimensioni del gruppo di utenti sono molto più piccole per testare il nuovo concetto. Queste funzionalità sono nascoste per impostazione predefinita finché la funzionalità non viene implementata o l'esperimento non è completato. I flag di esperimento vengono usati per abilitare e disabilitare queste funzionalità.

## <a name="about-the-ecs"></a>Informazioni sul servizio di sperimentazione e configurazione

In tutti gli scenari precedenti, il servizio recapita i valori del flag di funzionalità al client del browser in modo che possano essere applicati. A seconda dell'aggiornamento, le configurazioni vengono applicate immediatamente o quando l'utente riavvia il browser.

L'interazione di Microsoft Edge con questo servizio è controllato dalle impostazioni del criterio [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol). Puoi configurare le impostazioni dei criteri per:

- Recuperare solo le configurazioni
- Recuperare configurazioni ed esperimenti
- Disabilitare la comunicazione con il servizio

  > [!CAUTION]
  > Se disabiliti le comunicazioni con il servizio, la capacità di Microsoft di rispondere tempestivamente a un bug grave ne sarà influenzata.

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoftedgeinsider.com/enterprise)
- [Pagina di destinazione della documentazione di Microsoft Edge](./index.yml)