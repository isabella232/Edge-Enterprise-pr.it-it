---
title: Associare le estensioni file alla modalità Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Associare le estensioni file alla modalità Internet Explorer
ms.openlocfilehash: 6c651499401757d9a58e697d1d019a7294bb5fa7
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447370"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a><span data-ttu-id="f0e58-103">Associare le estensioni file alla modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f0e58-103">Associate file extensions with Internet Explorer mode</span></span>

<span data-ttu-id="f0e58-104">Questo articolo spiega come associare Microsoft Edge alla modalità Internet Explorer con estensioni di file per applicazioni desktop.</span><span class="sxs-lookup"><span data-stu-id="f0e58-104">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e58-105">Questo articolo si applica a Microsoft Edge versione 86 o successiva.</span><span class="sxs-lookup"><span data-stu-id="f0e58-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a><span data-ttu-id="f0e58-106">Indicazioni per l'associazione di estensioni di file con la modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f0e58-106">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="f0e58-107">Le istruzioni seguenti mostrano una voce che associa Microsoft Edge alla modalità IE con tipo di file .mht.</span><span class="sxs-lookup"><span data-stu-id="f0e58-107">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="f0e58-108">Seguire questa procedura come guida per l'impostazione di un'associazione di file.</span><span class="sxs-lookup"><span data-stu-id="f0e58-108">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e58-109">È possibile impostare estensioni di file specifiche da aprire in modalità Internet Explorer per impostazione predefinita usando il criterio **Imposta file di configurazione delle associazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="f0e58-109">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="f0e58-110">Per altre informazioni, vedere [Criteri CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span><span class="sxs-lookup"><span data-stu-id="f0e58-110">For more information, see [Policy CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="f0e58-111">Definire un nuovo ProgID con il canale Microsoft Edge da usare per aprire con la modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f0e58-111">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="f0e58-112">Il ProgID include il nome dell'applicazione, l'icona e il percorso completo di msedge.exe.</span><span class="sxs-lookup"><span data-stu-id="f0e58-112">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

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

2. <span data-ttu-id="f0e58-113">Configurare gli aggiornamenti della shell per passare la riga di comando necessaria per l'apertura con la modalità IE.</span><span class="sxs-lookup"><span data-stu-id="f0e58-113">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="f0e58-114">Infine, associare l'estensione file .mht con un nuovo ProgID.</span><span class="sxs-lookup"><span data-stu-id="f0e58-114">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="f0e58-115">Aggiungere il ProgID come nome di valore, con il tipo di valore di REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="f0e58-115">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="f0e58-116">Dopo aver impostato le chiavi descritte nell'esempio precedente, gli utenti vedranno un'opzione aggiuntiva nel menu **Apri con** per aprire un file con estensione .mht usando Microsoft Edge \<channel\> in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f0e58-116">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <a name="registry-example"></a><span data-ttu-id="f0e58-117">Esempio di registro di sistema</span><span class="sxs-lookup"><span data-stu-id="f0e58-117">Registry Example</span></span>

<span data-ttu-id="f0e58-118">È possibile salvare il frammento di codice seguente come file con estensione .reg e importarlo nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="f0e58-118">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

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
## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a><span data-ttu-id="f0e58-119">Configurazione di tipi di file da aprire in modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f0e58-119">Configuring file types to open in Internet Explorer mode</span></span>

<span data-ttu-id="f0e58-120">Avviando Edge 88, è possibile configurare collegamenti specifici per il tipo di file da aprire in modalità Internet Explorer con il [Mostra menu di scelta rapida per aprire i collegamenti in modalità Internet Explorer](./microsoft-edge-policies.md#show-context-menu-to-open-a-link-in-internet-explorer-mode).</span><span class="sxs-lookup"><span data-stu-id="f0e58-120">Starting Edge 88, you can configure specific file type links to open in Internet Explorer mode using the policy [Show context menu to open links in Internet Explorer mode](./microsoft-edge-policies.md#show-context-menu-to-open-a-link-in-internet-explorer-mode).</span></span> 

<span data-ttu-id="f0e58-121">È possibile definire i tipi di file a cui dovrebbe essere applicata questa opzione, specificando le estensioni di file in questo criterio [Aprire file locali nell'elenco Consenti estensione file in modalità Internet Explorer](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist).</span><span class="sxs-lookup"><span data-stu-id="f0e58-121">You can define file types this option should apply to, by specifying file extensions in this policy [Open local files in Internet Explorer mode file extension allow list](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist).</span></span> 

## <a name="see-also"></a><span data-ttu-id="f0e58-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0e58-122">See also</span></span>

- [<span data-ttu-id="f0e58-123">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="f0e58-123">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="f0e58-124">Informazioni sui siti configurabili</span><span class="sxs-lookup"><span data-stu-id="f0e58-124">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="f0e58-125">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="f0e58-125">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="f0e58-126">Configurare associazioni di tipi di file</span><span class="sxs-lookup"><span data-stu-id="f0e58-126">Setting file type associations</span></span>](/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="f0e58-127">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="f0e58-127">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)