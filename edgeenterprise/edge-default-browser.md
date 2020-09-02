---
title: Impostare Microsoft Edge come browser predefinito in Windows e macOS
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come impostare Microsoft Edge come browser predefinito
ms.openlocfilehash: c8cc45e0fe42dcbbd828dd81ae568f141cda2985
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980172"
---
# <span data-ttu-id="21dde-103">Impostare Microsoft Edge come browser predefinito</span><span class="sxs-lookup"><span data-stu-id="21dde-103">Set Microsoft Edge as the default browser</span></span>

<span data-ttu-id="21dde-104">Questo articolo spiega come impostare Microsoft Edge come browser predefinito in Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="21dde-104">This article explains how you can set Microsoft Edge as the default browser on Windows and macOS.</span></span>

> [!NOTE]
> <span data-ttu-id="21dde-105">Questo articolo si applica a Microsoft Edge, versione 77 in Windows 8 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="21dde-105">This article applies to Microsoft Edge version 77 or later on Windows 8 and Windows 10.</span></span> <span data-ttu-id="21dde-106">Per Windows 7 e macOS, vedi il criterio [Impostare Microsoft Edge come browser predefinito](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled).</span><span class="sxs-lookup"><span data-stu-id="21dde-106">For Windows 7 and macOS, see the [Set Microsoft Edge as default browser](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) policy.</span></span>

## <span data-ttu-id="21dde-107">Introduzione</span><span class="sxs-lookup"><span data-stu-id="21dde-107">Introduction</span></span>

<span data-ttu-id="21dde-108">Puoi usare l'impostazione di Criteri di gruppo **Imposta file di configurazione delle associazioni predefinite** o l'impostazione di gestione dei dispositivi mobili [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) per configurare Microsoft Edge come browser predefinito per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21dde-108">You can use the **Set a default associations configuration file** Group Policy or the [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting to set Microsoft Edge as the default browser for your organization.</span></span>

<span data-ttu-id="21dde-109">Per configurare Microsoft Edge Stable come browser predefinito per i file html, i collegamenti http/https e i file PDF, usa il seguente file di associazione dell'applicazione nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="21dde-109">To set Microsoft Edge Stable as the default browser for html files, http/https links, and PDF files use the following application association file example:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="21dde-110">Per configurare Microsoft Edge Beta come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Beta" e **ProgId** su "MSEdgeBHTML".</span><span class="sxs-lookup"><span data-stu-id="21dde-110">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="21dde-111">Per configurare Microsoft Edge Dev come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Dev" e **ProgId** su "MSEdgeDHTML".</span><span class="sxs-lookup"><span data-stu-id="21dde-111">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>


> [!NOTE]
> <span data-ttu-id="21dde-112">Le associazioni di file predefinite non vengono applicate se Microsoft Edge non è installato nel dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="21dde-112">The default file associations aren't applied if Microsoft Edge isn't installed on the target device.</span></span> <span data-ttu-id="21dde-113">In questo scenario, agli utenti viene richiesto di selezionare l'applicazione predefinita quando aprono un collegamento o un file htm/html.</span><span class="sxs-lookup"><span data-stu-id="21dde-113">In this scenario, users are prompted to select their default application when they open a link or a htm/html file.</span></span>

## <span data-ttu-id="21dde-114">Impostare Microsoft Edge come browser predefinito in dispositivi aggiunti al dominio</span><span class="sxs-lookup"><span data-stu-id="21dde-114">Set Microsoft Edge as the default browser on domain-joined devices</span></span>

