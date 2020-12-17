---
title: Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229617"
---
# Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge (basata su Chromium)

In questo articolo viene descritto Blocker Toolkit per disabilitare la distribuzione e l'installazione automatica di Microsoft Edge.

Gli aggiornamenti seguenti sono stati apportati a questo articolo:

- **09/01/2020** con ulteriori informazioni sui dispositivi che potrebbero richiedere l'uso di Blocker Toolkit
- **28/02/2020** per rimuovere "MDM Managed" dai criteri dei dispositivi da escludere da questo aggiornamento automatico
- **30/06/2020** per garantire che tutti i dispositivi connessi a Windows Update possano ricevere questo aggiornamento (effettivo a partire dal 30/07/2020)
- **10/12/2020** per spiegare le situazioni pre 20H2 in cui le impostazioni di Blocker Toolkit verranno ignorate

> [!NOTE]
> Questo articolo si applica al canale stabile di Microsoft Edge.

## Panoramica

Per consentire ai clienti di restare sempre protetti e aggiornati, Microsoft distribuirà Microsoft Edge (basato su Chromium) a tutti i dispositivi connessi a Windows Update con la versione 1803 di Windows 10 e versioni successive. Questo processo verrà avviato dopo il 15 gennaio 2020 e ulteriori informazioni saranno disponibili a partire da tale data.

Blocker Toolkit è progettato per le organizzazioni che desiderano bloccare la distribuzione automatica di Microsoft Edge (basato su Chromium) nei dispositivi connessi a Windows Update con la versione 1803 di Windows 10 e versioni successive. I dispositivi Windows Server Update Services (WSUS) o Windows Update per le aziende gestiti verranno esclusi da questo aggiornamento automatico di Windows, ma potrebbero ricevere il nuovo Microsoft Edge (basato su Chromium) tramite la propria organizzazione.

**È importante notare che:**

- Blocker Toolkit non impedisce agli utenti di installare manualmente Microsoft Edge (basato su Chromium) tramite download da Internet o supporti esterni.
- Le organizzazioni con gli aggiornamenti gestiti tramite Windows Update per le aziende (WUfB) non riceveranno automaticamente questo aggiornamento e non devono distribuire Blocker Toolkit.
- Le organizzazioni con ambienti gestiti con una soluzione per la gestione degli aggiornamenti come Windows Server Update Services (WSUS) o System Center Configuration Manager (SCCM) non devono distribuire Blocker Toolkit. Possono usare questi prodotti per gestire in modo completo la distribuzione degli aggiornamenti rilasciati tramite Windows Update e Microsoft Update, incluso l'[aggiornamento in WSUS per il nuovo Microsoft Edge](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge), all'interno del loro ambiente.
- Questo aggiornamento è un aggiornamento indipendente (non incluso nell'aggiornamento cumulativo mensile) per offrire ai clienti aziendali la flessibilità e il massimo controllo sulla distribuzione di questo aggiornamento.
- Il nuovo Microsoft Edge (basato su Chromium) è incluso nell'aggiornamento delle funzionalità di Windows 10, versione 20H2 nella seconda metà di 2020. Il toolkit Blocker non influisce sui comportamenti e sulla distribuzione della versione 20H2. Vedere ulteriori informazioni sulla versione 20H2 di Windows 10 [qui](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).

Puoi scaricare il file eseguibile di Blocker Toolkit all'indirizzo [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).

### Componenti del toolkit

Il toolkit contiene i seguenti componenti:

- Script di blocco eseguibile (.CMD)
- Modello amministrativo Criteri di gruppo (.ADMX e .ADML)

### Sistemi operativi supportati

Windows 10, versione 1803 e versioni successive.

## Script di blocco

Lo script crea una chiave del Registro di sistema e imposta il valore associato per bloccare o sbloccare (a seconda dell'opzione della riga di comando utilizzata) la distribuzione automatica di Microsoft Edge (basato su Chromium) nel computer locale o in un computer di destinazione remoto.

**Chiave del Registro di sistema:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**Nome del valore della chiave:** `DoNotUpdateToEdgeWithChromium`

| Valore                | Risultato                         |
|----------------------|--------------------------------|
| *La chiave non è definita* | La distribuzione *non* è bloccata. |
| 0                    | La distribuzione *non* è bloccata. |
| 1                    | La distribuzione è bloccata.       |

Lo script ha la seguente sintassi della riga di comando:<br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### Nome computer

Il parametro `<machine name>` è facoltativo. Se non viene specificato, l'azione viene eseguita nel computer locale. In caso contrario, l'accesso al computer remoto avviene tramite le funzionalità del Registro di sistema remoto del comando `REG`. Se non è possibile accedere al Registro di sistema remoto a causa di autorizzazioni di sicurezza o non è possibile trovare il computer remoto, viene restituito un messaggio di errore dal comando `REG`.

### Opzioni

Le opzioni usate dallo script si escludono a vicenda e viene attivata solo la prima opzione valida di un determinato comando. Lo script può essere eseguito più volte nello stesso computer.

| Opzione       | Descrizione                              |
|--------------|------------------------------------------|
| `/B`         | La distribuzione è bloccata                      |
| `/U`         | La distribuzione è sbloccata                    |
| `/H` o `/?` | Viene visualizzata la seguente guida di riepilogo:<br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## Modello amministrativo Criteri di gruppo (file .ADMX e .ADML)

Il modello amministrativo Criteri di gruppo (file .ADMX e .ADML) consente agli amministratori di importare le nuove impostazioni di Criteri di gruppo per bloccare o sbloccare la distribuzione automatica di Microsoft Edge (basato su Chromium) nell'ambiente Criteri di gruppo e usare Criteri di gruppo per eseguire l'azione in modo centralizzato nei sistemi dell'ambiente.

Per gli utenti che eseguono Windows 10 RS3 Enterprise/EDU e RS4 e versioni successive, i criteri sono nel percorso seguente:

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

Questa impostazione è disponibile solo come impostazione per computer, non è disponibile un'impostazione per utente.

> [!IMPORTANT]
> Questa impostazione del Registro di sistema non è archiviata in una chiave dei criteri e viene considerata una *preferenza*. Pertanto, se l'oggetto Criteri di gruppo che implementa l'impostazione viene rimosso o se il criterio è impostato su **Non configurato**, l'impostazione rimane inalterata. Per sbloccare la distribuzione di Microsoft Edge (basata su Chromium) tramite Criteri di gruppo, imposta i criteri su **Disabilitato**.

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://www.microsoftedgeinsider.com/enterprise)
- [Aggiornamenti di Windows per supportare Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [Come accedere alla versione precedente di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
