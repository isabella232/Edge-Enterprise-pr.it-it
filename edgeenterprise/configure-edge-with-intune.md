---
title: Configurare le impostazioni dei criteri di Microsoft Edge per Windows usando Microsoft Intune
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge per Windows usando Microsoft Intune.
ms.openlocfilehash: 6200b52e9061f37f85fe0bfe7cf59a2172db97df
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980158"
---
# <span data-ttu-id="82fa2-103">Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="82fa2-103">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>

<span data-ttu-id="82fa2-104">Questo articolo descrive come configurare le impostazioni dei criteri di Microsoft Edge per Windows 10 usando Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="82fa2-104">This article explains how to configure Microsoft Edge policy settings for Windows 10 using Microsoft Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="82fa2-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="82fa2-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="82fa2-106">Puoi configurare i criteri e le impostazioni di Microsoft Edge aggiungendo un profilo di configurazione del dispositivo a Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="82fa2-106">You can configure Microsoft Edge policies and settings by adding a device configuration profile to Microsoft Intune.</span></span> <span data-ttu-id="82fa2-107">L'uso di Intune per la gestione e l'applicazione dei criteri è equivalente all'uso di Criteri di gruppo di Active Directory o alla configurazione delle impostazioni di un oggetto Criteri di gruppo locale nei dispositivi utente.</span><span class="sxs-lookup"><span data-stu-id="82fa2-107">Using Intune to manage and enforce policies is equivalent to using Active Directory Group Policy or configuring local Group Policy Object (GPO) settings on user devices.</span></span>

<span data-ttu-id="82fa2-108">Per altre informazioni sulla gestione dei criteri di Microsoft Edge con Microsoft Intune, puoi leggere l'articolo [Gestire l'accesso Web usando Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge), ma tieni presente che tale articolo è specifico per Microsoft Edge versione 45 e versioni precedenti e pertanto può contenere informazioni e riferimenti che non si applicano a Microsoft Edge in modalità Enterprise versione 77 e successive.</span><span class="sxs-lookup"><span data-stu-id="82fa2-108">For more information about managing Microsoft Edge policies with Microsoft Intune, you can read [Manage web access by using Microsoft Edge with Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge), but keep in mind that the linked article is specific to Microsoft Edge version 45 and earlier and therefore may contain information and references that don't apply to Microsoft Edge Enterprise version 77 and later.</span></span>

> [!TIP]
> <span data-ttu-id="82fa2-109">Per informazioni su come configurare Microsoft Edge su macOS usando Microsoft Intune, vedi [Configurare per macOS](configure-microsoft-edge-on-mac.md).</span><span class="sxs-lookup"><span data-stu-id="82fa2-109">For information on how to configure Microsoft Edge on macOS using Microsoft Intune, see [Configure for macOS](configure-microsoft-edge-on-mac.md).</span></span>

## <span data-ttu-id="82fa2-110">Creare un profilo per gestire le impostazioni in Microsoft Edge per Windows 10</span><span class="sxs-lookup"><span data-stu-id="82fa2-110">Create a profile to manage settings in Microsoft Edge for Windows 10</span></span>

<span data-ttu-id="82fa2-111">Con i modelli amministrativi in Microsoft Intune, puoi gestire criteri di gruppo di Microsoft Edge nei dispositivi Windows 10 usando il cloud.</span><span class="sxs-lookup"><span data-stu-id="82fa2-111">Using Administrative Templates in Microsoft Intune, you can manage Microsoft Edge group policies on your Windows 10 devices using the cloud.</span></span> <span data-ttu-id="82fa2-112">Questa sezione consente di creare un modello per configurare le impostazioni dell'applicazione specifiche per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="82fa2-112">This section will help you create a template to configure Microsoft Edge-specific application settings.</span></span> <span data-ttu-id="82fa2-113">Quando crei il modello, viene creato un profilo di configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="82fa2-113">When you create the template, it creates a device configuration profile.</span></span> <span data-ttu-id="82fa2-114">Puoi quindi assegnare o distribuire questo profilo ai dispositivi Windows 10 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82fa2-114">You can then assign or deploy this profile to Windows 10 devices in your organization.</span></span>

