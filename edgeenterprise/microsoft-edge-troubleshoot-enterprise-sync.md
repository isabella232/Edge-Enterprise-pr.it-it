---
title: Diagnosticare e risolvere i problemi di sincronizzazione di Microsoft Edge
ms.author: collw
author: AndreaLBarr
manager: silvanam
ms.date: 07/27/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Linee guida e strumenti che un amministratore di Microsoft Edge può usare per risolvere i problemi comuni di sincronizzazione aziendale
ms.openlocfilehash: 61ef4b69e16ecc2955f3f4dc46b9a22e3a8563a1e5c691430fe0645ceb23ad79
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11725724"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a>Diagnosticare e risolvere i problemi di sincronizzazione di Microsoft Edge

Questo articolo fornisce indicazioni per la risoluzione dei problemi di sincronizzazione più comuni in un ambiente Azure Active Directory (Azure AD). Include anche gli strumenti consigliati per raccogliere i log necessari per la risoluzione di un problema di sincronizzazione.

Se un utente riscontra un problema durante la sincronizzazione dei dati del browser tra i dispositivi, può provare a [reimpostare la sincronizzazione.](edge-learnmore-reset-data-in-cloud.md) Se non funziona, gli amministratori o il personale di supporto possono usare le indicazioni seguenti per risolvere un problema di sincronizzazione.

> [!NOTE]
> Si applica a Microsoft Edge versione 77 o successiva, se non diversamente specificato.

## <a name="identity-issues-versus-sync-issues"></a>Problemi di identità e problemi di sincronizzazione

Prima di iniziare, è importante comprendere la differenza tra problemi di identità e problemi di sincronizzazione. Uno dei casi di utilizzo più diffusi per gestire l'identità degli utenti nel browser è supportare la sincronizzazione. Per questo motivo, i problemi di identità vengono spesso confusi con i problemi di sincronizzazione. Comprendere la differenza tra i problemi di identità e sincronizzazione prima di avviare la risoluzione dei problemi di sincronizzazione.

Prima di considerare un problema di sincronizzazione, verificare se l'utente ha eseguito l'accesso al browser con un account valido.

Nella schermata successiva viene illustrato un esempio di errore di identità. L'errore è "**errore token ultimo, EDGE_AUTH_ERROR: 3, 54, 3ea**", disponibile in *Edge://Sync-internals* in **Credenziali**:

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="Errore ultimo token EDGE_AUTH_ERROR: 3, 54, 3ea":::

## <a name="common-sync-issues"></a>Problemi comuni di sincronizzazione

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a>Problema: Non è possibile accedere all'abbonamento M365 o Azure Information Protection

Se hai un precedente abbonamento M365 o Azure Information Protection (AIP) che abbia scaduto e sia stato sostituito con un nuovo abbonamento? In questo caso, l'ID tenant è cambiato e i dati del servizio devono essere reimpostati. Vedi le istruzioni per reimpostare i dati nel problema dell'**errore di Cryptographer riscontrato**.

### <a name="issue-sync-is-not-available-for-this-account"></a>Problema: "La sincronizzazione non è disponibile per questo account".

Se si verifica questo errore per un account di Azure Active Directory o se DISABLED_BY_ADMIN viene visualizzato in *edge://sync-internals*, seguire i passaggi della procedura successiva in sequenza fino a risolvere il problema.

> [!NOTE]
> Poiché l'origine di questo errore è in genere una modifica della configurazione in un tenant di Azure Active Directory, questa procedura di risoluzione dei problemi può essere eseguita solo da un amministratore del tenant e non dagli utenti finali.

