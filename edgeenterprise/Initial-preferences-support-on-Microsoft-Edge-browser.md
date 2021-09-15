---
title: Supporto delle preferenze iniziali Microsoft Edge browser
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/27/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Supporto delle preferenze iniziali Microsoft Edge browser.
ms.openlocfilehash: 7a497fd2f3305b0c027a396936ef86bacbcb5b20
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979818"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>Configurare Microsoft Edge scegliendo le impostazioni delle Preferenze iniziali per la prima esecuzione

Usa le informazioni seguenti per configurare Microsoft Edge preferenze iniziali nei dispositivi Windows dispositivi.

> [!Note]
> Questo articolo si applica Microsoft Edge versione 93 o successiva.

## <a name="configure-policy-settings-on-windows"></a>Configurare le impostazioni dei criteri in Windows

A partire Microsoft Edge versione 93, Microsoft supporta un numero limitato di preferenze iniziali, in precedenza denominate "Preferenze principali", per aiutare gli amministratori a configurare i browser per la prima esecuzione; vedi l'elenco delle impostazioni supportate di seguito.  

Quando viene distribuito, le preferenze iniziali fungono da impostazioni predefinite del browser nei dispositivi gestiti. queste sono le impostazioni preferite dagli amministratori per essere usate come predefinite, ma che possono essere modificate dagli utenti o non sono disponibili per alcuni dispositivi in quanto non sono aggiunti a un dominio di Active Directory®.

Alcuni esempi di impostazioni delle preferenze iniziali includono la configurazione iniziale di una home page predefinita o di schede con URL specifici.

Le preferenze vengono copiate dal file initial_preferences una sola volta e qualsiasi modifica apportata a questo file dopo la configurazione non verrà rispettata. Se un'impostazione viene gestita da un criterio [Microsoft Edge](/deployedge/microsoft-edge-policies) e configurata nel file initial_preferences, il criterio ha sempre la precedenza.

Di seguito è riportato l'elenco delle impostazioni delle preferenze attualmente supportate da Microsoft Edge:

| Categoria Preferenze | Impostazione |
| - | - |
| Bookmark_bar | show_apps_shortcut<br>show_managed_bookmarks<br>show_on_all_tabs |
| Bookmarks | editing_enabled |
| Browser/clear_data | browsing_history<br>browsing_history_basic"<br>cache<br>cache_basic<br>cookie<br>download_history<br>form_data<br>password |
| Cronologia | browsing_history<br>cache<br>cookie<br>download_history<br>form_data<br>hosted_apps_data<br>password<br>site_settings |
| Browser | first_run_tabs<br>dark_theme<br>show_toolbar_bookmarks_button<br>show_toolbar_collections_butto<br>show_toolbar_downloads_button<br>show_home_button<br>show_prompt_before_closing_tabs<br>show_toolbar_history_button |
| default_search_provider | [default_search_provider] abilitato |
| Schermo intero | Permesse |
| home page | Homepage_url |
| homepage_is_newtabpage | homepage_is_newtabpage |
| Session | restore_on_startup<br>startup_urls |
| Extensions | Estensioni : impostazioni |

## <a name="1-download-an-example-initial_preferences-file"></a>1: Scaricare un file di initial_preferences di esempio

To get started, download the "Policy" file from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download). Estrarre i file e aprirli `initial_preferences` all'interno della `examples` cartella.

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2: personalizzare e convalidare il file initial_preferences file

Personalizza le impostazioni delle preferenze nel file *initial_preferences* scaricato e convalida le modifiche per assicurarti che non ci siano errori nel codice JSON. Se vengono rilevati errori, controllare la sintassi e la struttura del file *initial_preferences,* apportare correzioni e convalidarlo di nuovo. Pochi strumenti di esempio per convalidare JSON, Strumenti [JSON](https://jsonformatter.org/) online o [modifica JSON in Visual Studio Code](https://code.visualstudio.com/docs/languages/json).

## <a name="3-deploy-preferences-to-users-computer"></a>3: Distribuire le preferenze nel computer degli utenti

Distribuisci *initial_preferences* file nei dispositivi degli utenti contemporaneamente alla distribuzione di Microsoft Edge Browser e posiziona il file nel percorso seguente nel dispositivo.

### <a name="windows-amd64-and-arm64"></a>Windows (AMD64 e ARM64)

| Canale | Percorso |
| - | - |
| Stable | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

**Nota:** *il* file initial_preferences deve essere distribuito nella stessa cartella del file msedge.exe nei computer Windows degli utenti.  

### <a name="macos"></a>macOS

| Canale | Percorso |
| - | - |
| Stable | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| Beta | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>Note importanti: distribuzione MSI/Pkg *e* initial_preferences interazione

Le preferenze iniziali avranno effetto solo quando il file initial_preferences viene distribuito prima della prima esecuzione del browser da parte degli utenti finali.  

## <a name="see-also"></a>Vedi anche

- [File *modello initial_prefrences* di esempio](https://www.microsoft.com/edge/business/download)
