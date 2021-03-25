---
title: Configurare la sincronizzazione aziendale di Microsoft Edge
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Opzioni di amministratore e utente per la configurazione di Microsoft Edge per la sincronizzazione di preferiti, password e altri dati del browser.
ms.openlocfilehash: 93af96bd864f08bb17bb1d6f0669f602a56fd8ca
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448120"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a><span data-ttu-id="2b0d9-103">Configurare la sincronizzazione aziendale di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2b0d9-103">Configure Microsoft Edge enterprise sync</span></span>

<span data-ttu-id="2b0d9-104">Questo articolo spiega come gli amministratori possono configurare Microsoft Edge per sincronizzare i preferiti, le password e altri dati del browser degli utenti in tutti i dispositivi connessi.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-104">This article explains how admins can configure Microsoft Edge to sync user favorites, passwords, and other browser data across all signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0d9-105">Si applica a Microsoft Edge versione 77 o successiva, se non diversamente specificato.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-105">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="overview"></a><span data-ttu-id="2b0d9-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="2b0d9-106">Overview</span></span>

<span data-ttu-id="2b0d9-107">La sincronizzazione di Microsoft Edge consente agli utenti di accedere ai dati di esplorazione in tutti i dispositivi connessi.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="2b0d9-108">I dati supportati dalla sincronizzazione sono:</span><span class="sxs-lookup"><span data-stu-id="2b0d9-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="2b0d9-109">Preferiti</span><span class="sxs-lookup"><span data-stu-id="2b0d9-109">Favorites</span></span>
- <span data-ttu-id="2b0d9-110">Password</span><span class="sxs-lookup"><span data-stu-id="2b0d9-110">Passwords</span></span>
- <span data-ttu-id="2b0d9-111">Indirizzi e altro (riempimento di moduli)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="2b0d9-112">Raccolte</span><span class="sxs-lookup"><span data-stu-id="2b0d9-112">Collections</span></span>
- <span data-ttu-id="2b0d9-113">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="2b0d9-113">Settings</span></span>
- <span data-ttu-id="2b0d9-114">Estensione</span><span class="sxs-lookup"><span data-stu-id="2b0d9-114">Extension</span></span>
- <span data-ttu-id="2b0d9-115">Schede aperte (disponibile in Microsoft Edge versione 88)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-115">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="2b0d9-116">Cronologia (disponibile in Microsoft Edge versione 88)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-116">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="2b0d9-117">La funzionalità di sincronizzazione è abilitata tramite il consenso dell'utente e gli utenti possono attivare o disattivare la sincronizzazione per ognuno dei tipi di dati elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-117">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span> <span data-ttu-id="2b0d9-118">Se un utente riscontra un problema di sincronizzazione, potrebbe dover reimpostare la sincronizzazione in **Impostazioni** > **Profili** > **Reimposta sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-118">If a user is experiencing a sync issue they might need to reset sync in **Settings** > **Profiles** > **Reset sync**.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0d9-119">Per supportare la funzionalità di sincronizzazione vengono caricati altri dati di configurazione e connettività del dispositivo (ad esempio il nome dispositivo, la marca e il modello).</span><span class="sxs-lookup"><span data-stu-id="2b0d9-119">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b0d9-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2b0d9-120">Prerequisites</span></span>

<span data-ttu-id="2b0d9-121">La sincronizzazione di Microsoft Edge per gli account di Azure Active Directory (Azure AD) è disponibile per le sottoscrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b0d9-121">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="2b0d9-122">Azure AD Premium (P1 o P2)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-122">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="2b0d9-123">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="2b0d9-123">M365 Business Premium</span></span>
- <span data-ttu-id="2b0d9-124">Office 365 E1 e superiore</span><span class="sxs-lookup"><span data-stu-id="2b0d9-124">Office 365 E1 and above</span></span>
- <span data-ttu-id="2b0d9-125">Azure Information Protection (AIP) (P1 o P2)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-125">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="2b0d9-126">Tutti gli abbonamenti EDU (Microsoft Apps per studenti o istituti di istruzione, Exchange Online per studenti o istituti di istruzione, Office 365 A1 o versione successiva, Microsoft 365 A1 o superiore o Azure Information Protection P1 o P2 per studenti o istituti di istruzione)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-126">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <a name="sync-group-policies"></a><span data-ttu-id="2b0d9-127">Criteri di gruppo per la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="2b0d9-127">Sync group policies</span></span>

