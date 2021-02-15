---
title: Microsoft Edge ed Enterprise State Roaming
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge ed Enterprise State Roaming
ms.openlocfilehash: 6090ecfda2f792d49e452771943bc6348066a3d8
ms.sourcegitcommit: 90b8eab62edbed0e0a84780abd7d3854bf95c130
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328058"
---
# <span data-ttu-id="0bd02-103">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="0bd02-103">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="0bd02-104">Questo articolo spiega come cambia la partecipazione di Microsoft Edge all'offerta Enterprise State Roaming (ESR) per supportare meglio la sincronizzazione su piattaforme e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0bd02-104">This article explains how Microsoft Edge participation in the Enterprise State Roaming (ESR) offering is changing to better support sync across platforms and devices.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd02-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="0bd02-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="0bd02-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="0bd02-106">Introduction</span></span>

<span data-ttu-id="0bd02-107">Con Windows 10, gli utenti di [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) hanno la possibilità di sincronizzare in modo sicuro nel cloud le impostazioni dell'utente e i dati delle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bd02-107">With Windows 10, [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) users gained the ability to securely synchronize their user settings and application settings data to the cloud.</span></span> <span data-ttu-id="0bd02-108">[Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) offre agli utenti un'esperienza unificata su tutti i loro dispositivi Windows e riduce il tempo necessario per la configurazione di un nuovo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bd02-108">[Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) provides users with a unified experience across their Windows devices and reduces the time needed for configuring a new device.</span></span>

<span data-ttu-id="0bd02-109">Come parte di Microsoft Edge che adotta la piattaforma Chromium, la soluzione di sincronizzazione è ora disconnessa dal framework di sincronizzazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd02-109">As part of Microsoft Edge adopting the Chromium platform, its sync solution is now disconnected from Windows sync framework.</span></span> <span data-ttu-id="0bd02-110">Ciò influisce sulla relazione di Microsoft Edge rispetto all'offerta di ESR.</span><span class="sxs-lookup"><span data-stu-id="0bd02-110">This affects the relationship of Microsoft Edge to the ESR offering.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bd02-111">Il nuovo Microsoft Edge non partecipa all'offerta di ESR.</span><span class="sxs-lookup"><span data-stu-id="0bd02-111">The new Microsoft Edge does not participate in the ESR offering.</span></span>

## <span data-ttu-id="0bd02-112">Cosa cambia con Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="0bd02-112">What’s changing with Microsoft Edge?</span></span>

<span data-ttu-id="0bd02-113">Con il nuovo Microsoft Edge, la soluzione di sincronizzazione non è legata all'ecosistema di sincronizzazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd02-113">With the new Microsoft Edge, the sync solution isn’t tied to Windows sync ecosystem.</span></span> <span data-ttu-id="0bd02-114">Questo ci consente di offrire Microsoft Edge in tutte le piattaforme, ad esempio Windows 7, Windows 8.1, iOS, Android e macOS.</span><span class="sxs-lookup"><span data-stu-id="0bd02-114">This enables us to offer Microsoft Edge across all the platforms, such as Windows 7, Windows 8.1, iOS, Android and macOS.</span></span> <span data-ttu-id="0bd02-115">Ci consente inoltre di offrire la sincronizzazione per gli account non primari su Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd02-115">This also enables us to offer sync for non-primary accounts on Windows.</span></span> <span data-ttu-id="0bd02-116">Inoltre, possiamo distribuire Microsoft Edge a una cadenza di rilascio più frequente e flessibile rispetto a Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd02-116">In addition, we can ship Microsoft Edge at a more frequent and flexible release cadence than Windows.</span></span> <span data-ttu-id="0bd02-117">Per altre informazioni, vedi [Aggiornamenti di Windows per supportare la prossima versione di Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md).</span><span class="sxs-lookup"><span data-stu-id="0bd02-117">(For more information, see [Windows updates to support the next version of Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md).</span></span> <span data-ttu-id="0bd02-118">Tutti questi fattori hanno evidenziato la necessità di rivalutare la partecipazione di Microsoft Edge all'offerta ESR.</span><span class="sxs-lookup"><span data-stu-id="0bd02-118">All these factors highlighted the need to re-assess Microsoft Edge participation in the ESR offering.</span></span>

