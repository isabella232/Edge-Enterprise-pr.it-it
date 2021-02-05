---
title: Domande frequenti sulla modalità IE
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 02/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Domande frequenti e risoluzione dei problemi per Microsoft Edge in modalità IE
ms.openlocfilehash: aeae79dfd1745c754fb5ab690338f87fd25c080b
ms.sourcegitcommit: ff67ccc93d07588a9128e9b1fe007d5393a9d6af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312592"
---
# Domande frequenti sulla modalità IE

Questo articolo fornisce suggerimenti per la risoluzione dei problemi, oltre alle domande frequenti per Microsoft Edge (versione 77 o successiva).

> [!NOTE]
> Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.

## Risoluzione dei problemi in modalità IE

Utilizza le informazioni contenute in questa sezione per diagnosticare e risolvere i problemi relativi alla modalità IE.

### Informazioni di diagnostica della modalità Internet Explorer

È possibile ottenere le informazioni di diagnostica della modalità Internet Explorer nella scheda Compatibilità di Microsoft Edge. Per aprire questa scheda, passare a *edge://compat/iediagnostic*. Questa pagina può mostrare messaggi di diagnostica. Questa pagina include inoltre le informazioni riguardanti le seguenti categorie:

- **Controllo della chiave del Registro di sistema**. Verifica se l'integrazione di Internet Explorer è impostata correttamente nel registro di sistema (visualizzato solo se il controllo ha esito negativo). In caso contrario, l'utente può fare clic su **Correggi** per risolvere il problema.
- **Modalità Internet Explorer**. Indica la versione API utilizzata, in base alla configurazione e al sistema operativo. In caso di problemi, all'utente potrebbe essere richiesto di installare un **Windows Update**.
- **Impostazione della modalità di Internet Explorer**. Indica se la modalità Internet Explorer è abilitata e come è configurata.
- **Riga di comando**. Mostra la stringa della riga di comando e gli switch usati per avviare Microsoft Edge.
- **Impostazioni di Criteri di gruppo**. Indica se la modalità IE è configurata utilizzando i criteri di gruppo e i criteri applicati.

### Messaggio di errore: "Per aprire questa pagina in modalità Internet Explorer, reinstallare Microsoft Edge con privilegi di amministratore".

È possibile visualizzare questo errore se non si dispone di tutti i Windows Update richiesti. Vedere i prerequisiti elencati in [Informazioni sulla modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode) per le versioni richieste di Windows e Microsoft Edge.

Se sono già stati installati tutti i Windows Update richiesti, è possibile visualizzare questo errore se:

- Si sta utilizzando il canale Canary, che è installato a livello di utente per impostazione predefinita.
- Si sta utilizzando il canale stabile, Beta o Dev, ma quando è richiesto di eseguire un'elevazione durante l'installazione, l'elevazione viene stata annullata. Quando si annulla la richiesta di elevazione, l'installazione continuerà a livello di utente.
- Internet Explorer 11 è stato disabilitato nelle funzionalità di Windows.

Soluzioni possibili:

- Esegui il programma di installazione per qualsiasi canale a livello di sistema: `installer.exe --system-level`.
- Abilita Internet Explorer 11 nelle funzionalità di Windows.

Per verificare se Microsoft Edge è installato a livello di sistema, digitare "edge://version" nella barra degli indirizzi di Microsoft Edge. Il percorso del file eseguibile mostrerà un percorso che inizia con *C:\Programmi*, che indica un'installazione a livello di sistema. Se il percorso del file eseguibile inizia con *C:\Utenti\*, disinstallare e quindi reinstallare Microsoft Edge con privilegi di amministratore.

### Messaggio di errore: "Per aprire questa pagina in modalità IE, prova a riavviare Microsoft Edge".

È possibile che venga visualizzato questo errore se si è verificato un errore imprevisto in Internet Explorer. Il riavvio di Microsoft Edge di solito corregge questo errore.

### Messaggio di errore: "Disattiva debug remoto per aprire il sito in modalità Internet Explorer altrimenti potrebbe non funzionare come previsto".

