---
title: Aggiungere la modalità Internet Explorer al menu di scelta rapida Apri con
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Aggiungere la modalità Internet Explorer al menu di scelta rapida Apri con
ms.openlocfilehash: 6453cd2587e3bec10404d2491914debb999fcf3f
ms.sourcegitcommit: e3c80274a9b8ef15761c968214b3cba593476132
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168487"
---
# <span data-ttu-id="4ad84-103">Aggiungere la modalità Internet Explorer al menu di scelta rapida "Apri con"</span><span class="sxs-lookup"><span data-stu-id="4ad84-103">Add Internet Explorer mode to the "Open with" context menu</span></span>

<span data-ttu-id="4ad84-104">Questo articolo spiega come associare Microsoft Edge alla modalità Internet Explorer con estensioni di file per applicazioni desktop.</span><span class="sxs-lookup"><span data-stu-id="4ad84-104">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="4ad84-105">Questo articolo si applica a Microsoft Edge versione 86 o successiva.</span><span class="sxs-lookup"><span data-stu-id="4ad84-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="4ad84-106">Indicazioni per l'associazione di estensioni di file con la modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="4ad84-106">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="4ad84-107">Le istruzioni seguenti mostrano una voce che associa Microsoft Edge alla modalità IE con tipo di file .mht.</span><span class="sxs-lookup"><span data-stu-id="4ad84-107">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="4ad84-108">Seguire questa procedura come guida per l'impostazione di un'associazione di file.</span><span class="sxs-lookup"><span data-stu-id="4ad84-108">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="4ad84-109">È possibile impostare estensioni di file specifiche da aprire in modalità Internet Explorer per impostazione predefinita usando il criterio **Imposta file di configurazione delle associazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="4ad84-109">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="4ad84-110">Per altre informazioni, vedere [Criteri CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span><span class="sxs-lookup"><span data-stu-id="4ad84-110">For more information, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="4ad84-111">Definire un nuovo ProgID con il canale Microsoft Edge da usare per aprire con la modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ad84-111">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="4ad84-112">Il ProgID include il nome dell'applicazione, l'icona e il percorso completo di msedge.exe.</span><span class="sxs-lookup"><span data-stu-id="4ad84-112">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""
```

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"
```

2. <span data-ttu-id="4ad84-113">Configurare gli aggiornamenti della shell per passare la riga di comando necessaria per l'apertura con la modalità IE.</span><span class="sxs-lookup"><span data-stu-id="4ad84-113">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="4ad84-114">Infine, associare l'estensione file .mht con un nuovo ProgID.</span><span class="sxs-lookup"><span data-stu-id="4ad84-114">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="4ad84-115">Aggiungere il ProgID come nome di valore, con il tipo di valore di REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="4ad84-115">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="4ad84-116">Dopo aver impostato le chiavi descritte nell'esempio precedente, gli utenti vedranno un'opzione aggiuntiva nel menu **Apri con** per aprire un file con estensione .mht usando Microsoft Edge \<channel\> in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ad84-116">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <span data-ttu-id="4ad84-117">Esempio di registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4ad84-117">Registry Example</span></span>

<span data-ttu-id="4ad84-118">È possibile salvare il frammento di codice seguente come file con estensione .reg e importarlo nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4ad84-118">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

```markdown
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""

```

## <span data-ttu-id="4ad84-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad84-119">See also</span></span>

- [<span data-ttu-id="4ad84-120">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="4ad84-120">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="4ad84-121">Informazioni sui siti configurabili</span><span class="sxs-lookup"><span data-stu-id="4ad84-121">Configurable sites information</span></span>](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [<span data-ttu-id="4ad84-122">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="4ad84-122">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="4ad84-123">Configurare associazioni di tipi di file</span><span class="sxs-lookup"><span data-stu-id="4ad84-123">Setting file type associations</span></span>](https://docs.microsoft.com/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="4ad84-124">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="4ad84-124">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