<span data-ttu-id="0bd02-119">ESR è inquadrato come un'offerta di prodotti Windows con la promessa di gestione dei dati dai dispositivi Windows, ma la sincronizzazione di Microsoft Edge si estende oltre i dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd02-119">ESR is framed as a Windows product offering with promises about how data from Windows devices is handled, but Microsoft Edge sync will extend beyond Windows devices.</span></span> <span data-ttu-id="0bd02-120">Inoltre, poiché i dati vengono trasferiti su questi dispositivi, risulta difficile definire l'offerta di sincronizzazione di Microsoft Edge nel contesto di ESR.</span><span class="sxs-lookup"><span data-stu-id="0bd02-120">And, as the data roams across these devices, it makes it difficult to define the Microsoft Edge sync offering in the context of ESR.</span></span> <span data-ttu-id="0bd02-121">Per semplificare il funzionamento e la gestione della sincronizzazione e per soddisfare le modifiche evidenziate, è stata presa la decisione di eliminare Microsoft Edge dall'offerta ESR.</span><span class="sxs-lookup"><span data-stu-id="0bd02-121">To simplify how sync works and is managed, and to accommodate the changes that are highlighted, a decision was made to pull Microsoft Edge out of the ESR offering.</span></span>

## <span data-ttu-id="0bd02-122">Questo significa che le imprese perderanno le capacità che avevano come parte dell'ESR?</span><span class="sxs-lookup"><span data-stu-id="0bd02-122">Does this mean Enterprises will lose the abilities they had as part of ESR?</span></span>

<span data-ttu-id="0bd02-123">No.</span><span class="sxs-lookup"><span data-stu-id="0bd02-123">No.</span></span> <span data-ttu-id="0bd02-124">Microsoft Edge continuerà a supportare la maggior parte delle funzionalità fornite nell'offerta ESR.</span><span class="sxs-lookup"><span data-stu-id="0bd02-124">Microsoft Edge will continue to support most of the abilities provided in the ESR offering.</span></span>

### <span data-ttu-id="0bd02-125">Esperienza unificata tra dispositivi e nuovo tempo di configurazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="0bd02-125">Unified experience across devices and new device configuration time</span></span>

<span data-ttu-id="0bd02-126">Quando un utente è connesso al dispositivo Windows con Azure Active Directory (account Azure AD), Microsoft Edge eredita l'identità in modo implicito al primo avvio del nuovo browser.</span><span class="sxs-lookup"><span data-stu-id="0bd02-126">When a user is signed into their windows device with an Azure Active Directory (Azure AD account), Microsoft Edge will implicitly inherit that Identity on first launch of the new browser.</span></span>

<span data-ttu-id="0bd02-127">Dopo che un utente ha acconsentito esplicitamente ad attivare la sincronizzazione nel nuovo Microsoft Edge, il browser sincronizza tutti i dati del browser, ad esempio i preferiti, le password e la cronologia.</span><span class="sxs-lookup"><span data-stu-id="0bd02-127">After a user has explicitly consented to turning on sync in the new Microsoft Edge, the browser will sync all the browser data, such as favorites, passwords, and history.</span></span> <span data-ttu-id="0bd02-128">Questo garantisce un'esperienza unificata tra i dispositivi e riduce il tempo necessario per personalizzare il browser.</span><span class="sxs-lookup"><span data-stu-id="0bd02-128">This ensures a unified experience across devices and reduces the time needed to personalize the browser.</span></span>

### <span data-ttu-id="0bd02-129">Separazione dei dati aziendali e consumer</span><span class="sxs-lookup"><span data-stu-id="0bd02-129">Separation of corporate and consumer data</span></span>