È possibile che venga visualizzato questo errore se si esegue il debug remoto e si accede a una pagina Web configurata per essere eseguita in modalità IE. Puoi continuare, ma verrà eseguito il rendering della pagina usando Microsoft Edge.

### Messaggio di errore: "Errore: Impossibile recuperare l'elenco dei siti EMIE".

Questo errore potrebbe essere visualizzato nella pagina del sito *edge://compat/enterprise*, indicando che il download dell'elenco dei siti non è riuscito. A partire da Microsoft Edge versione 87, quando i cookie vengono bloccati per le richieste di terze parti tramite il criterio [BlockThirdPartyCookies](https://docs.microsoft.com/deployedge/microsoft-edge-policies#blockthirdpartycookies), non è consentita nemmeno l'autenticazione HTTP. È possibile consentire i cookie per il dominio specifico che ospita l'elenco di siti in modalità Enterprise usando i criteri di [CookieAllowedForURLs](https://docs.microsoft.com/deployedge/microsoft-edge-policies#cookiesallowedforurls), per avere la garanzia che i download degli elenchi di siti siano eseguiti correttamente.

## Domande frequenti

### La modalità IE sostituirà Internet Explorer 11?

Ci impegniamo a mantenere Internet Explorer un browser supportato, affidabile e sicuro. Internet Explorer è ancora un componente di Windows e segue il ciclo di vita del supporto del sistema operativo in cui è installato. Per informazioni dettagliate, vedi [Domande frequenti sul ciclo di vita - Internet Explorer](https://support.microsoft.com/help/17454/). Mentre Microsoft continua a supportare e aggiornare Internet Explorer, gli aggiornamenti delle funzionalità e della piattaforma più recenti saranno disponibili solo in Microsoft Edge.

### È possibile usare "Apri con Esplora risorse" o "Visualizza in Esplora file" in SharePoint con la modalità IE?

Sì, se funziona in Internet Explorer 11 autonomo, funzionerà nella modalità IE. Tuttavia, invece di usare l'opzione Apri con Esplora risorse, l'approccio consigliato per la gestione di file e cartelle all'esterno di SharePoint consiste nel [sincronizzare i file di SharePoint](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) oppure nello [spostare o copiare i file in SharePoint](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc).

### La modalità IE in Microsoft Edge supporta l'opzione *nomerge* che era supportata in Internet Explorer 11?

In Microsoft Edge non è presente una riga di comando esplicita che riflette l'opzione *nomerge*, ma ci sono alcune alternative consigliate che offrono questa funzionalità.

1. Usare i profili in Microsoft Edge: ogni profilo esegue il mapping a una sessione di IE diversa per le pagine in modalità IE, in modo che l'opzione *nomerge* sia identica.
2. Usare la riga di comando `--user-data-dir=<path>`, ma con un percorso diverso per ogni sessione. Se necessario, è possibile creare un'utilità per l'esecuzione dell'utente che avvia Microsoft Edge e modifica il percorso per la sessione.

Se nessuna delle opzioni descritte sopra funziona per un determinato scenario, usare uno dei canali di feedback disponibili: supporto Microsoft, [Forum TechCommunity](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)o [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise).

### È possibile salvare I collegamenti come pagine Web in modalità Internet Explorer?
 
Sì, è possibile abilitare l'opzione Salva destinazione come nel menu di scelta rapida per la modalità Internet Explorer in Microsoft Edge. A questo scopo, configurare i criteri di gruppo *"Consenti Salva destinazione come in modalità Internet Explorer"* disponibile in *Configurazione computer > modelli amministrativi > componenti di Windows > Internet Explorer*.
Il meccanismo di salvataggio funziona allo stesso modo in Internet Explorer e se la destinazione viene salvata come file HTML, riaprendo il file verrà eseguito il rendering della pagina in Microsoft Edge.
 
Tieni presente che questa funzionalità richiede gli aggiornamenti minimi del sistema operativo seguenti:
- Windows 10, versione 2004, Windows Server versione 2004, Windows 10, versione 20H2: [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10, versione 1903, Windows 10, versione 1909, Windows Server versione 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10, versione 1809, Windows Server versione 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10, versione 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10, versione 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10, versione 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)


## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [Informazioni aggiuntive sulla modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
