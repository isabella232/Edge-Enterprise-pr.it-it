---
title: Monitoraggio password con abilitazione automatica per gli utenti
ms.author: supalsul
author: AndreLBarr
manager: tulasim
ms.date: 07/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Monitoraggio password con abilitazione automatica per gli utenti
ms.openlocfilehash: bd1fe390b972c66cd9b4c20ab3a9fabde76c7e03
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980338"
---
# <a name="password-monitor-auto-enabled-for-users"></a>Monitoraggio password con abilitazione automatica per gli utenti

Questo articolo descrive come verrà attivato Monitoraggio password in Microsoft Edge per gli utenti selezionati e fornisce agli amministratori le istruzioni per controllare come viene abilitato il monitoraggio.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 88 o successiva.

## <a name="introduction-benefits-and-availability"></a>Introduzione, vantaggi e disponibilità

Monitoraggio password consente agli utenti di Microsoft Edge di proteggere i propri account online informandoli se una delle loro password è stata trovata in una fuga di dati online. Le fughe di dati online o le violazioni dei dati si verificano quando gli utenti malintenzionati rubano dati da app o siti Web di terze parti. Per altre informazioni, vedere [Monitoraggio password: protezione delle password in Microsoft Edge](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/) nel blog di Microsoft Research.

### <a name="benefits"></a>Vantaggi

Considerando la frequenza e l'ambito di questi attacchi online, è diventato necessario per tutti avere questo tipo di protezione. Microsoft Edge consente di controllare in modo sicuro le password salvate da un utente rispetto alle password segnalate come compromesse e di avvisarlo se viene trovata una corrispondenza.  

## <a name="configure-group-policy-for-password-monitor"></a>Configurare criteri di gruppo per Monitoraggio password

Questa funzione viene controllata tramite il criterio di gruppo [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed).

Dopo aver abilitato i criteri, gli utenti devono comunque fornire il consenso per attivare la funzione. Il consenso è necessario perché la funzione contiene dati personali e riservati dell'utente (password). Se la funzione viene disabilitata tramite i criteri di gruppo, gli utenti non possono sostituire questa impostazione.  

## <a name="enabling-password-monitor-for-users"></a>Abilitazione di Monitoraggio password per gli utenti

Una volta abilitati i criteri di monitoraggio password, questa funzione viene resa disponibile agli utenti in diversi modi.

- Abilitazione automatica. Gli utenti connessi con l'account aziendale (Active Directory o Azure Active Directory) e che sincronizzano le loro password avranno l’abilitazione automatica per questa funzione. Nella schermata successiva verrà visualizzata la notifica che informa l'utente che la funzione è abilitata.

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="Avviso di abilitazione di Monitoraggio password":::

-  Ottenere il consenso esplicito. Agli utenti per cui non è abilitata la Sincronizzazione password verrà richiesta l'autorizzazione per abilitare Monitoraggio password. Gli utenti riceveranno la richiesta quando si verificano le azioni seguenti:
   - Quando un utente salva una nuova password.
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="Richiesta di salvataggio della password":::

   - Quando un utente ha eseguito l'accesso al browser con una password salvata.
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="Richiesta di conferma dopo l'accesso":::
   
- Attivazione diretta. Gli utenti possono andare a **Impostazioni** > **Password** in qualsiasi momento per attivare o disattivare la funzione.

## <a name="user-scenarios-with-password-monitor-auto-enabled"></a>Scenari utente con abilitazione automatica di Monitoraggio password 

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

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="how-can-password-monitor-be-disabled-for-my-organization"></a>Come può essere disabilitato Monitoraggio password per l'organizzazione?

È possibile disabilitare Monitoraggio password per l'organizzazione mediante:
- L’uso dei criteri di gruppo PasswordMonitorAllowed.
- L’interruzione della sincronizzazione e dell'invio dei dati ai server Microsoft.

  > [!NOTE]
  > Monitoraggio password può funzionare anche se la Sincronizzazione password è disabilitata, a condizione che l'utente abbia fornito il consenso esplicito per attivare la funzione o l'abbia attivata autonomamente tramite Impostazioni.

### <a name="what-happens-if-a-user-for-whom-the-feature-has-been-auto-enabled-turns-password-monitor-off-via-settings"></a>Cosa succede se un utente per cui è stata abilitata automaticamente la funzione disattiva Monitoraggio password tramite Impostazioni?

L'impostazione scelta dall'utente viene rispettata e la funzione rimarrà disabilitata per quell'utente. Tuttavia, potrebbe essere visualizzata di nuovo una finestra di dialogo di consenso nel caso in cui l’utente non abbia mai risposto in precedenza alla richiesta di consenso.

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)