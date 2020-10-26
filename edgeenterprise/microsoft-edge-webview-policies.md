---
title: Documentazione sui criteri di Microsoft Edge WebView2
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 10/16/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione di Windows e Mac per tutti i criteri supportati dal browser Microsoft Edge
ms.openlocfilehash: 4298b25f7f158bc54f798442b4426494f046fa68
ms.sourcegitcommit: 7d160257010f75b86b89c8802d0dd27f1f8761ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134445"
---
# <span data-ttu-id="e4cc4-103">Criteri: Microsoft Edge WebView2</span><span class="sxs-lookup"><span data-stu-id="e4cc4-103">Microsoft Edge WebView2 - Policies</span></span>

<span data-ttu-id="e4cc4-104">La versione più recente di Microsoft Edge WebView2 include i criteri riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-104">The latest version of Microsoft Edge WebView2 includes the following policies.</span></span> <span data-ttu-id="e4cc4-105">È possibile usare questi criteri per configurare la modalità di esecuzione di Microsoft Edge WebView2 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-105">You can use these policies to configure how Microsoft Edge WebView2 runs in your organization.</span></span>

<span data-ttu-id="e4cc4-106">Sono disponibili informazioni su un set aggiuntivo di criteri usati per controllare come e quando viene aggiornato Microsoft Edge WebView2 nell'articolo [Informazioni di riferimento sui criteri dell'aggiornamento di Microsoft Edge](microsoft-edge-update-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4cc4-106">For information about an additional set of policies used to control how and when Microsoft Edge WebView2 is updated, check out [Microsoft Edge update policy reference](microsoft-edge-update-policies.md).</span></span>


> [!NOTE]
> <span data-ttu-id="e4cc4-107">Questo articolo si applica a Microsoft Edge versione 87 o successiva.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-107">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="e4cc4-108">Criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="e4cc4-108">Available policies</span></span>

<span data-ttu-id="e4cc4-109">In queste tabelle sono elencati tutti i criteri di gruppo disponibili in questa versione di Microsoft Edge WebView2.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-109">These tables list all of the group policies available in this release of Microsoft Edge WebView2.</span></span> <span data-ttu-id="e4cc4-110">Usa i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-110">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="e4cc4-111">Impostazioni di override del caricatore</span><span class="sxs-lookup"><span data-stu-id="e4cc4-111">Loader Override Settings</span></span>](#loader-override-settings)|

### [*<span data-ttu-id="e4cc4-112">Impostazioni di override del caricatore</span><span class="sxs-lookup"><span data-stu-id="e4cc4-112">Loader Override Settings</span></span>*](#loader-override-settings-policies)

|<span data-ttu-id="e4cc4-113">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-113">Policy Name</span></span>|<span data-ttu-id="e4cc4-114">Didascalia</span><span class="sxs-lookup"><span data-stu-id="e4cc4-114">Caption</span></span>|
|-|-|
|[<span data-ttu-id="e4cc4-115">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="e4cc4-115">browserExecutableFolder</span></span>](#browserexecutablefolder)|<span data-ttu-id="e4cc4-116">Configura il percorso della cartella eseguibile del browser</span><span class="sxs-lookup"><span data-stu-id="e4cc4-116">Configure the location of the browser executable folder</span></span>|
|[<span data-ttu-id="e4cc4-117">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="e4cc4-117">releaseChannelPreference</span></span>](#releasechannelpreference)|<span data-ttu-id="e4cc4-118">Imposta la preferenza dell'ordine di ricerca del canale di rilascio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-118">Set the release channel search order preference</span></span>|




  ## <span data-ttu-id="e4cc4-119">Criteri delle impostazioni di override del caricatore</span><span class="sxs-lookup"><span data-stu-id="e4cc4-119">Loader Override Settings policies</span></span>

  [<span data-ttu-id="e4cc4-120">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-120">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="e4cc4-121">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="e4cc4-121">browserExecutableFolder</span></span>

  #### <span data-ttu-id="e4cc4-122">Configura il percorso della cartella eseguibile del browser</span><span class="sxs-lookup"><span data-stu-id="e4cc4-122">Configure the location of the browser executable folder</span></span>

  
  
  #### <span data-ttu-id="e4cc4-123">Versioni supportate:</span><span class="sxs-lookup"><span data-stu-id="e4cc4-123">Supported versions:</span></span>

  - <span data-ttu-id="e4cc4-124">In Windows dalla versione 87 o successive</span><span class="sxs-lookup"><span data-stu-id="e4cc4-124">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="e4cc4-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4cc4-125">Description</span></span>

  <span data-ttu-id="e4cc4-126">Questo criterio configura le applicazioni WebView2 per l’uso di WebView2 Runtime nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-126">This policy configures WebView2 applications to use the WebView2 Runtime in the specified path.</span></span> <span data-ttu-id="e4cc4-127">La cartella deve contenere i file seguenti: msedgewebview2.exe, msedge.dll, and così via.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-127">The folder should contain the following files: msedgewebview2.exe, msedge.dll, and so on.</span></span>

<span data-ttu-id="e4cc4-128">Per impostare il valore per il percorso della cartella, specifica il Nome del valore e la Coppia valori.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-128">To set the value for the folder path, provide a Value name and Value pair.</span></span> <span data-ttu-id="e4cc4-129">Imposta il nome del valore sull'ID modello utente dell'applicazione o sul nome del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-129">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="e4cc4-130">È possibile usare il carattere jolly "\*" come nome del valore da applicare a tutte le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-130">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="e4cc4-131">Funzionalità supportate:</span><span class="sxs-lookup"><span data-stu-id="e4cc4-131">Supported features:</span></span>

  - <span data-ttu-id="e4cc4-132">Può essere obbligatorio: sì</span><span class="sxs-lookup"><span data-stu-id="e4cc4-132">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="e4cc4-133">Può essere consigliato: no</span><span class="sxs-lookup"><span data-stu-id="e4cc4-133">Can be recommended: No</span></span>
  - <span data-ttu-id="e4cc4-134">Aggiornamento dei criteri dinamici: sì</span><span class="sxs-lookup"><span data-stu-id="e4cc4-134">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="e4cc4-135">Tipo:</span><span class="sxs-lookup"><span data-stu-id="e4cc4-135">Data Type:</span></span>

  - <span data-ttu-id="e4cc4-136">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="e4cc4-136">List of strings</span></span>

  #### <span data-ttu-id="e4cc4-137">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="e4cc4-137">Windows information and settings</span></span>

  ##### <span data-ttu-id="e4cc4-138">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="e4cc4-138">Group Policy (ADMX) info</span></span>

  - <span data-ttu-id="e4cc4-139">Nome Criteri di gruppo univoco: browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="e4cc4-139">GP unique name: browserExecutableFolder</span></span>
  - <span data-ttu-id="e4cc4-140">Nome Criteri di gruppo: configura il percorso della cartella eseguibile del browser</span><span class="sxs-lookup"><span data-stu-id="e4cc4-140">GP name: Configure the location of the browser executable folder</span></span>
  - <span data-ttu-id="e4cc4-141">Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge WebView2/Impostazioni di override del caricatore</span><span class="sxs-lookup"><span data-stu-id="e4cc4-141">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="e4cc4-142">Percorso Criteri di gruppo (consigliato): N/D</span><span class="sxs-lookup"><span data-stu-id="e4cc4-142">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="e4cc4-143">Nome file ADMX Criteri di gruppo: MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="e4cc4-143">GP ADMX file name: MSEdgeWebView2.admx</span></span>

  ##### <span data-ttu-id="e4cc4-144">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="e4cc4-144">Windows Registry Settings</span></span>

  - <span data-ttu-id="e4cc4-145">Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebView2\browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="e4cc4-145">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder</span></span>
  - <span data-ttu-id="e4cc4-146">Percorso (consigliato): N/D</span><span class="sxs-lookup"><span data-stu-id="e4cc4-146">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="e4cc4-147">Nome valore: elenco di REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e4cc4-147">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="e4cc4-148">Tipo valore: elenco di REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e4cc4-148">Value Type: list of REG_SZ</span></span>

  ##### <span data-ttu-id="e4cc4-149">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-149">Example value:</span></span>

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [<span data-ttu-id="e4cc4-150">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-150">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="e4cc4-151">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="e4cc4-151">releaseChannelPreference</span></span>

  #### <span data-ttu-id="e4cc4-152">Imposta la preferenza dell'ordine di ricerca del canale di rilascio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-152">Set the release channel search order preference</span></span>

  
  
  #### <span data-ttu-id="e4cc4-153">Versioni supportate:</span><span class="sxs-lookup"><span data-stu-id="e4cc4-153">Supported versions:</span></span>

  - <span data-ttu-id="e4cc4-154">In Windows dalla versione 87 o successive</span><span class="sxs-lookup"><span data-stu-id="e4cc4-154">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="e4cc4-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4cc4-155">Description</span></span>

  <span data-ttu-id="e4cc4-156">L'ordine di ricerca del canale predefinito è WebView2 Runtime, Beta, Dev, and Canary.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-156">The default channel search order is WebView2 Runtime, Beta, Dev, and Canary.</span></span>

<span data-ttu-id="e4cc4-157">Per invertire l'ordine di ricerca predefinito, imposta questo criterio su 1.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-157">To reverse the default search order, set this policy to 1.</span></span>

<span data-ttu-id="e4cc4-158">Per impostare il valore per la preferenza del canale di rilascio, specifica il Nome del valore e la Coppia valori.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-158">To set the value for the release channel preference, provide a Value name and Value pair.</span></span> <span data-ttu-id="e4cc4-159">Imposta il nome del valore sull'ID modello utente dell'applicazione o sul nome del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-159">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="e4cc4-160">È possibile usare il carattere jolly "\*" come nome del valore da applicare a tutte le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e4cc4-160">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="e4cc4-161">Funzionalità supportate:</span><span class="sxs-lookup"><span data-stu-id="e4cc4-161">Supported features:</span></span>

  - <span data-ttu-id="e4cc4-162">Può essere obbligatorio: sì</span><span class="sxs-lookup"><span data-stu-id="e4cc4-162">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="e4cc4-163">Può essere consigliato: no</span><span class="sxs-lookup"><span data-stu-id="e4cc4-163">Can be recommended: No</span></span>
  - <span data-ttu-id="e4cc4-164">Aggiornamento dei criteri dinamici: sì</span><span class="sxs-lookup"><span data-stu-id="e4cc4-164">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="e4cc4-165">Tipo:</span><span class="sxs-lookup"><span data-stu-id="e4cc4-165">Data Type:</span></span>

  - <span data-ttu-id="e4cc4-166">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="e4cc4-166">List of strings</span></span>

  #### <span data-ttu-id="e4cc4-167">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="e4cc4-167">Windows information and settings</span></span>

  ##### <span data-ttu-id="e4cc4-168">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="e4cc4-168">Group Policy (ADMX) info</span></span>

  - <span data-ttu-id="e4cc4-169">Nome Criteri di gruppo univoco: releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="e4cc4-169">GP unique name: releaseChannelPreference</span></span>
  - <span data-ttu-id="e4cc4-170">Nome Criteri di gruppo: imposta la preferenza dell'ordine di ricerca del canale di rilascio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-170">GP name: Set the release channel search order preference</span></span>
  - <span data-ttu-id="e4cc4-171">Percorso Criteri di gruppo (obbligatorio): Modelli amministrativi/Microsoft Edge WebView2/Impostazioni di override del caricatore</span><span class="sxs-lookup"><span data-stu-id="e4cc4-171">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="e4cc4-172">Percorso Criteri di gruppo (consigliato): N/D</span><span class="sxs-lookup"><span data-stu-id="e4cc4-172">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="e4cc4-173">Nome file ADMX Criteri di gruppo: MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="e4cc4-173">GP ADMX file name: MSEdgeWebView2.admx</span></span>

  ##### <span data-ttu-id="e4cc4-174">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="e4cc4-174">Windows Registry Settings</span></span>

  - <span data-ttu-id="e4cc4-175">Percorso (obbligatorio): SOFTWARE\Criteri\Microsoft\Edge\WebView2\releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="e4cc4-175">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference</span></span>
  - <span data-ttu-id="e4cc4-176">Percorso (consigliato): N/D</span><span class="sxs-lookup"><span data-stu-id="e4cc4-176">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="e4cc4-177">Nome valore: elenco di REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e4cc4-177">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="e4cc4-178">Tipo valore: elenco di REG_SZ</span><span class="sxs-lookup"><span data-stu-id="e4cc4-178">Value Type: list of REG_SZ</span></span>

  ##### <span data-ttu-id="e4cc4-179">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-179">Example value:</span></span>

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference = "Name: *, Value: 1"

```

  

  [<span data-ttu-id="e4cc4-180">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="e4cc4-180">Back to top</span></span>](#microsoft-edge-webview2---policies)


## <span data-ttu-id="e4cc4-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4cc4-181">See also</span></span>

- [<span data-ttu-id="e4cc4-182">Configurazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e4cc4-182">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="e4cc4-183">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="e4cc4-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="e4cc4-184">Blog sulle basi di riferimento della sicurezza di Microsoft</span><span class="sxs-lookup"><span data-stu-id="e4cc4-184">Microsoft Security Baselines Blog</span></span>](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)