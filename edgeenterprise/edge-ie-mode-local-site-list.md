---
title: Elenco siti locali per la modalità IE
ms.author: shisub
author: AndreaLBarr
manager: srugh
ms.date: 07/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Informazioni su come abilitare gli elenchi di siti locali e accedere facilmente alla modalità IE
ms.openlocfilehash: 0c79622a1f96cad83a2436f5e79e69914f4a2c40
ms.sourcegitcommit: 9088e839e82d80c72460586e9af0610c6ca71b83
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2021
ms.locfileid: "11676170"
---
## <a name="local-site-list-for-ie-mode"></a>Elenco siti locali per la modalità IE

>[!Note]
> L'applicazione desktop Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Per altre informazioni, vedere](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Questo articolo spiega come configurare l'accesso semplice alla modalità Internet Explorer (modalità Internet Explorer) e consentire l'uso di elenchi di siti locali nell'organizzazione.

> [!NOTE]
> Questo articolo si applica Microsoft Edge versione 92 o successiva.

### <a name="prerequisites"></a>Prerequisiti

1. Aggiornamenti di Windows

- Windows 10 versione 1909 - [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620) o versione successiva  

- Windows 10, versione 2004; Windows 10, versione 20H2 e Windows 10, versione 21H1 – [KB5003690](https://support.microsoft.com/topic/june-21-2021-kb5003690-os-builds-19041-1081-19042-1081-and-19043-1081-preview-11a7581f-2a01-47d5-ba12-431709ee2248) o versione successiva

2. Microsoft Edge versione 92 (92.0.925.0 o successiva)

## <a name="overview"></a>Panoramica

La modalità IE è alimentata dalla configurazione dell'elenco Enterprise siti in modalità avanzata. Durante l'identificazione e la configurazione dei siti nell'elenco dei siti per l'utilizzo della modalità IE, gli utenti non devono più attendere o eseguire il fall back all'applicazione IE11 autonoma.

A partire da Microsoft Edge versione 92, l'accesso ripetuto ai siti in modalità *IE* non configurati è più semplice. Gli utenti possono ricaricare i siti in modalità IE. Possono aggiungere questi siti all'elenco dei siti locali per eseguire automaticamente il rendering in modalità IE per un periodo di 30 giorni, mentre l'elenco dei siti dell'organizzazione viene aggiornato. Quando [IE11 è disabilitato](/deployedge/edge-ie-disable-ie11) nell'ambiente, gli utenti non dipendono più solo dall'elenco dei siti dell'organizzazione.

È possibile configurare questa esperienza tramite criteri di gruppo per l'organizzazione.

Nota: un sito non *configurato* richiede la modalità IE ma non è configurato per l'apertura in modalità IE nell'elenco siti Enterprise modalità utente.

## <a name="local-site-list-experience"></a>Esperienza elenco siti locali

Per abilitare l'esperienza dell'elenco di siti locali, gli utenti possono accedere all'URL *edge://settings/defaultBrowser* e impostare Consenti il ricaricare i siti **in modalità Internet Explorer** su **Consenti**.

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Compatibilità di Internet Explorer":::

>[! Nota:]  

>1. Se è stato abilitato il test della modalità Internet Internet Tramite il criterio *InternetExplorerIntegrationTestingAllowed,* questa impostazione verrà visualizzata, ma verrà disattivata a meno che non si abiliti esplicitamente il criterio *InternetExplorerIntegrationReloadInIEModeAllowed.*  
>2. Se **l'opzione** Consenti il ricaricamento dei siti in modalità Internet Explorer è impostata su **Predefinito,** gli utenti potrebbero essere in grado di ricaricare i siti in modalità Internet Explorer se dispongono di un utilizzo esistente di Internet Explorer 11.  

Quando questa impostazione è abilitata, gli utenti possono ricaricare un sito in modalità Internet Explorer selezionando Impostazioni e altro (icona con i puntini di sospensione ...) > Ricarica in modalità **Internet Explorer.** Gli utenti possono anche selezionare Ricarica scheda in modalità **Internet Explorer** quando fanno clic con il pulsante destro del mouse su una scheda o scelgono Apri collegamento nella nuova scheda modalità Internet **Explorer** quando fanno clic con il pulsante destro del mouse su un collegamento.

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="Ricarica in modalità Internet Explorer":::

**L'icona Ricarica in modalità Internet Explorer** può essere aggiunta alla barra degli strumenti. Il pulsante della barra degli strumenti consente agli utenti di entrare ed uscire facilmente dalla modalità Internet Online e può essere gestito tramite l edge://settings/appearance *URL.*

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="Icona Ricarica in modalità Internet Explorer":::

>[!Note]
>Se l'utente si trova in un sito già in elenco siti in modalità Enterprise dell'organizzazione, le opzioni per ricaricare (o uscire) la modalità Internet Explorer saranno visibili ma disattivate.

Quando l'opzione è selezionata, il sito viene ricaricato in modalità IE. L'icona dell'indicatore della modalità Internet Explorer è visibile a sinistra della barra degli indirizzi e il riquadro a comparsa mostra un'opzione che gli utenti possono passare ad Aprire la pagina in modalità Internet Explorer la volta successiva. In questo modo viene aggiunta la pagina specifica in cui si trova l'utente all'elenco dei siti locali e verrà aperta automaticamente in modalità IE per i prossimi 30 giorni.

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="Questa pagina è aperta in modalità Internet Explorer":::

Dopo che un sito è stato ricaricato in modalità IE gli spostamenti "nella pagina" rimarranno in modalità IE (ad esempio, un collegamento, uno script o un modulo nella pagina o un reindirizzamento sul lato server da un altro spostamento "nella pagina").  

Durante la modalità IE, gli utenti vedranno un banner che indica che sono in modalità IE, l'opzione per uscire dalla modalità IE e per aggiungere l'icona della modalità IE alla barra degli strumenti (se non è già stata aggiunta).

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="Banner modalità IE":::

Gli utenti possono scegliere di uscire dalla modalità Internet Explorer usando il pulsante Esci nel banner, l'icona della modalità IE aggiunta o Impostazioni e altro ancora (l'icona dei puntini di sospensione ...) > Esci dalla modalità **Internet Explorer,** altrimenti Microsoft Edge esce automaticamente dalla modalità Internet Explorer quando si verifica uno spostamento che non è "nella pagina" (ad esempio, utilizzando la barra degli indirizzi, il pulsante Indietro o un collegamento preferito).