### <span data-ttu-id="82fa2-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="82fa2-115">Prerequisites</span></span>

- <span data-ttu-id="82fa2-116">Windows 10, con i requisiti minimi di sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fa2-116">Windows 10 with the following minimum system requirements:</span></span>
  - <span data-ttu-id="82fa2-117">Windows 10, versione 1909</span><span class="sxs-lookup"><span data-stu-id="82fa2-117">Windows 10, version 1909</span></span>
  - <span data-ttu-id="82fa2-118">Windows 10, versione 1903 con [KB4512941](https://support.microsoft.com/kb/4512941) installato</span><span class="sxs-lookup"><span data-stu-id="82fa2-118">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/kb/4512941) installed</span></span>
  - <span data-ttu-id="82fa2-119">Windows 10, versione 1809 con [KB4512534](https://support.microsoft.com/kb/4512534) installato</span><span class="sxs-lookup"><span data-stu-id="82fa2-119">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/kb/4512534) installed</span></span>
  - <span data-ttu-id="82fa2-120">Windows 10, versione 1803 con [KB4512509](https://support.microsoft.com/kb/4512509) installato</span><span class="sxs-lookup"><span data-stu-id="82fa2-120">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/kb/4512509) installed</span></span>
  - <span data-ttu-id="82fa2-121">Windows 10, versione 1709 con [KB4516071](https://support.microsoft.com/kb/4516071) installato</span><span class="sxs-lookup"><span data-stu-id="82fa2-121">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/kb/4516071) installed</span></span>

### <span data-ttu-id="82fa2-122">Usare i modelli amministrativi per creare un criterio per Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="82fa2-122">Use Administrative Templates to create a policy for Microsoft Edge</span></span>

<span data-ttu-id="82fa2-123">Questa procedura consente di usare i modelli amministrativi (con cui si potrebbe avere familiarità grazie ai criteri di gruppo), integrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="82fa2-123">This procedure leverages Administrative templates (which you might be familiar with from Group Policy) that are built into Intune.</span></span> <span data-ttu-id="82fa2-124">È possibile usare questi modelli per creare un criterio per Microsoft Edge selezionando le impostazioni da un elenco già configurato.</span><span class="sxs-lookup"><span data-stu-id="82fa2-124">You can use these templates to create a policy for Microsoft Edge by selecting settings from a pre-configured list.</span></span>

1. <span data-ttu-id="82fa2-125">Accedere al portale [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="82fa2-125">Sign in to the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) portal.</span></span>
2. <span data-ttu-id="82fa2-126">Selezionare **Dispositivi** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="82fa2-126">Select **Devices** in the left-hand navigation pane.</span></span>
3. <span data-ttu-id="82fa2-127">Da **Panoramica** | **dispositivi**, selezionare **Profili di configurazione** (sotto l'intestazione del criterio).</span><span class="sxs-lookup"><span data-stu-id="82fa2-127">From **Devices** | **Overview**, select **Configuration Profiles** (under Policy heading).</span></span>
4. <span data-ttu-id="82fa2-128">Sulla barra dei comandi superiore seleziona **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-128">On the top command bar, select **Create profile**.</span></span>
5. <span data-ttu-id="82fa2-129">Nell'elenco a discesa **Piattaforma**, selezionare **Windows 10 e versioni successive**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-129">In the drop-down list below **Platform**, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="82fa2-130">Nell'elenco a discesa sotto **Profilo**, selezionare **Modelli amministrativi**, quindi fare clic sul pulsante **Crea**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-130">In the drop-down list below **Profile**, select **Administrative Templates** and then click the **Create** button.</span></span> <span data-ttu-id="82fa2-131">Lo screenshot seguente mostra gli elenchi a discesa per selezionare la piattaforma e il tipo di profilo.</span><span class="sxs-lookup"><span data-stu-id="82fa2-131">The next screenshot shows the drop-down lists to select the platform and type of profile.</span></span>

    ![Selezionare la piattaforma e il tipo di profilo](./media/configure-edge-with-intune/create-profile-platform.png)

7. <span data-ttu-id="82fa2-133">Nella scheda **Dati principali**, immettere Nome descrittivo, ad esempio criteri di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="82fa2-133">On the **Basics** tab, enter a descriptive **Name**, such as Microsoft Edge Policy.</span></span> <span data-ttu-id="82fa2-134">È facoltativo inserire una **Descrizione** del criterio.</span><span class="sxs-lookup"><span data-stu-id="82fa2-134">Optionally, enter a  **Description** for the policy.</span></span>
<span data-ttu-id="82fa2-135">Lo screenshot seguente mostra il modulo della scheda **Dati principali** e la barra dei menu indica i passaggi successivi (come schede disabilitate) per creare il profilo.</span><span class="sxs-lookup"><span data-stu-id="82fa2-135">The next screenshot shows the form for the **Basics** tab and the menu bar shows the next steps (as grayed out tabs) to create the profile.</span></span>

   ![Immettere Nome e Descrizione](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. <span data-ttu-id="82fa2-137">Seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-137">Select **Next**.</span></span>
9. <span data-ttu-id="82fa2-138">Nella scheda **Impostazioni di configurazione** selezionare la cartella Microsoft Edge in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fa2-138">On the **Configuration settings** tab, select the Microsoft Edge folder in one of the following locations:</span></span>

   - <span data-ttu-id="82fa2-139">cartella Configurazione computer</span><span class="sxs-lookup"><span data-stu-id="82fa2-139">below the Computer Configuration folder</span></span>
   - <span data-ttu-id="82fa2-140">cartella Configurazione utente.</span><span class="sxs-lookup"><span data-stu-id="82fa2-140">below the User Configuration folder.</span></span>

   <span data-ttu-id="82fa2-141">Le impostazioni disponibili per Microsoft Edge verranno visualizzate nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="82fa2-141">The available settings for Microsoft Edge will be shown on the right pane.</span></span> <span data-ttu-id="82fa2-142">Ad esempio, *Configurazione computer/Microsoft Edge/Consenti restrizioni download* come è mostrato nello screenshot seguente.</span><span class="sxs-lookup"><span data-stu-id="82fa2-142">For example, *Computer Configuration/Microsoft Edge/Allow download restrictions* shown in the following screenshot.</span></span>

   ![Scheda Impostazioni di configurazione](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > <span data-ttu-id="82fa2-144">Vedi [Microsoft Edge-Policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) e [Microsoft Edge-Update policy](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies) per l'elenco più completo e aggiornato di tutte le impostazioni disponibili per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="82fa2-144">See [Microsoft Edge – Policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) and [Microsoft Edge – Update policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies) for the most complete and up to date list of all the available settings for Microsoft Edge.</span></span>

10. <span data-ttu-id="82fa2-145">Usare il campo di ricerca ("Cerca per filtrare gli elementi...") per trovare un'opzione specifica da configurare.</span><span class="sxs-lookup"><span data-stu-id="82fa2-145">Use the search field ("Search to filter items ...") to find a specific setting you want to configure.</span></span> <span data-ttu-id="82fa2-146">In questo esempio la stringa di ricerca è "home page".</span><span class="sxs-lookup"><span data-stu-id="82fa2-146">In this example, the search string is "home page".</span></span> <span data-ttu-id="82fa2-147">Lo screenshot seguente mostra i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="82fa2-147">The next screenshot shows the search results.</span></span>

    ![Risultati ricerca](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. <span data-ttu-id="82fa2-149">Dopo aver individuato l'impostazione che si intende configurare, selezionarla per esporre i valori che è possibile impostare.</span><span class="sxs-lookup"><span data-stu-id="82fa2-149">After you find the setting you intend to configure, select it to expose the values you can set.</span></span> <span data-ttu-id="82fa2-150">Nello screenshot seguente è stato selezionato "Configura l'URL della home page" come esempio.</span><span class="sxs-lookup"><span data-stu-id="82fa2-150">In the next screenshot, we selected "Configure the home page URL" as an example.</span></span>

    ![Configurare il criterio dell'URL della home page](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. <span data-ttu-id="82fa2-152">Abilitare il criterio e immettere un valore per l'URL della home page, come illustrato nello screenshot precedente.</span><span class="sxs-lookup"><span data-stu-id="82fa2-152">Enable the policy and enter a value for the Home page URL, as shown in the previous screenshot.</span></span>

13. <span data-ttu-id="82fa2-153">Fai clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-153">Click **OK**.</span></span> <span data-ttu-id="82fa2-154">La colonna "Stato" delle impostazioni dovrebbe essere visualizzata come "Enabled", come mostrato nello screenshot seguente.</span><span class="sxs-lookup"><span data-stu-id="82fa2-154">The settings "State" column should appear as "Enabled", as shown in the following screenshot example.</span></span>

    ![Lo stato dell'impostazione è abilitato](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. <span data-ttu-id="82fa2-156">Fare clic sul pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-156">Click the **Next** button.</span></span>

15. <span data-ttu-id="82fa2-157">Nella scheda **Tag di ambito**, aggiungere un tag di ambito, se del caso, altrimenti fare clic sul pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-157">On the **Scope tags** tab, add a Scope tag if wanted, otherwise click the **Next** button.</span></span>

16. <span data-ttu-id="82fa2-158">Nella scheda **Assegnazioni**, fare clic su + Seleziona gruppi da includere per assegnare il criterio al gruppo di Azure Active Directory (Azure AD) che contiene i dispositivi o gli utenti che si desidera ricevano questa impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="82fa2-158">On the **Assignments** tab, click **+ Select groups to include** to assign this policy to the Azure Active Directory (Azure AD) group that contains the devices or the users that you want to receive this policy setting.</span></span> <span data-ttu-id="82fa2-159">Vedere [Assegnare profili utente e profili di dispositivo in Microsoft Intune](https://docs.microsoft.com/intune/device-profile-assign) per informazioni su come assegnare il profilo ai gruppi di utenti o di dispositivi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82fa2-159">See [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/device-profile-assign) for information about how to assign the profile to your Azure AD user or device groups.</span></span>

    ![Selezionare i gruppi da includere](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. <span data-ttu-id="82fa2-161">Fare clic sul pulsante **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-161">Click the **Next** button.</span></span>

18. <span data-ttu-id="82fa2-162">Nella scheda **Controlla e crea**, rivedere il riepilogo delle modifiche per assicurarsi che sia corretto e quindi fare clic sul pulsante **Crea**.</span><span class="sxs-lookup"><span data-stu-id="82fa2-162">On the **Review + create** tab, review the summary of your changes to ensure it's correct and then click the **Create** button.</span></span>

19. <span data-ttu-id="82fa2-163">Il criterio appena creato (criterio Microsoft Edge) viene mostrato nello screenshot seguente.</span><span class="sxs-lookup"><span data-stu-id="82fa2-163">The newly created policy (Microsoft Edge Policy) is shown in the following screenshot.</span></span>

    ![Selezionare i gruppi da includere](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

<span data-ttu-id="82fa2-165">Per altre informazioni sui profili di Windows 10, vedi [Usare i modelli di Windows 10 per configurare le impostazioni di Criteri di gruppo in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows).</span><span class="sxs-lookup"><span data-stu-id="82fa2-165">For more information about Windows 10 profiles, see [Use Windows 10 templates to configure group policy settings in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows).</span></span>

## <span data-ttu-id="82fa2-166">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="82fa2-166">See also</span></span>

- [<span data-ttu-id="82fa2-167">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="82fa2-167">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="82fa2-168">Gestire l'accesso Web usando Microsoft Edge con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="82fa2-168">Manage web access by using Microsoft Edge with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/manage-microsoft-edge)
- [<span data-ttu-id="82fa2-169">Usare i modelli di Windows 10 per configurare le impostazioni di Criteri di gruppo in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="82fa2-169">Use Windows 10 templates to configure group policy settings in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/administrative-templates-windows)
- [<span data-ttu-id="82fa2-170">Distribuire Microsoft Edge usando Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="82fa2-170">Deploy Microsoft Edge using Microsoft Intune</span></span>](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
