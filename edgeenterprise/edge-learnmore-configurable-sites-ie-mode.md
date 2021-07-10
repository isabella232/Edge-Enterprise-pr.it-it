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
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641802"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a><span data-ttu-id="34ad4-103">Altre informazioni su Siti configurabili nella modalità IE</span><span class="sxs-lookup"><span data-stu-id="34ad4-103">Learn about Configurable sites in IE mode</span></span>

<span data-ttu-id="34ad4-104">Questo articolo descrive la funzionalità Siti configurabili nell'Elenco siti modalità Enterprise durante l'uso di Internet Explorer in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="34ad4-104">This article explains the Configurable sites feature of the Enterprise Mode Site List when using IE mode in Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34ad4-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34ad4-105">Prerequisites</span></span>

- <span data-ttu-id="34ad4-106">Aggiornamenti di Windows</span><span class="sxs-lookup"><span data-stu-id="34ad4-106">Windows updates</span></span>

  - <span data-ttu-id="34ad4-107">Windows 10 versione 1909, Windows Server versione 1909 – KB4550945  o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-107">Windows 10 version 1909, Windows server version 1909 – KB4550945  or higher</span></span>
  - <span data-ttu-id="34ad4-108">Windows 10 versione 1903, Windows Server versione 1903 – KB4550945  o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-108">Windows 10 version 1903, Windows server version 1903 – KB4550945  or higher</span></span>
  - <span data-ttu-id="34ad4-109">Windows 10 versione 1809, Windows Server versione 1809, e Windows Server 2019 - KB4550969 o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-109">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4550969 or higher</span></span>
  - <span data-ttu-id="34ad4-110">Windows 10 versione 1803 – KB4550944 o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-110">Windows 10 version 1803 – KB4550944 or higher</span></span>
  - <span data-ttu-id="34ad4-111">Windows 10 versione 1607, Windows Server 2016 - KB4556826 o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-111">Windows 10 version 1607, Windows Server 2016 - KB4556826 or higher</span></span>
  - <span data-ttu-id="34ad4-112">Windows 10 versione iniziale, luglio 2015 - KB4550947 o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-112">Windows 10 initial version, July 2015 - KB4550947 or higher</span></span>
  - <span data-ttu-id="34ad4-113">Windows 8.1 - KB4556798 o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-113">Windows 8.1 – KB4556798 or higher</span></span>

- <span data-ttu-id="34ad4-114">Microsoft Edge version 83 o successive</span><span class="sxs-lookup"><span data-stu-id="34ad4-114">Microsoft Edge version 83 or later</span></span>
- <span data-ttu-id="34ad4-115">[Modalità IE](./edge-ie-mode.md) configurata con l'Elenco siti modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="34ad4-115">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="34ad4-116">Panoramica</span><span class="sxs-lookup"><span data-stu-id="34ad4-116">Overview</span></span>

<span data-ttu-id="34ad4-117">La configurazione dei siti che hanno bisogno della modalità IE nell'Elenco siti modalità Enterprise funziona bene per gran parte degli ambienti con applicazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="34ad4-117">Configuring sites needing IE mode in the Enterprise Mode Site List will work well for most environments with legacy applications.</span></span> <span data-ttu-id="34ad4-118">Tuttavia, in alcuni casi questo approccio non è il modo migliore di configurare un sottogruppi di siti da aprire nella modalità IE senza eseguire il rendering di un intero dominio nella modalità IE.</span><span class="sxs-lookup"><span data-stu-id="34ad4-118">However, in some cases this approach isn't the best to configure a subset of sites to open in IE mode without rendering an entire domain in IE mode.</span></span> <span data-ttu-id="34ad4-119">Ad esempio, quando l'ambiente include sia applicazioni moderne che applicazioni che sono eseguite su singoli server, e si vuole avere la flessibilità di eseguire il rendering solo delle applicazioni legacy nella modalità IE, eseguendo il rendering delle altre applicazioni nella modalità Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="34ad4-119">For example, when your environment contains both modern and legacy applications running on a single server and you would like the flexibility to render only the legacy applications in IE mode and the remaining applications to render in Microsoft Edge mode.</span></span>

<span data-ttu-id="34ad4-120">La soluzione è usare la funzionalità Siti configurabili nell'Elenco siti modalità Enterprise.</span><span class="sxs-lookup"><span data-stu-id="34ad4-120">The solution is to use the Configurable sites feature of the Enterprise Mode Site List.</span></span> <span data-ttu-id="34ad4-121">Quando la funzionalità è abilitata, Microsoft Edge consente ai siti contrassegnati con il tag "configurabile" di essere inclusi nella determinazione del modulo della modalità IE.</span><span class="sxs-lookup"><span data-stu-id="34ad4-121">When the feature is enabled, Microsoft Edge will allow sites with the "configurable" tag to participate in IE mode engine determination.</span></span>

## <a name="how-configurable-sites-works"></a><span data-ttu-id="34ad4-122">Funzionamento di Siti configurabili</span><span class="sxs-lookup"><span data-stu-id="34ad4-122">How Configurable sites works</span></span>

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a><span data-ttu-id="34ad4-123">Passare automaticamente dal motore di Microsoft Edge a quello di Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="34ad4-123">Automatic switching from the Microsoft Edge engine to the IE mode engine</span></span>

<span data-ttu-id="34ad4-124">Per usare la funzionalità Siti configurabili, è necessario che uno o più siti dell'Elenco siti modalità enterprise abbiano l'opzione `<open-in>Configurable</open-in>`.</span><span class="sxs-lookup"><span data-stu-id="34ad4-124">To use the Configurable sites feature, you'll need one or more sites in the Enterprise Mode Site List to have the `<open-in>Configurable</open-in>` option.</span></span>

