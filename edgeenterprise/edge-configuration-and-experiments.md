---
title: Configurazioni e sperimentazione di Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurazioni e sperimentazione di Microsoft Edge
ms.openlocfilehash: f66da4075c33c1f375dfb593c1a1bd2b4a139833
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980180"
---
# <span data-ttu-id="8145b-103">Configurazioni e sperimentazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8145b-103">Microsoft Edge configurations and experimentation</span></span>

<span data-ttu-id="8145b-104">Questo articolo descrive l'interazione tra Microsoft Edge e il servizio di sperimentazione e configurazione.</span><span class="sxs-lookup"><span data-stu-id="8145b-104">This article describes the interaction between Microsoft Edge and the Experimentation and Configuration Service (ECS).</span></span> <span data-ttu-id="8145b-105">Microsoft Edge comunica con questo servizio per richiedere e ricevere diversi tipi di payload.</span><span class="sxs-lookup"><span data-stu-id="8145b-105">Microsoft Edge communicates with this service to request and receive different kinds of payloads.</span></span> <span data-ttu-id="8145b-106">Questi payload includono configurazioni, implementazioni di funzionalità ed esperimenti.</span><span class="sxs-lookup"><span data-stu-id="8145b-106">These payloads include configurations, feature rollouts, and experiments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8145b-107">Assicurarsi che i client possano accedere a `https://config.edge.skype.com` in modo da poter ricevere i payload.</span><span class="sxs-lookup"><span data-stu-id="8145b-107">Make sure clients are able to access `https://config.edge.skype.com` so payloads can be received.</span></span>

> [!NOTE]
> <span data-ttu-id="8145b-108">Si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="8145b-108">This applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="8145b-109">Configurazioni</span><span class="sxs-lookup"><span data-stu-id="8145b-109">Configurations</span></span>

<span data-ttu-id="8145b-110">Le configurazioni sono il payload destinato a garantire l'integrità, la sicurezza e la conformità alla privacy del prodotto e hanno lo stesso valore per tutti gli utenti (in base a piattaforme e canali). Ciò potrebbe essere usato per abilitare un flag di funzionalità per un'azione di dominio e anche per disabilitare un flag di funzionalità nel caso di un bug.</span><span class="sxs-lookup"><span data-stu-id="8145b-110">Configurations are the payload meant to ensure product health, security, and privacy compliance, and are intended to have the same value for all the users (based on platforms and channels.) This could be to enable a feature flag for a domain action, and can also be used to disable a feature flag in the event of a bug.</span></span>

## <span data-ttu-id="8145b-111">Implementazione controllata delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="8145b-111">Controlled Feature Rollout</span></span>

<span data-ttu-id="8145b-112">L'implementazione controllata della funzionalità è una procedura per aumentare lentamente le dimensioni del gruppo di utenti che riceve una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8145b-112">Controlled Feature Rollout (CFR) is a procedure for slowly increasing the size of the user group that receives a feature.</span></span> <span data-ttu-id="8145b-113">Distribuendo una nuova funzionalità a un sottoinsieme selezionato in modo casuale della popolazione degli utenti, è possibile confrontare il feedback degli utenti con un gruppo di controllo di dimensioni uguali senza la possibilità per misurare l'impatto della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8145b-113">By distributing a new feature to a randomly selected subset of the user population, it’s possible to compare user feedback to an equally sized control group without the feature to measure the impact of the feature.</span></span>

## <span data-ttu-id="8145b-114">Esperimenti</span><span class="sxs-lookup"><span data-stu-id="8145b-114">Experiments</span></span>

<span data-ttu-id="8145b-115">Nelle build di Microsoft Edge sono presenti funzionalità ancora in fase di sviluppo o sperimentali.</span><span class="sxs-lookup"><span data-stu-id="8145b-115">Microsoft Edge builds have features and functionality that are still in development or are experimental.</span></span> <span data-ttu-id="8145b-116">Gli esperimenti sono simili alla procedura di implementazione controllata delle funzionalità, ma le dimensioni del gruppo di utenti sono molto più piccole per testare il nuovo concetto.</span><span class="sxs-lookup"><span data-stu-id="8145b-116">Experiments are like CFR, but the size of the user group is much smaller for testing the new concept.</span></span> <span data-ttu-id="8145b-117">Queste funzionalità sono nascoste per impostazione predefinita finché la funzionalità non viene implementata o l'esperimento non è completato.</span><span class="sxs-lookup"><span data-stu-id="8145b-117">These features are hidden by default until the feature's rolled out or the experiment's finished.</span></span> <span data-ttu-id="8145b-118">I flag di esperimento vengono usati per abilitare e disabilitare queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8145b-118">Experiment flags are used to enable and disable these features.</span></span>

## <span data-ttu-id="8145b-119">Informazioni sul servizio di sperimentazione e configurazione</span><span class="sxs-lookup"><span data-stu-id="8145b-119">About the ECS</span></span>

<span data-ttu-id="8145b-120">In tutti gli scenari precedenti, il servizio recapita i valori del flag di funzionalità al client del browser in modo che possano essere applicati.</span><span class="sxs-lookup"><span data-stu-id="8145b-120">In all the preceding scenarios, the service delivers the feature flag values to the browser client so they can be applied.</span></span> <span data-ttu-id="8145b-121">A seconda dell'aggiornamento, le configurazioni vengono applicate immediatamente o quando l'utente riavvia il browser.</span><span class="sxs-lookup"><span data-stu-id="8145b-121">Depending on the update, configurations are applied immediately or when the user restarts the browser.</span></span>

<span data-ttu-id="8145b-122">L'interazione di Microsoft Edge con questo servizio è controllato dalle impostazioni del criterio [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol).</span><span class="sxs-lookup"><span data-stu-id="8145b-122">Microsoft Edge's interaction with this service is controlled by settings in the [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol) policy.</span></span> <span data-ttu-id="8145b-123">Puoi configurare le impostazioni dei criteri per:</span><span class="sxs-lookup"><span data-stu-id="8145b-123">You can configure policy settings to:</span></span>

- <span data-ttu-id="8145b-124">Recuperare solo le configurazioni</span><span class="sxs-lookup"><span data-stu-id="8145b-124">Retrieve configurations only</span></span>
- <span data-ttu-id="8145b-125">Recuperare configurazioni ed esperimenti</span><span class="sxs-lookup"><span data-stu-id="8145b-125">Retrieve configurations and experiments</span></span>
- <span data-ttu-id="8145b-126">Disabilitare la comunicazione con il servizio</span><span class="sxs-lookup"><span data-stu-id="8145b-126">Disable communication with the service</span></span>

  > [!CAUTION]
  > <span data-ttu-id="8145b-127">Se disabiliti le comunicazioni con il servizio, la capacità di Microsoft di rispondere tempestivamente a un bug grave ne sarà influenzata.</span><span class="sxs-lookup"><span data-stu-id="8145b-127">If you disable communications with the service, this will affect Microsoft’s ability to respond to a severe bug in a timely manner.</span></span>

## <span data-ttu-id="8145b-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8145b-128">See also</span></span>

- [<span data-ttu-id="8145b-129">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="8145b-129">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="8145b-130">Pagina di destinazione della documentazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8145b-130">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
