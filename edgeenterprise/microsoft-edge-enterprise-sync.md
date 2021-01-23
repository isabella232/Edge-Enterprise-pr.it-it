---
title: Configurare e risolvere i problemi relativi a Microsoft Edge Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/22/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare e risolvere i problemi relativi a Microsoft Edge Sync
ms.openlocfilehash: 36912d2fd1c33a227ce1d4b7c912f6ef1dfdcc00
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297457"
---
# Configurare e risolvere i problemi relativi a Microsoft Edge Sync

Questo articolo spiega come usare Microsoft Edge per sincronizzare preferiti, password e altri dati del browser in tutti i dispositivi connessi. Questo articolo fornisce anche i passaggi per la risoluzione dei problemi di sincronizzazione più comuni. Include anche gli strumenti consigliati per raccogliere i log necessari per la risoluzione dei problemi.

> [!NOTE]
> Applica a Microsoft Edge versione 77 o successiva, se non diversamente specificato.

## Panoramica

La sincronizzazione di Microsoft Edge consente agli utenti di accedere ai dati di esplorazione in tutti i dispositivi connessi. I dati supportati dalla sincronizzazione sono:

- Preferiti
- Password
- Indirizzi e altro (riempimento di moduli)
- Raccolte
- Impostazioni
- Estensione
- Schede aperte (disponibile in Microsoft Edge versione 88)
- Cronologia (disponibile in Microsoft Edge versione 88)

La funzionalità di sincronizzazione è abilitata tramite il consenso dell'utente e gli utenti possono attivare o disattivare la sincronizzazione per ognuno dei tipi di dati elencati in precedenza.

> [!NOTE]
> Per supportare la funzionalità di sincronizzazione vengono caricati altri dati di configurazione e connettività del dispositivo (ad esempio il nome dispositivo, la marca e il modello).

## Prerequisiti

La sincronizzazione di Microsoft Edge per gli account di Azure Active Directory (Azure AD) è disponibile per le sottoscrizioni seguenti:

- Azure AD Premium (P1 o P2)
- Microsoft 365 Business Premium
- Office 365 E1 e superiore
- Azure Information Protection (AIP) (P1 o P2)
- Tutti gli abbonamenti EDU (Microsoft Apps per studenti o istituti di istruzione, Exchange Online per studenti o istituti di istruzione, Office 365 A1 o versione successiva, Microsoft 365 A1 o superiore o Azure Information Protection P1 o P2 per studenti o istituti di istruzione)

## Criteri di gruppo per la sincronizzazione

È possibile usare i criteri di gruppo seguenti per configurare e gestire Microsoft Edge Sync:

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): disabilita completamente la sincronizzazione.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilita anche la sincronizzazione delle schede aperte.
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): quando questo criterio è disabilitato, verrà disabilitata anche la sincronizzazione della cronologia.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): consente di configurare l'elenco dei tipi esclusi dalla sincronizzazione.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): consente ai profili di Active Directory (AD) di usare lo spazio di archiviazione locale. Per altre informazioni, vedere [Sincronizzazione locale per gli utenti di Active Directory (AD)](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): attivare la sincronizzazione per default e non richiedere il consenso dell'utente per la sincronizzazione.  

## Configurare Microsoft Edge Sync

Le opzioni di configurazioni per la sincronizzazione di Microsoft Edge sono disponibili tramite il servizio di Azure Information Protection (AIP). Quando AIP è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze. [Qui](https://docs.microsoft.com/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.

Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AIP](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true)  per gli utenti. Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell.

> [!CAUTION]
> L'attivazione di Azure Information Protection consentirà inoltre ad altre applicazioni, come Microsoft Word o Microsoft Outlook, di proteggere il contenuto con AIP. I criteri di controllo onboarding usati per limitare la sincronizzazione Edge impediranno anche ad altre applicazioni di proteggere il contenuto tramite AIP.

