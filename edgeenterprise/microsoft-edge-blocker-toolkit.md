---
title: Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge
ms.openlocfilehash: 7563d2c94cf91a8434328699e46c75dbcfb77561
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980285"
---
# <span data-ttu-id="49b84-103">Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge (basata su Chromium)</span><span class="sxs-lookup"><span data-stu-id="49b84-103">Blocker Toolkit to disable automatic delivery of Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="49b84-104">In questo articolo viene descritto Blocker Toolkit per disabilitare la distribuzione e l'installazione automatica di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="49b84-104">This article describes the Blocker Toolkit for disabling automatic delivery and installation of Microsoft Edge.</span></span> <span data-ttu-id="49b84-105">Questo articolo è stato aggiornato il **09/01/2020** con altre informazioni sui dispositivi che potrebbero richiedere l'uso del toolkit Blocker, il **28/02/2020** per rimuovere la dicitura "Gestiti da MDM" dai criteri dei dispositivi da escludere da questo aggiornamento automatico e il **30/06/2020** per indicare che tutti i dispositivi connessi a Windows Update possono ricevere questo aggiornamento (a partire dal 30/07/2020).</span><span class="sxs-lookup"><span data-stu-id="49b84-105">This article was updated on **01/09/2020** with more information about devices that might require you to use the Blocker Toolkit, on **2/28/2020** to remove "MDM managed" from the criteria of devices to be excluded from this automatic update, and on **6/30/2020** to reflect that all Windows Update connected devices are in scope to receive this update (effective no sooner than 7/30/2020).</span></span>

> [!NOTE]
> <span data-ttu-id="49b84-106">Questo articolo si applica al canale Microsoft Edge Stable.</span><span class="sxs-lookup"><span data-stu-id="49b84-106">This applies to Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="49b84-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="49b84-107">Overview</span></span>

<span data-ttu-id="49b84-108">Per consentire ai clienti di restare sempre protetti e aggiornati, Microsoft distribuirà Microsoft Edge (basato su Chromium) a tutti i dispositivi connessi a Windows Update con la versione 1803 di Windows 10 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="49b84-108">To help our customers become more secure and up-to-date, Microsoft will distribute Microsoft Edge (Chromium-based) to all Windows Update-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="49b84-109">Questo processo verrà avviato dopo il 15 gennaio 2020 e ulteriori informazioni saranno disponibili a partire da tale data.</span><span class="sxs-lookup"><span data-stu-id="49b84-109">This process will start after January 15, 2020 and more information will be available on that date.</span></span>

<span data-ttu-id="49b84-110">Blocker Toolkit è progettato per le organizzazioni che desiderano bloccare la distribuzione automatica di Microsoft Edge (basato su Chromium) nei dispositivi connessi a Windows Update con la versione 1803 di Windows 10 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="49b84-110">The Blocker Toolkit is intended for organizations that would like to block automatic delivery of Microsoft Edge (Chromium-based) to Windows Updated-connected devices running Windows 10 version 1803 and newer.</span></span>
<span data-ttu-id="49b84-111">I dispositivi gestiti da Windows Server Update Services (WSUS) o Windows Update per le aziende (WUfB) verranno esclusi dall'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="49b84-111">Devices that are Windows Server Update Services (WSUS) or Windows Update for Business (WUfB) managed will be excluded from this automatic update.</span></span>

**<span data-ttu-id="49b84-112">È importante notare che:</span><span class="sxs-lookup"><span data-stu-id="49b84-112">It's important to note that:</span></span>**