<span data-ttu-id="0bd02-130">Le organizzazioni hanno il controllo dei propri dati e non vi è alcuna combinazione di dati aziendali di un account cloud consumer o un account cloud aziendale.</span><span class="sxs-lookup"><span data-stu-id="0bd02-130">Organizations are in control of their data, and there is no mixing of corporate data in a consumer cloud account or consumer data in an enterprise cloud account.</span></span>

### <span data-ttu-id="0bd02-131">Sicurezza avanzata</span><span class="sxs-lookup"><span data-stu-id="0bd02-131">Enhanced security</span></span>

<span data-ttu-id="0bd02-132">I dati vengono crittografati automaticamente prima di lasciare il dispositivo Windows 10 dell'utente tramite Azure Information Protection e rimangono crittografati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="0bd02-132">Data is automatically encrypted before leaving the user’s Windows 10 device by using Azure Information Protection, and data stays encrypted at rest in the cloud.</span></span> <span data-ttu-id="0bd02-133">Tutti i contenuti rimangono crittografati nel cloud, fatta eccezione per gli spazi dei nomi, come i nomi delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0bd02-133">All content stays encrypted at rest in the cloud, except for the namespaces, like settings names.</span></span>

### <span data-ttu-id="0bd02-134">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="0bd02-134">Monitoring</span></span>

<span data-ttu-id="0bd02-135">Viene fornito il controllo e la visibilità per l'utente che sincronizza le impostazioni dell'organizzazione e i dispositivi utilizzati, tramite l'integrazione con il portale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0bd02-135">We will provide control and visibility over who syncs settings in your organization and on which devices through integration with the Azure AD portal.</span></span> <span data-ttu-id="0bd02-136">Questa capacità verrà abilitata in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="0bd02-136">This capability will be enabled in a future release.</span></span>

### <span data-ttu-id="0bd02-137">Gestione</span><span class="sxs-lookup"><span data-stu-id="0bd02-137">Management</span></span>

<span data-ttu-id="0bd02-138">Gli amministratori sono in grado di controllare quali membri dell'organizzazione possono abilitare la sincronizzazione. Per informazioni, vedi [Configurare la sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync) e [Criteri di gruppo per la sincronizzazione](microsoft-edge-enterprise-sync.md#sync-group-policies).</span><span class="sxs-lookup"><span data-stu-id="0bd02-138">Admins will be able to control which members in your organization can enable sync. See [Configure Microsoft Edge sync](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync) and [Sync group policies](microsoft-edge-enterprise-sync.md#sync-group-policies).</span></span> <span data-ttu-id="0bd02-139">Inoltre, gli utenti possono attivare o disattivare la sincronizzazione per ogni dispositivo, nonché attivare o disattivare singolarmente ogni attributo di dati per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bd02-139">Additionally, users can turn sync on/off for each of their devices as well as toggle each data attribute individually for sync.</span></span>

### <span data-ttu-id="0bd02-140">Gestione delle chiavi</span><span class="sxs-lookup"><span data-stu-id="0bd02-140">Key management</span></span>

<span data-ttu-id="0bd02-141">La funzionalità di sincronizzazione utilizza Azure Information Protection (AIP) per proteggere i dati sincronizzati solo per l'utente e gli amministratori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bd02-141">The synchronization feature leverages Azure Information Protection (AIP) to protect the synchronized data for only the user and the enterprise admins.</span></span> <span data-ttu-id="0bd02-142">AIP supporta sia la chiave gestita da Microsoft (impostazione predefinita) che la tua chiave per la gestione delle chiavi del cloud.</span><span class="sxs-lookup"><span data-stu-id="0bd02-142">AIP supports both Microsoft managed (default) and bring your own key for cloud-key management.</span></span> <span data-ttu-id="0bd02-143">La strategia di gestione delle chiavi del cloud utilizzata dall'organizzazione è trasparente per Microsoft Edge e non ha alcun impatto sulla funzionalità di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bd02-143">The cloud-key management strategy your organization uses is transparent to Microsoft Edge and has no impact on the synchronization feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bd02-144">[Hold your own key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) e il servizio Active Directory Rights Management Services non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0bd02-144">[Hold your own key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) and the Active Directory Rights Management Service aren't supported.</span></span>

