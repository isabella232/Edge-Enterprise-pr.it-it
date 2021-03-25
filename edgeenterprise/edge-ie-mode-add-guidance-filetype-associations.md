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
# <a name="associate-file-extensions-with-internet-explorer-mode"></a>Associare le estensioni file alla modalità Internet Explorer

Questo articolo spiega come associare Microsoft Edge alla modalità Internet Explorer con estensioni di file per applicazioni desktop.

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

Avviando Edge 88, è possibile configurare collegamenti specifici per il tipo di file da aprire in modalità Internet Explorer con il [Mostra menu di scelta rapida per aprire i collegamenti in modalità Internet Explorer](./microsoft-edge-policies.md#show-context-menu-to-open-a-link-in-internet-explorer-mode). 

È possibile definire i tipi di file a cui dovrebbe essere applicata questa opzione, specificando le estensioni di file in questo criterio [Aprire file locali nell'elenco Consenti estensione file in modalità Internet Explorer](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist). 

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni sui siti configurabili](./edge-learnmore-configurable-sites-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Configurare associazioni di tipi di file](/windows/win32/shell/fa-file-types)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)