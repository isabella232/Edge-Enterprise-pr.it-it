---
title: Distribuire Microsoft Edge tramite System Center Configuration Manager
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come distribuire Microsoft Edge con System Center Configuration Manager (SCCM)
ms.openlocfilehash: be14f2db3b28b7585bfad1706b9f82209235df0a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980187"
---
# <span data-ttu-id="457f5-103">Distribuire Microsoft Edge tramite System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="457f5-103">Deploy Microsoft Edge using System Center Configuration Manager</span></span>

<span data-ttu-id="457f5-104">In questo articolo viene illustrato come automatizzare una distribuzione di Microsoft Edge tramite System Center Configuration Manager (SCCM).</span><span class="sxs-lookup"><span data-stu-id="457f5-104">This article shows you how to automate a Microsoft Edge deployment by using System Center Configuration Manager (SCCM).</span></span>

>[!NOTE]
><span data-ttu-id="457f5-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="457f5-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="457f5-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="457f5-106">Before you begin</span></span>

<span data-ttu-id="457f5-107">Leggere le informazioni in [Introduzione alla gestione delle applicazioni in Configuration Manager](https://docs.microsoft.com/sccm/apps/understand/introduction-to-application-management).</span><span class="sxs-lookup"><span data-stu-id="457f5-107">Review the information in [Introduction to application management in Configuration Manager](https://docs.microsoft.com/sccm/apps/understand/introduction-to-application-management).</span></span> <span data-ttu-id="457f5-108">Questo articolo sulla gestione delle applicazioni consente di comprendere la terminologia usata ed è una guida alla preparazione del sito per l'installazione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="457f5-108">This application management article will help you understand the terminology used in this article and is a guide to preparing your site to install applications.</span></span>

<span data-ttu-id="457f5-109">Scarica il file di installazione di Microsoft Edge in modalità Enterprise (**MicrosoftEdgeDevEnterpriseX64.msi** e/o **MicrosoftEdgeDevEnterpriseX86.msi**) nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).</span><span class="sxs-lookup"><span data-stu-id="457f5-109">Download the Microsoft Edge Enterprise installation files (**MicrosoftEdgeDevEnterpriseX64.msi** and/or **MicrosoftEdgeDevEnterpriseX86.msi**) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="457f5-110">Assicurati di archiviare i file di installazione di Microsoft Edge in un percorso di rete accessibile.</span><span class="sxs-lookup"><span data-stu-id="457f5-110">Make sure you store the Microsoft Edge installation files in an accessible network location.</span></span>

## <span data-ttu-id="457f5-111">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="457f5-111">Create the application</span></span>

<span data-ttu-id="457f5-112">Creerai l'applicazione usando una procedura guidata di Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-112">You'll create the application using a Configuration Manager wizard.</span></span>

### <span data-ttu-id="457f5-113">Avviare la Creazione guidata applicazione e creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="457f5-113">Start the Create Application Wizard and create the application</span></span>  

1. <span data-ttu-id="457f5-114">Nella console di Gestione configurazione fai clic su **Raccolta software** > **Gestione applicazioni** > **Applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="457f5-114">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>  

