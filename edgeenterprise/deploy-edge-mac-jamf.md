---
title: Automatizzare la distribuzione di Microsoft Edge per macOS con Jamf
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Come automatizzare la distribuzione di Microsoft Edge per macOS con Jamf.
ms.openlocfilehash: 3065e4f02dbfed70b887a60b1cf076335dbff19a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980109"
---
# <span data-ttu-id="5f19d-103">Distribuire in macOS con Jamf</span><span class="sxs-lookup"><span data-stu-id="5f19d-103">Deploy to macOS with Jamf</span></span>

<span data-ttu-id="5f19d-104">Questo articolo descrive come distribuire Microsoft Edge per macOS con Jamf.</span><span class="sxs-lookup"><span data-stu-id="5f19d-104">This article describes how to deploy Microsoft Edge for macOS using Jamf.</span></span>

> [!NOTE]
> <span data-ttu-id="5f19d-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="5f19d-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="5f19d-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5f19d-106">Prerequisites</span></span>

<span data-ttu-id="5f19d-107">Prima di iniziare a distribuire Microsoft Edge, verifica che siano soddisfatti i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="5f19d-107">Before you deploy Microsoft Edge, make sure you meet the following prerequisites:</span></span>

- <span data-ttu-id="5f19d-108">Il file di installazione di Microsoft Edge, **MicrosoftEdgeDev-\<version\>pkg**, si trova in un percorso di rete accessibile.</span><span class="sxs-lookup"><span data-stu-id="5f19d-108">The Microsoft Edge installation file,  **MicrosoftEdgeDev-\<version\>.pkg** is in an accessible location on your network.</span></span> <span data-ttu-id="5f19d-109">Puoi scaricare i file di installazione per Microsoft Edge in modalità Enterprise nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).</span><span class="sxs-lookup"><span data-stu-id="5f19d-109">You can download the Microsoft Edge Enterprise installation files from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="5f19d-110">Devi disporre di un account Jamf Cloud con il livello di accesso e i privilegi necessari per creare e distribuire file di installazione nei computer.</span><span class="sxs-lookup"><span data-stu-id="5f19d-110">You have a Jamf Cloud account with the level of access and privileges needed to create and deploy installation files to computers.</span></span>

## <span data-ttu-id="5f19d-111">Per distribuire Microsoft Edge tramite Jamf:</span><span class="sxs-lookup"><span data-stu-id="5f19d-111">To deploy Microsoft Edge using Jamf:</span></span>

