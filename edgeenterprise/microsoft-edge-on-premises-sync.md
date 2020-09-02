---
title: Sincronizzazione locale per gli utenti di Active Directory (AD)
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 08/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione locale per gli utenti di Active Directory (AD)
ms.openlocfilehash: 89f061072fdaa748d317ca8dc0c290893cfdfd6c
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980292"
---
# <span data-ttu-id="a2272-103">Sincronizzazione locale per gli utenti di Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="a2272-103">On-premises sync for Active Directory (AD) users</span></span>

<span data-ttu-id="a2272-104">Questo articolo fornisce informazioni sul come gli utenti di Active Directory (AD) possono effettuare il roaming tra i preferiti e le impostazioni di Microsoft Edge da computer diversi senza connettersi ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2272-104">This article explains how Active Directory (AD) users can roam Microsoft Edge favorites and settings between computers without connecting to Microsoft cloud services.</span></span>

> [!NOTE]
> <span data-ttu-id="a2272-105">Questo articolo si applica a Microsoft Edge versione 85 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a2272-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="a2272-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a2272-106">Introduction</span></span>

<span data-ttu-id="a2272-107">In genere la sincronizzazione dei dati utente in Microsoft Edge richiede un account Microsoft o un account di Azure Active Directory (Azure AD) e una connessione ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2272-107">Syncing user data in Microsoft Edge normally requires either a Microsoft Account or an Azure Active Directory (Azure AD) account, and a connection to Microsoft cloud services.</span></span> <span data-ttu-id="a2272-108">Con la sincronizzazione locale, Microsoft Edge salva i preferiti e le impostazioni di un utente di Active Directory in un file che può essere spostato da un computer all’altro.</span><span class="sxs-lookup"><span data-stu-id="a2272-108">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can be moved between different computers.</span></span> <span data-ttu-id="a2272-109">La sincronizzazione locale non interferisce con la sincronizzazione cloud per i profili che la consentono.</span><span class="sxs-lookup"><span data-stu-id="a2272-109">On-premises sync doesn't interfere with cloud syncing for those profiles that allow it.</span></span>

## <span data-ttu-id="a2272-110">Come funziona</span><span class="sxs-lookup"><span data-stu-id="a2272-110">How it works</span></span>

<span data-ttu-id="a2272-111">Microsoft Edge consente l'associazione dei profili agli account di Active Directory (AD), che non possono essere usati con la sincronizzazione cloud. Una volta abilitata la sincronizzazione locale, i dati del profilo AD vengono salvati in un file denominato profile.pb.</span><span class="sxs-lookup"><span data-stu-id="a2272-111">Microsoft Edge allows profiles to be associated with Active Directory (AD) accounts, which can't be used with cloud sync. When on-premises sync is enabled, the data from the AD profile is saved to a file named profile.pb.</span></span> <span data-ttu-id="a2272-112">Per impostazione predefinita, il file viene archiviato in *%APP_DATA%/Microsoft/Edge*.</span><span class="sxs-lookup"><span data-stu-id="a2272-112">By default, this file is stored in *%APP_DATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="a2272-113">Una volta scritto, il file potrà essere spostato tra diversi computer e i dati utente verranno letti e scritti in ogni computer.</span><span class="sxs-lookup"><span data-stu-id="a2272-113">After this file is written, it can be moved between different computers, and user data will be read and written on each computer.</span></span>

## <span data-ttu-id="a2272-114">Utilizzare la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="a2272-114">Use on-premises sync</span></span>

<span data-ttu-id="a2272-115">Per utilizzare la sincronizzazione locale è necessario abilitarla, associare un profilo a un account di Active Directory e, facoltativamente, cambiare il percorso dei dati utente.</span><span class="sxs-lookup"><span data-stu-id="a2272-115">To use on-premises sync, you have to enable it, associate a profile with an AD account, and optionally, change the location of the user data.</span></span>

### <span data-ttu-id="a2272-116">Abilitare la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="a2272-116">Enable on-premises sync</span></span>

<span data-ttu-id="a2272-117">Per abilitare la sincronizzazione locale in Microsoft Edge, configurare il criterio [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled).</span><span class="sxs-lookup"><span data-stu-id="a2272-117">To enable on-premises sync in Microsoft Edge, configure the [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) policy.</span></span>

### <span data-ttu-id="a2272-118">Verificare che un profilo sia associato a un account di Active Directory</span><span class="sxs-lookup"><span data-stu-id="a2272-118">Ensure that a profile is associated with an Active Directory account</span></span>

<span data-ttu-id="a2272-119">La sincronizzazione locale funziona solo se il profilo è associato a un account di Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="a2272-119">On-premises sync only works with the profile associated with an Active Directory (AD) account.</span></span> <span data-ttu-id="a2272-120">Se non esistono profili di questo tipo, la sincronizzazione locale non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="a2272-120">If no such profile exists, on-premises sync will not function.</span></span> <span data-ttu-id="a2272-121">Per assicurarsi che gli utenti accedano con un account di Active Directory, configurare il criterio [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin).</span><span class="sxs-lookup"><span data-stu-id="a2272-121">To ensure that users sign on with an AD account, configure the [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) policy.</span></span>

### <span data-ttu-id="a2272-122">Cambiare il percorso dei dati utente (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a2272-122">Change the location of the user data (optional)</span></span>