<span data-ttu-id="34ad4-125">Esempio:</span><span class="sxs-lookup"><span data-stu-id="34ad4-125">Example:</span></span>

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

<span data-ttu-id="34ad4-126">Quando la funzionalità Siti configurabili è abilitata, Edge si comporta in questo modo:</span><span class="sxs-lookup"><span data-stu-id="34ad4-126">When the Configurable sites feature is enabled, the following behavior occurs:</span></span>

1. <span data-ttu-id="34ad4-127">Quando viene inviata una richiesta a un sito configurabile, Microsoft Edge invia l'intestazione della richiesta HTTP "`X-InternetExplorerModeConfigurable: 1`".</span><span class="sxs-lookup"><span data-stu-id="34ad4-127">When making a request to a Configurable site, Microsoft Edge will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`".</span></span>
2. <span data-ttu-id="34ad4-128">Un sito configurabile potrebbe inviare una risposta di reindirizzamento (ad esempio, HTTP 302) con l'intestazione della risposta HTTP "`X-InternetExplorerMode: 1`" in modo da richiedere a Microsoft Edge di cariare il sito nella modalità IE.</span><span class="sxs-lookup"><span data-stu-id="34ad4-128">A Configurable site may send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 1`" to request that Microsoft Edge loads the site in IE mode.</span></span>
3. <span data-ttu-id="34ad4-129">Anche la destinazione del reindirizzamento (ossia il valore dell'intestazione della risposta di **Location**) deve essere un sito **Configurabile** o **Neutro**, altrimenti l'intestazione della risposta della modalità IE sarà ignorata.</span><span class="sxs-lookup"><span data-stu-id="34ad4-129">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="34ad4-130">Ci si attende che la destinazione del reindirizzamento sia di norma uguale all'URL originale.</span><span class="sxs-lookup"><span data-stu-id="34ad4-130">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="34ad4-131">Ma non deve essere necessariamente così.</span><span class="sxs-lookup"><span data-stu-id="34ad4-131">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="34ad4-132">La risposta di reindirizzamento viene memorizzata nella cache in base al comportamento normale di memorizzazione nella cache dei reindirizzamenti di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="34ad4-132">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a><span data-ttu-id="34ad4-133">Tornare al Microsoft Edge dal motore Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="34ad4-133">Switching back from IE mode engine to Microsoft Edge engine</span></span>

<span data-ttu-id="34ad4-134">L'abilitazione dei siti configurabili in Microsoft Edge determina l'abilitazione automatica dei seguenti comportamenti nella modalità IE:</span><span class="sxs-lookup"><span data-stu-id="34ad4-134">Enabling Configurable sites in Microsoft Edge automatically enables the following behaviors in IE mode tabs:</span></span>

1. <span data-ttu-id="34ad4-135">Quando viene inviata una richiesta a un sito configurabile, le schede della modalità IE inviano l'intestazione della richiesta HTTP "`X-InternetExplorerModeConfigurable: 1`", la stessa delle schede di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="34ad4-135">When making a request to a Configurable site, IE mode tabs will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`", the same as Microsoft Edge tabs.</span></span>
2. <span data-ttu-id="34ad4-136">Un sito configurabile potrebbe inviare una risposta di reindirizzamento (ad esempio, HTTP 302) con l'intestazione della risposta HTTP "`X-InternetExplorerMode: 0`" in modo da richiedere di ritornare alla modalità di navigazione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="34ad4-136">A Configurable site might send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 0`" to request that the navigation switch back to Microsoft Edge mode.</span></span>
3. <span data-ttu-id="34ad4-137">Anche la destinazione del reindirizzamento (ossia il valore dell'intestazione della risposta di **Location**) deve essere un sito **Configurabile** o **Neutro**, altrimenti l'intestazione della risposta della modalità IE sarà ignorata.</span><span class="sxs-lookup"><span data-stu-id="34ad4-137">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="34ad4-138">Ci si attende che la destinazione del reindirizzamento sia di norma uguale all'URL originale.</span><span class="sxs-lookup"><span data-stu-id="34ad4-138">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="34ad4-139">Ma non deve essere necessariamente così.</span><span class="sxs-lookup"><span data-stu-id="34ad4-139">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="34ad4-140">La risposta di reindirizzamento viene memorizzata nella cache in base al comportamento normale di memorizzazione nella cache dei reindirizzamenti di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="34ad4-140">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

> [!TIP]
> <span data-ttu-id="34ad4-141">Entrambi i motori di ricerca inviano la stessa intestazione di richiesta "`X-InternetExplorerModeConfigurable: 1`" a Siti configurabili.</span><span class="sxs-lookup"><span data-stu-id="34ad4-141">Both browser engines send the same "`X-InternetExplorerModeConfigurable: 1`" request header to Configurable sites.</span></span> <span data-ttu-id="34ad4-142">Si consiglia di usare lestazione di richiesta Utente-Agente per distinguere le richieste della modalità Microsoft Edge da quelle della modalità IE, ed evitare il reindirizzamento quando il sito è già caricato dal motore corretto.</span><span class="sxs-lookup"><span data-stu-id="34ad4-142">You should use the User-Agent request header to distinguish between requests from Microsoft Edge mode vs. IE mode to avoid redirecting when the site is already loading in the correct engine.</span></span>

## <a name="see-also"></a><span data-ttu-id="34ad4-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34ad4-143">See also</span></span>

- [<span data-ttu-id="34ad4-144">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="34ad4-144">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="34ad4-145">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="34ad4-145">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="34ad4-146">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="34ad4-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)