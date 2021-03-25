---
title: Configurare Microsoft Edge per macOS con un file plist
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge in macOS con un file di elenco delle proprietà (con estensione plist)
ms.openlocfilehash: 3f297c11d8009c85a1bc5e17447681ee2b9ef1e2
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447450"
---
# <a name="configure-microsoft-edge-policy-settings-for-macos-using-a-plist"></a><span data-ttu-id="d4074-103">Configurare le impostazioni dei criteri di Microsoft Edge per macOS con un file di elenco delle proprietà (con estensione plist)</span><span class="sxs-lookup"><span data-stu-id="d4074-103">Configure Microsoft Edge policy settings for macOS using a .plist</span></span>

<span data-ttu-id="d4074-104">Questo articolo descrive come configurare Microsoft Edge su macOS usando un file di elenco delle proprietà (con estensione plist).</span><span class="sxs-lookup"><span data-stu-id="d4074-104">This article describes how to configure Microsoft Edge on macOS using a property list (.plist) file.</span></span> <span data-ttu-id="d4074-105">Informazioni su come creare il file e poi distribuirlo in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d4074-105">You'll learn how to create this file and then deploy it to Microsoft Intune.</span></span>

<span data-ttu-id="d4074-106">Per altre informazioni, vedi [Informazioni sui file di elenco delle proprietà di informazione](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (sito Web di Apple) e [Impostazioni di payload personalizzate](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span><span class="sxs-lookup"><span data-stu-id="d4074-106">For more information, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple's website) and [Custom payload settings](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span></span>

> [!NOTE]
> <span data-ttu-id="d4074-107">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="d4074-107">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="configure-microsoft-edge-policies-on-macos"></a><span data-ttu-id="d4074-108">Configurare i criteri di Microsoft Edge in macOS</span><span class="sxs-lookup"><span data-stu-id="d4074-108">Configure Microsoft Edge policies on macOS</span></span>

<span data-ttu-id="d4074-109">Il primo passaggio consiste nel creare un file plist.</span><span class="sxs-lookup"><span data-stu-id="d4074-109">The first step is to create your plist.</span></span> <span data-ttu-id="d4074-110">Puoi creare il file plist con qualsiasi editor di testo oppure puoi usare [Terminal per creare il profilo di configurazione](#create-a-configuration-profile-using-terminal).</span><span class="sxs-lookup"><span data-stu-id="d4074-110">You can create the plist file with any text editor or you can use [Terminal to create the configuration profile](#create-a-configuration-profile-using-terminal).</span></span> <span data-ttu-id="d4074-111">Tuttavia, è più semplice creare e modificare un file plist usando uno strumento che formatti automaticamente il codice XML.</span><span class="sxs-lookup"><span data-stu-id="d4074-111">However, it's easier to create and edit a plist file using a tool that formats the XML code for you.</span></span> <span data-ttu-id="d4074-112">*Xcode* è un ambiente di sviluppo integrato gratuito che puoi ottenere da una delle seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="d4074-112">*Xcode* is a free integrated development environment that you can get from one of the following locations:</span></span>

- [<span data-ttu-id="d4074-113">Sito Web per sviluppatori Apple</span><span class="sxs-lookup"><span data-stu-id="d4074-113">Apple developer website</span></span>](https://developer.apple.com/xcode/)
- [<span data-ttu-id="d4074-114">App Store Mac</span><span class="sxs-lookup"><span data-stu-id="d4074-114">Mac App Store</span></span>](https://apps.apple.com/app/xcode/id497799835?mt=12)

<span data-ttu-id="d4074-115">Per un elenco dei criteri supportati e dei relativi nomi chiave di preferenza, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d4074-115">For a list of supported policies and their preference key names, see [Microsoft Edge browser policies reference](microsoft-edge-policies.md).</span></span> <span data-ttu-id="d4074-116">Nel file dei modelli di criteri, che può essere scaricato dalla [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise), è disponibile un file plist di esempio (*itadminexample.plist*) nella cartella **esempi**.</span><span class="sxs-lookup"><span data-stu-id="d4074-116">In the policy templates file, which can be downloaded from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise), there's an example plist (*itadminexample.plist*) in the **examples** folder.</span></span> <span data-ttu-id="d4074-117">Il file di esempio contiene tutti i tipi di dati supportati che puoi personalizzare per definire le impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d4074-117">The example file contains all supported data types that you can customize to define your policy settings.</span></span> 

<span data-ttu-id="d4074-118">Il passaggio successivo dopo aver creato il contenuto del file plist è quello di nominarlo usando il dominio di preferenza di Microsoft Edge, ovvero *com.mcrosoft.Edge*.</span><span class="sxs-lookup"><span data-stu-id="d4074-118">The next step after you create the contents of your plist, is to name it using the Microsoft Edge preference domain, *com.microsoft.Edge*.</span></span> <span data-ttu-id="d4074-119">Il nome fa distinzione tra maiuscole e minuscole e non deve includere il canale di destinazione, perché si applica a tutti i canali Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d4074-119">The name is case sensitive and should not include the channel you are targeting because it applies to all Microsoft Edge channels.</span></span> <span data-ttu-id="d4074-120">Il nome del file plist deve essere **_com.microsoft.Edge.plist_**.</span><span class="sxs-lookup"><span data-stu-id="d4074-120">The plist file name must be **_com.microsoft.Edge.plist_**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4074-121">A partire dalla build 78.0.249.2, tutti i canali Microsoft Edge in macOS leggono dal dominio delle preferenze **com.microsoft.Edge**.</span><span class="sxs-lookup"><span data-stu-id="d4074-121">Starting with build 78.0.249.2, all Microsoft Edge channels on macOS read from the **com.microsoft.Edge** preference domain.</span></span> <span data-ttu-id="d4074-122">Tutte le versioni precedenti vengono lette da un dominio specifico, ad esempio **com.microsoft.Edge.Dev** per il canale Dev.</span><span class="sxs-lookup"><span data-stu-id="d4074-122">All prior releases read from a channel specific domain, such as **com.microsoft.Edge.Dev** for Dev channel.</span></span>

<span data-ttu-id="d4074-123">L'ultimo passaggio consiste nel distribuire il file plist nei dispositivi Mac degli utenti usando il provider MDM preferito, ad esempio Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d4074-123">The last step is to deploy your plist to your users' Mac devices using your preferred MDM provider, such as Microsoft Intune.</span></span> <span data-ttu-id="d4074-124">Per istruzioni, vedi [Distribuire il file plist](#deploy-your-plist).</span><span class="sxs-lookup"><span data-stu-id="d4074-124">For instructions see [Deploy your plist](#deploy-your-plist).</span></span>

### <a name="create-a-configuration-profile-using-terminal"></a><span data-ttu-id="d4074-125">Creare un profilo di configurazione con Terminal</span><span class="sxs-lookup"><span data-stu-id="d4074-125">Create a configuration profile using Terminal</span></span>

1. <span data-ttu-id="d4074-126">In Terminal usa il comando seguente per creare un file plist per Microsoft Edge sul desktop con le impostazioni preferite:</span><span class="sxs-lookup"><span data-stu-id="d4074-126">In Terminal, use the following command to create a plist for Microsoft Edge on your desktop with your preferred settings:</span></span>

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. <span data-ttu-id="d4074-127">Converti il file plist dal formato binario al testo normale:</span><span class="sxs-lookup"><span data-stu-id="d4074-127">Convert the plist from binary to plain text format:</span></span>

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```

<span data-ttu-id="d4074-128">Dopo la conversione del file, verifica che i dati dei criteri siano corretti e che il file contenga le impostazioni desiderate per il profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d4074-128">After converting the file verify that your policy data is correct and contains the settings you want for your configuration profile.</span></span>

> [!NOTE]
> <span data-ttu-id="d4074-129">Solo le coppie chiave-valore devono essere nel contenuto del file plist o XML.</span><span class="sxs-lookup"><span data-stu-id="d4074-129">Only key value pairs should be in the contents of the plist or xml file.</span></span> <span data-ttu-id="d4074-130">Prima di caricare il file in Intune, rimuovi tutti i valori \<plist> e \<dict> e le intestazioni XML dal file.</span><span class="sxs-lookup"><span data-stu-id="d4074-130">Prior to uploading your file into Intune remove all the \<plist> and \<dict> values, and xml headers from your file.</span></span> <span data-ttu-id="d4074-131">Il file deve contenere solo coppie chiave-valore.</span><span class="sxs-lookup"><span data-stu-id="d4074-131">The file should only contain key value pairs.</span></span>

## <a name="deploy-your-plist"></a><span data-ttu-id="d4074-132">Distribuire il file plist</span><span class="sxs-lookup"><span data-stu-id="d4074-132">Deploy your plist</span></span>

<span data-ttu-id="d4074-133">Per Microsoft Intune crea un nuovo profilo di configurazione del dispositivo destinato alla piattaforma macOS e seleziona il tipo di profilo *File delle preferenze*.</span><span class="sxs-lookup"><span data-stu-id="d4074-133">For Microsoft Intune create a new device configuration profile targeting the macOS platform and select the *Preference file* profile type.</span></span> <span data-ttu-id="d4074-134">Definisci **com.microsoft.Edge** come nome di dominio di preferenze e carica il file plist.</span><span class="sxs-lookup"><span data-stu-id="d4074-134">Target **com.microsoft.Edge** as the preference domain name and upload your plist.</span></span> <span data-ttu-id="d4074-135">Per altre informazioni, vedi [Aggiungere un file di elenco delle proprietà ai dispositivi macOS usando Microsoft Intune](/intune/configuration/preference-file-settings-macos).</span><span class="sxs-lookup"><span data-stu-id="d4074-135">For more information see [Add a property list file to macOS devices using Microsoft Intune](/intune/configuration/preference-file-settings-macos).</span></span>

<span data-ttu-id="d4074-136">Per Jamf carica il file plist come un payload *Impostazioni personalizzate*.</span><span class="sxs-lookup"><span data-stu-id="d4074-136">For Jamf upload the .plist file as a *Custom Settings* payload.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4074-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4074-137">See also</span></span>

- [<span data-ttu-id="d4074-138">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4074-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d4074-139">Configurare per macOS con Jamf</span><span class="sxs-lookup"><span data-stu-id="d4074-139">Configure for macOS with Jamf</span></span>](configure-microsoft-edge-on-mac-jamf.md)
- [<span data-ttu-id="d4074-140">Configurare per Windows</span><span class="sxs-lookup"><span data-stu-id="d4074-140">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="d4074-141">Configurare per Windows con Intune</span><span class="sxs-lookup"><span data-stu-id="d4074-141">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)