<span data-ttu-id="21dde-115">Puoi impostare Microsoft Edge come browser predefinito in dispositivi aggiunti al dominio configurando l'impostazione di Criteri di gruppo **Imposta file di configurazione delle associazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="21dde-115">You can set Microsoft Edge as the default browser on domain-joined devices by configuring the **Set a default associations configuration file** group policy.</span></span> <span data-ttu-id="21dde-116">Per attivare questa impostazione devi inoltre creare e archiviare un file di configurazione di associazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="21dde-116">Turning this group policy on requires you to create and store a default associations configuration file.</span></span> <span data-ttu-id="21dde-117">Questo file viene archiviato localmente o in una condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="21dde-117">This file is stored locally or on a network share.</span></span> <span data-ttu-id="21dde-118">Per altre informazioni sulla creazione di questo file, vedi [Esportare o importare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)</span><span class="sxs-lookup"><span data-stu-id="21dde-118">For more information about creating this file, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations).</span></span>

### <span data-ttu-id="21dde-119">Per configurare i criteri di gruppo per un tipo di file e un file di configurazione di associazioni di protocollo predefiniti:</span><span class="sxs-lookup"><span data-stu-id="21dde-119">To configure the group policy for a default file type and protocol associations configuration file:</span></span>

1. <span data-ttu-id="21dde-120">Apri Editor Criteri di gruppo e vai a **Configurazione computer\Modelli amministrativi\Componenti Windows\Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="21dde-120">Open the Group Policy editor and go to the **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
2. <span data-ttu-id="21dde-121">Seleziona **Imposta file di configurazione delle associazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="21dde-121">Select **Set a default associations configuration file**.</span></span>
3. <span data-ttu-id="21dde-122">Fai clic su **Impostazione criterio** e quindi fai clic su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="21dde-122">Click **policy setting**, and then click **Enabled**.</span></span>
4. <span data-ttu-id="21dde-123">Nell'area **Opzioni** digita il percorso del file di configurazione delle associazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="21dde-123">Under **Options:**, type the location to your default associations configuration file.</span></span>
5. <span data-ttu-id="21dde-124">Fai clic su **OK** per salvare le impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="21dde-124">Click **OK** to save the policy settings.</span></span>