<span data-ttu-id="2b0d9-128">Gli amministratori possono usare i seguenti criteri di gruppo per configurare e gestire la sincronizzazione di Microsoft Edge:</span><span class="sxs-lookup"><span data-stu-id="2b0d9-128">Admins can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="2b0d9-129">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): disabilita completamente la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-129">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="2b0d9-130">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilita anche la sincronizzazione delle schede aperte.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-130">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="2b0d9-131">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): quando questo criterio è disabilitato, verrà disabilitata anche la sincronizzazione della cronologia.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-131">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="2b0d9-132">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): consente di configurare l'elenco dei tipi esclusi dalla sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-132">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="2b0d9-133">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): consente ai profili di Active Directory (AD) di usare lo spazio di archiviazione locale.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-133">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="2b0d9-134">Per altre informazioni, vedere [Sincronizzazione locale per gli utenti di Active Directory (AD)](./microsoft-edge-on-premises-sync.md).</span><span class="sxs-lookup"><span data-stu-id="2b0d9-134">For more information, see [On-premises sync for Active Directory (AD) users](./microsoft-edge-on-premises-sync.md).</span></span>
- <span data-ttu-id="2b0d9-135">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): attivare la sincronizzazione per default e non richiedere il consenso dell'utente per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-135">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <a name="configure-microsoft-edge-sync"></a><span data-ttu-id="2b0d9-136">Configurare Microsoft Edge Sync</span><span class="sxs-lookup"><span data-stu-id="2b0d9-136">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="2b0d9-137">Le opzioni di configurazioni per la sincronizzazione di Microsoft Edge sono disponibili tramite il servizio di Azure Information Protection (AIP).</span><span class="sxs-lookup"><span data-stu-id="2b0d9-137">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="2b0d9-138">Quando AIP è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-138">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="2b0d9-139">[Qui](/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-139">Instructions on how to enable AIP can be found [here](/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="2b0d9-140">Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AIP](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps)  per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-140">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) for those users.</span></span> <span data-ttu-id="2b0d9-141">Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-141">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="2b0d9-142">L'attivazione di Azure Information Protection consentirà inoltre ad altre applicazioni, come Microsoft Word o Microsoft Outlook, di proteggere il contenuto con AIP.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-142">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="2b0d9-143">I criteri di controllo onboarding usati per limitare la sincronizzazione Edge impediranno anche ad altre applicazioni di proteggere il contenuto tramite AIP.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-143">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a><span data-ttu-id="2b0d9-144">Microsoft Edge e Enterprise state roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="2b0d9-144">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="2b0d9-145">Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per sincronizzare i dati degli utenti in tutti i loro dispositivi e non fa più parte del roaming dello stato di Azure AD Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-145">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="2b0d9-146">Tuttavia, Microsoft Edge soddisfa le promesse per la protezione dei dati di ESR, come la possibilità di creare una chiave personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2b0d9-146">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="2b0d9-147">Per ulteriori informazioni, vedere [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span><span class="sxs-lookup"><span data-stu-id="2b0d9-147">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b0d9-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b0d9-148">See also</span></span>

- [<span data-ttu-id="2b0d9-149">Sincronizzazione di Microsoft Edge in modalità enterprise</span><span class="sxs-lookup"><span data-stu-id="2b0d9-149">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="2b0d9-150">Diagnosticare e risolvere i problemi di sincronizzazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2b0d9-150">Diagnose and fix Microsoft Edge sync issues</span></span>](microsoft-edge-troubleshoot-enterprise-sync.md)
- [<span data-ttu-id="2b0d9-151">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2b0d9-151">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="2b0d9-152">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="2b0d9-152">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)