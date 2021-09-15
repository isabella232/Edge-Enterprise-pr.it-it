---
title: Domande frequenti sulla sincronizzazione aziendale di Microsoft Edge
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Domande frequenti sulla sincronizzazione aziendale di Microsoft Edge.
ms.openlocfilehash: a13e1f02f6e871004d45f81159d5cf0a3397b6ad
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980288"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a>Domande frequenti sulla sincronizzazione aziendale di Microsoft Edge

Questo articolo risponde alle domande frequenti sulla sincronizzazione aziendale per Microsoft Edge versione 77 o successiva.

## <a name="security-and-serverdata-compliance"></a>Sicurezza e conformità di server e dati

### <a name="is-the-synced-data-encrypted"></a>I dati sincronizzati sono crittografati?

I dati vengono crittografati durante la trasmissione con TLS 1.2 o versione successiva. Inoltre, tutti tipi di dati inattivi vengono crittografati nel servizio Microsoft usando AES128. Tutti i tipi di dati, ad eccezione di quelli usati per la sincronizzazione delle schede aperte e della cronologia, vengono inoltre crittografati prima di lasciare il dispositivo dell'utente con chiavi gestite tramite le norme di [Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern).

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a>Perché per i dati delle schede aperte e della cronologia non viene applicata crittografia del lato del client?

Per ridurre l'utilizzo delle risorse nei dispositivi degli utenti finali, i dati della cronologia vengono generati sul lato server in base ai dati di roaming delle schede aperte. Questo processo non sarebbe possibile con la crittografia lato client di questi dati. Per disabilitare la sincronizzazione delle schede aperte e della cronologia, applicare i criteri [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) o [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled).

### <a name="can-tenant-admins-bring-their-own-key"></a>Gli amministratori del tenant possono usare le chiavi personali?

Sì, tramite  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

### <a name="where-is-microsoft-edge-sync-data-stored"></a>Dove vengono archiviati i dati di sincronizzazione di Microsoft Edge?

I dati sincronizzati per gli account Azure AD sono archiviati in server protetti in base all'ID tenant. Ad esempio, i dati per un tenant registrato negli Stati Uniti sono archiviati in server geografici specifici per l'area geografica e usano la stessa soluzione di archiviazione delle applicazioni di Office.

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a>Oltre alla sincronizzazione con Microsoft Edge, i dati lasciano mai il cloud di Microsoft?

No.

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a>Quali sono le condizioni d'uso che interessano la sincronizzazione aziendale?

Le condizioni d'uso del servizio di sincronizzazione di Microsoft Edge rientrano nella licenza software Microsoft, visualizzabile in Microsoft Edge in *edge://terms*. Le condizioni d'uso e la sottoscrizione di Azure AD rientrano nelle [Condizioni per l'utilizzo dei servizi online ](https://www.microsoft.com/licensing/product-licensing/products)di Microsoft".

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a>Microsoft Edge supporta la conformità del Government Community Cloud (GCC) High?

Al momento no. Per i clienti nel cloud GCC High, la sincronizzazione di Microsoft Edge è disabilitata.

## <a name="applying-sync"></a>Applicazione della sincronizzazione

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a>Perché la sincronizzazione di Microsoft Edge non è supportata in tutti gli abbonamenti a Microsoft 365?

La sincronizzazione aziendale dipende dalla [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), che non è disponibile in tutti gli abbonamenti a M365.

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a>La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?

No. ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR. Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](/DeployEdge/microsoft-edge-enterprise-sync) e [Microsoft Edge e Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming).

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a>Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?

Non è previsto il supporto di questa sincronizzazione. Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, considerare la [nuova modalità Internet Explorer](./edge-ie-mode.md).

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a>Microsoft Edge verrà sincronizzato con la versione legacy di Microsoft Edge?

No. Crediamo che connettere questi due ecosistemi possa compromettere l'affidabilità della sincronizzazione in Microsoft Edge. Garantiamo la migrazione dei dati esistenti in Microsoft Edge. Gli utenti potranno anche importare dati dal browser a loro scelta, il che significa anche che Microsoft Edge non sarà in grado di eseguire la sincronizzazione con Internet Explorer.

## <a name="managing-sync"></a>Gestione della sincronizzazione

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a>È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?

Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern).

## <a name="see-also"></a>Vedere anche

- [Sincronizzazione di Microsoft Edge in modalità Enterprise](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)