## <span data-ttu-id="0bd02-145">Riepilogo degli attributi di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="0bd02-145">Summary of sync attributes</span></span>

<span data-ttu-id="0bd02-146">I seguenti attributi di dati verranno sincronizzati nella nuova versione di Microsoft Edge al primo avvio:</span><span class="sxs-lookup"><span data-stu-id="0bd02-146">The following data attributes will sync in the new version of Microsoft Edge at first launch:</span></span>

- <span data-ttu-id="0bd02-147">Preferiti</span><span class="sxs-lookup"><span data-stu-id="0bd02-147">Favorites</span></span>
- <span data-ttu-id="0bd02-148">Password</span><span class="sxs-lookup"><span data-stu-id="0bd02-148">Passwords</span></span>
- <span data-ttu-id="0bd02-149">Riempimento di moduli</span><span class="sxs-lookup"><span data-stu-id="0bd02-149">Form-fill</span></span>
- <span data-ttu-id="0bd02-150">Cronologia</span><span class="sxs-lookup"><span data-stu-id="0bd02-150">History</span></span>
- <span data-ttu-id="0bd02-151">Schede aperte (sessioni)</span><span class="sxs-lookup"><span data-stu-id="0bd02-151">Open tabs (sessions)</span></span>
- <span data-ttu-id="0bd02-152">Impostazioni (preferenze)</span><span class="sxs-lookup"><span data-stu-id="0bd02-152">Settings (preferences)</span></span>
- <span data-ttu-id="0bd02-153">Estensioni</span><span class="sxs-lookup"><span data-stu-id="0bd02-153">Extensions</span></span>

<span data-ttu-id="0bd02-154">L'elenco degli attributi precedente è diverso dagli attributi che possono essere sincronizzati in Microsoft Edge Legacy.</span><span class="sxs-lookup"><span data-stu-id="0bd02-154">The preceding list of attributes is different than the attributes that could be synced in Microsoft Edge Legacy.</span></span> <span data-ttu-id="0bd02-155">Per informazioni dettagliate sulle impostazioni di Microsoft Edge Legacy, vedi [Impostazioni di roaming di Windows 10](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference). Gli utenti possono abilitare o disabilitare selettivamente questi attributi usando le impostazioni di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0bd02-155">(For details about Microsoft Edge Legacy settings, see [Windows 10 roaming settings](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference).) Users can selectively enable/disable these attributes using Microsoft Edge settings.</span></span> <span data-ttu-id="0bd02-156">Data la differenza negli attributi tra le due versioni (ad esempio, la cronologia), agli utenti potrebbe essere richiesto di concedere nuovamente il consenso per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bd02-156">Given the difference in attributes between the two versions (for example, history), users might be asked to give sync consent again.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd02-157">A differenza di Microsoft Edge Legacy, il nuovo Microsoft Edge non usa Gestione credenziali di Windows per le password e di conseguenza non sincronizza le password con Internet Explorer o altre app che usano Gestione credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd02-157">Unlike Microsoft Edge Legacy, the new Microsoft Edge doesn't use Windows credential Manager for passwords and as a result, won't sync passwords with Internet Explorer or other apps that use Windows Credential manager.</span></span>

## <span data-ttu-id="0bd02-158">Condizioni per l'utilizzo del servizio</span><span class="sxs-lookup"><span data-stu-id="0bd02-158">Terms of service</span></span>

<span data-ttu-id="0bd02-159">Le condizioni per l'utilizzo del servizio di sincronizzazione Microsoft Edge rientrano nella licenza software Microsoft visualizzabile in Microsoft Edge all'indirizzo *edge://terms*.</span><span class="sxs-lookup"><span data-stu-id="0bd02-159">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span>

## <span data-ttu-id="0bd02-160">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0bd02-160">See also</span></span>

- [<span data-ttu-id="0bd02-161">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bd02-161">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="0bd02-162">Sincronizzazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0bd02-162">Microsoft Edge Sync</span></span>](microsoft-edge-enterprise-sync.md)