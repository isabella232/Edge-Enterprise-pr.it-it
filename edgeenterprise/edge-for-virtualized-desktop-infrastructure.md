---
title: Edge per Virtualization Desktop Infrastructure (VDI)
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge per Virtualized Desktop Infrastructure.
ms.openlocfilehash: 5dc234b0e6fbba4778f8236399a0ff438f704578
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641852"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="93fd8-103">Microsoft Edge per Virtualized Desktop Infrastructure</span><span class="sxs-lookup"><span data-stu-id="93fd8-103">Microsoft Edge for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="93fd8-104">In questo articolo vengono descritti i requisiti e le limitazioni per Microsoft Edge in un ambiente virtualizzato.</span><span class="sxs-lookup"><span data-stu-id="93fd8-104">This article describes the requirements and limitations for using Microsoft Edge in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="93fd8-105">Che cos'è VDI?</span><span class="sxs-lookup"><span data-stu-id="93fd8-105">What is VDI?</span></span>

<span data-ttu-id="93fd8-106">Virtual Desktop Infrastructure (VDI) è una tecnologia di virtualizzazione che ospita un sistema operativo desktop e applicazioni su un server centralizzato in un data center.</span><span class="sxs-lookup"><span data-stu-id="93fd8-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="93fd8-107">Ciò consente di offrire agli utenti un'esperienza desktop completamente personalizzata con un'origine centralizzata completamente protetta e conforme.</span><span class="sxs-lookup"><span data-stu-id="93fd8-107">This enables a fully personalized desktop experience for users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="93fd8-108">Microsoft Edge può essere usato in un ambiente virtualizzato allo stesso modo che su un dispositivo locale, mentre è in esecuzione da un ambiente server sicuro e controllato.</span><span class="sxs-lookup"><span data-stu-id="93fd8-108">Microsoft Edge can be used in such a virtualized environment in much the same ways as it can be used on the local device, all the while running from secure and controlled server environment.</span></span> <span data-ttu-id="93fd8-109">A seconda della soluzione VDI scelta, è inoltre possibile consentire agli utenti di accedere facilmente alle applicazioni e ai siti Intranet.</span><span class="sxs-lookup"><span data-stu-id="93fd8-109">Depending on your chosen VDI solution it may also be possible to give your users seamless access to intranet Applications and Sites.</span></span>

<span data-ttu-id="93fd8-110">La maggior parte delle funzionalità di Edge è supportata in ambienti VDI senza alcuna configurazione particolare.</span><span class="sxs-lookup"><span data-stu-id="93fd8-110">Most features of Edge are supported on VDI environments without any special configuration.</span></span> <span data-ttu-id="93fd8-111">Tuttavia, per garantire un'esperienza ottimale, è consigliabile seguire le indicazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="93fd8-111">However, to ensure an optimal experience it’s recommended to follow the guidance below.</span></span>

## <a name="platforms-certified-for-edge"></a><span data-ttu-id="93fd8-112">Piattaforme certificate per Edge</span><span class="sxs-lookup"><span data-stu-id="93fd8-112">Platforms certified for Edge</span></span>

- <span data-ttu-id="93fd8-113">Desktop virtuale Azure</span><span class="sxs-lookup"><span data-stu-id="93fd8-113">Azure Virtual Desktop</span></span>
- <span data-ttu-id="93fd8-114">App e desktop virtuali Citrix (in precedenza noti come XenApp e XenDesktop)</span><span class="sxs-lookup"><span data-stu-id="93fd8-114">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop)</span></span>

<span data-ttu-id="93fd8-115">Sebbene altre soluzioni VDI non siano ancora state verificate dal team Edge, si ritene che i flussi di lavoro più comuni in Edge siano supportati.</span><span class="sxs-lookup"><span data-stu-id="93fd8-115">While other VDI solutions have not yet been verified by the Edge team, it is expected that the most common workflows in Edge should be supported.</span></span> <span data-ttu-id="93fd8-116">Le indicazioni fornite di seguito potrebbero o meno essere applicabili alla soluzione scelta.</span><span class="sxs-lookup"><span data-stu-id="93fd8-116">Guidance provided below may or may not be applicable to your chosen solution.</span></span>