1. <span data-ttu-id="5f19d-112">Accedi a Jamf e vai a **Tutte le impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-112">Sign on to Jamf and go to **All Settings**.</span></span>

    ![Aprire Tutte le impostazioni](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. <span data-ttu-id="5f19d-114">In **Tutte le impostazioni** fai clic su **Gestione computer**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-114">Under **All Settings**, click **Computer Management**.</span></span>

    ![Selezionare Gestione computer](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. <span data-ttu-id="5f19d-116">In **Gestione computer** fai clic su **Pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-116">Under **Computer Management**, click **Packages**.</span></span>

    ![Selezionare Pacchetti.](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. <span data-ttu-id="5f19d-118">Nella pagina **Pacchetti** fai clic su **+ Nuovo** per aggiungere un nuovo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5f19d-118">On the **Packages** page, click **+ New** to add a new package.</span></span>

    ![Selezionare Nuovo per aggiungere un nuovo pacchetto](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. <span data-ttu-id="5f19d-120">Nella pagina **Nuovo pacchetto** immetti i dettagli relativi al pacchetto e quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-120">On the **New Package** page, enter the details about the package and then click **Save**.</span></span> <span data-ttu-id="5f19d-121">(Ad esempio NOME VISUALIZZATO, INFO o NOTE.)</span><span class="sxs-lookup"><span data-stu-id="5f19d-121">(For example, DISPLAY NAME, INFO, or NOTES.)</span></span>

    ![Seleziona Salva per salvare le informazioni sul pacchetto](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. <span data-ttu-id="5f19d-123">Seleziona **Computer** sulla barra dei menu e quindi seleziona **Criteri** sulla barra di spostamento.</span><span class="sxs-lookup"><span data-stu-id="5f19d-123">Select **Computers** on the menu bar, and then select **Policies** in the navigation bar.</span></span>

7. <span data-ttu-id="5f19d-124">Seleziona **+ Nuovo** per visualizzare il riquadro **Nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-124">Select **+ New** to display the **New Policy** pane.</span></span>

    ![Selezionare Nuovo per creare un nuovo criterio](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. <span data-ttu-id="5f19d-126">Nella scheda **Opzioni** scegliere **Generale**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-126">On the **Options** tab, select **General**.</span></span>

    - <span data-ttu-id="5f19d-127">In **NOME VISUALIZZATO** immetti il nome visualizzato per il criterio.</span><span class="sxs-lookup"><span data-stu-id="5f19d-127">Under **DISPLAY NAME**, enter the display name for the policy.</span></span>
    - <span data-ttu-id="5f19d-128">In **Attivazione** seleziona l'evento che attiverà il criterio.</span><span class="sxs-lookup"><span data-stu-id="5f19d-128">Under **Trigger**, select the event that will trigger the policy.</span></span> <span data-ttu-id="5f19d-129">Nell'esempio seguente l'evento è l'avvio.</span><span class="sxs-lookup"><span data-stu-id="5f19d-129">(In the following example, the event is Startup.)</span></span>

    ![Immettere le informazioni sulla distribuzione](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. <span data-ttu-id="5f19d-131">Nella scheda **Opzioni** fai clic su **Pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-131">On the **Options** tab, click **Packages**.</span></span>

10. <span data-ttu-id="5f19d-132">Nella finestra popup **Configura pacchetti** fai clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-132">On the **Configure Packages** popup, click **Configure**.</span></span>

    ![Configurare un pacchetto](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. <span data-ttu-id="5f19d-134">Il pacchetto aggiunto viene visualizzato nel riquadro **Pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-134">The package that you added shows on the **Packages** pane.</span></span> <span data-ttu-id="5f19d-135">Fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-135">Click **Add**.</span></span> <span data-ttu-id="5f19d-136">Per questo esempio, il pacchetto è "MicrosoftEdgeBeta" nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="5f19d-136">For this example, the package is "MicrosoftEdgeBeta" in the following screenshot.</span></span>

    ![Aggiungere un pacchetto](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. <span data-ttu-id="5f19d-138">Nella pagina **Nuovo criterio** usa gli elenchi a discesa per selezionare il **PUNTO DI DISTRIBUZIONE** e l'**AZIONE** da eseguire per il criterio.</span><span class="sxs-lookup"><span data-stu-id="5f19d-138">On the **New Policy** page, uUse the drop-down lists to select the **DISTRIBUTION POINT** and **ACTION** to take for the policy.</span></span> <span data-ttu-id="5f19d-139">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-139">Click **Save**.</span></span> <span data-ttu-id="5f19d-140">Nella schermata seguente vengono usati "Punto di distribuzione predefinito di ogni computer" e "Installa" come esempio.</span><span class="sxs-lookup"><span data-stu-id="5f19d-140">The following screenshot uses "Each computer's default distribution point" and "Install" as an example.</span></span>

    ![Selezionare il punto di distribuzione e l'azione](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. <span data-ttu-id="5f19d-142">Nella pagina **Nuovo criterio** selezionare la scheda **Ambito**. Puoi gestire l'ambito della distribuzione in base a computer oppure a utenti.</span><span class="sxs-lookup"><span data-stu-id="5f19d-142">On the **New Policy** page, select the **Scope** tab. You can manage the scope of the deployment based on computers or users.</span></span> <span data-ttu-id="5f19d-143">Per questo esempio, seleziona **Tutti i computer** nell'elenco a discesa **COMPUTER DI DESTINAZIONE** e quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-143">For this example, select **All Computers** from the **TARGET COMPUTERS** drop-down list and then click **Save**.</span></span>

    ![Selezionare l'ambito della distribuzione](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. <span data-ttu-id="5f19d-145">A questo punto puoi esaminare i criteri di distribuzione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5f19d-145">At this point you can review the Microsoft Edge deployment policy.</span></span> <span data-ttu-id="5f19d-146">Se le opzioni di distribuzione soddisfano i requisiti, fai clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5f19d-146">If the deployment options meet your requirements, click **Done**.</span></span>

    ![Fare clic su Fine.](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > <span data-ttu-id="5f19d-148">Puoi tornare a un criterio di distribuzione in qualsiasi momento per modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5f19d-148">You can return to a deployment policy at any time to change settings.</span></span>

<span data-ttu-id="5f19d-149">Complimenti.</span><span class="sxs-lookup"><span data-stu-id="5f19d-149">Congratulations!</span></span> <span data-ttu-id="5f19d-150">Hai appena finito di configurare Jamf per distribuire Microsoft Edge per macOS.</span><span class="sxs-lookup"><span data-stu-id="5f19d-150">You’ve just finished configuring Jamf to deploy Microsoft Edge for macOS.</span></span> <span data-ttu-id="5f19d-151">Quando la condizione di trigger definita è true, il pacchetto verrà distribuito ai computer specificati.</span><span class="sxs-lookup"><span data-stu-id="5f19d-151">When the trigger condition you defined is true, the package will get deployed to the computers you specified.</span></span>

## <span data-ttu-id="5f19d-152">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5f19d-152">See also</span></span>

- [<span data-ttu-id="5f19d-153">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="5f19d-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5f19d-154">Jamf.com</span><span class="sxs-lookup"><span data-stu-id="5f19d-154">Jamf.com</span></span>](https://www.jamf.com/)
- [<span data-ttu-id="5f19d-155">Integrare Jamf con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5f19d-155">Integrate Jamf with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/conditional-access-integrate-jamf)