2. <span data-ttu-id="457f5-115">Nella scheda **Home**, nel gruppo **Crea** fai clic su **Crea applicazione**.</span><span class="sxs-lookup"><span data-stu-id="457f5-115">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span> <span data-ttu-id="457f5-116">In alternativa, fai clic con il pulsante destro del mouse su **Applicazioni** sulla barra di spostamento e quindi fai clic su **Crea applicazione**.</span><span class="sxs-lookup"><span data-stu-id="457f5-116">Or, right-click on **Applications** in the navigation bar and then click **Create Application**.</span></span>

    ![Creare l'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. <span data-ttu-id="457f5-118">Nella pagina **Generale** della **Creazione guidata applicazione** seleziona la casella di controllo **Rileva automaticamente le informazioni sull'applicazione dai file di installazione**.</span><span class="sxs-lookup"><span data-stu-id="457f5-118">On the **General** page of the **Create Application Wizard**, choose **Automatically detect information about this application from installation files**.</span></span> <span data-ttu-id="457f5-119">In questo esempio vengono pre-popolate alcune informazioni della procedura guidata con le informazioni estratte dal file di installazione msi.</span><span class="sxs-lookup"><span data-stu-id="457f5-119">This pre-populates some of the information in the wizard with information that's extracted from the installation .msi file.</span></span> <span data-ttu-id="457f5-120">Specifica le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="457f5-120">Provide the following information:</span></span>  

   - <span data-ttu-id="457f5-121">**Tipo**: scegli **Windows Installer (file \*.msi)**.</span><span class="sxs-lookup"><span data-stu-id="457f5-121">**Type**: Choose **Windows Installer (\*.msi file)**.</span></span>  

   - <span data-ttu-id="457f5-122">**Percorso**: digita il percorso (o fai clic su **Sfoglia** per selezionare il percorso) del file di installazione **MicrosoftEdgeDevEnterpriseX64.msi** o **MicrosoftEdgeDevEnterpriseX86.msi**.</span><span class="sxs-lookup"><span data-stu-id="457f5-122">**Location**: Type the location (or click **Browse** to select the location) of the installation file **MicrosoftEdgeDevEnterpriseX64.msi** or **MicrosoftEdgeDevEnterpriseX86.msi**.</span></span> <span data-ttu-id="457f5-123">Nota che il percorso deve essere specificato nella forma *\\\Server\Condivisione\File* affinché Gestione configurazione individui i file di installazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-123">Note that the location must be specified in the form *\\\Server\Share\File* for Configuration Manager to locate the installation files.</span></span>  

   <span data-ttu-id="457f5-124">La pagina **Specifica le impostazioni per l'applicazione** avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="457f5-124">Your **Specify settings for this application** page will look like the following example:</span></span>  

    ![Specifica le impostazioni per l'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. <span data-ttu-id="457f5-126">Fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-126">Click **Next**.</span></span> <span data-ttu-id="457f5-127">In **Dettagli** nella pagina **Informazioni importate** vengono visualizzate le informazioni sull'applicazione e su tutti i file associati importati.</span><span class="sxs-lookup"><span data-stu-id="457f5-127">Under **Details** on the **Imported Information** page, you'll see information about the application and any associated files that were imported.</span></span> <span data-ttu-id="457f5-128">Fai clic su **Avanti** per continuare con la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="457f5-128">Click **Next** to continue with the wizard.</span></span>  

    ![Visualizzare le informazioni importate](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. <span data-ttu-id="457f5-130">Nella pagina **Informazioni generali** puoi aggiungere altre informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-130">On the **General Information** page, you can add more information about the application.</span></span> <span data-ttu-id="457f5-131">Ad esempio, la versione del software, i commenti dell'amministratore e l'autore.</span><span class="sxs-lookup"><span data-stu-id="457f5-131">For example, Software version, Administrator comments, and Publisher.</span></span> <span data-ttu-id="457f5-132">Puoi usare queste informazioni per facilitare l'ordinamento e trovare l'applicazione nella console di Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-132">You can use this information to to help you sort and find the application in the Configuration Manager console.</span></span>

   <span data-ttu-id="457f5-133">Puoi anche usare il campo **Programma di installazione** per specificare la riga di comando completa da usare per installare l'applicazione sui PC.</span><span class="sxs-lookup"><span data-stu-id="457f5-133">You can also use the **Installation program** field to specify the full command line that will be used to install the application on PCs.</span></span> <span data-ttu-id="457f5-134">Puoi modificare questa operazione per aggiungere proprietà personalizzate, ad esempio **/q** per un'installazione automatica.</span><span class="sxs-lookup"><span data-stu-id="457f5-134">You can edit this to add your own properties (for example, **/q** for an unattended installation).</span></span>

   <span data-ttu-id="457f5-135">Nella schermata seguente viene illustrato un esempio in cui vengono usati i campi **Specifica le informazioni sull'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="457f5-135">The following screenshot shows an example where the **Specify information about this application** fields are used.</span></span>

   ![Specificare i metadati dell'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. <span data-ttu-id="457f5-137">Fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-137">Click **Next**.</span></span>
7. <span data-ttu-id="457f5-138">Nella pagina **Riepilogo** puoi verificare le impostazioni dell'applicazione in **Dettagli** e quindi uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="457f5-138">On the **Summary** page, you can confirm your application settings under **Details** and then finish using the wizard.</span></span> <span data-ttu-id="457f5-139">Fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-139">Click **Next**.</span></span>  

    ![Dettagli delle impostazioni dell'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. <span data-ttu-id="457f5-141">Nella pagina **Completamento** fai clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="457f5-141">On the **Completion** page, click **Close**.</span></span>

    ![Finestra di dialogo per l'operazione riuscita](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

<span data-ttu-id="457f5-143">Hai completato la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-143">You've finished creating the application.</span></span> <span data-ttu-id="457f5-144">Per visualizzarla in Gestione configurazione, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="457f5-144">Use the following steps to see it in Configuration Manager:</span></span>

- <span data-ttu-id="457f5-145">seleziona l'area di lavoro **Raccolta software**</span><span class="sxs-lookup"><span data-stu-id="457f5-145">select the **Software Library** workspace</span></span>
- <span data-ttu-id="457f5-146">espandi **Gestione applicazioni**</span><span class="sxs-lookup"><span data-stu-id="457f5-146">expand **Application Management**</span></span>
- <span data-ttu-id="457f5-147">fai clic su **Applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="457f5-147">click **Applications**.</span></span>

<span data-ttu-id="457f5-148">Nella schermata seguente viene illustrato l'esempio usato per questo articolo.</span><span class="sxs-lookup"><span data-stu-id="457f5-148">The following screenshot shows the example used for this article.</span></span>  

![Applicazioni](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <span data-ttu-id="457f5-150">Modificare le proprietà dell'applicazione e le impostazioni di distribuzione</span><span class="sxs-lookup"><span data-stu-id="457f5-150">Change application properties and deployment settings</span></span>

<span data-ttu-id="457f5-151">Dopo aver creato un'applicazione, puoi ottimizzare le impostazioni dell'applicazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="457f5-151">After you create an application, you can refine the application settings if you need to.</span></span> <span data-ttu-id="457f5-152">Per visualizzare le proprietà dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="457f5-152">To look at the application properties:</span></span>

- <span data-ttu-id="457f5-153">seleziona l'applicazione</span><span class="sxs-lookup"><span data-stu-id="457f5-153">select the application</span></span>
- <span data-ttu-id="457f5-154">in **Home**>**Proprietà**, fai clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="457f5-154">in **Home**>**Properties**, click **Properties**.</span></span>  

   ![Configurare le proprietà dell'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 <span data-ttu-id="457f5-156">Nella finestra di dialogo **<nome applicazione\> Proprietà applicazione** viene visualizzata una vista a schede degli elementi che puoi configurare per modificare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-156">In the **<application name\> Application Properties** dialog page, you'll see a tabbed view of the items that you can configure to change the behavior of the application.</span></span> <span data-ttu-id="457f5-157">Per altre informazioni sulle impostazioni che puoi configurare, vedi [Creare applicazioni](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications).</span><span class="sxs-lookup"><span data-stu-id="457f5-157">For more information about the settings you can configure, see [Create applications](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications).</span></span>

<span data-ttu-id="457f5-158">Per questo esempio, modificherai alcune proprietà del tipo di distribuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-158">For this example, you'll change some properties of the application's deployment type.</span></span> <span data-ttu-id="457f5-159">Per modificare le proprietà di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="457f5-159">To change the deployment properties:</span></span>

1. <span data-ttu-id="457f5-160">Fai clic sulla scheda **Tipi di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="457f5-160">Click the **Deployment Types** tab.</span></span>
2. <span data-ttu-id="457f5-161">In **Tipi di distribuzione** seleziona il **Nome** dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-161">Under **Deployment types:**, select the application **Name**</span></span>
3. <span data-ttu-id="457f5-162">Fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="457f5-162">Click **Edit**.</span></span>

   ![Modificare il tipo di distribuzione](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <span data-ttu-id="457f5-164">Aggiungere un requisito al tipo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="457f5-164">Add a requirement to the deployment type</span></span>

 <span data-ttu-id="457f5-165">I requisiti specificano le condizioni che devono essere soddisfatte prima che un'applicazione possa essere installata in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="457f5-165">Requirements specify conditions that must be met before an application is installed on a device.</span></span> <span data-ttu-id="457f5-166">Puoi scegliere tra requisiti predefiniti oppure puoi creare requisiti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="457f5-166">You can choose from built-in requirements or you can create your own.</span></span> <span data-ttu-id="457f5-167">Puoi ad esempio aggiungere un requisito in base al quale l'applicazione verrà installata solo in PC che eseguono Windows 10 **x86** o **x64**, a seconda dell'architettura del processore di destinazione del file di installazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-167">For example, you can add a requirement that the application will only be installed on PCs that are running Windows 10 **x86** or **x64**, depending on the installation file's target processor architecture.</span></span> <span data-ttu-id="457f5-168">In questo esempio, devi specificare Windows 10 **x86**.</span><span class="sxs-lookup"><span data-stu-id="457f5-168">In this example, you'll specify Windows 10 **x86**.</span></span>

1. <span data-ttu-id="457f5-169">Nella pagina delle proprietà del tipo di distribuzione aperta, fai clic sulla scheda **Requisiti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-169">From the deployment type properties page you just opened, click the **Requirements** tab.</span></span>

2. <span data-ttu-id="457f5-170">Fai clic su **Aggiungi** per aprire la finestra di dialogo **Crea requisito**.</span><span class="sxs-lookup"><span data-stu-id="457f5-170">Click **Add** to open the **Create Requirement** dialog.</span></span>

    ![Creare il requisito](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. <span data-ttu-id="457f5-172">Nella finestra di dialogo **Crea requisito** specifica le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="457f5-172">In the **Create Requirement** dialog box, specify the following information:</span></span>

    - <span data-ttu-id="457f5-173">**Categoria**: **Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="457f5-173">**Category**: **Device**</span></span>  

    - <span data-ttu-id="457f5-174">**Condizione**: **Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="457f5-174">**Condition**: **Operating system**</span></span>  

    - <span data-ttu-id="457f5-175">**Tipo di regola**: **Valore**</span><span class="sxs-lookup"><span data-stu-id="457f5-175">**Rule type**: **Value**</span></span>  

    - <span data-ttu-id="457f5-176">**Operatore**: **Uno di**</span><span class="sxs-lookup"><span data-stu-id="457f5-176">**Operator**: **One of**</span></span>  

    - <span data-ttu-id="457f5-177">Nell'elenco di sistemi operativi seleziona **Windows 10** > **Tutte le piattaforme Windows 10 (32-bit)**.</span><span class="sxs-lookup"><span data-stu-id="457f5-177">From the operating systems list, select **Windows 10** > **All Windows 10 (32-bit)**.</span></span>  

    <span data-ttu-id="457f5-178">Al termine, la finestra di dialogo sarà simile alla schermata di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="457f5-178">When you're finished, the dialog will look like the following screenshot example:</span></span>

    ![Aggiungere un requisito](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. <span data-ttu-id="457f5-180">Fai clic su **OK** per chiudere la pagina delle proprietà aperta e tornare all'elenco **Applicazioni** nella console di Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-180">Click **OK** to close each open property page and return to the **Applications** list in the Configuration Manager console.</span></span>  

## <span data-ttu-id="457f5-181">Aggiungere il contenuto dell'applicazione a un punto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="457f5-181">Add the application content to a distribution point</span></span>  

<span data-ttu-id="457f5-182">Per distribuire l'applicazione aggiornata ai PC, assicurati che il contenuto dell'applicazione venga copiato in un punto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="457f5-182">To deploy the updated application to PCs, make sure that the application content is copied to a distribution point.</span></span> <span data-ttu-id="457f5-183">I PC accedono al punto di distribuzione per installare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-183">PCs access the distribution point to install the application.</span></span>  

>[!TIP]
><span data-ttu-id="457f5-184">Per altre informazioni sui punti di distribuzione e la gestione dei contenuti in Gestione configurazione, vedi [Distribuire e gestire il contenuto per System Center Configuration Manager](https://docs.microsoft.com/sccm/core/servers/deploy/configure/deploy-and-manage-content).</span><span class="sxs-lookup"><span data-stu-id="457f5-184">To find out more about distribution points and content management in Configuration Manager, see [Deploy and manage content for System Center Configuration Manager](https://docs.microsoft.com/sccm/core/servers/deploy/configure/deploy-and-manage-content).</span></span>  

1. <span data-ttu-id="457f5-185">Nella console di Gestione configurazione fai clic su **Raccolta software**.</span><span class="sxs-lookup"><span data-stu-id="457f5-185">In the Configuration Manager console, click **Software Library**.</span></span>  

2. <span data-ttu-id="457f5-186">Nell'area di lavoro **Raccolta software** espandi **Applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="457f5-186">In the **Software Library** workspace, expand **Applications**.</span></span> <span data-ttu-id="457f5-187">Seleziona l'applicazione creata nell'elenco delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="457f5-187">Select the application you created in the list of applications.</span></span>

3. <span data-ttu-id="457f5-188">Nella scheda **Home**, nel gruppo **Distribuzione** fai clic su **Distribuisci contenuto**.</span><span class="sxs-lookup"><span data-stu-id="457f5-188">On the **Home** tab in the **Deployment** group, click **Distribute Content**.</span></span>  

4. <span data-ttu-id="457f5-189">Nella pagina **Generale** della **Distribuzione guidata contenuto** verifica che il nome dell'applicazione sia corretto e quindi fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-189">On the **General** page of the **Distribute Content Wizard**, check that the application name is correct, and then click **Next**.</span></span>  

5. <span data-ttu-id="457f5-190">Nella pagina **Contenuto** esamina le informazioni che verranno copiate nel punto di distribuzione e quindi fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-190">On the **Content** page, review the information that will be copied to the distribution point, and then click **Next**.</span></span>  

6. <span data-ttu-id="457f5-191">Nella pagina **Destinazione contenuto** fai clic su **Aggiungi** per selezionare una o più raccolte oppure uno o più punti di distribuzione o gruppi di punti di distribuzione in cui installare il contenuto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-191">On the **Content Destination** page, click **Add** to select one or more collections, distribution points, or distribution point groups on which to install the application content.</span></span>

7. <span data-ttu-id="457f5-192">Completa la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="457f5-192">Complete the wizard.</span></span>

<span data-ttu-id="457f5-193">Puoi verificare che il contenuto dell'applicazione si stato copiato in modo corretto al punto di distribuzione nell'area di lavoro **Monitoraggio**, in **Stato distribuzione** > **Stato contenuto**.</span><span class="sxs-lookup"><span data-stu-id="457f5-193">You can check that the application content was copied successfully to the distribution point from the **Monitoring** workspace, under **Distribution Status** > **Content Status**.</span></span>  

## <span data-ttu-id="457f5-194">Distribuire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="457f5-194">Deploy the application</span></span>  

<span data-ttu-id="457f5-195">Distribuisci quindi l'applicazione in una raccolta dispositivi nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="457f5-195">Next, deploy the application to a device collection in your hierarchy.</span></span> <span data-ttu-id="457f5-196">In questo esempio, l'applicazione viene distribuita nella raccolta di dispositivi **Tutti i sistemi**.</span><span class="sxs-lookup"><span data-stu-id="457f5-196">In this example, you deploy the application to the **All Systems** device collection.</span></span>  

>[!TIP]
><span data-ttu-id="457f5-197">Tieni presente che solo i computer Windows 10 con l'architettura del processore specificata installeranno l'applicazione a causa dei requisiti selezionati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="457f5-197">Remember that only Windows 10 computers of the specified processor architecture will install the application because of the requirements that you selected earlier.</span></span>  

1. <span data-ttu-id="457f5-198">Nella console di Gestione configurazione fai clic su **Raccolta software** > **Gestione applicazioni** > **Applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="457f5-198">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>

2. <span data-ttu-id="457f5-199">Nell'elenco di applicazioni, seleziona l'applicazione creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="457f5-199">From the list of applications, select the application that you created earlier.</span></span> <span data-ttu-id="457f5-200">Nella scheda **Home**, nel gruppo **Distribuzione** fai clic su **Distribuisci** o fai clic con il pulsante destro del mouse sull'applicazione e seleziona **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="457f5-200">Then, on the **Home** tab in the **Deployment** group, click **Deploy**, or right-click the application and select **Deploy**.</span></span>

    ![Distribuire l'applicazione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. <span data-ttu-id="457f5-202">Nella pagina **Generale** della **Distribuzione guidata software** fai clic su **su Sfoglia** per selezionare la raccolta di dispositivi in cui desideri distribuire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-202">On the **General** page of the **Deploy Software Wizard**, click **Browse** to select the device collection to which you want to deploy the application.</span></span>

    ![Accedere al file di installazione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. <span data-ttu-id="457f5-204">Nella pagina **Contenuto** verifica che il punto di distribuzione da cui desideri installare sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="457f5-204">On the **Content** page, check that the distribution point from which you want PCs to install the application is selected.</span></span>

    ![Specificare il punto di distribuzione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. <span data-ttu-id="457f5-206">Nella pagina **Impostazioni di distribuzione** verifica che l'azione di distribuzione sia impostata su **Installa** e che lo scopo della distribuzione sia impostato su **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="457f5-206">On the **Deployment Settings** page, make sure that the deployment action is set to **Install**, and the deployment purpose is set to **Required**.</span></span>

    ![Configurare le impostazioni di distribuzione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    ><span data-ttu-id="457f5-208">Impostando lo scopo della distribuzione su **Obbligatorio**, assicuri che l'applicazione sia installata nei PC che soddisfano i requisiti impostati.</span><span class="sxs-lookup"><span data-stu-id="457f5-208">By setting the deployment purpose to **Required**, you make sure that the application is installed on PCs that meet the requirements that you set.</span></span> <span data-ttu-id="457f5-209">Se imposti questo valore su **Disponibile**, gli utenti possono installare l'applicazione su richiesta da Software Center.</span><span class="sxs-lookup"><span data-stu-id="457f5-209">If you set this value to **Available**, then users can install the application on demand from Software Center.</span></span>  

6. <span data-ttu-id="457f5-210">Nella pagina **Pianificazione** puoi configurare il momento in cui installare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-210">On the **Scheduling** page, you can configure when the application will be installed.</span></span> <span data-ttu-id="457f5-211">Per questo esempio, seleziona **Appena possibile dopo il tempo disponibile**.</span><span class="sxs-lookup"><span data-stu-id="457f5-211">For this example, select **As soon as possible after the available time**.</span></span>

    ![Pianificare la distribuzione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. <span data-ttu-id="457f5-213">Nella pagina **Esperienza utente** seleziona in valori desiderati e quindi fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-213">On the **User Experience** page, select your desired values and click **Next**.</span></span>

    ![Specificare l'esperienza utente](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. <span data-ttu-id="457f5-215">Specifica le opzioni di avviso desiderate e fai clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="457f5-215">Specify your desired alert options and click **Next**.</span></span>

    ![Specificare le impostazioni di avviso](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. <span data-ttu-id="457f5-217">Completa la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="457f5-217">Complete the wizard.</span></span>

<span data-ttu-id="457f5-218">Usa le informazioni riportate nella sezione **Monitorare l'applicazione** seguente per visualizzare lo stato della distribuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-218">Use the information in the following **Monitor the application** section to see the status of your application deployment.</span></span>  

## <span data-ttu-id="457f5-219">Monitorare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="457f5-219">Monitor the application</span></span>

 <span data-ttu-id="457f5-220">In questa sezione puoi esaminare rapidamente lo stato dell'applicazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="457f5-220">In this section, you'll take a quick look at the deployment status of the application that you just deployed.</span></span>  

### <span data-ttu-id="457f5-221">Per esaminare lo stato di distribuzione</span><span class="sxs-lookup"><span data-stu-id="457f5-221">To review the deployment status</span></span>  

1. <span data-ttu-id="457f5-222">Nella console di Gestione configurazione fai clic su **Monitoraggio** > **Distribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="457f5-222">In the Configuration Manager console, click **Monitoring** > **Deployments**.</span></span>  

2. <span data-ttu-id="457f5-223">Nell'elenco delle distribuzioni seleziona l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="457f5-223">From the list of deployments, select the application.</span></span>

    ![Monitorare la distribuzione](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. <span data-ttu-id="457f5-225">Nella scheda **Home** fai clic su **Visualizza stato** nel gruppo **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="457f5-225">On the **Home** tab in the **Deployment** group, click **View Status**.</span></span>  

4. <span data-ttu-id="457f5-226">Seleziona una delle seguenti schede per visualizzare ulteriori aggiornamenti sullo stato della distribuzione delle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="457f5-226">Select one of the following tabs to see more status updates about the application deployment:</span></span>  

    - <span data-ttu-id="457f5-227">**Operazione riuscita**: l'applicazione è stata installata nei PC indicati.</span><span class="sxs-lookup"><span data-stu-id="457f5-227">**Success**: The application installed successfully on the indicated PCs.</span></span>  

    - <span data-ttu-id="457f5-228">**In corso**: l'installazione dell'applicazione non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="457f5-228">**In Progress**: The application has not yet finished installing.</span></span>  

    - <span data-ttu-id="457f5-229">**Errore**: si è verificato un errore durante l'installazione dell'applicazione nei PC indicati.</span><span class="sxs-lookup"><span data-stu-id="457f5-229">**Error**: An error occurred installing the application on the indicated PCs.</span></span> <span data-ttu-id="457f5-230">Vengono inoltre visualizzate altre informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="457f5-230">Further information about the error is also displayed.</span></span>  

    - <span data-ttu-id="457f5-231">**Requisiti non soddisfatti**: non è stato effettuato alcun tentativo di installazione sui dispositivi indicati perché non soddisfano i requisiti configurati (in questo esempio perché non vengono eseguiti in Windows 10).</span><span class="sxs-lookup"><span data-stu-id="457f5-231">**Requirements Not Met**: No installation attempt was made on the indicated devices because they did not meet the requirements you configured (in this example, because they do not run on Windows 10.)</span></span>

    - <span data-ttu-id="457f5-232">**Sconosciuto**: Gestione configurazione non è riuscito a segnalare lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="457f5-232">**Unknown**: Configuration Manager was unable to report the status of the deployment.</span></span> <span data-ttu-id="457f5-233">Ricontrolla in seguito.</span><span class="sxs-lookup"><span data-stu-id="457f5-233">Check back again later.</span></span>  

    >[!TIP]
    ><span data-ttu-id="457f5-234">Esistono diversi modi per monitorare le distribuzioni delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="457f5-234">There are several ways you can monitor application deployments.</span></span> <span data-ttu-id="457f5-235">Per altre informazioni, vedi [Monitorare le applicazioni dalla console di System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/monitor-applications-from-the-console).</span><span class="sxs-lookup"><span data-stu-id="457f5-235">For more information, see [Monitor applications from the System Center Configuration Manager console](https://docs.microsoft.com/sccm/apps/deploy-use/monitor-applications-from-the-console).</span></span>  

## <span data-ttu-id="457f5-236">Esperienza dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="457f5-236">End-user experience</span></span>  

<span data-ttu-id="457f5-237">Gli utenti che dispongono di PC gestiti da Gestione configurazione e che eseguono Windows 10 con l'architettura del processore specificata, ricevono un messaggio che indica la necessità di installare l'applicazione Microsoft Edge Dev.</span><span class="sxs-lookup"><span data-stu-id="457f5-237">Users who have PCs that are managed by Configuration Manager and are running Windows 10 of the specified processor architecture, will see a message telling them that they must install the Microsoft Edge Dev application.</span></span> <span data-ttu-id="457f5-238">Quando accettano questa opzione di installazione, l'applicazione viene installata.</span><span class="sxs-lookup"><span data-stu-id="457f5-238">When they accept this installation option, the application is installed.</span></span>  

## <span data-ttu-id="457f5-239">Vedi</span><span class="sxs-lookup"><span data-stu-id="457f5-239">See also</span></span>

- [<span data-ttu-id="457f5-240">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="457f5-240">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="457f5-241">Per altre informazioni su come distribuire i pacchetti MSI, vedi Creare e distribuire un'applicazione con System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="457f5-241">Create and deploy an application with System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/apps/get-started/create-and-deploy-an-application)
