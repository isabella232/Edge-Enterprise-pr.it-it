---
title: Documentazione sui criteri di Microsoft Edge Update
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 06/10/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione per tutti i criteri supportati da Microsoft Edge Update
ms.openlocfilehash: d772d8dd6f60b89e9bd12a77b740e5fad699756a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980242"
---
# <span data-ttu-id="773b8-103">Microsoft Edge - Criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="773b8-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="773b8-104">La versione più recente di Microsoft Edge include i seguenti criteri che puoi usare per controllare come e quando Microsoft Edge viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="773b8-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

           
<span data-ttu-id="773b8-105">Per informazioni su altri criteri disponibili in Microsoft Edge, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="773b8-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="773b8-106">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="773b8-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="773b8-107">Criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="773b8-107">Available policies</span></span>
<span data-ttu-id="773b8-108">In queste tabelle sono elencati tutti i criteri di gruppo correlati agli aggiornamenti disponibili in questa versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="773b8-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="773b8-109">Usa i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="773b8-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="773b8-110">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-110">Applications</span></span>](#applications)|[<span data-ttu-id="773b8-111">Preferenze</span><span class="sxs-lookup"><span data-stu-id="773b8-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="773b8-112">Server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-112">Proxy Server</span></span>](#proxy-server)||

