---
title: Effettuare il provisioning dei preferiti per Microsoft Edge
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 09/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Effettuare il provisioning dei preferiti per Microsoft Edge
ms.openlocfilehash: 67627fa10806435d76cecae00f79867bc5af03df
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447600"
---
# <a name="provision-favorites-for-microsoft-edge"></a><span data-ttu-id="afb69-103">Effettuare il provisioning dei preferiti per Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="afb69-103">Provision favorites for Microsoft Edge</span></span>

<span data-ttu-id="afb69-104">Sulla base del feedback dei clienti, sono stati apportati miglioramenti al provisioning dei preferiti.</span><span class="sxs-lookup"><span data-stu-id="afb69-104">Based on customer feedback, we've made improvements to provisioning favorites.</span></span> <span data-ttu-id="afb69-105">A partire da Microsoft Edge versione 85, gli amministratori non devono più creare manualmente un file per eseguire il provisioning dei preferiti.</span><span class="sxs-lookup"><span data-stu-id="afb69-105">Starting with Microsoft Edge version 85, Admins no longer have to manually craft a file to provision favorites.</span></span> <span data-ttu-id="afb69-106">Possono aggiungere preferiti e cartelle mediante l'interfaccia utente di Microsoft Edge per generare un file che può essere esportato in un criterio di gruppo.</span><span class="sxs-lookup"><span data-stu-id="afb69-106">Admins can add favorites and folders using the Microsoft Edge UI to generate a file that can be exported to a group policy.</span></span>

<span data-ttu-id="afb69-107">Questo articolo descrive come eseguire il provisioning di un set di preferiti e di cartelle per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afb69-107">This article describes how to provision a set of favorites and folders for your organization.</span></span> <span data-ttu-id="afb69-108">È possibile usare il criterio [Configura i Preferiti](//DeployEdge/microsoft-edge-policies#configure-favorites) per effettuare il provisioning di preferiti e cartelle.</span><span class="sxs-lookup"><span data-stu-id="afb69-108">You can use the [Configure favorites](//DeployEdge/microsoft-edge-policies#configure-favorites) policy to provision favorites and folders.</span></span>

> [!NOTE]
> <span data-ttu-id="afb69-109">Questo articolo si applica a Microsoft Edge versione 85 o successiva.</span><span class="sxs-lookup"><span data-stu-id="afb69-109">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="afb69-110">Prerequisiti e consigli</span><span class="sxs-lookup"><span data-stu-id="afb69-110">Prerequisites and recommendations</span></span>

- <span data-ttu-id="afb69-111">Microsoft Edge versione 85 con il modello amministrativo appropriato installato per i criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="afb69-111">Microsoft Edge version 85 with the appropriate administrative template installed for group policies.</span></span>
- <span data-ttu-id="afb69-112">È consigliabile usare un nuovo profilo in Microsoft Edge per effettuare il provisioning di questi preferiti.</span><span class="sxs-lookup"><span data-stu-id="afb69-112">We recommend that you use a new profile in Microsoft Edge to provision these favorites.</span></span> <span data-ttu-id="afb69-113">Tutti i preferiti salvati con il profilo verranno inclusi nell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="afb69-113">All favorites that are saved with the profile will be included in the export.</span></span>  

## <a name="provision-favorites-and-folders"></a><span data-ttu-id="afb69-114">Provisioning di preferiti e cartelle</span><span class="sxs-lookup"><span data-stu-id="afb69-114">Provision favorites and folders</span></span>

<span data-ttu-id="afb69-115">Seguire questa procedura per eseguire il provisioning di preferiti e cartelle per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="afb69-115">Use the following steps to provision favorites and folders for your users.</span></span>

1. <span data-ttu-id="afb69-116">Passare alla barra degli indirizzi di Microsoft Edge e digitare questo URL: *edge://flags/#edge-favorites-admin-export*.</span><span class="sxs-lookup"><span data-stu-id="afb69-116">Go to the Microsoft Edge address bar and type this URL: *edge://flags/#edge-favorites-admin-export*.</span></span>
2. <span data-ttu-id="afb69-117">In **Esportazione configurazione dei preferiti per gli amministratori** scegliere **Abilitato** nell'elenco a discesa e quindi fare clic su **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="afb69-117">Under **Favorites configuration export for administrators**, pick **Enabled** from the dropdown list and then click **Restart**.</span></span>