## <a name="edge-on-vdi-performance-considerations"></a><span data-ttu-id="93fd8-117">Considerazioni sulle prestazioni di VDI su Edge</span><span class="sxs-lookup"><span data-stu-id="93fd8-117">Edge on VDI performance considerations</span></span>

<span data-ttu-id="93fd8-118">Nel progettare l'ambiente VDI, è consigliabile considerare attentamente i flussi di lavoro e le esigenze degli utenti in modo da ottenere prestazioni ottimali, nonché limiti alla configurazione del server.</span><span class="sxs-lookup"><span data-stu-id="93fd8-118">When designing your VDI environment you should carefully consider the workflows and needs of your users to achieve optimal performance, as well as the limits of your server configuration.</span></span>

<span data-ttu-id="93fd8-119">Edge consiglia i seguenti requisiti minimi per la distribuzione di Edge in ambienti VDI:</span><span class="sxs-lookup"><span data-stu-id="93fd8-119">Edge recommends the following minimal requirements for deploying Edge to VDI environments:</span></span>

- <span data-ttu-id="93fd8-120">vCPU: 2-4 Core per utente</span><span class="sxs-lookup"><span data-stu-id="93fd8-120">vCPU – 2-4 Cores per User</span></span>
- <span data-ttu-id="93fd8-121">RAM: 1 GB per utente</span><span class="sxs-lookup"><span data-stu-id="93fd8-121">RAM – 1 GB per User</span></span>

<span data-ttu-id="93fd8-122">Tenere presente che le estensioni e le applicazioni Web complesse di grandi dimensioni richiedono maggiore memoria e devono essere gestite durante la configurazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="93fd8-122">Please note that large complex web applications and extensions will require more memory and will have to be accounted for when configuring your environment.</span></span>

## <a name="edge-on-non-persisted-vdi-environments"></a><span data-ttu-id="93fd8-123">Edge in ambienti VDI non persistenti</span><span class="sxs-lookup"><span data-stu-id="93fd8-123">Edge on non-persisted VDI environments</span></span>

<span data-ttu-id="93fd8-124">Molte soluzioni VDI consentono l'accesso agli ambienti persistenti. All’interno di questi ultimi, agli utenti viene assegnato un ambiente virtuale che persiste tra una sessione e l’altra e ambienti non persistenti, in cui gli utenti vengono assegnati a uno dei computer disponibili, probabilmente a un computer diverso per ogni sessione. È possibile sincronizzare o meno i dati degli utenti tra una sessione e l’altra.</span><span class="sxs-lookup"><span data-stu-id="93fd8-124">Many VDI solutions allow access to persisted environments, where users are assigned a virtual environment that persists between sessions, and non-persisted environments, where users are assigned to one of several available machines, possibly a different machine each session, user data may or may not sync between sessions.</span></span>

<span data-ttu-id="93fd8-125">Quando si utilizza un ambiente non persistente, in genere viene creata un’"immagine di riferimento" che viene usata per ogni dispositivo che include le app e le configurazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="93fd8-125">When using a non-persisted environment, one usually creates a “golden image” which is used for each device that includes the needed apps and configurations.</span></span> <span data-ttu-id="93fd8-126">Di seguito sono riportati i suggerimenti per la preparazione di Edge per un'immagine di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="93fd8-126">Below are our recommendations for preparing Edge for such an image.</span></span>

### <a name="deploy-edge"></a><span data-ttu-id="93fd8-127">Distribuire Edge</span><span class="sxs-lookup"><span data-stu-id="93fd8-127">Deploy Edge</span></span>

<span data-ttu-id="93fd8-128">Se si utilizza Windows 10, versione 1803 e successive, è necessario aver installato Microsoft Edge sul sistema.</span><span class="sxs-lookup"><span data-stu-id="93fd8-128">If you are on Windows 10, version 1803 and above, you should have Microsoft Edge installed on your system.</span></span> <span data-ttu-id="93fd8-129">Tuttavia, se si utilizza una versione precedente di Windows o si desidera distribuire un canale diverso di Edge, è consigliabile seguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="93fd8-129">However, if you are on an older version of Windows or wish to deploy a different channel of Edge, the following steps are recommended.</span></span>

