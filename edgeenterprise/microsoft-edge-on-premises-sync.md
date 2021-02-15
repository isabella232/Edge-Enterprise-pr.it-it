---
title: Sincronizzazione locale per gli utenti di Active Directory (AD)
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 02/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione locale per gli utenti di Active Directory (AD)
ms.openlocfilehash: adf0adc8370aa1e18d07d0d2e91727d1ac607bf1
ms.sourcegitcommit: 90b8eab62edbed0e0a84780abd7d3854bf95c130
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328048"
---
# <span data-ttu-id="c5a0f-103">Sincronizzazione locale per gli utenti di Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="c5a0f-103">On-premises sync for Active Directory (AD) users</span></span>

<span data-ttu-id="c5a0f-104">Questo articolo fornisce informazioni sul come gli utenti di Active Directory (AD) possono effettuare il roaming tra i preferiti e le impostazioni di Microsoft Edge da computer diversi senza connettersi ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-104">This article explains how Active Directory (AD) users can roam Microsoft Edge favorites and settings between computers without connecting to Microsoft cloud services.</span></span>

> [!NOTE]
> <span data-ttu-id="c5a0f-105">Questo articolo si applica a Microsoft Edge versione 85 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="c5a0f-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="c5a0f-106">Introduction</span></span>

<span data-ttu-id="c5a0f-107">In genere la sincronizzazione dei dati utente in Microsoft Edge richiede un account Microsoft o un account di Azure Active Directory (Azure AD) e una connessione ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-107">Syncing user data in Microsoft Edge normally requires either a Microsoft Account or an Azure Active Directory (Azure AD) account, and a connection to Microsoft cloud services.</span></span> <span data-ttu-id="c5a0f-108">Con la sincronizzazione locale, Microsoft Edge salva i preferiti e le impostazioni di un utente di Active Directory in un file che può essere spostato da un computer all’altro.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-108">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can be moved between different computers.</span></span> <span data-ttu-id="c5a0f-109">La sincronizzazione locale non interferisce con la sincronizzazione cloud per i profili che la consentono.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-109">On-premises sync doesn't interfere with cloud syncing for those profiles that allow it.</span></span>

## <span data-ttu-id="c5a0f-110">Come funziona</span><span class="sxs-lookup"><span data-stu-id="c5a0f-110">How it works</span></span>

<span data-ttu-id="c5a0f-111">Microsoft Edge consente l'associazione dei profili agli account di Active Directory (AD), che non possono essere usati con la sincronizzazione cloud. Una volta abilitata la sincronizzazione locale, i dati del profilo AD vengono salvati in un file denominato profile.pb.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-111">Microsoft Edge allows profiles to be associated with Active Directory (AD) accounts, which can't be used with cloud sync. When on-premises sync is enabled, the data from the AD profile is saved to a file named profile.pb.</span></span> <span data-ttu-id="c5a0f-112">Per impostazione predefinita, il file viene archiviato in *%APPDATA%/Microsoft/Edge*.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-112">By default, this file is stored in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="c5a0f-113">Una volta scritto, il file potrà essere spostato tra diversi computer e i dati utente verranno letti e scritti in ogni computer.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-113">After this file is written, it can be moved between different computers, and user data will be read and written on each computer.</span></span> <span data-ttu-id="c5a0f-114">Microsoft Edge legge e scrive solo da questo file; è responsabilità dell'amministratore assicurarsi che il file sia stato spostato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-114">Microsoft Edge only reads and writes from this file; it is the admin's responsibility to ensure that the file is moved as needed.</span></span>

## <span data-ttu-id="c5a0f-115">Utilizzare la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="c5a0f-115">Use on-premises sync</span></span>

<span data-ttu-id="c5a0f-116">Per utilizzare la sincronizzazione locale è necessario abilitarla, associare un profilo a un account di Active Directory e, facoltativamente, cambiare il percorso dei dati utente.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-116">To use on-premises sync, you have to enable it, associate a profile with an AD account, and optionally, change the location of the user data.</span></span>

### <span data-ttu-id="c5a0f-117">Abilitare la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="c5a0f-117">Enable on-premises sync</span></span>

<span data-ttu-id="c5a0f-118">Per abilitare la sincronizzazione locale in Microsoft Edge, configurare il criterio [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled).</span><span class="sxs-lookup"><span data-stu-id="c5a0f-118">To enable on-premises sync in Microsoft Edge, configure the [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) policy.</span></span>

### <span data-ttu-id="c5a0f-119">Verificare che un profilo sia associato a un account di Active Directory</span><span class="sxs-lookup"><span data-stu-id="c5a0f-119">Ensure that a profile is associated with an Active Directory account</span></span>

<span data-ttu-id="c5a0f-120">La sincronizzazione locale funziona solo se il profilo è associato a un account di Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="c5a0f-120">On-premises sync only works with the profile associated with an Active Directory (AD) account.</span></span> <span data-ttu-id="c5a0f-121">Se non esistono profili di questo tipo, la sincronizzazione locale non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-121">If no such profile exists, on-premises sync will not function.</span></span> <span data-ttu-id="c5a0f-122">Per assicurarsi che gli utenti accedano con un account di Active Directory, configurare il criterio [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin).</span><span class="sxs-lookup"><span data-stu-id="c5a0f-122">To ensure that users sign on with an AD account, configure the [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) policy.</span></span> <span data-ttu-id="c5a0f-123">Per la sincronizzazione locale, Microsoft Edge si basa solo su AD per stabilire un'identità per i dati utente e non esiste alcuna relazione diretta tra il modo in cui Microsoft Edge legge e scrive i dati locali in modo che l'amministratore abbia configurato il roaming per un utente AD.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-123">For on-premises sync, Microsoft Edge only relies on AD to establish an identity for the user data, and there's no direct relationship between how Microsoft Edge reads and writes on-premises data to how the admin has configured roaming for an AD user.</span></span>

