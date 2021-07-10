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
ms.openlocfilehash: 1ebfe5fc1da107aa7e9e20b629f14aff468bdd6d
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641562"
---
# <a name="microsoft-edge-configurations-and-experimentation"></a><span data-ttu-id="5b98d-103">Configurazioni e sperimentazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5b98d-103">Microsoft Edge configurations and experimentation</span></span>

<span data-ttu-id="5b98d-104">Questo articolo descrive l'interazione tra Microsoft Edge e il servizio di sperimentazione e configurazione.</span><span class="sxs-lookup"><span data-stu-id="5b98d-104">This article describes the interaction between Microsoft Edge and the Experimentation and Configuration Service (ECS).</span></span> <span data-ttu-id="5b98d-105">Microsoft Edge comunica con questo servizio per richiedere e ricevere diversi tipi di payload.</span><span class="sxs-lookup"><span data-stu-id="5b98d-105">Microsoft Edge communicates with this service to request and receive different kinds of payloads.</span></span> <span data-ttu-id="5b98d-106">Questi payload includono configurazioni, implementazioni di funzionalità ed esperimenti.</span><span class="sxs-lookup"><span data-stu-id="5b98d-106">These payloads include configurations, feature rollouts, and experiments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b98d-107">Assicurarsi che i client possano accedere a `https://config.edge.skype.com` in modo da poter ricevere i payload.</span><span class="sxs-lookup"><span data-stu-id="5b98d-107">Make sure clients are able to access `https://config.edge.skype.com` so payloads can be received.</span></span>

> [!NOTE]
> <span data-ttu-id="5b98d-108">Si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="5b98d-108">This applies to Microsoft Edge version 77 or later.</span></span>

## <a name="configurations"></a><span data-ttu-id="5b98d-109">Configurazioni</span><span class="sxs-lookup"><span data-stu-id="5b98d-109">Configurations</span></span>

<span data-ttu-id="5b98d-110">Le configurazioni sono il payload destinato a garantire l'integrità, la sicurezza e la conformità alla privacy del prodotto e hanno lo stesso valore per tutti gli utenti (in base a piattaforme e canali). Ciò potrebbe essere usato per abilitare un flag di funzionalità per un'azione di dominio e anche per disabilitare un flag di funzionalità nel caso di un bug.</span><span class="sxs-lookup"><span data-stu-id="5b98d-110">Configurations are the payload meant to ensure product health, security, and privacy compliance, and are intended to have the same value for all the users (based on platforms and channels.) This could be to enable a feature flag for a domain action, and can also be used to disable a feature flag in the event of a bug.</span></span>

## <a name="controlled-feature-rollout"></a><span data-ttu-id="5b98d-111">Implementazione controllata delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="5b98d-111">Controlled Feature Rollout</span></span>

<span data-ttu-id="5b98d-112">L'implementazione controllata della funzionalità è una procedura per aumentare lentamente le dimensioni del gruppo di utenti che riceve una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5b98d-112">Controlled Feature Rollout (CFR) is a procedure for slowly increasing the size of the user group that receives a feature.</span></span> <span data-ttu-id="5b98d-113">Distribuendo una nuova funzionalità a un sottoinsieme selezionato in modo casuale della popolazione degli utenti, è possibile confrontare il feedback degli utenti con un gruppo di controllo di dimensioni uguali senza la possibilità per misurare l'impatto della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5b98d-113">By distributing a new feature to a randomly selected subset of the user population, it’s possible to compare user feedback to an equally sized control group without the feature to measure the impact of the feature.</span></span>

## <a name="experiments"></a><span data-ttu-id="5b98d-114">Esperimenti</span><span class="sxs-lookup"><span data-stu-id="5b98d-114">Experiments</span></span>

<span data-ttu-id="5b98d-115">Nelle build di Microsoft Edge sono presenti funzionalità ancora in fase di sviluppo o sperimentali.</span><span class="sxs-lookup"><span data-stu-id="5b98d-115">Microsoft Edge builds have features and functionality that are still in development or are experimental.</span></span> <span data-ttu-id="5b98d-116">Gli esperimenti sono simili alla procedura di implementazione controllata delle funzionalità, ma le dimensioni del gruppo di utenti sono molto più piccole per testare il nuovo concetto.</span><span class="sxs-lookup"><span data-stu-id="5b98d-116">Experiments are like CFR, but the size of the user group is much smaller for testing the new concept.</span></span> <span data-ttu-id="5b98d-117">Queste funzionalità sono nascoste per impostazione predefinita finché la funzionalità non viene implementata o l'esperimento non è completato.</span><span class="sxs-lookup"><span data-stu-id="5b98d-117">These features are hidden by default until the feature's rolled out or the experiment's finished.</span></span> <span data-ttu-id="5b98d-118">I flag di esperimento vengono usati per abilitare e disabilitare queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5b98d-118">Experiment flags are used to enable and disable these features.</span></span>

## <a name="about-the-ecs"></a><span data-ttu-id="5b98d-119">Informazioni sul servizio di sperimentazione e configurazione</span><span class="sxs-lookup"><span data-stu-id="5b98d-119">About the ECS</span></span>

<span data-ttu-id="5b98d-120">In tutti gli scenari precedenti, il servizio recapita i valori del flag di funzionalità al client del browser in modo che possano essere applicati.</span><span class="sxs-lookup"><span data-stu-id="5b98d-120">In all the preceding scenarios, the service delivers the feature flag values to the browser client so they can be applied.</span></span> <span data-ttu-id="5b98d-121">A seconda dell'aggiornamento, le configurazioni vengono applicate immediatamente o quando l'utente riavvia il browser.</span><span class="sxs-lookup"><span data-stu-id="5b98d-121">Depending on the update, configurations are applied immediately or when the user restarts the browser.</span></span>

<span data-ttu-id="5b98d-122">L'interazione di Microsoft Edge con questo servizio è controllato dalle impostazioni del criterio [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol).</span><span class="sxs-lookup"><span data-stu-id="5b98d-122">Microsoft Edge's interaction with this service is controlled by settings in the [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) policy.</span></span> <span data-ttu-id="5b98d-123">Puoi configurare le impostazioni dei criteri per:</span><span class="sxs-lookup"><span data-stu-id="5b98d-123">You can configure policy settings to:</span></span>

- <span data-ttu-id="5b98d-124">Recuperare solo le configurazioni</span><span class="sxs-lookup"><span data-stu-id="5b98d-124">Retrieve configurations only</span></span>
- <span data-ttu-id="5b98d-125">Recuperare configurazioni ed esperimenti</span><span class="sxs-lookup"><span data-stu-id="5b98d-125">Retrieve configurations and experiments</span></span>
- <span data-ttu-id="5b98d-126">Disabilitare la comunicazione con il servizio</span><span class="sxs-lookup"><span data-stu-id="5b98d-126">Disable communication with the service</span></span>

  > [!CAUTION]
  > <span data-ttu-id="5b98d-127">Se disabiliti le comunicazioni con il servizio, la capacità di Microsoft di rispondere tempestivamente a un bug grave ne sarà influenzata.</span><span class="sxs-lookup"><span data-stu-id="5b98d-127">If you disable communications with the service, this will affect Microsoft’s ability to respond to a severe bug in a timely manner.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b98d-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5b98d-128">See also</span></span>

- [<span data-ttu-id="5b98d-129">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="5b98d-129">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="5b98d-130">Pagina di destinazione della documentazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5b98d-130">Microsoft Edge documentation landing page</span></span>](./index.yml)