## Microsoft Edge e Enterprise state roaming (ESR)

Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per la sincronizzazione dei dati degli utenti in tutti i loro dispositivi e non è una parte di longaer di Azure AD Enterprise State Roaming. Tuttavia, Microsoft Edge soddisfa le promesse per la protezione dei dati di ESR, come la possibilità di creare una chiave personalizzata. Per ulteriori informazioni, vedi [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

## Risolvere i problemi di sincronizzazione

In questa sezione vengono illustrati i passaggi per la risoluzione dei problemi di sincronizzazione più rilevati. Include anche gli strumenti consigliati per raccogliere i log necessari per la risoluzione dei problemi.

### Problemi di identità versus ai problemi di sincronizzazione

Uno dei casi di utilizzo più diffusi per gestire l'identità degli utenti nel browser è supportare la sincronizzazione. Per questo motivo, i problemi di identità vengono spesso confusi con i problemi di sincronizzazione. Comprendere la differenza tra i problemi di identità e sincronizzazione prima di avviare la risoluzione dei problemi di sincronizzazione.

Prima di considerare un problema di sincronizzazione, verificare se l'utente ha eseguito l'accesso al browser con un account valido.

Nella schermata successiva viene illustrato un esempio di errore di identità. L'errore è "**errore token ultimo, EDGE_AUTH_ERROR: 3, 54, 3ea**", disponibile in *Edge://Sync-internals* in **Credenziali**:

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="Errore ultimo token EDGE_AUTH_ERROR: 3, 54, 3ea":::

### Problemi comuni di sincronizzazione

#### Problema: Non è possibile accedere all'abbonamento M365 o Azure Information Protection

Se hai un precedente abbonamento M365 o Azure Information Protection (AIP) che abbia scaduto e sia stato sostituito con un nuovo abbonamento? In questo caso, l'ID tenant è cambiato e i dati del servizio devono essere reimpostati. Vedi le istruzioni per reimpostare i dati nel problema dell'**errore di Cryptographer riscontrato**.

#### Problema: "La sincronizzazione non è disponibile per questo account".

Se si verifica questo errore per un account di Azure Active Directory o se DISABLED_BY_ADMIN viene visualizzato in *edge://sync-internals*, seguire i passaggi della procedura successiva in sequenza fino a risolvere il problema.

> [!NOTE]
> Poiché l'origine di questo errore è in genere una modifica della configurazione in un tenant di Azure Active Directory, questa procedura di risoluzione dei problemi può essere eseguita solo da un amministratore del tenant e non dagli utenti finali.

1. Verifica che il tenant aziendale abbia un abbonamento M365 supportato. L'elenco corrente dei tipi di abbonamento [disponibile qui](https://docs.microsoft.com/azure/information-protection/activate-office365). Se il tenant non ha un abbonamento supportato, può acquistare Azure Information Protection separatamente oppure eseguire l'aggiornamento a uno degli abbonamenti supportati.
2. Se è disponibile un abbonamento supportato, verifica che nel tenant sia disponibile Azure Information Protection (AIP). Le istruzioni per controllare lo stato di AIP e, se necessario, attivare AIP sono disponibili [qui](https://docs.microsoft.com/azure/information-protection/activate-office365).
3. Se il passaggio 2 indica che AIP è attivo ma la sincronizzazione non funziona comunque, attiva Enterprise State Roaming (ESR). Le istruzioni per l'abilitazione di ESR sono riportate [qui](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable). Tieni presente che ESR non deve rimanere in funzione. Puoi disattivare ESR se questo passaggio consente di risolvere il problema.
4. Verifica che l'ambito di Azure Information Protection non sia in base a un criterio di onboarding. Puoi usare l'applet [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps)  applet PowerShell per verificare se l'ambito è abilitato. I due esempi seguenti mostrano una configurazione non attiva e un ambito di configurazione per un gruppo di sicurezza specifico.

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```


   Se l'ambito è abilitato, l'utente interessato deve essere aggiunto al gruppo di sicurezza per l'ambito oppure l'ambito deve essere rimosso. Nell'esempio seguente l'ambito del processo di onboarding è AIP nel gruppo di sicurezza indicato e l'ambito deve essere rimosso con l'applet PowerShell[Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps).

5. Verifica che IPCv3Service sia attivato nel tenant. L’applet di Powersell[Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) mostra lo stato del servizio.

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="Verificare se IPCv3Service è abilitato.":::

6. Se il problema persiste, contattare il [supporto Microsoft Edge](https://www.microsoftedgeinsider.com/support).

#### Problema: Bloccato a “Configurazione della sincronizzazione in corso...” o "Non è possibile connettersi al server di sincronizzazione”. Riprova

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
   - [Endpoint del servizio di notifica di Windows](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).

5. Se il problema persiste, contatta il [supporto di Microsoft Edge](https://www.microsoftedgeinsider.com/support).

### Problema: Errore di Cryptographer rilevato

Questo errore è visibile in **Digita informazione** in *edge://sync-internals* e può significare che i dati sul lato del servizio dell'utente devono essere reimpostati. L'esempio seguente mostra un messaggio di errore di crittografia:
<br>"Errore: GenerateCryptoErrorsForTypes@.. /.. /Components/Sync/driver/data_type_manager_impl. cc: 42, si è verificato un errore di crittografia".

1. Riavvia Microsoft Edge e passa alla *edge://sync-internals* e controlla la sezione "**Stato della chiave dell'account AAD**"
   - "Success" in "Last MIP Result": l'errore del crittografo indica che i dati del server potrebbero essere stati crittografati con una chiave persa. La reimpostazione dei dati è necessaria per riprendere la sincronizzazione.
   - "Nessuna autorizzazione" in "Ultimo risultato MIP": la causa potrebbe essere una modifica di Azure AD o una modifica all’abbonamento del tenant. La reimpostazione dei dati è necessaria per riprendere la sincronizzazione.
   - Altri errori possono significare problemi di configurazione del server.
2. Se è necessaria la reimpostazione dei dati, vedi i [Dati di Microsoft Edge nel cloud](edge-learnmore-reset-data-in-cloud.md).

#### Problema: "La sincronizzazione è stata disattivata dall'amministratore".

Assicurarsi che il [criterio di SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)  sia impostato.

## Domande frequenti

### SICUREZZA e CONFORMITÀ SERVER/DATI

#### I dati sincronizzati sono crittografati?

I dati vengono crittografati durante la trasmissione con TLS 1.2 o versione successiva. Inoltre, tutti tipi di dati inattivi vengono crittografati nel servizio Microsoft usando AES128. Tutti i tipi di dati, ad eccezione di quelli usati per la sincronizzazione delle schede aperte e della cronologia, vengono inoltre crittografati prima di lasciare il dispositivo dell'utente con chiavi gestite tramite le norme di [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern).

#### Perché per i dati delle schede aperte e della cronologia non viene applicata crittografia del lato del client?

Per ridurre l'utilizzo delle risorse nei dispositivi degli utenti finali, i dati della cronologia vengono generati sul lato server in base ai dati di roaming delle schede aperte. Questo processo non sarebbe possibile con la crittografia lato client di questi dati. Per disabilitare la sincronizzazione delle schede aperte e della cronologia, applicare i criteri [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) o [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled).

#### Gli amministratori del tenant possono usare le chiavi personali?

Sì, tramite  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

#### Dove vengono archiviati i dati di sincronizzazione di Microsoft Edge?

I dati sincronizzati per gli account Azure AD sono archiviati in server protetti in base all'ID tenant. Ad esempio, i dati per un tenant registrato negli Stati Uniti sono archiviati in server geografici specifici per l'area geografica e usano la stessa soluzione di archiviazione delle applicazioni di Office.

#### Oltre alla sincronizzazione con Microsoft Edge, i dati lasciano mai il cloud di Microsoft?

No.

#### Quali sono le condizioni d'uso che interessano la sincronizzazione aziendale?

Le condizioni d'uso del servizio di sincronizzazione di Microsoft Edge rientrano nella licenza software Microsoft, visualizzabile in Microsoft Edge in *edge://terms*. Le condizioni d'uso e la sottoscrizione di Azure AD rientrano nelle [Condizioni per l'utilizzo dei servizi online ](https://www.microsoft.com/licensing/product-licensing/products)di Microsoft".

#### Microsoft Edge supporta la conformità del Government Community Cloud (GCC) High?

Al momento no. Per i clienti nel cloud GCC High, la sincronizzazione di Microsoft Edge è disabilitata.

### APPLICAZIONE DELLA SINCRONIZZAZIONE

#### Perché la sincronizzazione di Microsoft Edge non è supportata in tutti gli abbonamenti a Microsoft 365?

La sincronizzazione aziendale dipende dalla [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), che non è disponibile in tutti gli abbonamenti a M365.

#### La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?

No. ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR. Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync) e [Microsoft Edge e Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming).

#### Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?

Non è previsto il supporto di questa sincronizzazione. Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, considerare la [nuova modalità Internet Explorer](https://docs.microsoft.com/deployedge/edge-ie-mode).

#### Microsoft Edge verrà sincronizzato con la versione legacy di Microsoft Edge?

No. Crediamo che connettere questi due ecosistemi possa compromettere l'affidabilità della sincronizzazione in Microsoft Edge. Garantiamo la migrazione dei dati esistenti in Microsoft Edge. Gli utenti potranno anche importare dati dal browser a loro scelta, il che significa anche che Microsoft Edge non sarà in grado di eseguire la sincronizzazione con Internet Explorer.

### GESTIONE DELLA SINCRONIZZAZIONE

#### È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?

Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern).

## Vedere anche

- [Sincronizzazione di Microsoft Edge in modalità Enterprise](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
