---
title: Impostazioni proxy di Microsoft Edge
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Usare le opzioni della riga di comando per configurare le impostazioni proxy '
ms.openlocfilehash: b5e2326e075ad89481560a6642944a8e88f4daa3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980270"
---
# <span data-ttu-id="0fdd1-103">Come usare le opzioni della riga di comando di Microsoft Edge per configurare le impostazioni proxy</span><span class="sxs-lookup"><span data-stu-id="0fdd1-103">How to use Microsoft Edge command-line options to configure proxy settings</span></span>

<span data-ttu-id="0fdd1-104">In questo articolo viene descritto come è possibile usare le opzioni della riga di comando per sostituire le impostazioni di rete del sistema predefinite.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-104">This article describes how you can use command-line options to override the default system network settings.</span></span>

>[!NOTE]
><span data-ttu-id="0fdd1-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="0fdd1-106">Impostazioni di rete del sistema</span><span class="sxs-lookup"><span data-stu-id="0fdd1-106">System network settings</span></span>

<span data-ttu-id="0fdd1-107">Per impostazione predefinita, lo stack di rete di Microsoft Edge usa le impostazioni di rete del sistema.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-107">The Microsoft Edge network stack uses the system network settings by default.</span></span> <span data-ttu-id="0fdd1-108">Sono incluse le *impostazioni proxy* e gli *archivi di certificai e chiavi private*.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-108">These settings include *proxy settings*, and *certificate and private key stores*.</span></span>

<span data-ttu-id="0fdd1-109">Esistono scenari in cui gli utenti richiedono un'alternativa all'uso delle impostazioni proxy predefinite del sistema.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-109">There are scenarios where users request an alternative to using the system's default proxy settings.</span></span> <span data-ttu-id="0fdd1-110">Per supportare questi scenari, Microsoft Edge supporta le opzioni della riga di comando che puoi usare per configurare le impostazioni proxy personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-110">To support these scenarios, Microsoft Edge supports command-line options that you can use to configure custom proxy settings.</span></span>

<span data-ttu-id="0fdd1-111">Queste opzioni della riga di comando corrispondono ai seguenti criteri nel gruppo **Server proxy**:</span><span class="sxs-lookup"><span data-stu-id="0fdd1-111">These command-line options correspond to the following policies in the **Proxy server** group:</span></span>

