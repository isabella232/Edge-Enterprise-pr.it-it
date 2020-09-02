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
# <span data-ttu-id="ee8a7-103">Distribuzioni progressive per gli aggiornamenti del Canale Stable di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ee8a7-103">Progressive rollouts for Microsoft Edge Stable channel updates</span></span>

<span data-ttu-id="ee8a7-104">A partire dalla versione 83 di Microsoft Edge, Microsoft effettuerà distribuzioni progressive degli aggiornamenti principali del canale Stable di Microsoft Edge nel corso di pochi giorni.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-104">Starting with Microsoft Edge 83 release, we will perform gradual rollouts of major updates to Microsoft Edge Stable channel over the span of a few days.</span></span> <span data-ttu-id="ee8a7-105">La distribuzione progressiva ci consente di controllare gli aggiornamenti e aggiornare in modo sicuro il browser in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-105">This progressive rollout allows us to monitor upgrades and safely update the browser across the organization.</span></span>

> [!NOTE]
> <span data-ttu-id="ee8a7-106">Questo si applica alla versione 83 di Microsoft Edge sul canale Stable, o successive.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-106">This applies to Microsoft Edge Stable channel version 83 or later.</span></span>

## <span data-ttu-id="ee8a7-107">Perché è necessaria la distribuzione progressiva?</span><span class="sxs-lookup"><span data-stu-id="ee8a7-107">Why do we need progressive rollout?</span></span>

<span data-ttu-id="ee8a7-108">Monitorando l'attentamente integrità dei nostri aggiornamenti e distribuendo gli aggiornamenti nel corso di alcuni giorni, possiamo limitare l'impatto dei problemi che possono verificarsi con il nuovo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-108">By monitoring the health of our updates closely and rolling out the updates over the course of several days, we can limit the impact of issues that might occur with the new update.</span></span> <span data-ttu-id="ee8a7-109">Con la versione 83 di Microsoft Edge, le distribuzioni progressive saranno abilitate per tutte le versioni di Microsoft Edge per Windows 7, Windows 8 e 8.1, e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-109">With Microsoft Edge release 83, Progressive Rollouts will be enabled for all Windows 7, Windows 8 & 8.1, and Windows 10 versions of Microsoft Edge.</span></span> <span data-ttu-id="ee8a7-110">Microsoft Edge per Mac sarà supportato non appena possibile.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-110">We will support Microsoft Edge on Mac as soon as it is ready.</span></span>

## <span data-ttu-id="ee8a7-111">Come funzionano gli aggiornamenti?</span><span class="sxs-lookup"><span data-stu-id="ee8a7-111">How will the updates work?</span></span>

<span data-ttu-id="ee8a7-112">A ogni installazione di Microsoft Edge viene assegnato un valore di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-112">Each installation of Microsoft Edge is assigned an upgrade value.</span></span> <span data-ttu-id="ee8a7-113">Quando la distribuzione incrementale viene avviata, l'aggiornamento viene mostrato quando il valore del dispositivo rientra nell'intervallo di valori dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-113">When we start rolling out incrementally, you'll see the update when the value on your device falls within the upgrade value range.</span></span> <span data-ttu-id="ee8a7-114">Durante il progresso della distribuzione (entro un paio di giorni), tutti gli utenti avranno eseguito l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-114">As the rollout progresses (within a few days), all users will eventually get the update.</span></span> <span data-ttu-id="ee8a7-115">Gli aggiornamenti del browser che apportano correzioni critiche per la sicurezza avranno una cadenza di distribuzione più rapida di quelli che non le apportano.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-115">Browser updates with critical security fixes will have a faster rollout cadence than updates that don't have critical security fixes.</span></span> <span data-ttu-id="ee8a7-116">Ciò è fatto per garantire la tempestiva protezione delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-116">This is done to ensure prompt protection from vulnerabilities.</span></span>

## <span data-ttu-id="ee8a7-117">Come sono condizionate le imprese da tutto questo?</span><span class="sxs-lookup"><span data-stu-id="ee8a7-117">How does this affect enterprises?</span></span>

<span data-ttu-id="ee8a7-118">Gli artefatti Microsoft Edge sono distribuiti alle organizzazioni tramite meccanismi multipli, come Microsoft Intune, Windows Server Update Services (WSUS) e Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-118">Microsoft Edge artifacts are distributed to enterprises using multiple mechanisms such as Microsoft Intune, Windows Server Update Service (WSUS), and Configuration Manager.</span></span> <span data-ttu-id="ee8a7-119">Questi strumenti di distribuzione si comportano in modo diverso rispetto alle distribuzioni progressive:</span><span class="sxs-lookup"><span data-stu-id="ee8a7-119">These deployment tools behave differently with respect to Progressive Rollout:</span></span>

- <span data-ttu-id="ee8a7-120">le organizzazioni che gestiscono la distribuzione tramite Microsoft Intune sono registrate per gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-120">Enterprises that manage distribution via Microsoft Intune are registered for auto-updates.</span></span> <span data-ttu-id="ee8a7-121">Viene usata la distribuzione progressiva, e tutti gli utenti vedono un aggiornamento entro pochi giorni.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-121">Progressive Rollout is used, and all the users will see an update in a few days.</span></span>
- <span data-ttu-id="ee8a7-122">Le organizzazioni che gestiscono la distribuzione con WSUS (Windows Server Update Services) o con Gestione configurazione non sono registrate per gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-122">Enterprises that manage distribution through WSUS (Windows Server Update Services) or Configuration Manager are not registered for auto-updates.</span></span> <span data-ttu-id="ee8a7-123">Gli amministratori gestiscono e applicano gli aggiornamenti che saranno disponibili fin da subito.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-123">Administrators manage and apply the updates that will be available from the start.</span></span> <span data-ttu-id="ee8a7-124">La distribuzione progressiva non influisce su questo processo.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-124">Progressive Rollout does not affect this process.</span></span>

<span data-ttu-id="ee8a7-125">Si prega di condividere il proprio prezioso feedback usando l'utente, il pulsante del feedback nell'app, o sotto nei commenti in caso di domande o dubbi.</span><span class="sxs-lookup"><span data-stu-id="ee8a7-125">Please share your valuable feedback through user voice, the in-application feedback button, or below in the comments if you have any concerns or questions.</span></span>

## <span data-ttu-id="ee8a7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee8a7-126">See also</span></span>

- [<span data-ttu-id="ee8a7-127">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="ee8a7-127">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
