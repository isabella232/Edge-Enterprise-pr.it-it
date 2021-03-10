---
title: Configurare la sincronizzazione aziendale di Microsoft Edge
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Opzioni di amministratore e utente per la configurazione di Microsoft Edge per la sincronizzazione di preferiti, password e altri dati del browser.
ms.openlocfilehash: bfaa1db297093d0b0655a8d217aefcd59d11ac5e
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400140"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a>Configurare la sincronizzazione aziendale di Microsoft Edge

Questo articolo spiega come gli amministratori possono configurare Microsoft Edge per sincronizzare i preferiti, le password e altri dati del browser degli utenti in tutti i dispositivi connessi.

> [!NOTE]
> Si applica a Microsoft Edge versione 77 o successiva, se non diversamente specificato.

## <a name="overview"></a>Panoramica

La sincronizzazione di Microsoft Edge consente agli utenti di accedere ai dati di esplorazione in tutti i dispositivi connessi. I dati supportati dalla sincronizzazione sono:

- Preferiti
- Password
- Indirizzi e altro (riempimento di moduli)
- Raccolte
- Impostazioni
- Estensione
- Schede aperte (disponibile in Microsoft Edge versione 88)
- Cronologia (disponibile in Microsoft Edge versione 88)

La funzionalità di sincronizzazione è abilitata tramite il consenso dell'utente e gli utenti possono attivare o disattivare la sincronizzazione per ognuno dei tipi di dati elencati in precedenza. Se un utente riscontra un problema di sincronizzazione, potrebbe dover reimpostare la sincronizzazione in **Impostazioni** > **Profili** > **Reimposta sincronizzazione**.

> [!NOTE]
> Per supportare la funzionalità di sincronizzazione vengono caricati altri dati di configurazione e connettività del dispositivo (ad esempio il nome dispositivo, la marca e il modello).

## <a name="prerequisites"></a>Prerequisiti

La sincronizzazione di Microsoft Edge per gli account di Azure Active Directory (Azure AD) è disponibile per le sottoscrizioni seguenti:

- Azure AD Premium (P1 o P2)
- Microsoft 365 Business Premium
- Office 365 E1 e superiore
- Azure Information Protection (AIP) (P1 o P2)
- Tutti gli abbonamenti EDU (Microsoft Apps per studenti o istituti di istruzione, Exchange Online per studenti o istituti di istruzione, Office 365 A1 o versione successiva, Microsoft 365 A1 o superiore o Azure Information Protection P1 o P2 per studenti o istituti di istruzione)

## <a name="sync-group-policies"></a>Criteri di gruppo per la sincronizzazione

Gli amministratori possono usare i seguenti criteri di gruppo per configurare e gestire la sincronizzazione di Microsoft Edge:

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): disabilita completamente la sincronizzazione.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilita anche la sincronizzazione delle schede aperte.
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): quando questo criterio è disabilitato, verrà disabilitata anche la sincronizzazione della cronologia.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): consente di configurare l'elenco dei tipi esclusi dalla sincronizzazione.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): consente ai profili di Active Directory (AD) di usare lo spazio di archiviazione locale. Per altre informazioni, vedere [Sincronizzazione locale per gli utenti di Active Directory (AD)](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): attivare la sincronizzazione per default e non richiedere il consenso dell'utente per la sincronizzazione.  

## <a name="configure-microsoft-edge-sync"></a>Configurare Microsoft Edge Sync

Le opzioni di configurazioni per la sincronizzazione di Microsoft Edge sono disponibili tramite il servizio di Azure Information Protection (AIP). Quando AIP è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze. [Qui](https://docs.microsoft.com/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.

Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AIP](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true)  per gli utenti. Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell.

> [!CAUTION]
> L'attivazione di Azure Information Protection consentirà inoltre ad altre applicazioni, come Microsoft Word o Microsoft Outlook, di proteggere il contenuto con AIP. I criteri di controllo onboarding usati per limitare la sincronizzazione Edge impediranno anche ad altre applicazioni di proteggere il contenuto tramite AIP.

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a>Microsoft Edge e Enterprise state roaming (ESR)

Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per sincronizzare i dati degli utenti in tutti i loro dispositivi e non fa più parte del roaming dello stato di Azure AD Enterprise. Tuttavia, Microsoft Edge soddisfa le promesse per la protezione dei dati di ESR, come la possibilità di creare una chiave personalizzata. Per ulteriori informazioni, vedere [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

## <a name="see-also"></a>Vedere anche

- [Sincronizzazione di Microsoft Edge in modalità enterprise](microsoft-edge-enterprise-sync.md)
- [Diagnosticare e risolvere i problemi di sincronizzazione di Microsoft Edge](microsoft-edge-troubleshoot-enterprise-sync.md)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