- [<span data-ttu-id="0fdd1-112">ProxyBypassList</span><span class="sxs-lookup"><span data-stu-id="0fdd1-112">ProxyBypassList</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist)
- [<span data-ttu-id="0fdd1-113">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0fdd1-113">ProxyMode</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode)
- [<span data-ttu-id="0fdd1-114">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0fdd1-114">ProxyPacUrl</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl)
- [<span data-ttu-id="0fdd1-115">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0fdd1-115">ProxyServer</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver)
- [<span data-ttu-id="0fdd1-116">ProxySettings</span><span class="sxs-lookup"><span data-stu-id="0fdd1-116">ProxySettings</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxysettings)

## <span data-ttu-id="0fdd1-117">Opzioni della riga di comando per le impostazioni proxy</span><span class="sxs-lookup"><span data-stu-id="0fdd1-117">Command-line options for proxy settings</span></span>

<span data-ttu-id="0fdd1-118">Microsoft Edge supporta le opzioni della riga di comando correlate al proxy seguenti.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-118">Microsoft Edge supports the following proxy-related command-line options.</span></span>

 **`--no-proxy-server`**
 
<span data-ttu-id="0fdd1-119">Indica a Microsoft Edge di non usare un proxy, anche se il sistema è configurato in altro modo per usarne uno.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-119">Tells Microsoft Edge not to use a Proxy, even if the system is otherwise configured to use one.</span></span> <span data-ttu-id="0fdd1-120">Sostituisce tutte le altre impostazioni proxy fornite.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-120">It overrides any other proxy settings that are provided.</span></span>

**`--proxy-auto-detect`**

<span data-ttu-id="0fdd1-121">Indica a Microsoft Edge di provare a rilevare automaticamente la configurazione del proxy.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-121">Tells Microsoft Edge to try and automatically detect your proxy configuration.</span></span> <span data-ttu-id="0fdd1-122">Questo argomento viene ignorato se `--proxy-server` è configurato.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-122">This argument is ignored if `--proxy-server` is configured.</span></span>

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

<span data-ttu-id="0fdd1-123">Indica a Microsoft Edge di usare una configurazione proxy personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-123">Tells Microsoft Edge to use a custom proxy configuration.</span></span> <span data-ttu-id="0fdd1-124">Puoi specificare una configurazione proxy personalizzata in tre modi.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-124">You can specify a custom proxy configuration in three ways.</span></span>

1. <span data-ttu-id="0fdd1-125">Specificare un mapping dello schema di elenchi a coppie di URL/porte separato da punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-125">Provide a semicolon-separated mapping of list scheme to url/port pairs.</span></span> <span data-ttu-id="0fdd1-126">Ad esempio, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` indica a Microsoft Edge di usare il proxy HTTP "proxy1:8080" per gli URL http e il proxy HTTP "ftpproxy:80" per gli URL ftp.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-126">For example, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` tells Microsoft Edge to use HTTP proxy "proxy1:8080" for http URLs and HTTP proxy "ftpproxy:80" for ftp URLs.</span></span>
2. <span data-ttu-id="0fdd1-127">Fornire un singolo URI con porta facoltativa da usare per tutti gli URL.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-127">By providing a single uri with optional port to use for all URLs.</span></span> <span data-ttu-id="0fdd1-128">Ad esempio, `--proxy-server="proxy2:8080"` userà il proxy in "proxy2:8080" per tutto il traffico.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-128">For example, `--proxy-server="proxy2:8080"` will use the proxy at "proxy2:8080" for all traffic.</span></span>
3. <span data-ttu-id="0fdd1-129">Usare il valore "direct://" speciale.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-129">By using the special "direct://" value.</span></span> <span data-ttu-id="0fdd1-130">Ad esempio, `--proxy-server="direct://"` stabilirà che tutte le connessioni non useranno un proxy.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-130">For example, `--proxy-server="direct://"` will make all connections not use a proxy.</span></span> 

>[!NOTE]
><span data-ttu-id="0fdd1-131">Puoi configurare Microsoft Edge per provare a usare un proxy e un'opzione di fallback per il passaggio diretto se il proxy non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-131">You can configure Microsoft Edge to try using a proxy and fallback to going direct if the proxy isn't available.</span></span> <span data-ttu-id="0fdd1-132">Ad esempio: `--proxy-server="http://proxy2:8080,direct://`.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-132">For example, `--proxy-server="http://proxy2:8080,direct://`.</span></span>

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

<span data-ttu-id="0fdd1-133">Indica a Microsoft Edge di ignorare qualsiasi proxy specificato per l'elenco di host separati da punto e virgola specificato.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-133">Tells Microsoft Edge to bypass any specified proxy for the specified semicolon-separated list of hosts.</span></span> <span data-ttu-id="0fdd1-134">Questo flag deve essere usato con `--proxy-server`.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-134">This flag must be used with `--proxy-server`.</span></span>

>[!NOTE]
><span data-ttu-id="0fdd1-135">La corrispondenza del dominio finale non richiede separatori "." e quindi "\*microsoft.com" corrisponderà a "imicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="0fdd1-135">Trailing-domain matching doesn't require "." separators, "\*microsoft.com" will match "imicrosoft.com".</span></span> <span data-ttu-id="0fdd1-136">Ad esempio, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` userà il server proxy "proxy2" sulla porta 8080 per tutti gli host ad eccezione delle richieste per \*.microsoft.com, example.com e 127.0.0.1 sulla porta 8080.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-136">For example, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` will use the proxy server "proxy2" on port 8080 for all hosts except requests for \*.microsoft.com, example.com, and 127.0.0.1 on port 8080.</span></span> <span data-ttu-id="0fdd1-137">Nell'esempio precedente, le richieste di imicrosoft.com verranno ancora inoltrate tramite proxy.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-137">In the previous example, imicrosoft.com requests will still be proxied.</span></span> <span data-ttu-id="0fdd1-138">Tuttavia, le richieste iexample.com ignorano il proxy perché è stato specificato \*example.com anziché \*.example.com.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-138">However, iexample.com requests will bypass the proxy because \*example.com was specified instead of \*.example.com.</span></span>

**`--proxy-pac-url=<pac-file-url>`**

<span data-ttu-id="0fdd1-139">Indica a Microsoft Edge di usare il file PAC nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-139">Tells Microsoft Edge to use the PAC file at the specified URL.</span></span> <span data-ttu-id="0fdd1-140">Ad esempio, `--proxy-pac-url="https://wpad/proxy.pac"` indica a Microsoft Edge di risolvere le informazioni proxy per le richieste URL usando il file **proxy.pac**.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-140">For example, `--proxy-pac-url="https://wpad/proxy.pac"` tells Microsoft Edge to resolve proxy information for URL requests using the **proxy.pac** file.</span></span>

## <span data-ttu-id="0fdd1-141">Licenza dei contenuti</span><span class="sxs-lookup"><span data-stu-id="0fdd1-141">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="0fdd1-142">Parti di questa pagina sono modifiche basate sul lavoro creato e condiviso da Chromium.org e usate in base ai termini descritti nella [licenza Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="0fdd1-142">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="0fdd1-143">La pagina originale è disponibile [qui](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span><span class="sxs-lookup"><span data-stu-id="0fdd1-143">The original page can be found [here](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="0fdd1-144">Questo lavoro è concesso in licenza in base a una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">licenza Creative Commons Attribution 4.0 International</a>.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-144">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="0fdd1-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fdd1-145">See also</span></span>

- <span data-ttu-id="0fdd1-146">Per visualizzare le impostazioni di configurazione avanzate e le opzioni aggiuntive, vedi la [documentazione del proxy](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) nel progetto open source Chromium.</span><span class="sxs-lookup"><span data-stu-id="0fdd1-146">To see advanced configuration settings and additional options, consult the [proxy documentation](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) in the Chromium Open Source project.</span></span>
- [<span data-ttu-id="0fdd1-147">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="0fdd1-147">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
