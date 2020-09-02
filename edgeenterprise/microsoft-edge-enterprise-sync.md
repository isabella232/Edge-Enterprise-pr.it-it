---
title: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 08/03/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.openlocfilehash: a6d01356db478871a7c6b386bbb731b32dc4739a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980277"
---
# Sincronizzazione di Microsoft Edge in modalità Enterprise

Questo articolo spiega come usare Microsoft Edge per sincronizzare preferiti, password e altri dati del browser in tutti i dispositivi connessi.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Panoramica

La sincronizzazione di Microsoft Edge consente agli utenti di accedere ai dati di esplorazione in tutti i dispositivi connessi. I dati supportati dalla sincronizzazione sono:

- Preferiti
- Password
- Indirizzi e altro (riempimento di moduli)
- Raccolte
- Impostazioni

La funzionalità di sincronizzazione è abilitata tramite il consenso dell'utente e gli utenti possono attivare o disattivare la sincronizzazione per ognuno dei tipi di dati elencati in precedenza.

> [!NOTE]
> Per supportare la funzionalità di sincronizzazione vengono caricati altri dati di configurazione e connettività del dispositivo (ad esempio il nome dispositivo, la marca e il modello).

## Prerequisiti

Attualmente la sincronizzazione di Microsoft Edge per gli account di Azure Active Directory (Azure AD) è disponibile per gli abbonamenti seguenti:

- Azure AD Premium (P1 e P2)
- M365 Business Premium
- Office 365 E3 e superiore
- Azure Information Protection (AIP) (P1& P2)
- Tutte le sottoscrizioni EDU (O365 A1 o superiore, M365 A1 o superiore o Azure Information Protection P1 o P2 per studenti o docenti)

> [!NOTE]
> La sincronizzazione ha una dipendenza dal servizio di protezione offerto da Azure Information Protection (AIP) per proteggere i dati di sincronizzazione. Questo servizio è attualmente disponibile per le sottoscrizioni precedenti. Per vedere l'elenco completo degli SKU con AIP, vedi [Prezzi per la protezione delle informazioni](https://azure.microsoft.com/pricing/details/information-protection/).

## Opzioni di configurazioni per la sincronizzazione di Microsoft Edge

Per abilitare la sincronizzazione di Microsoft Edge, sono disponibili le opzioni di configurazione seguenti:

- Azure Information Protection (AIP)
- Azure AD Enterprise State Roaming (ESR)

Se sia AIP che ESR sono disabilitati, gli utenti riceveranno un messaggio di errore indicante che la sincronizzazione non è disponibile per i loro account.

### Azure Information Protection (AIP)

Se il servizio Azure Information Protection (AIP) è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze. [Qui](https://docs.microsoft.com/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.

Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AADRM](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) per gli utenti. Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell.

> [!CAUTION]
> L'attivazione di Azure Information Protection limiterà inoltre l'accesso per altre applicazioni che usano AIP, come Microsoft Word o Microsoft Outlook.

### Azure AD Enterprise State Roaming (ESR)

Se la funzionalità di Azure Active Directory [Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) è abilitata per un utente o un tenant, la funzionalità di sincronizzazione Microsoft Edge è disponibile indipendentemente dall'impostazione dei criteri di controllo di onboarding.

## Microsoft Edge ed Enterprise State Roaming

Il nuovo Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per la sincronizzazione dei dati degli utenti in tutti i dispositivi e non fa più parte di Azure AD Enterprise State Roaming. Tuttavia, il nuovo Microsoft Edge conserva le caratteristiche della protezione dei dati di ESR, ad esempio la possibilità di portare la propria chiave. Per ulteriori informazioni, vedi [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

## Criteri di gruppo per la sincronizzazione

I criteri di gruppo seguenti influiscono sulla sincronizzazione di Microsoft Edge:

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): disabilita completamente la sincronizzazione.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilitata anche la sincronizzazione delle schede aperte.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): configurare l'elenco dei tipi esclusi dalla sincronizzazione.

## Domande frequenti

### SICUREZZA e CONFORMITÀ SERVER/DATI

#### I dati sincronizzati sono crittografati? 

I dati vengono crittografati durante la trasmissione tramite TLS 1.2 o versione successiva, e successivamente in modo statico nel servizio Microsoft tramite AES256.

#### Dove vengono archiviati i dati sincronizzati di Microsoft Edge?

I dati sincronizzati per gli account Azure AD sono archiviati in server protetti in base all'ID tenant. Ad esempio, i dati per un tenant registrato negli Stati Uniti sono archiviati in server geografici specifici per l'area geografica e usano la stessa soluzione di archiviazione delle applicazioni di Office.

#### Oltre alla sincronizzazione con Microsoft Edge, i dati lasciano mai il cloud di Microsoft?

No.

#### Gli amministratori del tenant possono usare le chiavi personali?

Sì, tramite [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

#### Quali sono le condizioni dell'utilizzo del servizio che interessano la sincronizzazione aziendale?

Le condizioni dell'utilizzo del servizio sono le stesse dell'abbonamento a Azure AD. Tutte le condizioni dell'utilizzo del servizio di Azure AD rientrano nelle [Condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products) di Microsoft.

#### Microsoft Edge supporta la conformità del Government Community Cloud (GCC) High?

Al momento no. GCC High è di livello D, mentre Microsoft Edge supporta fino al livello C.

### APPLICAZIONE DELLA SINCRONIZZAZIONE

#### Cosa accade per i clienti aziendali e di istituti di istruzione che decidono di rimanere con Microsoft Edge Legacy?

La versione corrente del browser Microsoft Edge continuerà a partecipare all'offerta ESR.

#### Perché è necessario un abbonamento Premium ad Azure AD per la sincronizzazione?

La sincronizzazione aziendale dipende da Azure Information Protection, che non è disponibile in tutti i livelli di Azure Active Directory.

#### La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?

No. ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR. Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md) e [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

#### Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?

Non è previsto il supporto di questa sincronizzazione. Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, prendere in considerazione la [nuova modalità di IE](https://docs.microsoft.com/deployedge/edge-ie-mode).

#### Il nuovo browser Microsoft Edge verrà sincronizzato con la Versione legacy di Microsoft Edge?

No, non viene sincronizzato. Riteniamo che la connessione di questi due ecosistemi consente compromessi nell'affidabilità della sincronizzazione nel nuovo Microsoft Edge. Garantiamo la migrazione dei dati esistenti al nuovo Microsoft Edge. Gli utenti saranno anche in grado di importare i dati dal browser che desiderano. Questo significa anche che il nuovo browser Microsoft Edge non avrà un modo per eseguire la sincronizzazione con Internet Explorer.

### GESTIONE DELLA SINCRONIZZAZIONE

#### È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?

Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern).

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