3. <span data-ttu-id="afb69-118">Passare alla pagina **Preferiti** in *edge://favorites* per aggiungere i preferiti e le cartelle di cui effettuate il provisioning.</span><span class="sxs-lookup"><span data-stu-id="afb69-118">Go to the **Favorites** page at *edge://favorites* so you can add the favorites and folders that you want to provision.</span></span>

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. <span data-ttu-id="afb69-119">Dopo aver aggiunto i preferiti e le cartelle si procederà ad esportarli, in modo che possano essere usati dal criterio **Configura i Preferiti**.</span><span class="sxs-lookup"><span data-stu-id="afb69-119">When you finish adding favorites and folders you'll export them so they can be used by the **Configure favorites** policy.</span></span> <span data-ttu-id="afb69-120">Andare alla barra degli indirizzi, passare a *edge://favorites*, fare clic sui puntini di sospensione "**…**" e scegliere **Esporta configurazione dei preferiti**.</span><span class="sxs-lookup"><span data-stu-id="afb69-120">Go to the address bar and navigate to *edge://favorites*, click the ellipsis "**…**" and choose **Export favorites configuration**.</span></span> <span data-ttu-id="afb69-121">Il prossimo screenshot mostra le opzioni disponibili durante il provisioning dei preferiti.</span><span class="sxs-lookup"><span data-stu-id="afb69-121">The next screenshot shows the options you have when provisioning favorites.</span></span>

   ![Opzioni di menu per l'uso dei preferiti.](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. <span data-ttu-id="afb69-123">In **Esporta configurazione dei preferiti** specificare un nome per la cartella che gli utenti vedranno.</span><span class="sxs-lookup"><span data-stu-id="afb69-123">Under **Export your favorites configuration** you provide a name for the folder that your users will see.</span></span> <span data-ttu-id="afb69-124">Digitare il nome della cartella e selezionare il formato della piattaforma da usare.</span><span class="sxs-lookup"><span data-stu-id="afb69-124">Type the Folder name and pick the Platform format you want to use.</span></span> <span data-ttu-id="afb69-125">Fare clic su **Copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="afb69-125">Click **Copy to clipboard**.</span></span> <span data-ttu-id="afb69-126">Lo screenshot seguente mostra il nome "Preferiti gestiti" per la cartella e la piattaforma scelta è Windows.</span><span class="sxs-lookup"><span data-stu-id="afb69-126">The next screenshot shows "Managed favorites" for the folder name and the platform is Windows.</span></span>

   ![Finestra di dialogo per l'esportazione dei preferiti in una cartella di Windows.](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. <span data-ttu-id="afb69-128">Aprire l'Editor Criteri di gruppo, passare a *Configurazione computer/Modelli amministrativi/* e scegliere **Configura i Preferiti**.</span><span class="sxs-lookup"><span data-stu-id="afb69-128">Open the Group Policy Editor, navigate to *Computer Configuration/Administrative Templates/* and pick **Configure Favorites**.</span></span> <span data-ttu-id="afb69-129">Abilitare il criterio "Configura i Preferiti".</span><span class="sxs-lookup"><span data-stu-id="afb69-129">Enable the "Configure Favorites" policy.</span></span> <span data-ttu-id="afb69-130">In **Opzioni:** incollare il contenuto esportato nell'area di testo Configura i Preferiti e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="afb69-130">Under **Options:**, paste the exported contents in the Configure favorites text area then click **Apply**.</span></span> <span data-ttu-id="afb69-131">Lo screenshot seguente mostra un esempio della cartella "Preferiti gestiti" del passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="afb69-131">The next screenshot shows an example of the "Managed favorites" folder from step 5.</span></span>

   ![Utilizzare gpedit per abilitare e configurare il criterio "Configura i Preferiti".](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. <span data-ttu-id="afb69-133">Fare clic su **OK** o su **Applica** per salvare queste impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="afb69-133">Click **OK** or **Apply** to safe the policy settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="afb69-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afb69-134">See also</span></span>

- [<span data-ttu-id="afb69-135">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="afb69-135">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)