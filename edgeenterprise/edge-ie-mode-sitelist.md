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
# <span data-ttu-id="aa3db-103">Configurare i siti nell'elenco di siti in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa3db-103">Configure Sites on the Enterprise Mode Site List</span></span>

<span data-ttu-id="aa3db-104">Questo articolo descrive le modifiche apportate all'elenco di siti in modalità Enterprise che supportano la configurazione della modalità IE per Microsoft Edge versione 77 e successive.</span><span class="sxs-lookup"><span data-stu-id="aa3db-104">This article describes changes to the Enterprise Mode Site List that support configuring IE mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="aa3db-105">Per altre informazioni sullo schema per il file XML dell'elenco di siti in modalità Enterprise, vedere [Indicazioni per lo schema v.2 della modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span><span class="sxs-lookup"><span data-stu-id="aa3db-105">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="aa3db-106">Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="aa3db-106">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="aa3db-107">Elementi dello schema aggiornati</span><span class="sxs-lookup"><span data-stu-id="aa3db-107">Updated schema elements</span></span>

<span data-ttu-id="aa3db-108">La tabella seguente descrive l'elemento \<open-in app\> aggiunto allo schema v.2 della modalità Enterprise:</span><span class="sxs-lookup"><span data-stu-id="aa3db-108">The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:</span></span>

| **<span data-ttu-id="aa3db-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa3db-109">Element</span></span>** | **<span data-ttu-id="aa3db-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa3db-110">Description</span></span>** |
| --- | --- |
| \<open-in app="**true**"\> | <span data-ttu-id="aa3db-111">Un elemento figlio che controlla il browser usato per i siti.</span><span class="sxs-lookup"><span data-stu-id="aa3db-111">A child element that controls what browser is used for sites.</span></span> <span data-ttu-id="aa3db-112">Questo elemento è obbligatorio per i siti che devono essere **aperti in IE11**.</span><span class="sxs-lookup"><span data-stu-id="aa3db-112">This element is required for sites that need to **open in IE11**.</span></span>|

**<span data-ttu-id="aa3db-113">Esempio:</span><span class="sxs-lookup"><span data-stu-id="aa3db-113">Example:</span></span>**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

<span data-ttu-id="aa3db-114">La tabella seguente indica i valori possibili dell'elemento \<open-in\>:</span><span class="sxs-lookup"><span data-stu-id="aa3db-114">The following table shows the possible values of the \<open-in\> element:</span></span>

| **<span data-ttu-id="aa3db-115">Value</span><span class="sxs-lookup"><span data-stu-id="aa3db-115">Value</span></span>** | **<span data-ttu-id="aa3db-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa3db-116">Description</span></span>** |
| --- | --- |
| **\<open-in\><span data-ttu-id="aa3db-117">IE11</span><span class="sxs-lookup"><span data-stu-id="aa3db-117">IE11</span></span>\</open-in\>** | <span data-ttu-id="aa3db-118">Apre il sito in modalità IE o in una finestra a schermo intero di IE11.</span><span class="sxs-lookup"><span data-stu-id="aa3db-118">Opens the site in IE mode or a full IE11 window.</span></span> <span data-ttu-id="aa3db-119">Per abilitare la modalità IE, vedere [Configurare i criteri della modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)</span><span class="sxs-lookup"><span data-stu-id="aa3db-119">To enable IE mode, see [Configure IE mode policies](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)</span></span>|
| **\<open-in app="**true**"\><span data-ttu-id="aa3db-120">IE11</span><span class="sxs-lookup"><span data-stu-id="aa3db-120">IE11</span></span>\</open-in\>** | <span data-ttu-id="aa3db-121">Apre il sito in una finestra a schermo intero di IE11</span><span class="sxs-lookup"><span data-stu-id="aa3db-121">Opens the site in a full IE11 window</span></span> |
| **\<open-in\><span data-ttu-id="aa3db-122">MSEdge</span><span class="sxs-lookup"><span data-stu-id="aa3db-122">MSEdge</span></span>\</open-in\>** | <span data-ttu-id="aa3db-123">Apre il sito in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="aa3db-123">Opens the site in Microsoft Edge</span></span> |
| **\<open-in\><span data-ttu-id="aa3db-124">Nessuno o non specificato.</span><span class="sxs-lookup"><span data-stu-id="aa3db-124">None or not specified</span></span>\</open-in\>** | <span data-ttu-id="aa3db-125">Apre il sito nel browser predefinito o nel browser in cui l'utente ha avviato la navigazione.</span><span class="sxs-lookup"><span data-stu-id="aa3db-125">Opens the site in the default browser or in the browser where the user navigated to the site.</span></span> |
|**\<open-in\><span data-ttu-id="aa3db-126">Configurabile</span><span class="sxs-lookup"><span data-stu-id="aa3db-126">Configurable</span></span>\</open-in\>** | <span data-ttu-id="aa3db-127">Consente al sito di partecipare alla determinazione del motore in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="aa3db-127">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="aa3db-128">Per altre informazioni, vedere [Informazioni sui siti configurabili in modalità Internet Explorer](edge-learnmore-configurable-sites-ie-mode.md).</span><span class="sxs-lookup"><span data-stu-id="aa3db-128">To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).</span></span>  |

