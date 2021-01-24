---
title: Monitoraggio password con abilitazione automatica per gli utenti
ms.author: supalsul
author: dan-wesley
manager: tulasim
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Monitoraggio password con abilitazione automatica per gli utenti
ms.openlocfilehash: 8ea96522fe99082579e88b2eab330fb265d02b12
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297508"
---
# Monitoraggio password con abilitazione automatica per gli utenti

Questo articolo descrive come verrà attivato Monitoraggio password in Microsoft Edge per gli utenti selezionati e fornisce agli amministratori le istruzioni per controllare come viene abilitato il monitoraggio.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 88 o successiva.

## Introduzione, vantaggi e disponibilità

Monitoraggio password consente agli utenti di Microsoft Edge di proteggere i propri account online informandoli se una delle loro password è stata trovata in una fuga di dati online. Le fughe di dati online o le violazioni dei dati si verificano quando gli utenti malintenzionati rubano dati da app o siti Web di terze parti.

### Vantaggi

Considerando la frequenza e l'ambito di questi attacchi online, è diventato necessario per tutti avere questo tipo di protezione. Microsoft Edge consente di controllare in modo sicuro le password salvate da un utente rispetto alle password segnalate come compromesse e di avvisarlo se viene trovata una corrispondenza.  

### Disponibilità

Monitoraggio password era presente nei primi canali di anteprima (Canary/Dev) e verrà assegnato a Stable Channel versione 88 a partire da gennaio 2021. L'implementazione sarà graduale e potrebbero essere necessarie alcune settimane prima che vengano visualizzati il messaggio e il controllo seguenti nella pagina **Impostazioni** > **Profilo** > **Password**.

:::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enable-option.png" alt-text="Opzione per abilitare Monitoraggio password":::

## Configurare criteri di gruppo per Monitoraggio password

Questa funzione viene controllata tramite il criterio di gruppo [PasswordMonitorAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#passwordmonitorallowed).

Dopo aver abilitato i criteri, gli utenti devono comunque fornire il consenso per attivare la funzione. Il consenso è necessario perché la funzione contiene dati personali e riservati dell'utente (password). Se la funzione viene disabilitata tramite i criteri di gruppo, gli utenti non possono sostituire questa impostazione.  

## Abilitazione di Monitoraggio password per gli utenti

Una volta abilitati i criteri di monitoraggio password, questa funzione viene resa disponibile agli utenti in diversi modi.

- Abilitazione automatica. Gli utenti connessi con l'account aziendale (Active Directory o Azure Active Directory) e che sincronizzano le loro password avranno l’abilitazione automatica per questa funzione. Nella schermata successiva verrà visualizzata la notifica che informa l'utente che la funzione è abilitata.

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="Avviso di abilitazione di Monitoraggio password":::

-  Ottenere il consenso esplicito. Agli utenti per cui non è abilitata la Sincronizzazione password verrà richiesta l'autorizzazione per abilitare Monitoraggio password. Gli utenti riceveranno la richiesta quando si verificano le azioni seguenti:
   - Quando un utente salva una nuova password.
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="Richiesta di salvataggio della password":::

   - Quando un utente ha eseguito l'accesso al browser con una password salvata.
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="Richiesta di conferma dopo l'accesso":::
   
- Attivazione diretta. Gli utenti possono andare a **Impostazioni** > **Password** in qualsiasi momento per attivare o disattivare la funzione.

## Scenari utente con abilitazione automatica di Monitoraggio password 

La tabella seguente illustra gli scenari in cui Monitoraggio password è abilitato automaticamente e il suo funzionamento nei dispositivi degli utenti.

| Scenario | Condizioni di base | Impatto |
|--|--|--|
| 1 con Sincronizzazione attiva | Sincronizzazione attiva<br>Funzione abilitata in precedenza: No<br>Risposta all'interfaccia utente di consenso: Nessuna | Funzione abilitata per impostazione predefinita e viene visualizzato un avviso 2 minuti dopo l'avvio del browser.<br>- Se successivamente la sincronizzazione viene disattivata, la funzione viene disabilitata.<br>- Se la funzione viene disattivata prima di modificare la sincronizzazione, la sincronizzazione non avrà più effetto sulla funzione.   |
| 2 con Sincronizzazione attivata | Sincronizzazione attiva<br>Funzione abilitata in precedenza: Sì<br>Risposta all'interfaccia utente di consenso: Nessuna | La funzione rimane uguale all’opzione scelta dall'utente.  L’avviso non viene visualizzato e la modifica della sincronizzazione non ha effetto sul valore della funzione.|
| 3 con Sincronizzazione disattivata | Sincronizzazione disattivata<br>Funzione abilitata in precedenza: No<br>Risposta all'interfaccia utente di consenso: Nessuna | La sincronizzazione sarà disattivata e la funzione rimarrà disabilitata<br>- In qualsiasi momento successivo, se l'utente attiva la sincronizzazione senza modificare la funzione: la funzione è abilitata e l’avviso di abilitazione automatica viene visualizzato 2 minuti dopo l'attivazione della sincronizzazione. <br> - Se la sincronizzazione è di nuovo disattivata, la funzione è disabilitata <br>- Se la funzione viene modificata prima di attivare la sincronizzazione, la sincronizzazione non avrà più effetto su Monitoraggio password.  |  
| 4 con Sincronizzazione disattivata | Sincronizzazione disattivata<br>Funzione abilitata in precedenza: Sì<br>Risposta all'interfaccia utente di consenso: Nessuna | La funzione rimane uguale all'opzione scelta dall'utente, l’avviso non viene visualizzato e la modifica della sincronizzazione non ha effetto sul valore della funzione.  |

Inoltre, se un utente ha eseguito l'accesso con un account aziendale con restrizioni tramite criteri per uno degli elementi seguenti, la funzione NON verrà abilitata automaticamente:

- Monitoraggio password è disabilitato  
- Sincronizzazione password è disabilitata
- La condivisione di dati con i server Microsoft è disabilitata

## Domande frequenti

### Come può essere disabilitato Monitoraggio password per l'organizzazione?

È possibile disabilitare Monitoraggio password per l'organizzazione mediante:
- L’uso dei criteri di gruppo PasswordMonitorAllowed.
- L’interruzione della sincronizzazione e dell'invio dei dati ai server Microsoft.

  > [!NOTE]
  > Monitoraggio password può funzionare anche se la Sincronizzazione password è disabilitata, a condizione che l'utente abbia fornito il consenso esplicito per attivare la funzione o l'abbia attivata autonomamente tramite Impostazioni.

### Cosa succede se un utente per cui è stata abilitata automaticamente la funzione disattiva Monitoraggio password tramite Impostazioni?

L'impostazione scelta dall'utente viene rispettata e la funzione rimarrà disabilitata per quell'utente. Tuttavia, potrebbe essere visualizzata di nuovo una finestra di dialogo di consenso nel caso in cui l’utente non abbia mai risposto in precedenza alla richiesta di consenso.

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)