1. Verifica che il tenant aziendale abbia un abbonamento M365 supportato. L'elenco corrente dei tipi di abbonamento [disponibile qui](/azure/information-protection/activate-office365). Se il tenant non ha un abbonamento supportato, può acquistare Azure Information Protection separatamente oppure eseguire l'aggiornamento a uno degli abbonamenti supportati.
2. Se è disponibile un abbonamento supportato, verifica che nel tenant sia disponibile Azure Information Protection (AIP). Le istruzioni per controllare lo stato di AIP e, se necessario, attivare AIP sono disponibili [qui](/azure/information-protection/activate-office365).
3. Se il passaggio 2 indica che AIP è attivo ma la sincronizzazione non funziona comunque, attiva Enterprise State Roaming (ESR). Le istruzioni per l'abilitazione di ESR sono riportate [qui](/azure/active-directory/devices/enterprise-state-roaming-enable). Tieni presente che ESR non deve rimanere in funzione. Puoi disattivare ESR se questo passaggio consente di risolvere il problema.
4. Verifica che l'ambito di Azure Information Protection non sia in base a un criterio di onboarding. È possibile utilizzare il cmdlet [Di PowerShell Get-AIPServiceOnboardingControlPolicy](/powershell/module/aipservice/get-aipserviceonboardingcontrolpolicy?view=azureipps) per verificare se l'ambito è abilitato. Assicurati che il monitor powershell aIPService sia installato. È possibile ottenerlo qui: [Installare il modulo AIPService PowerShell per Azure Information Protection.](/azure/information-protection/install-powershell) I due esempi seguenti mostrano una configurazione senza ambito e una configurazione che ha come ambito un gruppo di sicurezza specifico.

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AIPServiceOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AIPServiceOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```

   Se l'ambito è abilitato, l'utente interessato deve essere aggiunto al gruppo di sicurezza per l'ambito oppure l'ambito deve essere rimosso. Nell'esempio seguente, l'onboarding ha ambito AIP al gruppo di sicurezza indicato e l'ambito deve essere rimosso con l'applet di PowerShell [Set-AIPServiceOnboardingControlPolicy.](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps)

5. Verifica che IPCv3Service sia attivato nel tenant. Il cmdlet [Di PowerShell Get-AIPServiceConfiguration ](/powershell/module/aipservice/get-aipserviceconfiguration?view=azureipps)  mostra lo stato del servizio.

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="Verificare se IPCv3Service è abilitato.":::

6. Se il problema persiste, contattare il [supporto Microsoft Edge](https://www.microsoftedgeinsider.com/support).

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a>Problema: Bloccato a “Configurazione della sincronizzazione in corso...” o "Non è possibile connettersi al server di sincronizzazione”. Riprova

1. Disconnettersi e quindi accedere nuovamente.
2. Passa a *edge://sync-internals*. Se nella sezione "**Digita info**" è presente l'errore seguente, passa al problema seguente problema **errore di Cryptographer rilevato**.

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. Provare a effettuare il ping all'endpoint del server. L'endpoint server per un client è disponibile in *edge://sync-internals*. Lo screenshot successivo mostra le informazioni sull'endpoint in **Informazioni dell’ambiente**.

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="Informazioni sull'endpoint":::

4. Se l'endpoint del server è vuoto o se non è possibile effettuare il ping al server e nell'ambiente è presente un firewall, verificare che gli endpoint del servizio necessari siano disponibili per il computer client.

   - Endpoint del servizio di sincronizzazione Microsoft Edge:
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - Endpoint di Azure Information Protection:
      - [https://api.aadrm.com](https://api.aadrm.com) (per la maggior parte dei tenant)
      - [https://api.aadrm.de](https://api.aadrm.de) (per i tenant in Germania)
      - [https://api.aadrm.cn](https://api.aadrm.cn) (per i tenant in Cina)
   - [Endpoint del servizio di notifica di Windows](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).

5. Se il problema persiste, contatta il [supporto di Microsoft Edge](https://www.microsoftedgeinsider.com/support).

### <a name="issue-cryptographer-error-encountered"></a>Problema: Errore di Cryptographer rilevato

Questo errore è visibile in **Digita informazione** in *edge://sync-internals* e può significare che i dati sul lato del servizio dell'utente devono essere reimpostati. L'esempio seguente mostra un messaggio di errore di crittografia:
<br>"Errore: GenerateCryptoErrorsForTypes@.. /.. /Components/Sync/driver/data_type_manager_impl. cc: 42, si è verificato un errore di crittografia".

1. Riavvia Microsoft Edge e passa alla *edge://sync-internals* e controlla la sezione "**Stato della chiave dell'account AAD**"
   - "Success" in "Last MIP Result": l'errore del crittografo indica che i dati del server potrebbero essere stati crittografati con una chiave persa. La reimpostazione dei dati è necessaria per riprendere la sincronizzazione.
   - "Nessuna autorizzazione" in "Ultimo risultato MIP": la causa potrebbe essere una modifica di Azure AD o una modifica all’abbonamento del tenant. La reimpostazione dei dati è necessaria per riprendere la sincronizzazione.
   - Altri errori possono significare problemi di configurazione del server.
2. Se è necessaria la reimpostazione dei dati, vedi i [Dati di Microsoft Edge nel cloud](edge-learnmore-reset-data-in-cloud.md).

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a>Problema: "La sincronizzazione è stata disattivata dall'amministratore".

Assicurarsi che non sia impostato il [criterio SyncDisabled](./microsoft-edge-policies.md#syncdisabled).

## <a name="see-also"></a>Vedere anche

- [Sincronizzazione di Microsoft Edge in modalità Enterprise](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)