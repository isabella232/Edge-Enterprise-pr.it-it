---
title: Associare le estensioni file alla modalità Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Associare le estensioni file alla modalità Internet Explorer
ms.openlocfilehash: c027b11e426cd665cb9e6cc25b4c9f66a0c6762a
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617456"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a><span data-ttu-id="61d99-103">Associare le estensioni file alla modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="61d99-103">Associate file extensions with Internet Explorer mode</span></span>

>[!Note]
> <span data-ttu-id="61d99-104">L'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto dal 15 giugno 2022, per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549).</span><span class="sxs-lookup"><span data-stu-id="61d99-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="61d99-105">Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="61d99-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="61d99-106">[Altre informazioni sono disponibili qui](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span><span class="sxs-lookup"><span data-stu-id="61d99-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="61d99-107">Questo articolo spiega come associare Microsoft Edge alla modalità Internet Explorer con estensioni file per le applicazioni desktop.</span><span class="sxs-lookup"><span data-stu-id="61d99-107">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="61d99-108">Questo articolo si applica a Microsoft Edge versione 86 o successiva.</span><span class="sxs-lookup"><span data-stu-id="61d99-108">This article applies to Microsoft Edge version 86 or later.</span></span>

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a><span data-ttu-id="61d99-109">Indicazioni per l'associazione di estensioni di file con la modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="61d99-109">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="61d99-110">Le istruzioni seguenti mostrano una voce che associa Microsoft Edge alla modalità IE con tipo di file .mht.</span><span class="sxs-lookup"><span data-stu-id="61d99-110">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="61d99-111">Seguire questa procedura come guida per l'impostazione di un'associazione di file.</span><span class="sxs-lookup"><span data-stu-id="61d99-111">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="61d99-112">È possibile impostare estensioni di file specifiche da aprire in modalità Internet Explorer per impostazione predefinita usando il criterio **Imposta file di configurazione delle associazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="61d99-112">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="61d99-113">Per altre informazioni, vedere [Criteri CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span><span class="sxs-lookup"><span data-stu-id="61d99-113">For more information, see [Policy CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="61d99-114">Definire un nuovo ProgID con il canale Microsoft Edge da usare per aprire con la modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="61d99-114">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="61d99-115">Il ProgID include il nome dell'applicazione, l'icona e il percorso completo di msedge.exe.</span><span class="sxs-lookup"><span data-stu-id="61d99-115">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

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

2. <span data-ttu-id="61d99-116">Configurare gli aggiornamenti della shell per passare la riga di comando necessaria per l'apertura con la modalità IE.</span><span class="sxs-lookup"><span data-stu-id="61d99-116">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="61d99-117">Infine, associare l'estensione file .mht con un nuovo ProgID.</span><span class="sxs-lookup"><span data-stu-id="61d99-117">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="61d99-118">Aggiungere il ProgID come nome di valore, con il tipo di valore di REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="61d99-118">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="61d99-119">Dopo aver impostato le chiavi descritte nell'esempio precedente, gli utenti vedranno un'opzione aggiuntiva nel menu **Apri con** per aprire un file con estensione .mht usando Microsoft Edge \<channel\> in modalità Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="61d99-119">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <a name="registry-example"></a><span data-ttu-id="61d99-120">Esempio di registro di sistema</span><span class="sxs-lookup"><span data-stu-id="61d99-120">Registry Example</span></span>

<span data-ttu-id="61d99-121">È possibile salvare il frammento di codice seguente come file con estensione .reg e importarlo nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="61d99-121">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

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

## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a><span data-ttu-id="61d99-122">Configurazione di tipi di file da aprire in modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="61d99-122">Configuring file types to open in Internet Explorer mode</span></span>

<span data-ttu-id="61d99-123">Avviando Edge 88, è possibile configurare collegamenti specifici per il tipo di file da aprire in modalità Internet Explorer con il [Mostra menu di scelta rapida per aprire i collegamenti in modalità Internet Explorer](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed).</span><span class="sxs-lookup"><span data-stu-id="61d99-123">Starting Edge 88, you can configure specific file type links to open in Internet Explorer mode using the policy [Show context menu to open links in Internet Explorer mode](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed).</span></span>

<span data-ttu-id="61d99-124">È possibile definire i tipi di file a cui dovrebbe essere applicata questa opzione, specificando le estensioni di file in questo criterio [Aprire file locali nell'elenco Consenti estensione file in modalità Internet Explorer](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist).</span><span class="sxs-lookup"><span data-stu-id="61d99-124">You can define file types this option should apply to, by specifying file extensions in this policy [Open local files in Internet Explorer mode file extension allow list](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist).</span></span> 

## <a name="see-also"></a><span data-ttu-id="61d99-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61d99-125">See also</span></span>

- [<span data-ttu-id="61d99-126">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="61d99-126">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="61d99-127">Informazioni sui siti configurabili</span><span class="sxs-lookup"><span data-stu-id="61d99-127">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="61d99-128">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="61d99-128">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="61d99-129">Configurare associazioni di tipi di file</span><span class="sxs-lookup"><span data-stu-id="61d99-129">Setting file type associations</span></span>](/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="61d99-130">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="61d99-130">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)