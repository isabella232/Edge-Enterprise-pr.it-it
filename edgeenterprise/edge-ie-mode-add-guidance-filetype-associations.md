---
title: Associare le estensioni file alla modalità Internet Explorer
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Associare le estensioni file alla modalità Internet Explorer
ms.openlocfilehash: 43d856a293c22d3fe115387a37c2677112a96049d5b2a2ad4c6f28cb1a56cb03
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724579"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a>Associare le estensioni file alla modalità Internet Explorer

>[!Note]
> L'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto dal 15 giugno 2022, per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Altre informazioni sono disponibili qui](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Questo articolo spiega come associare Microsoft Edge alla modalità Internet Explorer con estensioni file per le applicazioni desktop.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 86 o successiva.

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a>Indicazioni per l'associazione di estensioni di file con la modalità Internet Explorer

Le istruzioni seguenti mostrano una voce che associa Microsoft Edge alla modalità IE con tipo di file .mht. Seguire questa procedura come guida per l'impostazione di un'associazione di file.

> [!NOTE]
> È possibile impostare estensioni di file specifiche da aprire in modalità Internet Explorer per impostazione predefinita usando il criterio **Imposta file di configurazione delle associazioni predefinite**. Per altre informazioni, vedere [Criteri CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).

1. Definire un nuovo ProgID con il canale Microsoft Edge da usare per aprire con la modalità Internet Explorer. Il ProgID include il nome dell'applicazione, l'icona e il percorso completo di msedge.exe.

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

2. Configurare gli aggiornamenti della shell per passare la riga di comando necessaria per l'apertura con la modalità IE.

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. Infine, associare l'estensione file .mht con un nuovo ProgID. Aggiungere il ProgID come nome di valore, con il tipo di valore di REG_SZ.

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

Dopo aver impostato le chiavi descritte nell'esempio precedente, gli utenti vedranno un'opzione aggiuntiva nel menu **Apri con** per aprire un file con estensione .mht usando Microsoft Edge \<channel\> in modalità Internet Explorer.

## <a name="registry-example"></a>Esempio di registro di sistema

È possibile salvare il frammento di codice seguente come file con estensione .reg e importarlo nel registro di sistema.

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

## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a>Configurazione di tipi di file da aprire in modalità Internet Explorer

Avviando Edge 88, è possibile configurare collegamenti specifici per il tipo di file da aprire in modalità Internet Explorer con il [Mostra menu di scelta rapida per aprire i collegamenti in modalità Internet Explorer](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed).

È possibile definire i tipi di file a cui dovrebbe essere applicata questa opzione, specificando le estensioni di file in questo criterio [Aprire file locali nell'elenco Consenti estensione file in modalità Internet Explorer](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist). 

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni sui siti configurabili](./edge-learnmore-configurable-sites-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Configurare associazioni di tipi di file](/windows/win32/shell/fa-file-types)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)