### <span data-ttu-id="c5a0f-124">Cambiare il percorso dei dati utente (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c5a0f-124">Change the location of the user data (optional)</span></span>

<span data-ttu-id="c5a0f-125">Per impostazione predefinita, i dati utente vengono archiviati in un file denominato **profile.pb** in *%APPDATA%/Microsoft/Edge*.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-125">By default, the user data is stored in a filed named **profile.pb** in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="c5a0f-126">Per modificare il percorso del file, configurare il criterio [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation).</span><span class="sxs-lookup"><span data-stu-id="c5a0f-126">To change the location of this file, configure the [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) policy.</span></span>

## <span data-ttu-id="c5a0f-127">Modifiche dell'esperienza utente quando è abilitata la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="c5a0f-127">Changes in the user experience when on-premises sync is enabled</span></span>

<span data-ttu-id="c5a0f-128">Quando la sincronizzazione locale è abilitata, agli utenti non viene richiesto di abilitare la sincronizzazione. Inoltre, gli utenti non possono disattivare la sincronizzazione nelle impostazioni di sincronizzazione e non possono attivare tipi di sincronizzazione non supportati dalla sincronizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-128">When on-premises sync is enabled, users won't be asked to enable sync. In addition, users can't turn off sync in Sync settings, and they can't turn on sync types that aren't supported by on-premises sync.</span></span>

## <span data-ttu-id="c5a0f-129">Note sull'utilizzo della sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="c5a0f-129">On-premises sync usage notes</span></span>

### <span data-ttu-id="c5a0f-130">Eseguire la sincronizzazione cloud e la sincronizzazione locale nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="c5a0f-130">Running cloud sync and on-premises sync on the same computer</span></span>

<span data-ttu-id="c5a0f-131">La sincronizzazione locale non interferisce con la sincronizzazione cloud. Se Microsoft Edge include più account Microsoft o profili Azure Active Directory che eseguono la sincronizzazione con il cloud, questi profili continueranno a farlo anche mentre la sincronizzazione locale è abilitata.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-131">On-premises sync doesn't interfere with cloud sync. If Microsoft Edge has multiple Microsoft Account or Azure Active Directory profiles that sync to the cloud, these profiles will continue to sync while on-premises sync is enabled.</span></span>

### <span data-ttu-id="c5a0f-132">Non è consigliabile eseguire Microsoft Edge in più computer alla volta</span><span class="sxs-lookup"><span data-stu-id="c5a0f-132">Running Microsoft Edge on more than one computer at a time isn't recommended</span></span>

<span data-ttu-id="c5a0f-133">Poiché la sincronizzazione locale funziona spostando un file di dati utente da un computer all’altro, la sincronizzazione locale non sincronizza le modifiche tra sessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-133">Because on-premises sync works by moving a user data file between computers, on-premises sync doesn't sync changes between simultaneous sessions.</span></span> <span data-ttu-id="c5a0f-134">Per questo motivo, la sincronizzazione locale funziona al meglio in un computer alla volta.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-134">For this reason, on-premises sync works best when used on one computer at a time.</span></span> <span data-ttu-id="c5a0f-135">Se sono in esecuzione sessioni locali simultanee, i dati di uno o più computer potrebbero essere sovrascritti in modo imprevisto con quelli di un altro computer all'avvio successivo di una sessione del browser.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-135">If there are simultaneous on-premises sessions running, data on any of the computers may be unexpectedly overwritten by data from another computer the next time you start a browser session.</span></span>

> [!NOTE]
> <span data-ttu-id="c5a0f-136">Microsoft Edge blocca il file **profile.pb** quando la sincronizzazione locale è abilitata.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-136">Microsoft Edge locks the **profile.pb** file when on-premises sync is enabled.</span></span> <span data-ttu-id="c5a0f-137">Se il reindirizzamento delle cartelle viene usato per condividere un singolo file **profile.pb** tra diversi computer, è possibile avviare una sola istanza di Microsoft Edge con quel file.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-137">If folder redirection is used to share a single **profile.pb** file between different computers, then only one instance of Microsoft Edge using that file can be started.</span></span>

### <span data-ttu-id="c5a0f-138">Utilizzare altri criteri di sincronizzazione con la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="c5a0f-138">Using other sync policies with on-premises sync</span></span>

<span data-ttu-id="c5a0f-139">È possibile utilizzare il criterio [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) per disabilitare in modo selettivo i preferiti o le impostazioni di sincronizzazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-139">The [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policy can be used to selectively disable either favorites or settings sync if desired.</span></span> <span data-ttu-id="c5a0f-140">Il [criterio SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) non ha alcun impatto sulla sincronizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="c5a0f-140">The [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) policy has no impact on on-premises sync.</span></span>

## <span data-ttu-id="c5a0f-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5a0f-141">See also</span></span>

- [<span data-ttu-id="c5a0f-142">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="c5a0f-142">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c5a0f-143">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="c5a0f-143">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="c5a0f-144">Sincronizzazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="c5a0f-144">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