<span data-ttu-id="21dde-125">L'esempio nella schermata successiva mostra un file di associazioni denominato *appassoc.xml* in una condivisione di rete accessibile dal dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="21dde-125">The example in the next screenshot shows an associations file named *appassoc.xml* on a network share that is accessible from the target device.</span></span>

   ![Abilitare l'associazione di file in Criteri di gruppo](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > <span data-ttu-id="21dde-127">Se questa impostazione è abilitata e il dispositivo dell'utente è aggiunto a un dominio, il file di configurazione delle associazioni viene elaborato al successivo accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="21dde-127">If this setting is enabled and the user's device is domain-joined, the associations configuration file is processed the next time the user signs on.</span></span>

## <span data-ttu-id="21dde-128">Configurare Microsoft Edge come browser predefinito in dispositivi aggiunti ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="21dde-128">Set Microsoft Edge as the default browser on Azure Active Directory joined devices</span></span>

<span data-ttu-id="21dde-129">Per configurare Microsoft Edge come browser predefinito in dispositivi aggiunti ad Azure Active Directory, attieniti ai passaggi descritti nell'impostazione di gestione dei dispositivi mobili [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) usando come esempio il file di associazione dell'applicazione che segue.</span><span class="sxs-lookup"><span data-stu-id="21dde-129">To set Microsoft Edge as the default browser on Azure Active Directory joined devices follow the steps in the [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting using the following application association file as an example.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="21dde-130">Per configurare Microsoft Edge Beta come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Beta" e **ProgId** su "MSEdgeBHTML".</span><span class="sxs-lookup"><span data-stu-id="21dde-130">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="21dde-131">Per configurare Microsoft Edge Dev come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Dev" e **ProgId** su "MSEdgeDHTML".</span><span class="sxs-lookup"><span data-stu-id="21dde-131">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>

## <span data-ttu-id="21dde-132">Impostare Microsoft Edge come browser predefinito in Windows e macOS</span><span class="sxs-lookup"><span data-stu-id="21dde-132">Set Microsoft Edge as the default browser on macOS</span></span>

<span data-ttu-id="21dde-133">Se tenti di impostare il browser predefinito a livello di codice su macOS viene visualizzata una richiesta per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="21dde-133">Attempting to programmatically set the default browser on macOS causes a prompt to appear for the end user.</span></span> <span data-ttu-id="21dde-134">Questa richiesta è una funzionalità di sicurezza di macOS che può essere automatizzata solo tramite AppleScript.</span><span class="sxs-lookup"><span data-stu-id="21dde-134">This prompt is a macOS security feature that can only be automated away by using an AppleScript.</span></span>

<span data-ttu-id="21dde-135">A causa di questa limitazione, esistono due metodi principali per impostare Microsoft Edge come browser predefinito in un macOS.</span><span class="sxs-lookup"><span data-stu-id="21dde-135">Because of this limitation, there are two main methods for setting Microsoft Edge as the default browser on a macOS.</span></span> <span data-ttu-id="21dde-136">La prima opzione consiste nell'eseguire il flash del dispositivo con un'immagine di macOS, in cui Microsoft Edge è già stato impostato come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="21dde-136">The first option is to flash the device with an image of macOS where Microsoft Edge has already been set as the default browser.</span></span> <span data-ttu-id="21dde-137">L'altra opzione consiste nell'usare i criteri [Impostare Microsoft Edge come browser predefinito](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) , che ti richiede di impostare Microsoft Edge come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="21dde-137">The other option is to use the [Set Microsoft Edge as default browser](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) policy, which prompts the user to set Microsoft Edge as the default browser.</span></span>

<span data-ttu-id="21dde-138">Quando usi uno di questi metodi, puoi comunque modificare il browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="21dde-138">When using either of these methods, it is still possible for a user to change the default browser.</span></span> <span data-ttu-id="21dde-139">Questo perché la preferenza del browser predefinito non può essere bloccata a livello di codice per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="21dde-139">This is because for security reasons, the default browser preference can’t be blocked programmatically.</span></span> <span data-ttu-id="21dde-140">Per questo motivo, ti consigliamo di distribuire i criteri **Impostare Microsoft Edge come browser predefinito** anche se crei un'immagine con Microsoft Edge come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="21dde-140">For this reason, we recommend that you deploy the **Set Microsoft Edge as default browser** policy even if you create an image with Microsoft Edge as the default browser.</span></span> <span data-ttu-id="21dde-141">Se i criteri sono impostati e un utente cambia il browser predefinito in un browser diverso da Microsoft Edge, la prossima volta che avvii Microsoft Edge ti verrà richiesto di impostarlo come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="21dde-141">If the policy is set and a user changes the default browser from Microsoft Edge the next time they open Microsoft Edge, they will be prompted to set it as the default.</span></span>

## <span data-ttu-id="21dde-142">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="21dde-142">See also</span></span>

- [<span data-ttu-id="21dde-143">Pianificare la distribuzione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="21dde-143">Plan your deployment of Microsoft Edge</span></span>](https://docs.microsoft.com/DeployEdge/deploy-edge-plan-deployment)
- [<span data-ttu-id="21dde-144">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="21dde-144">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="21dde-145">Impostare Microsoft Edge come browser predefinito (Windows 7 e macOS)</span><span class="sxs-lookup"><span data-stu-id="21dde-145">Set Microsoft Edge as default browser (Windows 7 and macOS)</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled)
- [<span data-ttu-id="21dde-146">Windows 10: come configurare le associazioni di file per i professionisti IT?</span><span class="sxs-lookup"><span data-stu-id="21dde-146">Windows 10 – How to configure file associations for IT Pros?</span></span>](https://docs.microsoft.com/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [<span data-ttu-id="21dde-147">Esportare o importare associazioni di applicazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="21dde-147">Export or Import Default Application Associations</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [<span data-ttu-id="21dde-148">Panoramica di DISM</span><span class="sxs-lookup"><span data-stu-id="21dde-148">DISM Overview</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism)
  - [<span data-ttu-id="21dde-149">DISM - Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="21dde-149">DISM - Deployment Image Servicing and Management</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)
