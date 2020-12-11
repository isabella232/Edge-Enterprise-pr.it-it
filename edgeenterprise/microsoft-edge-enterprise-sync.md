---
title: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 12/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.openlocfilehash: 791188b5d28c867d6409a4d5373ea6c1ec7e49c7
ms.sourcegitcommit: 482b2e440a62cbf974dc45ac817f9d9d187ba1b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205465"
---
# Sincronizzazione di Microsoft Edge in modalità Enterprise

Questo articolo spiega come usare Microsoft Edge per sincronizzare preferiti, password e altri dati del browser in tutti i dispositivi connessi.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva, se non diversamente specificato.

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

## Configurazione di Microsoft Edge

Le opzioni di configurazioni per la sincronizzazione di Microsoft Edge sono disponibili tramite il servizio di Azure Information Protection (AIP). Quando AIP è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze. [Qui](https://docs.microsoft.com/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.

Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AIP](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true)  per gli utenti. Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell.

> [!CAUTION]
> L'attivazione di Azure Information Protection consentirà inoltre ad altre applicazioni, come Microsoft Word o Microsoft Outlook, di proteggere il contenuto con AIP. I criteri di controllo onboarding usati per limitare la sincronizzazione Edge impediranno anche ad altre applicazioni di proteggere il contenuto tramite AIP.

## Microsoft Edge ed Enterprise State Roaming

Il nuovo Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per la sincronizzazione dei dati degli utenti in tutti i dispositivi e non fa più parte di Azure AD Enterprise State Roaming. Tuttavia, il nuovo Microsoft Edge conserva le caratteristiche della protezione dei dati di ESR, ad esempio la possibilità di portare la propria chiave. Per ulteriori informazioni, vedi [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

## Criteri di gruppo per la sincronizzazione

I criteri di gruppo seguenti influiscono sulla sincronizzazione di Microsoft Edge:

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): disabilita completamente la sincronizzazione.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilita anche la sincronizzazione delle schede aperte.
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): quando questo criterio è disabilitato, verrà disabilitata anche la sincronizzazione della cronologia.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): consente di configurare l'elenco dei tipi esclusi dalla sincronizzazione.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): consente ai profili di Active Directory (AD) di usare lo spazio di archiviazione locale. Per altre informazioni, vedere [Sincronizzazione locale per gli utenti di Active Directory (AD)](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): attiva la sincronizzazione per impostazione predefinita e non è necessario il consenso da parte dell’utente per la sincronizzazione.  

## Domande frequenti

### SICUREZZA e CONFORMITÀ SERVER/DATI

#### I dati sincronizzati sono crittografati?

I dati vengono crittografati durante la trasmissione con TLS 1.2 o versione successiva. Inoltre, tutti tipi di dati inattivi vengono crittografati nel servizio Microsoft usando AES128. Tutti i tipi di dati, ad eccezione di quelli usati per la sincronizzazione delle schede aperte e della cronologia, vengono inoltre crittografati prima di lasciare il dispositivo dell'utente con chiavi gestite tramite [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/).

#### Perché per i dati delle schede aperte e della cronologia non viene applicata crittografia lato client aggiuntiva?  

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

La sincronizzazione aziendale dipende da Azure Information Protection, che non è disponibile in tutti gli abbonamenti a Microsoft 365.

#### La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?

No. ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR. Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md) e [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

#### Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?

Non è previsto il supporto di questa sincronizzazione. Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, considerare la [nuova modalità Internet Explorer](https://docs.microsoft.com/deployedge/edge-ie-mode).

#### Microsoft Edge verrà sincronizzato con la versione legacy di Microsoft Edge?

No. Crediamo che connettere questi due ecosistemi possa compromettere l'affidabilità della sincronizzazione in Microsoft Edge. Garantiamo la migrazione dei dati esistenti in Microsoft Edge. Gli utenti saranno anche in grado di importare i dati dal browser che desiderano. Questo significa anche che il nuovo browser Microsoft Edge non avrà un modo per eseguire la sincronizzazione con Internet Explorer.

### GESTIONE DELLA SINCRONIZZAZIONE

#### È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?

Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern).

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