- <span data-ttu-id="49b84-113">Blocker Toolkit non impedisce agli utenti di installare manualmente Microsoft Edge (basato su Chromium) tramite download da Internet o supporti esterni.</span><span class="sxs-lookup"><span data-stu-id="49b84-113">The Blocker Toolkit will not prevent users from manually installing Microsoft Edge (Chromium-based) from Internet download, or from external media.</span></span>
- <span data-ttu-id="49b84-114">Le organizzazioni con gli aggiornamenti gestiti tramite Windows Update per le aziende (WUfB) non riceveranno automaticamente questo aggiornamento e non devono distribuire Blocker Toolkit.</span><span class="sxs-lookup"><span data-stu-id="49b84-114">Organizations with updates managed through Windows Update for Business (WUfB) will not automatically receive this update and do not need to deploy the blocker toolkit.</span></span>
- <span data-ttu-id="49b84-115">Le organizzazioni con ambienti gestiti con una soluzione per la gestione degli aggiornamenti come Windows Server Update Services (WSUS) o System Center Configuration Manager (SCCM) non devono distribuire Blocker Toolkit.</span><span class="sxs-lookup"><span data-stu-id="49b84-115">Organizations with environments managed with an update management solution such as Windows Server Update Services (WSUS) or System Center Configuration Manager (SCCM) do not have to deploy the Blocker Toolkit.</span></span> <span data-ttu-id="49b84-116">Possono usare questi prodotti per gestire completamente la distribuzione degli aggiornamenti rilasciati tramite Windows Update e Microsoft Update, tra cui Microsoft Edge (basato su Chromium), all'interno del loro ambiente.</span><span class="sxs-lookup"><span data-stu-id="49b84-116">They can use those products to fully manage deployment of updates released through Windows Update and Microsoft Update, including Microsoft Edge (Chromium-based), within their environment.</span></span>
- <span data-ttu-id="49b84-117">Questo aggiornamento è un aggiornamento indipendente (non incluso nell'aggiornamento cumulativo mensile) per offrire ai clienti aziendali la flessibilità e il massimo controllo sulla distribuzione di questo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="49b84-117">This update is a stand-alone update (not part of the monthly cumulative update) to give Enterprise customers flexibility and maximum control over deploying this update.</span></span>
- <span data-ttu-id="49b84-118">Il nuovo Microsoft Edge (basato su Chromium) verrà incluso nell'aggiornamento delle funzionalità di Windows 10, versione 20H2, nella seconda metà del 2020.</span><span class="sxs-lookup"><span data-stu-id="49b84-118">The new Microsoft Edge (Chromium-based) will be included as part of the Windows 10, version 20H2 feature update in the second half of 2020.</span></span> <span data-ttu-id="49b84-119">Il toolkit Blocker non influisce i comportamenti e la distribuzione della versione 20H2.</span><span class="sxs-lookup"><span data-stu-id="49b84-119">The Blocker toolkit does not impact 20H2 behaviors or deployment.</span></span> <span data-ttu-id="49b84-120">Vedere ulteriori informazioni sulla versione 20H2 di Windows 10 [qui](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span><span class="sxs-lookup"><span data-stu-id="49b84-120">See more information about Windows 10, version 20H2 [here](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span></span>

<span data-ttu-id="49b84-121">Puoi scaricare il file eseguibile di Blocker Toolkit all'indirizzo [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span><span class="sxs-lookup"><span data-stu-id="49b84-121">You can download the Blocker Toolkit executable file from [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span></span>

### <span data-ttu-id="49b84-122">Componenti del toolkit</span><span class="sxs-lookup"><span data-stu-id="49b84-122">Toolkit components</span></span>

<span data-ttu-id="49b84-123">Il toolkit contiene i seguenti componenti:</span><span class="sxs-lookup"><span data-stu-id="49b84-123">This toolkit contains the following components:</span></span>

- <span data-ttu-id="49b84-124">Script di blocco eseguibile (.CMD)</span><span class="sxs-lookup"><span data-stu-id="49b84-124">Executable blocker script (.CMD)</span></span>
- <span data-ttu-id="49b84-125">Modello amministrativo Criteri di gruppo (.ADMX e .ADML)</span><span class="sxs-lookup"><span data-stu-id="49b84-125">Group Policy Administrative Template (.ADMX and .ADML)</span></span>

### <span data-ttu-id="49b84-126">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="49b84-126">Supported Operating Systems</span></span>

<span data-ttu-id="49b84-127">Windows 10, versione 1803 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="49b84-127">Windows 10 version 1803 and newer.</span></span>

## <span data-ttu-id="49b84-128">Script di blocco</span><span class="sxs-lookup"><span data-stu-id="49b84-128">Blocker script</span></span>

<span data-ttu-id="49b84-129">Lo script crea una chiave del Registro di sistema e imposta il valore associato per bloccare o sbloccare (a seconda dell'opzione della riga di comando utilizzata) la distribuzione automatica di Microsoft Edge (basato su Chromium) nel computer locale o in un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="49b84-129">The script creates a registry key and sets the associated value to block or unblock (depending on the command-line option used) automatic delivery of Microsoft Edge (Chromium-based) on either the local machine or a remote target machine.</span></span>

**<span data-ttu-id="49b84-130">Chiave del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="49b84-130">Registry key:</span></span>** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**<span data-ttu-id="49b84-131">Nome del valore della chiave:</span><span class="sxs-lookup"><span data-stu-id="49b84-131">Key value name:</span></span>** `DoNotUpdateToEdgeWithChromium`

| <span data-ttu-id="49b84-132">Valore</span><span class="sxs-lookup"><span data-stu-id="49b84-132">Value</span></span>                | <span data-ttu-id="49b84-133">Risultato</span><span class="sxs-lookup"><span data-stu-id="49b84-133">Result</span></span>                         |
|----------------------|--------------------------------|
| *<span data-ttu-id="49b84-134">La chiave non è definita</span><span class="sxs-lookup"><span data-stu-id="49b84-134">Key is not defined</span></span>* | <span data-ttu-id="49b84-135">La distribuzione *non* è bloccata.</span><span class="sxs-lookup"><span data-stu-id="49b84-135">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="49b84-136">0</span><span class="sxs-lookup"><span data-stu-id="49b84-136">0</span></span>                    | <span data-ttu-id="49b84-137">La distribuzione *non* è bloccata.</span><span class="sxs-lookup"><span data-stu-id="49b84-137">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="49b84-138">1</span><span class="sxs-lookup"><span data-stu-id="49b84-138">1</span></span>                    | <span data-ttu-id="49b84-139">La distribuzione è bloccata.</span><span class="sxs-lookup"><span data-stu-id="49b84-139">Distribution is blocked.</span></span>       |

<span data-ttu-id="49b84-140">Lo script ha la seguente sintassi della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="49b84-140">The script has the following command-line syntax:</span></span><br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### <span data-ttu-id="49b84-141">Nome computer</span><span class="sxs-lookup"><span data-stu-id="49b84-141">Machine name</span></span>

<span data-ttu-id="49b84-142">Il parametro `<machine name>` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="49b84-142">The `<machine name>` parameter is optional.</span></span> <span data-ttu-id="49b84-143">Se non viene specificato, l'azione viene eseguita nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="49b84-143">If not specified, the action is performed on the local machine.</span></span> <span data-ttu-id="49b84-144">In caso contrario, l'accesso al computer remoto avviene tramite le funzionalità del Registro di sistema remoto del comando `REG`.</span><span class="sxs-lookup"><span data-stu-id="49b84-144">Otherwise, the remote machine is accessed through the remote registry capabilities of the `REG` command.</span></span> <span data-ttu-id="49b84-145">Se non è possibile accedere al Registro di sistema remoto a causa di autorizzazioni di sicurezza o non è possibile trovare il computer remoto, viene restituito un messaggio di errore dal comando `REG`.</span><span class="sxs-lookup"><span data-stu-id="49b84-145">If the remote registry can't be accessed due to security permissions or the remote machine can't be found, an error message is returned from the `REG` command.</span></span>

### <span data-ttu-id="49b84-146">Opzioni</span><span class="sxs-lookup"><span data-stu-id="49b84-146">Switches</span></span>

<span data-ttu-id="49b84-147">Le opzioni usate dallo script si escludono a vicenda e viene attivata solo la prima opzione valida di un determinato comando.</span><span class="sxs-lookup"><span data-stu-id="49b84-147">Switches used by the script are mutually exclusive and only the first valid switch from a given command is acted on.</span></span> <span data-ttu-id="49b84-148">Lo script può essere eseguito più volte nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="49b84-148">The script can be run multiple times on the same machine.</span></span>

| <span data-ttu-id="49b84-149">Opzione</span><span class="sxs-lookup"><span data-stu-id="49b84-149">Switch</span></span>       | <span data-ttu-id="49b84-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49b84-150">Description</span></span>                              |
|--------------|------------------------------------------|
| `/B`         | <span data-ttu-id="49b84-151">La distribuzione è bloccata</span><span class="sxs-lookup"><span data-stu-id="49b84-151">Blocks distribution</span></span>                      |
| `/U`         | <span data-ttu-id="49b84-152">La distribuzione è sbloccata</span><span class="sxs-lookup"><span data-stu-id="49b84-152">Unblocks distribution</span></span>                    |
| `/H` <span data-ttu-id="49b84-153">o</span><span class="sxs-lookup"><span data-stu-id="49b84-153">or</span></span> `/?` | <span data-ttu-id="49b84-154">Viene visualizzata la seguente guida di riepilogo:</span><span class="sxs-lookup"><span data-stu-id="49b84-154">Displays the following summary help:</span></span><br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## <span data-ttu-id="49b84-155">Modello amministrativo Criteri di gruppo (file .ADMX e .ADML)</span><span class="sxs-lookup"><span data-stu-id="49b84-155">Group Policy Administrative Template (.ADMX and .ADML files)</span></span>

<span data-ttu-id="49b84-156">Il modello amministrativo Criteri di gruppo (file .ADMX e .ADML) consente agli amministratori di importare le nuove impostazioni di Criteri di gruppo per bloccare o sbloccare la distribuzione automatica di Microsoft Edge (basato su Chromium) nell'ambiente Criteri di gruppo e usare Criteri di gruppo per eseguire l'azione in modo centralizzato nei sistemi dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="49b84-156">The Group Policy Administrative Template (.ADMX  and .ADML files) allows administrators to import the new Group Policy settings to block or unblock automatic delivery of Microsoft Edge (Chromium-based) into their Group Policy environment, and use Group Policy to centrally execute the action across systems in their environment.</span></span>

<span data-ttu-id="49b84-157">Per gli utenti che eseguono Windows 10 RS3 Enterprise/EDU e RS4 e versioni successive, i criteri sono nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="49b84-157">Users running Windows 10 RS3 Enterprise/EDU and RS4 and newer, will see the policy under the following path:</span></span>

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

<span data-ttu-id="49b84-158">Questa impostazione è disponibile solo come impostazione per computer, non è disponibile un'impostazione per utente.</span><span class="sxs-lookup"><span data-stu-id="49b84-158">This setting is available only as a Computer setting; there is no Per-User setting.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49b84-159">Questa impostazione del Registro di sistema non è archiviata in una chiave dei criteri e viene considerata una *preferenza*.</span><span class="sxs-lookup"><span data-stu-id="49b84-159">This registry setting isn't stored in a policies key and is considered a *preference*.</span></span> <span data-ttu-id="49b84-160">Pertanto, se l'oggetto Criteri di gruppo che implementa l'impostazione viene rimosso o se il criterio è impostato su **Non configurato**, l'impostazione rimane inalterata.</span><span class="sxs-lookup"><span data-stu-id="49b84-160">Therefore, if the Group Policy Object that implements the setting is ever removed or the policy is set to **Not Configured**, the setting will remain.</span></span> <span data-ttu-id="49b84-161">Per sbloccare la distribuzione di Microsoft Edge (basata su Chromium) tramite Criteri di gruppo, imposta i criteri su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="49b84-161">To unblock distribution of Microsoft Edge (Chromium-based) by using Group Policy, set the policy to **Disabled**.</span></span>

## <span data-ttu-id="49b84-162">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="49b84-162">See also</span></span>

- [<span data-ttu-id="49b84-163">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="49b84-163">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="49b84-164">Aggiornamenti di Windows per supportare Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49b84-164">Windows updates to support Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [<span data-ttu-id="49b84-165">Come accedere alla versione precedente di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49b84-165">How to access the old version of Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