Le voci rimangono nell'elenco dei siti locali per un periodo predefinito di 30 giorni. È consigliabile configurare i siti legacy per l'organizzazione nell'elenco Enterprise siti in modalità avanzata. L'elenco dei siti locali garantisce che gli utenti possano continuare il flusso di lavoro senza essere interrotti durante l'aggiornamento dell'elenco dei siti dell'organizzazione. Il giorno 31, quando gli utenti passano al sito, vedranno un banner che spiega che il sito non verrà più caricato in modalità IE. Se lo desiderano, gli utenti possono aggiungerlo di nuovo all'elenco dei siti locali.

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="La pagina non verrà più caricata in modalità IE":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>Criteri per configurare l'utilizzo di elenchi di siti locali per la modalità IE

Sono disponibili due criteri di gruppo per configurare l'esperienza dell'elenco siti locale in Microsoft Edge. Tali criteri sono:

### *<a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>Criterio: InternetExplorerIntegrationReloadInIEModeAllowed*

Questo criterio corrisponde all'impostazione Microsoft Edge "Consenti il ricaricare i siti in modalità Internet Explorer". Per accedere a questa impostazione, fare clic sull'URL seguente: *edge://settings/defaultbrowser*.

- Se abiliti questo criterio, gli utenti possono ricaricare un sito in modalità Internet Explorer selezionando Impostazioni e altro **ancora (icona**con i puntini di sospensione ... > Ricarica in modalità Internet Explorer . Gli utenti possono anche selezionare Ricarica scheda in modalità **Internet Explorer** quando fanno clic con il pulsante destro del mouse su una scheda oppure scegliere Apri collegamento nella nuova scheda modalità Internet **Explorer** quando fanno clic con il pulsante destro del mouse su un collegamento.
Gli utenti possono facoltativamente indicare Microsoft Edge usare la modalità IE per il sito in futuro. Questa scelta verrà memorizzata per un valore predefinito di 30 giorni e può essere gestita utilizzando il criterio *InternetExplorerIntegrationLocalSiteListExpirationDays.*

- Se disabiliti questo criterio, gli utenti non potranno ricaricare un sito non configurato in modalità Internet Directory.

- Se non si configura questo criterio, verranno mostrate agli utenti le opzioni per ricaricare i siti non configurati in modalità Internet Explorer a seconda dell'utilizzo recente di Internet Explorer 11.

Si noti che questo criterio ha la precedenza su come è stato configurato il criterio [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) e tale criterio verrà disabilitato.

### *<a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>Criteri: InternetExplorerIntegrationLocalSiteListExpirationDays*

Questo criterio può essere utilizzato per modificare il numero di giorni in cui un sito rimane nell'elenco dei siti locali per gli utenti.  

- Se si disabilita o non si configura questo criterio, viene utilizzato un valore predefinito di 30 giorni.

- Se si abilita il criterio, è necessario immettere un valore compreso tra 0 e 90 giorni per mantenere il sito nell'elenco dei siti locali di un utente.

Questo criterio non ha alcun effetto se è stato disabilitato il *criterio InternetExplorerIntegrationReloadInIEModeAllowed.*

**Nota:**

L'elenco dei siti locali non è attualmente sincronizzato tra dispositivi. Questo miglioramento si trova attualmente nel backlog e verrà aggiornato quando questo sarà disponibile.

## <a name="see-also"></a>Vedere anche

Disabilitare Internet Explorer 11 - [Disabilitare Internet Explorer 11 | Documenti Microsoft](/deployedge/edge-ie-disable-ie11)

Configure IE mode policies - [Configure IE mode Policies | Documenti Microsoft](/deployedge/edge-ie-mode-policies)

