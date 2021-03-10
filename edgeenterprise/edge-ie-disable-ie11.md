---
title: Disabilitare Internet Explorer 11
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Informazioni su come disabilitare Internet Explorer 11 e usare la modalità Internet Explorer in Microsoft Edge.
ms.openlocfilehash: a0486c2965b1868db67b6de1423f279905074410
ms.sourcegitcommit: f34ff11499a2b96941e704103bdd959d19e3d7e7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400606"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="9cf26-103">Disabilitare Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="9cf26-103">Disable Internet Explorer 11</span></span>

<span data-ttu-id="9cf26-104">Questo articolo descrive come disabilitare Internet Explorer 11 come browser autonomo.</span><span class="sxs-lookup"><span data-stu-id="9cf26-104">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9cf26-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9cf26-105">Prerequisites</span></span>

<span data-ttu-id="9cf26-106">Sono necessari gli aggiornamenti di Windows seguenti e il software Microsoft Edge:</span><span class="sxs-lookup"><span data-stu-id="9cf26-106">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="9cf26-107">Aggiornamenti di Windows</span><span class="sxs-lookup"><span data-stu-id="9cf26-107">Windows updates</span></span>

  - <span data-ttu-id="9cf26-108">Windows 10, versione 2004, Windows Server versione 2004, Windows 10, versione 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-108">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="9cf26-109">Windows 10 versione 1909, Windows Server versione 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-109">Windows 10 version 1909, Windows Server version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="9cf26-110">Windows 10 versione 1809, Windows Server versione 1809 e Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-110">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="9cf26-111">Windows 10, versione 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-111">Windows 10, version 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
   - <span data-ttu-id="9cf26-112">Versione iniziale di Windows 10 (luglio 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-112">Windows 10 initial version (July 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="9cf26-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="9cf26-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9cf26-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="9cf26-115">Canale stabile di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9cf26-115">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="9cf26-116">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9cf26-116">Overview</span></span>

<span data-ttu-id="9cf26-117">Per le organizzazioni che richiedono Internet Explorer 11 (IE11) per la compatibilità legacy, la modalità Internet Explorer (modalità IE) in Microsoft Edge offre un’esperienza senza interruzioni con un unico browser.</span><span class="sxs-lookup"><span data-stu-id="9cf26-117">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="9cf26-118">Gli utenti possono accedere alle applicazioni legacy da Microsoft Edge senza dover tornare a IE11.</span><span class="sxs-lookup"><span data-stu-id="9cf26-118">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="9cf26-119">Dopo aver configurato la modalità IE, è possibile disabilitare IE11 come browser autonomo **senza influire sul funzionamento della modalità IE** nell'organizzazione tramite i Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9cf26-119">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf26-120">Se è necessaria l'app autonoma IE11 per siti specifici e si vuole reindirizzare tutto il traffico del browser a Microsoft Edge, è possibile configurare il criterio [Invia tutti i siti non inclusi nell'elenco di siti a Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) per reindirizzare i siti da IE a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9cf26-120">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="9cf26-121">Esperienza utente dopo il reindirizzamento del traffico a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9cf26-121">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="9cf26-122">Quando viene abilitato il criterio **Disabilitare Internet Explorer 11 come browser autonomo**, tutte le attività di IE11 vengono reindirizzate a Microsoft Edge e l’esperienza utente è quella descritta di seguito:</span><span class="sxs-lookup"><span data-stu-id="9cf26-122">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="9cf26-123">L'icona di IE11 nel menu Start verrà rimossa, ma quella sulla barra delle applicazioni rimarrà.</span><span class="sxs-lookup"><span data-stu-id="9cf26-123">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="9cf26-124">Quando gli utenti proveranno ad avviare collegamenti o associazioni di file che usano IE11, verranno reindirizzati ad aprire lo stesso file/URL in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9cf26-124">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="9cf26-125">Quando gli utenti proveranno ad aprire IE11 richiamando direttamente il file binario iexplore.exe, si aprirà Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9cf26-125">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="9cf26-126">Nell’ambito dell'impostazione dei criteri per questa esperienza, è possibile mostrare un messaggio di reindirizzamento per ogni utente che prova ad aprire IE11.</span><span class="sxs-lookup"><span data-stu-id="9cf26-126">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="9cf26-127">Si può impostare questo messaggio in modo che si visualizzi "Sempre" o "Una volta per utente".</span><span class="sxs-lookup"><span data-stu-id="9cf26-127">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="9cf26-128">Per impostazione predefinita, il messaggio di reindirizzamento mostrato nello screenshot successivo non viene mai visualizzato.</span><span class="sxs-lookup"><span data-stu-id="9cf26-128">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Avviso quando si prova ad aprire IE dopo che è stato attivato un reindirizzamento a Microsoft Edge.":::

<span data-ttu-id="9cf26-130">Se l'elenco dei siti per la modalità Enterprise contiene applicazioni configurate per l'apertura nell'app IE11 e IE11 viene disabilitato con questo criterio, tali applicazioni verranno aperte in modalità IE su Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9cf26-130">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="9cf26-131">Si verifica un problema con il flusso dell’utente quando un sito è configurato per l'apertura in IE11 ed è impostato il criterio Disabilitare IE11.</span><span class="sxs-lookup"><span data-stu-id="9cf26-131">There is a known issue with the user flow when a site is configured to open in IE11 and the disable IE11 policy is set.</span></span> <span data-ttu-id="9cf26-132">Il problema è attualmente in corso di analisi.</span><span class="sxs-lookup"><span data-stu-id="9cf26-132">The issue being actively investigated.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="9cf26-133">Disabilitare Internet Explorer 11 come browser autonomo</span><span class="sxs-lookup"><span data-stu-id="9cf26-133">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="9cf26-134">Per disabilitare Internet Explorer 11 tramite i Criteri di gruppo, seguire la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="9cf26-134">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="9cf26-135">Assicurarsi di disporre dei prerequisiti relativi agli aggiornamenti del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9cf26-135">Ensure you have the pre-requisite operating system updates.</span></span> <span data-ttu-id="9cf26-136">Questo passaggio aggiornerà direttamente i file ADMX nel computer (nello specifico, inetres.adml e inetres.admx).</span><span class="sxs-lookup"><span data-stu-id="9cf26-136">This step will update the ADMX files on your machine directly (specifically inetres.adml and inetres.admx).</span></span> <span data-ttu-id="9cf26-137">Tenere presente che, se si desidera aggiornare l'archivio centrale, sarà necessario copiare i file con estensione .adml e .admx da un computer con gli aggiornamenti dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="9cf26-137">Please note that if you want to update your Central Store, you will need to copy over the .adml and .admx files from a machine that has the pre-requisite updates.</span></span> <span data-ttu-id="9cf26-138">Per altre informazioni, vedere [Creare e gestire l'archivio centrale](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store)</span><span class="sxs-lookup"><span data-stu-id="9cf26-138">For more information, see [Create and manage Central Store](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store)</span></span>
2. <span data-ttu-id="9cf26-139">Aprire l'Editor Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9cf26-139">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="9cf26-140">Passare a ***Configurazione computer/Modelli amministrativi/Componenti di Windows/Internet Explorer***.</span><span class="sxs-lookup"><span data-stu-id="9cf26-140">Go to ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***.</span></span> 
4. <span data-ttu-id="9cf26-141">Fare doppio clic su \*\* Disabilitare Internet Explorer 11 come browser autonomo.\*\*</span><span class="sxs-lookup"><span data-stu-id="9cf26-141">Double-click **Disable Internet Explorer 11 as a standalone browser**.</span></span>
5. <span data-ttu-id="9cf26-142">Selezionare **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="9cf26-142">Select **Enabled**.</span></span>
6. <span data-ttu-id="9cf26-143">In **Opzioni**, selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cf26-143">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="9cf26-144">**Mai**  se non si vuole avvertire gli utenti che IE11 è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="9cf26-144">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="9cf26-145">**Sempre**  se si vuole inviare una notifica agli utenti ogni volta che vengono reindirizzati da Internet 11.</span><span class="sxs-lookup"><span data-stu-id="9cf26-145">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="9cf26-146">**Una volta per utente**   se si vuole inviare una notifica agli utenti solo la prima volta che vengono reindirizzati.</span><span class="sxs-lookup"><span data-stu-id="9cf26-146">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="9cf26-147">Fare clic su **OK** o **Applica**  per salvare questa impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9cf26-147">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cf26-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cf26-148">See also</span></span>

- [<span data-ttu-id="9cf26-149">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="9cf26-149">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="9cf26-150">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="9cf26-150">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="9cf26-151">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="9cf26-151">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