### [<span data-ttu-id="773b8-113">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-113">Applications</span></span>](#applications-policies)
|<span data-ttu-id="773b8-114">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="773b8-114">Policy Name</span></span>|<span data-ttu-id="773b8-115">Didascalia</span><span class="sxs-lookup"><span data-stu-id="773b8-115">Caption</span></span>|
|-|-|
|[<span data-ttu-id="773b8-116">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-116">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="773b8-117">Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-117">Allow installation default</span></span>|
|[<span data-ttu-id="773b8-118">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-118">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="773b8-119">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-119">Update policy override default</span></span>|
|[<span data-ttu-id="773b8-120">Installazione</span><span class="sxs-lookup"><span data-stu-id="773b8-120">Install</span></span>](#install)|<span data-ttu-id="773b8-121">Consenti installazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="773b8-121">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="773b8-122">Update</span><span class="sxs-lookup"><span data-stu-id="773b8-122">Update</span></span>](#update)|<span data-ttu-id="773b8-123">Sostituzione dei criteri di aggiornamento (per canale)</span><span class="sxs-lookup"><span data-stu-id="773b8-123">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="773b8-124">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="773b8-124">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="773b8-125">Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="773b8-125">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="773b8-126">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-126">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="773b8-127">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-127">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="773b8-128">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="773b8-128">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="773b8-129">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="773b8-129">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="773b8-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="773b8-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="773b8-131">Sostituzione della versione di destinazione (in base al canale)</span><span class="sxs-lookup"><span data-stu-id="773b8-131">Target version override (per channel)</span></span>|

### [<span data-ttu-id="773b8-132">Preferenze</span><span class="sxs-lookup"><span data-stu-id="773b8-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="773b8-133">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="773b8-133">Policy Name</span></span>|<span data-ttu-id="773b8-134">Didascalia</span><span class="sxs-lookup"><span data-stu-id="773b8-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="773b8-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="773b8-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="773b8-136">Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="773b8-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="773b8-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="773b8-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="773b8-138">Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="773b8-138">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="773b8-139">Server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="773b8-140">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="773b8-140">Policy Name</span></span>|<span data-ttu-id="773b8-141">Didascalia</span><span class="sxs-lookup"><span data-stu-id="773b8-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="773b8-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="773b8-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="773b8-143">Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="773b8-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="773b8-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="773b8-145">URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="773b8-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="773b8-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="773b8-147">Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-147">Address or URL of proxy server</span></span>|

                 
      
  
             
            
                  

## <span data-ttu-id="773b8-148">Criteri delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-148">Applications policies</span></span>

[<span data-ttu-id="773b8-149">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-149">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="773b8-150">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-150">InstallDefault</span></span>
#### <span data-ttu-id="773b8-151">Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-151">Allow installation default</span></span>
><span data-ttu-id="773b8-152">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-152">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="773b8-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-153">Description</span></span>
<span data-ttu-id="773b8-154">È possibile specificare il comportamento predefinito di tutti i canali per consentire o bloccare gli aggiornamenti di Microsoft Edge mentre Microsoft Edge Update è in uso.</span><span class="sxs-lookup"><span data-stu-id="773b8-154">You can specify the default behavior of all channels to allow or block Microsoft Edge updates when Microsoft Edge Update is used.</span></span>

<span data-ttu-id="773b8-155">È possibile sostituire il criterio per i singoli canali abilitando il criterio "[Consenti installazione](#install)" per i canali specifici.</span><span class="sxs-lookup"><span data-stu-id="773b8-155">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="773b8-156">Disabilitando questo criterio, l'installazione di Microsoft Edge tramite Microsoft Edge Update verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="773b8-156">If you disable this policy, the installation of Microsoft Edge through Microsoft Edge Update is blocked.</span></span> <span data-ttu-id="773b8-157">Questa operazione interessa l'installazione del software Microsoft Edge solamente quando gli utenti eseguono Microsoft Edge Update e quando non è stato configurato il criterio "[Consenti installazione](#install)".</span><span class="sxs-lookup"><span data-stu-id="773b8-157">This only affects the installation of Microsoft Edge software only when users are running Microsoft Edge Update and when they haven't configured the '[Allow installation](#install)' policy.</span></span>

<span data-ttu-id="773b8-158">Questo criterio non impedisce l'esecuzione di Microsoft Edge Update, né impedisce l'installazione del software Microsoft Edge attraverso altri metodi.</span><span class="sxs-lookup"><span data-stu-id="773b8-158">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>
#### <span data-ttu-id="773b8-159">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-159">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-160">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-160">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-161">Nome univoco Criteri di gruppo: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-161">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="773b8-162">Nome Criteri di gruppo: Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-162">GP name: Allow installation default</span></span>
- <span data-ttu-id="773b8-163">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-163">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="773b8-164">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-164">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-165">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-165">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-166">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-166">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-167">Nome valore: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-167">Value Name: InstallDefault</span></span>
- <span data-ttu-id="773b8-168">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-168">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-169">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-169">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="773b8-170">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-170">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-171">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-171">UpdateDefault</span></span>
#### <span data-ttu-id="773b8-172">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-172">Update policy override default</span></span>
><span data-ttu-id="773b8-173">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-173">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="773b8-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-174">Description</span></span>
<span data-ttu-id="773b8-175">Consente di specificare il comportamento predefinito per tutti i canali in relazione al modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="773b8-175">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="773b8-176">Può essere sostituito per singoli canali specificando il criterio "[Sostituzione dei criteri di aggiornamento](#update)" per i canali specifici.</span><span class="sxs-lookup"><span data-stu-id="773b8-176">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="773b8-177">Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="773b8-177">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="773b8-178">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.</span><span class="sxs-lookup"><span data-stu-id="773b8-178">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="773b8-179">Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.</span><span class="sxs-lookup"><span data-stu-id="773b8-179">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="773b8-180">Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="773b8-180">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="773b8-181">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.</span><span class="sxs-lookup"><span data-stu-id="773b8-181">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="773b8-182">Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="773b8-182">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="773b8-183">Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="773b8-183">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="773b8-184">Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento](#update)".</span><span class="sxs-lookup"><span data-stu-id="773b8-184">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>
#### <span data-ttu-id="773b8-185">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-185">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-186">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-186">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-187">Nome univoco Criteri di gruppo: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-187">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="773b8-188">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-188">GP name: Update policy override default</span></span>
- <span data-ttu-id="773b8-189">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-189">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="773b8-190">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-190">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-191">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-191">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-192">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-192">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-193">Nome valore: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-193">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="773b8-194">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-194">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-195">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-195">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="773b8-196">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-196">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-197">Install</span><span class="sxs-lookup"><span data-stu-id="773b8-197">Install</span></span>
#### <span data-ttu-id="773b8-198">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="773b8-198">Allow installation</span></span>
><span data-ttu-id="773b8-199">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-199">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="773b8-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-200">Description</span></span>
<span data-ttu-id="773b8-201">Specifica se è possibile installare un canale Microsoft Edge tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-201">Specifies whether a Microsoft Edge channel can be installed using Microsoft Edge Update.</span></span>

  <span data-ttu-id="773b8-202">Se abiliti questo criterio per un canale, gli utenti possono installare tale canale di Microsoft Edge tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-202">If you enable this policy for a channel, users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="773b8-203">Se disabiliti questo criterio per un canale, gli utenti non possono installare tale canale di Microsoft Edge tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-203">If you disable this policy for a channel, users cannot install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="773b8-204">Se non configuri questo criterio per un canale, il criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare il canale di Microsoft Edge tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-204">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="773b8-205">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-205">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-206">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-206">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-207">Nome univoco Criteri di gruppo: Install</span><span class="sxs-lookup"><span data-stu-id="773b8-207">GP unique name: Install</span></span>
- <span data-ttu-id="773b8-208">Nome Criteri di gruppo: Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="773b8-208">GP name: Allow installation</span></span>
- <span data-ttu-id="773b8-209">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="773b8-209">GP path:</span></span> 
  - <span data-ttu-id="773b8-210">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="773b8-210">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="773b8-211">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="773b8-211">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="773b8-212">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="773b8-212">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="773b8-213">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="773b8-213">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="773b8-214">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-214">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-215">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-215">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-216">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-216">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-217">Nome valore:</span><span class="sxs-lookup"><span data-stu-id="773b8-217">Value Name:</span></span> 
  - <span data-ttu-id="773b8-218">(Stabile): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="773b8-218">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="773b8-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="773b8-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="773b8-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="773b8-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="773b8-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="773b8-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="773b8-222">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-222">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-223">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-223">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="773b8-224">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-224">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-225">Update</span><span class="sxs-lookup"><span data-stu-id="773b8-225">Update</span></span>
#### <span data-ttu-id="773b8-226">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="773b8-226">Update policy override</span></span>
><span data-ttu-id="773b8-227">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-227">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="773b8-228">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-228">Description</span></span>
<span data-ttu-id="773b8-229">Specifica il modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili da Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="773b8-229">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

  <span data-ttu-id="773b8-230">Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="773b8-230">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="773b8-231">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.</span><span class="sxs-lookup"><span data-stu-id="773b8-231">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="773b8-232">Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.</span><span class="sxs-lookup"><span data-stu-id="773b8-232">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="773b8-233">Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="773b8-233">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="773b8-234">Non tutte le app forniscono un'interfaccia per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="773b8-234">(Not all apps provide an interface for this option.)</span></span>
   - <span data-ttu-id="773b8-235">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.</span><span class="sxs-lookup"><span data-stu-id="773b8-235">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="773b8-236">Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="773b8-236">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="773b8-237">Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="773b8-237">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="773b8-238">Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento predefinita](#updatedefault)".</span><span class="sxs-lookup"><span data-stu-id="773b8-238">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>
#### <span data-ttu-id="773b8-239">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-239">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-240">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-240">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-241">Nome univoco Criteri di gruppo: Update</span><span class="sxs-lookup"><span data-stu-id="773b8-241">GP unique name: Update</span></span>
- <span data-ttu-id="773b8-242">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="773b8-242">GP name: Update policy override</span></span>
- <span data-ttu-id="773b8-243">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="773b8-243">GP path:</span></span> 
  - <span data-ttu-id="773b8-244">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="773b8-244">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="773b8-245">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="773b8-245">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="773b8-246">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="773b8-246">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="773b8-247">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="773b8-247">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="773b8-248">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-248">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-249">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-249">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-250">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-250">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-251">Nome:</span><span class="sxs-lookup"><span data-stu-id="773b8-251">Value Name:</span></span> 
  - <span data-ttu-id="773b8-252">(Stabile): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="773b8-252">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="773b8-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="773b8-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="773b8-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="773b8-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="773b8-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="773b8-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="773b8-256">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-256">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-257">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-257">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="773b8-258">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-258">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-259">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="773b8-259">Allowsxs</span></span>
#### <span data-ttu-id="773b8-260">Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="773b8-260">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="773b8-261">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-261">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="773b8-262">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-262">Description</span></span>
<span data-ttu-id="773b8-263">Questo criterio consente a un utente di eseguire Microsoft Edge (Edge HTML) e Microsoft Edge (basato su Chromium) in modalità affiancata.</span><span class="sxs-lookup"><span data-stu-id="773b8-263">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="773b8-264">Se questo criterio è impostato su "Non configurato", Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="773b8-264">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="773b8-265">Si tratta dello stesso comportamento correlato all'impostazione "Disabilitato".</span><span class="sxs-lookup"><span data-stu-id="773b8-265">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="773b8-266">L'impostazione "Disabilitato" blocca un'esperienza affiancata e Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="773b8-266">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="773b8-267">Si tratta dello stesso comportamento correlato all'impostazione "Non configurato".</span><span class="sxs-lookup"><span data-stu-id="773b8-267">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="773b8-268">Quando l'impostazione di questo criterio è "Abilitato", è possibile eseguire in modalità affiancata Microsoft Edge (basato su Chromium) e Microsoft Edge (Edge HTML) dopo l'installazione di Microsoft Edge (basato su Chromium).</span><span class="sxs-lookup"><span data-stu-id="773b8-268">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="773b8-269">Affinché questi criteri di gruppo abbiano effetto, è necessario configurarli prima dell'installazione automatica di Microsoft Edge (basato su Chromium) da Windows Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-269">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="773b8-270">Nota: un utente può bloccare l'aggiornamento automatico di Microsoft Edge (basato su Chromium) usando Blocker Toolkit di Microsoft Edge (basato su Chromium).</span><span class="sxs-lookup"><span data-stu-id="773b8-270">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="773b8-271">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-271">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-272">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-272">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-273">Nome univoco Criteri di gruppo: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="773b8-273">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="773b8-274">Nome Criteri di gruppo: Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="773b8-274">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="773b8-275">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-275">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="773b8-276">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-276">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-277">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-277">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-278">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-278">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-279">Nome valore:Allowsxs</span><span class="sxs-lookup"><span data-stu-id="773b8-279">Value Name: Allowsxs</span></span>
- <span data-ttu-id="773b8-280">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-280">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-281">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-281">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="773b8-282">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-282">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-283">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-283">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="773b8-284">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-284">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="773b8-285">Microsoft Edge Update 1.3.128.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-285">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="773b8-286">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-286">Description</span></span>
<span data-ttu-id="773b8-287">Consente di specificare il comportamento predefinito per tutti i canali per la creazione di un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="773b8-287">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="773b8-288">Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="773b8-288">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="773b8-289">Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="773b8-289">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="773b8-290">Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="773b8-290">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="773b8-291">Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="773b8-291">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="773b8-292">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-292">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-293">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-293">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-294">Nome univoco Criteri di gruppo: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-294">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="773b8-295">Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="773b8-295">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="773b8-296">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="773b8-296">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="773b8-297">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-297">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-298">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-298">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-299">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-299">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-300">Nome valore: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="773b8-300">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="773b8-301">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-301">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-302">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-302">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="773b8-303">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-303">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-304">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="773b8-304">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="773b8-305">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione</span><span class="sxs-lookup"><span data-stu-id="773b8-305">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="773b8-306">Microsoft Edge Update 1.3.128.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-306">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="773b8-307">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-307">Description</span></span>
<span data-ttu-id="773b8-308">Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="773b8-308">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="773b8-309">Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="773b8-309">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="773b8-310">Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="773b8-310">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="773b8-311">Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="773b8-311">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="773b8-312">Se questo criterio non viene configurato per un canale, la configurazione del criterio "[Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita](#createdesktopshortcutdefault)" determina la creazione del collegamento quando Microsoft Edge viene installato.</span><span class="sxs-lookup"><span data-stu-id="773b8-312">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="773b8-313">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-313">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-314">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-314">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-315">Nome univoco Criteri di gruppo: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="773b8-315">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="773b8-316">Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop dopo l'installazione</span><span class="sxs-lookup"><span data-stu-id="773b8-316">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="773b8-317">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="773b8-317">GP path:</span></span> 
  - <span data-ttu-id="773b8-318">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="773b8-318">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="773b8-319">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="773b8-319">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="773b8-320">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="773b8-320">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="773b8-321">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="773b8-321">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="773b8-322">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-322">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-323">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-323">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-324">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-324">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-325">Nome:</span><span class="sxs-lookup"><span data-stu-id="773b8-325">Value Name:</span></span> 
  - <span data-ttu-id="773b8-326">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="773b8-326">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="773b8-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="773b8-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="773b8-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="773b8-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="773b8-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="773b8-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="773b8-330">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-330">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-331">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-331">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="773b8-332">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-332">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-333">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="773b8-333">TargetVersionPrefix</span></span>
#### <span data-ttu-id="773b8-334">Sostituzione della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="773b8-334">Target version override</span></span>
><span data-ttu-id="773b8-335">Microsoft Edge Update 1.3.119.43 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-335">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="773b8-336">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-336">Description</span></span>
<span data-ttu-id="773b8-337">Abilitando questo criterio e l'aggiornamento automatico, Microsoft Edge verrà aggiornato alla versione specificata da questo valore criterio.</span><span class="sxs-lookup"><span data-stu-id="773b8-337">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="773b8-338">Il valore del criterio deve essere una specifica versione di Microsoft Edge, ad esempio: 83.0.499.12.</span><span class="sxs-lookup"><span data-stu-id="773b8-338">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="773b8-339">Se sul dispositivo è installata una versione più recente di Microsoft Edge del valore specificato, Edge manterrà la versione più recente e non eseguirà il downgrade alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="773b8-339">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="773b8-340">In caso la versione specificata non esista o non sia formattata correttamente, Microsoft Edge manterrà la versione attuale e non verrà aggiornato automaticamente alle versioni future.</span><span class="sxs-lookup"><span data-stu-id="773b8-340">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>
#### <span data-ttu-id="773b8-341">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-341">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-342">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-342">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-343">Nome univoco Criteri di gruppo: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="773b8-343">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="773b8-344">Nome Criteri di gruppo: Sostituzione della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="773b8-344">GP name: Target version override</span></span>
- <span data-ttu-id="773b8-345">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="773b8-345">GP path:</span></span> 
  - <span data-ttu-id="773b8-346">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="773b8-346">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="773b8-347">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="773b8-347">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="773b8-348">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="773b8-348">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="773b8-349">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="773b8-349">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="773b8-350">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-350">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-351">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-351">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-352">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-352">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-353">Nome:</span><span class="sxs-lookup"><span data-stu-id="773b8-353">Value Name:</span></span> 
  - <span data-ttu-id="773b8-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="773b8-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="773b8-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="773b8-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="773b8-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="773b8-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="773b8-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="773b8-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="773b8-358">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="773b8-358">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="773b8-359">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-359">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="773b8-360">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-360">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="773b8-361">Criteri delle preferenze</span><span class="sxs-lookup"><span data-stu-id="773b8-361">Preferences policies</span></span>

[<span data-ttu-id="773b8-362">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-362">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="773b8-363">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="773b8-363">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="773b8-364">Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="773b8-364">Auto-update check period override</span></span>
><span data-ttu-id="773b8-365">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-365">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="773b8-366">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-366">Description</span></span>
<span data-ttu-id="773b8-367">Se abilitata, questo criterio consente di impostare un valore per il numero minimo di minuti che devono intercorrere tra i controlli dell'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="773b8-367">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="773b8-368">In caso contrario, per impostazione predefinita, l'aggiornamento automatico verifica la disponibilità degli aggiornamenti ogni 10 ore.</span><span class="sxs-lookup"><span data-stu-id="773b8-368">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="773b8-369">Se desideri disabilitare tutti i controlli dell'aggiornamento automatico, imposta il valore su 0 (scelta non consigliata).</span><span class="sxs-lookup"><span data-stu-id="773b8-369">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="773b8-370">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-370">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-371">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-371">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-372">Nome univoco Criteri di gruppo: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="773b8-372">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="773b8-373">Nome Criteri di gruppo: Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="773b8-373">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="773b8-374">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze</span><span class="sxs-lookup"><span data-stu-id="773b8-374">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="773b8-375">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-375">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-376">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-376">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-377">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-378">Nome valore: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="773b8-378">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="773b8-379">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-379">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-380">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-380">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="773b8-381">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-381">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-382">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="773b8-382">UpdatesSuppressed</span></span>
#### <span data-ttu-id="773b8-383">Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="773b8-383">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="773b8-384">Microsoft Edge Update 1.3.33.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-384">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="773b8-385">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-385">Description</span></span>
<span data-ttu-id="773b8-386">Se abiliti questo criterio, i controlli degli aggiornamenti vengono soppressi ogni giorno a partire dall'ora e dal minuto specificati per un periodo stabilito (in minuti).</span><span class="sxs-lookup"><span data-stu-id="773b8-386">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="773b8-387">La durata non è influenzata dall'ora legale.</span><span class="sxs-lookup"><span data-stu-id="773b8-387">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="773b8-388">Ad esempio, se l'ora di inizio è 22.00 e la durata è 480 minuti, gli aggiornamenti verranno soppressi per esattamente 8 ore, indipendentemente dal fatto che l'ora legale venga avviata o termini durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="773b8-388">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="773b8-389">Se disabiliti o non configuri questo criterio, i controlli degli aggiornamenti non vengono soppressi durante alcun periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="773b8-389">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="773b8-390">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-390">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-391">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-391">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-392">Nome univoco Criteri di gruppo: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="773b8-392">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="773b8-393">Nome Criteri di gruppo: Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="773b8-393">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="773b8-394">Opzioni { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="773b8-394">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="773b8-395">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze</span><span class="sxs-lookup"><span data-stu-id="773b8-395">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="773b8-396">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-396">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-397">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-397">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-398">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-398">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-399">Nome:</span><span class="sxs-lookup"><span data-stu-id="773b8-399">Value Name:</span></span> 
  - <span data-ttu-id="773b8-400">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="773b8-400">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="773b8-401">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="773b8-401">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="773b8-402">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="773b8-402">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="773b8-403">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="773b8-403">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="773b8-404">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-404">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="773b8-405">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-405">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="773b8-406">Criteri server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-406">Proxy Server policies</span></span>
  
  

[<span data-ttu-id="773b8-407">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-407">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="773b8-408">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="773b8-408">ProxyMode</span></span>
#### <span data-ttu-id="773b8-409">Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-409">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="773b8-410">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-410">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="773b8-411">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-411">Description</span></span>
<span data-ttu-id="773b8-412">Consente di specificare le impostazioni del server proxy usate da Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-412">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="773b8-413">Se abiliti questo criterio, puoi scegliere una delle opzioni relative al server proxy seguenti:</span><span class="sxs-lookup"><span data-stu-id="773b8-413">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="773b8-414">Se scegli di non usare mai un server proxy e ti connetti sempre direttamente, tutte le altre opzioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="773b8-414">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="773b8-415">Se scegli di usare le impostazioni del proxy di sistema o di rilevare automaticamente il server proxy, tutte le altre opzioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="773b8-415">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="773b8-416">Se scegli la modalità proxy server fisso, puoi specificare altre opzioni nel criterio "[Indirizzo o URL del server proxy](#proxyserver)".</span><span class="sxs-lookup"><span data-stu-id="773b8-416">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="773b8-417">Se scegli di usare uno script proxy PAC, devi specificare l'URL per lo script nel criterio "[URL di un file PAC del proxy](#proxypacurl)".</span><span class="sxs-lookup"><span data-stu-id="773b8-417">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="773b8-418">Se abiliti questo criterio, gli utenti dell'organizzazione non possono modificare le impostazioni proxy in Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-418">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="773b8-419">Se disabiliti o non configuri questo criterio, non vengono configurate impostazioni del server proxy, ma gli utenti dell'organizzazione possono scegliere le proprie impostazioni proxy per Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-419">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="773b8-420">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-420">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-421">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-421">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-422">Nome univoco Criteri di gruppo: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="773b8-422">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="773b8-423">Nome Criteri di gruppo: Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-423">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="773b8-424">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-424">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="773b8-425">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-425">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-426">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-426">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-427">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-427">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-428">Nome valore: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="773b8-428">Value Name: ProxyMode</span></span>
- <span data-ttu-id="773b8-429">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="773b8-429">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="773b8-430">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-430">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="773b8-431">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-431">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-432">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="773b8-432">ProxyPacUrl</span></span>
#### <span data-ttu-id="773b8-433">URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-433">URL to a proxy .pac file</span></span>
><span data-ttu-id="773b8-434">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-434">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="773b8-435">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-435">Description</span></span>
<span data-ttu-id="773b8-436">Consente di specificare un URL per un file di configurazione automatica del proxy (PAC).</span><span class="sxs-lookup"><span data-stu-id="773b8-436">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="773b8-437">Se abiliti questo criterio, puoi specificare un URL per un file PAC per automatizzare il modo in cui Microsoft Edge Update seleziona il server proxy appropriato per il recupero di un particolare sito Web.</span><span class="sxs-lookup"><span data-stu-id="773b8-437">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="773b8-438">Questo criterio viene applicato solo se sono state specificate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="773b8-438">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="773b8-439">Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="773b8-439">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="773b8-440">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-440">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-441">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-441">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-442">Nome univoco Criteri di gruppo: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="773b8-442">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="773b8-443">Nome Criteri di Gruppo: URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-443">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="773b8-444">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-444">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="773b8-445">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-445">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-446">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-446">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-447">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-447">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-448">Nome valore: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="773b8-448">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="773b8-449">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="773b8-449">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="773b8-450">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-450">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="773b8-451">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-451">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="773b8-452">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="773b8-452">ProxyServer</span></span>
#### <span data-ttu-id="773b8-453">Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-453">Address or URL of proxy server</span></span>
><span data-ttu-id="773b8-454">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="773b8-454">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="773b8-455">Descrizione</span><span class="sxs-lookup"><span data-stu-id="773b8-455">Description</span></span>
<span data-ttu-id="773b8-456">Consente di specificare l'URL del server proxy per l'uso da parte di Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="773b8-456">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="773b8-457">Se abiliti questo criterio, puoi impostare l'URL del server proxy usato da Microsoft Edge Update nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="773b8-457">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="773b8-458">Questo criterio viene applicato solo se sono state selezionate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="773b8-458">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="773b8-459">Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="773b8-459">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="773b8-460">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-460">Windows information and settings</span></span>
##### <span data-ttu-id="773b8-461">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="773b8-461">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="773b8-462">Nome univoco Criteri di gruppo: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="773b8-462">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="773b8-463">Nome Criteri di gruppo: Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-463">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="773b8-464">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="773b8-464">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="773b8-465">Nome file ADMX Criteri di gruppo: edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="773b8-465">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="773b8-466">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="773b8-466">Windows Registry Settings</span></span>
- <span data-ttu-id="773b8-467">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="773b8-467">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="773b8-468">Nome valore: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="773b8-468">Value Name: ProxyServer</span></span>
- <span data-ttu-id="773b8-469">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="773b8-469">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="773b8-470">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="773b8-470">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="773b8-471">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="773b8-471">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="773b8-472">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="773b8-472">See also</span></span>
  - [<span data-ttu-id="773b8-473">Configurazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="773b8-473">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="773b8-474">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="773b8-474">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