1. <span data-ttu-id="93fd8-130">Scaricare il pacchetto MSI di Edge corrispondente al sistema operativo della macchina virtuale di VDI da:</span><span class="sxs-lookup"><span data-stu-id="93fd8-130">Download the Edge MSI package matching your VDI VM operating system from:</span></span>

    - [<span data-ttu-id="93fd8-131">Scaricare Microsoft Edge for Business - Microsoft</span><span class="sxs-lookup"><span data-stu-id="93fd8-131">Download Microsoft Edge for Business - Microsoft</span></span>](https://www.microsoft.com/edge/business/download)

2. <span data-ttu-id="93fd8-132">Installare il file MSI nella macchina virtuale di VDI eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="93fd8-132">Install the MSI to the VDI VM by running the following command:</span></span>

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a><span data-ttu-id="93fd8-133">Disabilitare gli aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="93fd8-133">Disable automatic updates</span></span>

<span data-ttu-id="93fd8-134">Per gli ambienti non persistenti è consigliabile disabilitare gli aggiornamenti automatici e aggiornare Edge eseguendo l’aggiornamento dell’“immagine di riferimento” per assicurarsi che non vi siano versioni non corrispondenti tra il pool di computer.</span><span class="sxs-lookup"><span data-stu-id="93fd8-134">For non-persisted machines it is best practice to disable automatic updates and instead update Edge by updating the “golden image” to ensure that there are no version mismatches among the pool of machines.</span></span>

<span data-ttu-id="93fd8-135">Per disabilitare gli aggiornamenti automatici, vedere i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="93fd8-135">See the following policies for disabling automatic updates:</span></span>

- [<span data-ttu-id="93fd8-136">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="93fd8-136">Update policy override default</span></span>](/deployedge/microsoft-edge-update-policies#updatedefault)

- [<span data-ttu-id="93fd8-137">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="93fd8-137">Update policy override</span></span>](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a><span data-ttu-id="93fd8-138">Gestione del profilo</span><span class="sxs-lookup"><span data-stu-id="93fd8-138">Profile management</span></span>

<span data-ttu-id="93fd8-139">Nelle configurazioni non persistenti è importante considerare che le macchine virtuali potrebbero non mantenere lo stato utente tra le sessioni o che gli utenti potrebbero essere assegnati a una macchina virtuale che non hanno mai usato prima e, di conseguenza, non disporre dei relativi dati utente.</span><span class="sxs-lookup"><span data-stu-id="93fd8-139">On non-persisted setups it is important to consider that VMs may not maintain user state between sessions or users may be assigned a VM they have never used before and as such has none of their user data.</span></span>

<span data-ttu-id="93fd8-140">Edge supporta diversi metodi per la sincronizzazione dei dati utente in modo che questi siano disponibili indipendentemente dalla modalità di accesso a Edge.</span><span class="sxs-lookup"><span data-stu-id="93fd8-140">Edge supports several methods for syncing user data such that it is available regardless of how they are accessing Edge.</span></span>

### <a name="azure-ad-sync"></a><span data-ttu-id="93fd8-141">Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="93fd8-141">Azure AD Sync</span></span>

<span data-ttu-id="93fd8-142">Se il piano di Azure AD lo supporta, la sincronizzazione aziendale è il metodo più rapido e semplice per garantire che i dati degli utenti Edge siano sincronizzati su tutti i dispositivi utente.</span><span class="sxs-lookup"><span data-stu-id="93fd8-142">If your Azure AD plan supports it, Enterprise sync is the fastest and easiest method to ensure that Edge user data is synced to all user devices.</span></span>  

<span data-ttu-id="93fd8-143">Per ulteriori informazioni sui requisiti e sulla configurazione, vedere quanto segue.</span><span class="sxs-lookup"><span data-stu-id="93fd8-143">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="93fd8-144">Configurare la sincronizzazione aziendale di Microsoft Edge | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="93fd8-144">Configure Microsoft Edge enterprise sync | Microsoft Docs</span></span>](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a><span data-ttu-id="93fd8-145">Sincronizzazione locale per gli utenti di Active Directory</span><span class="sxs-lookup"><span data-stu-id="93fd8-145">On-premise Sync for Active Directory Users</span></span>

<span data-ttu-id="93fd8-146">Con la sincronizzazione locale, Microsoft Edge salva i preferiti e le impostazioni di un utente di Active Directory in un file che può essere facilmente spostato da un computer all’altro.</span><span class="sxs-lookup"><span data-stu-id="93fd8-146">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can easily be moved between different computers.</span></span>  

<span data-ttu-id="93fd8-147">Per ulteriori informazioni sui requisiti e sulla configurazione, vedere quanto segue.</span><span class="sxs-lookup"><span data-stu-id="93fd8-147">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="93fd8-148">Sincronizzazione locale per gli utenti di Active Directory (AD) | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="93fd8-148">On-premises sync for Active Directory (AD) users | Microsoft Docs</span></span>](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a><span data-ttu-id="93fd8-149">Reindirizzamento profilo utente</span><span class="sxs-lookup"><span data-stu-id="93fd8-149">User Profile Redirection</span></span>  

<span data-ttu-id="93fd8-150">Esistono diverse soluzioni per la migrazione e il reindirizzamento dell'intera cartella utente in modo da garantire il mantenimento del contesto utente in tali ambienti non persistenti.</span><span class="sxs-lookup"><span data-stu-id="93fd8-150">There are several solutions for migrating and redirecting the entire user folder to ensure that user context is maintained in such non-persisted environments.</span></span> <span data-ttu-id="93fd8-151">Contattare il provider VDI per determinare la soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="93fd8-151">Check with your VDI provider to determine the recommended solution.</span></span>

<span data-ttu-id="93fd8-152">Alcune tra soluzioni più popolari includono:</span><span class="sxs-lookup"><span data-stu-id="93fd8-152">Some popular solutions include:</span></span>

- [<span data-ttu-id="93fd8-153">Panoramica di FSLogix - FSLogix | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="93fd8-153">FSLogix Overview - FSLogix | Microsoft Docs</span></span>](/fslogix/overview)
- [<span data-ttu-id="93fd8-154">Come configurare la gestione del profilo Citrix</span><span class="sxs-lookup"><span data-stu-id="93fd8-154">How to Configure Citrix Profile Management</span></span>](https://support.citrix.com/article/CTX222893)

<span data-ttu-id="93fd8-155">Quando si utilizza questo metodo, è inoltre consigliabile escludere dalla cartella utente di cui è stato eseguito il backup cartelle non necessarie, in modo da ridurre i tempi di caricamento iniziali durante l’accesso degli utenti a tale computer e la migrazione del profilo.</span><span class="sxs-lookup"><span data-stu-id="93fd8-155">It is also may be recommended that when using this method unnecessary folders be excluded from the backed-up user folder to reduce initial loading times when users are logging on to a machine and the profile is being migrated.</span></span> <span data-ttu-id="93fd8-156">In tal caso, è consigliabile escludere dal backup le cartelle seguenti per ridurne le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="93fd8-156">If so, we recommend the following folders be excluded from your backup to reduce size.</span></span>

- <span data-ttu-id="93fd8-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span><span class="sxs-lookup"><span data-stu-id="93fd8-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span></span>
- <span data-ttu-id="93fd8-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span><span class="sxs-lookup"><span data-stu-id="93fd8-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span></span>
- <span data-ttu-id="93fd8-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span><span class="sxs-lookup"><span data-stu-id="93fd8-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span></span>
- <span data-ttu-id="93fd8-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span><span class="sxs-lookup"><span data-stu-id="93fd8-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span></span>

## <a name="known-issues"></a><span data-ttu-id="93fd8-161">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="93fd8-161">Known issues</span></span>

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a><span data-ttu-id="93fd8-162">Microsoft Edge si arresta in modo anomalo nelle versioni precedenti di XenApp e XenDesktop</span><span class="sxs-lookup"><span data-stu-id="93fd8-162">Microsoft Edge crashes in older versions of XenApp and XenDesktop</span></span>

<span data-ttu-id="93fd8-163">È necessario risolvere tale problema nelle versioni più recenti. Tuttavia, se si verifica questo problema all’interno dell'ambiente, è possibile risolvere il problema disabilitando gli hook dell’API Citrix per Edge. Vedere [ Come disabilitare gli hook dell’API Citrix in base alle singole applicazioni.](https://support.citrix.com/article/CTX107825)</span><span class="sxs-lookup"><span data-stu-id="93fd8-163">This issue should be mitigated in newer versions however if you are encountering this issue in your environment, you can work around the issue by disabling Citrix API Hooks for Edge, see [How to Disable Citrix API Hooks on a Per-application Basis.](https://support.citrix.com/article/CTX107825)</span></span>

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a><span data-ttu-id="93fd8-164">Prestazioni ridotte durante il rendering delle pagine contenenti tabelle HTML eccezionalmente grandi</span><span class="sxs-lookup"><span data-stu-id="93fd8-164">Degraded performance when rendering pages with exceptionally large HTML tables</span></span>

<span data-ttu-id="93fd8-165">I criteri Citrix seguenti sono noti per rallentare il rendering delle pagine HTML contenenti tabelle di grandi dimensioni (oltre 30.000 righe).</span><span class="sxs-lookup"><span data-stu-id="93fd8-165">The following Citrix policies are known to slow rendering of html pages with very large (30,000+ row) tables.</span></span>

- <span data-ttu-id="93fd8-166">Visualizzazione automatica della tastiera</span><span class="sxs-lookup"><span data-stu-id="93fd8-166">Automatic keyboard display</span></span>
- <span data-ttu-id="93fd8-167">Eseguire in remoto la casella combinata</span><span class="sxs-lookup"><span data-stu-id="93fd8-167">Remote the combo box</span></span>

<span data-ttu-id="93fd8-168">Per ulteriori informazioni, vedere [Impostazioni dei criteri per l'esperienza su dispositivo mobile (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html).</span><span class="sxs-lookup"><span data-stu-id="93fd8-168">See [Mobile experience policy settings (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) for more information.</span></span> <span data-ttu-id="93fd8-169">La disabilitazione di questi criteri dovrebbe risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="93fd8-169">Disabling these policies should mitigate the issue.</span></span>

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a><span data-ttu-id="93fd8-170">Scenari di autorizzazione di Windows Account manager (ad esempio, sincronizzazione di Azure) hanno esito negativo in Edge quando questo viene eseguito come un’applicazione seamless Citrix</span><span class="sxs-lookup"><span data-stu-id="93fd8-170">Windows Account Manager authorization scenarios (i.e.  Azure sync) fail in Edge when run as a Citrix seamless application</span></span>

<span data-ttu-id="93fd8-171">Si tratta di un problema noto in Edge e in altre applicazioni che utilizzano WAM (ad esempio Office) a causa dei componenti Windows necessari a tali scenari non inizializzati durante l'esecuzione in modalità "seamless".</span><span class="sxs-lookup"><span data-stu-id="93fd8-171">This is a known issue in Edge and other applications that use WAM (i.e. Office) due to Windows components necessary for such scenarios not being initialized when running in the “seamless” mode.</span></span> <span data-ttu-id="93fd8-172">Per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="93fd8-172">To work around this issue:</span></span>

- <span data-ttu-id="93fd8-173">Usare Edge tramite desktop remoto per l'host Citrix anziché come applicazione seamless remota.</span><span class="sxs-lookup"><span data-stu-id="93fd8-173">Use Edge via a Remote Desktop to the Citrix Host instead of as a seamless remote application.</span></span>
- <span data-ttu-id="93fd8-174">Usare invece le app remote del Desktop virtuale Azure, che dispongono di una prevenzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="93fd8-174">Use Azure Virtual Desktop remote apps instead, which has mitigation's for this issue.</span></span>