<span data-ttu-id="a2272-123">Per impostazione predefinita, i dati utente vengono archiviati in un file denominato **profile.pb** in *%APP_DATA%/Microsoft/Edge*.</span><span class="sxs-lookup"><span data-stu-id="a2272-123">By default, the user data is stored in a filed named **profile.pb** in *%APP_DATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="a2272-124">Per modificare il percorso del file, configurare il criterio [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation).</span><span class="sxs-lookup"><span data-stu-id="a2272-124">To change the location of this file, configure the [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) policy.</span></span>

## <span data-ttu-id="a2272-125">Modifiche dell'esperienza utente quando è abilitata la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="a2272-125">Changes in the user experience when on-premises sync is enabled</span></span>

<span data-ttu-id="a2272-126">Quando la sincronizzazione locale è abilitata, agli utenti non viene richiesto di abilitare la sincronizzazione. Inoltre, gli utenti non possono disattivare la sincronizzazione nelle impostazioni di sincronizzazione e non possono attivare tipi di sincronizzazione non supportati dalla sincronizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="a2272-126">When on-premises sync is enabled, users won't be asked to enable sync. In addition, users can't turn off sync in Sync settings, and they can't turn on sync types that aren't supported by on-premises sync.</span></span>

## <span data-ttu-id="a2272-127">Note sull'utilizzo della sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="a2272-127">On-premises sync usage notes</span></span>

### <span data-ttu-id="a2272-128">Eseguire la sincronizzazione cloud e la sincronizzazione locale nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="a2272-128">Running cloud sync and on-premises sync on the same computer</span></span>

<span data-ttu-id="a2272-129">La sincronizzazione locale non interferisce con la sincronizzazione cloud. Se Microsoft Edge include più account Microsoft o profili Azure Active Directory che eseguono la sincronizzazione con il cloud, questi profili continueranno a farlo anche mentre la sincronizzazione locale è abilitata.</span><span class="sxs-lookup"><span data-stu-id="a2272-129">On-premises sync doesn't interfere with cloud sync. If Microsoft Edge has multiple Microsoft Account or Azure Active Directory profiles that sync to the cloud, these profiles will continue to sync while on-premises sync is enabled.</span></span>

### <span data-ttu-id="a2272-130">Non è consigliabile eseguire Microsoft Edge in più computer alla volta</span><span class="sxs-lookup"><span data-stu-id="a2272-130">Running Microsoft Edge on more than one computer at a time isn't recommended</span></span>

<span data-ttu-id="a2272-131">Poiché la sincronizzazione locale funziona spostando un file di dati utente da un computer all’altro, la sincronizzazione locale non sincronizza le modifiche tra sessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="a2272-131">Because on-premises sync works by moving a user data file between computers, on-premises sync doesn't sync changes between simultaneous sessions.</span></span> <span data-ttu-id="a2272-132">Per questo motivo, la sincronizzazione locale funziona al meglio in un computer alla volta.</span><span class="sxs-lookup"><span data-stu-id="a2272-132">For this reason, on-premises sync works best when used on one computer at a time.</span></span> <span data-ttu-id="a2272-133">Se sono in esecuzione sessioni locali simultanee, i dati di uno o più computer potrebbero essere sovrascritti in modo imprevisto con quelli di un altro computer all'avvio successivo di una sessione del browser.</span><span class="sxs-lookup"><span data-stu-id="a2272-133">If there are simultaneous on-premises sessions running, data on any of the computers may be unexpectedly overwritten by data from another computer the next time you start a browser session.</span></span>

> [!NOTE]
> <span data-ttu-id="a2272-134">Microsoft Edge blocca il file **profile.pb** quando la sincronizzazione locale è abilitata.</span><span class="sxs-lookup"><span data-stu-id="a2272-134">Microsoft Edge locks the **profile.pb** file when on-premises sync is enabled.</span></span> <span data-ttu-id="a2272-135">Se il reindirizzamento delle cartelle viene usato per condividere un singolo file **profile.pb** tra diversi computer, è possibile avviare una sola istanza di Microsoft Edge con quel file.</span><span class="sxs-lookup"><span data-stu-id="a2272-135">If folder redirection is used to share a single **profile.pb** file between different computers, then only one instance of Microsoft Edge using that file can be started.</span></span>

### <span data-ttu-id="a2272-136">Utilizzare altri criteri di sincronizzazione con la sincronizzazione locale</span><span class="sxs-lookup"><span data-stu-id="a2272-136">Using other sync policies with on-premises sync</span></span>

<span data-ttu-id="a2272-137">È possibile utilizzare il criterio [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) per disabilitare in modo selettivo i preferiti o le impostazioni di sincronizzazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="a2272-137">The [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policy can be used to selectively disable either favorites or settings sync if desired.</span></span> <span data-ttu-id="a2272-138">Se il criterio [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) è attivo, anche la sincronizzazione locale viene disabilitata.</span><span class="sxs-lookup"><span data-stu-id="a2272-138">If the [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) policy is active, then on-premises sync is disabled as well.</span></span>  

## <span data-ttu-id="a2272-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2272-139">See also</span></span>

- [<span data-ttu-id="a2272-140">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="a2272-140">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a2272-141">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="a2272-141">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="a2272-142">Sincronizzazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="a2272-142">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