>[!NOTE]
> <span data-ttu-id="aa3db-129">L'attributo app=**"true"** viene riconosciuto solo quando è associato a _'open-in' IE11_.</span><span class="sxs-lookup"><span data-stu-id="aa3db-129">The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_.</span></span> <span data-ttu-id="aa3db-130">Se lo si aggiunge agli altri elementi 'open-in', il comportamento del browser non cambia.</span><span class="sxs-lookup"><span data-stu-id="aa3db-130">Adding it to the other 'open-in' elements won't change browser behavior.</span></span>   

## <span data-ttu-id="aa3db-131">Configurare i siti neutri</span><span class="sxs-lookup"><span data-stu-id="aa3db-131">Configure neutral sites</span></span>

<span data-ttu-id="aa3db-132">Per il corretto funzionamento della modalità IE, i server di autenticazione e Single Sign-On devono essere configurati in modo esplicito come siti neutri.</span><span class="sxs-lookup"><span data-stu-id="aa3db-132">In order for IE mode to work properly, authentication / Single Sign-On servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="aa3db-133">In caso contrario, le pagine in modalità IE tenteranno di reindirizzare a Microsoft Edge e l'autenticazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="aa3db-133">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="aa3db-134">Quando viene avviata la navigazione, un sito neutrale usa il browser Microsoft Edge o la modalità IE.</span><span class="sxs-lookup"><span data-stu-id="aa3db-134">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="aa3db-135">La configurazione dei siti neutri garantisce che le applicazioni che usano tali server di autenticazione, moderni e legacy, continuino a funzionare.</span><span class="sxs-lookup"><span data-stu-id="aa3db-135">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="aa3db-136">È possibile configurare i siti neutri impostando l'elenco a discesa *Apri in* su 'Nessuno' nello strumento Enterprise Mode Site List Manager o aggiornando direttamente il file XML dell'elenco siti:</span><span class="sxs-lookup"><span data-stu-id="aa3db-136">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="aa3db-137">Per identificare i server di autenticazione, analizzare il traffico di rete da un'applicazione che usa gli strumenti di sviluppo di IE11.</span><span class="sxs-lookup"><span data-stu-id="aa3db-137">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="aa3db-138">Se serve più tempo per identificare i server di autenticazione, è possibile configurare un criterio in modo che tutti gli spostamenti nella pagina rimangano in modalità IE.</span><span class="sxs-lookup"><span data-stu-id="aa3db-138">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigation in IE mode.</span></span> <span data-ttu-id="aa3db-139">Per ridurre al minimo l'uso della modalità IE, disabilitare questa impostazione dopo aver identificato e aggiunto i server di autenticazione all'elenco dei siti.</span><span class="sxs-lookup"><span data-stu-id="aa3db-139">To minimize the use of IE mode, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="aa3db-140">Per altre informazioni, vedere [Configurare gli spostamenti nella pagina per rimanere in modalità IE](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect).</span><span class="sxs-lookup"><span data-stu-id="aa3db-140">For more information, see [Configure in-page navigation to remain in IE mode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect).</span></span>

>[!NOTE]
   ><span data-ttu-id="aa3db-141">Lo schema per la modalità Enterprise v.1 non è supportato per l'integrazione della modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="aa3db-141">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="aa3db-142">Se attualmente usi lo schema v.1 con Internet Explorer 11, devi eseguire l'aggiornamento allo schema v.2.</span><span class="sxs-lookup"><span data-stu-id="aa3db-142">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="aa3db-143">Per altre informazioni, vedi [Indicazioni per lo schema v.2 della modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span><span class="sxs-lookup"><span data-stu-id="aa3db-143">For more information, see [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <span data-ttu-id="aa3db-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa3db-144">See also</span></span>

- [<span data-ttu-id="aa3db-145">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa3db-145">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="aa3db-146">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="aa3db-146">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="aa3db-147">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="aa3db-147">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)