---
title: Sincronizzazione locale per gli utenti di Active Directory (AD)
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 02/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione locale per gli utenti di Active Directory (AD)
ms.openlocfilehash: 820188db94f4ab2bc9b1ad659c22c324bcea145b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448050"
---
# <a name="on-premises-sync-for-active-directory-ad-users"></a>Sincronizzazione locale per gli utenti di Active Directory (AD)

Questo articolo fornisce informazioni sul come gli utenti di Active Directory (AD) possono effettuare il roaming tra i preferiti e le impostazioni di Microsoft Edge da computer diversi senza connettersi ai servizi cloud Microsoft.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 85 o successiva.

## <a name="introduction"></a>Introduzione

In genere la sincronizzazione dei dati utente in Microsoft Edge richiede un account Microsoft o un account di Azure Active Directory (Azure AD) e una connessione ai servizi cloud Microsoft. Con la sincronizzazione locale, Microsoft Edge salva i preferiti e le impostazioni di un utente di Active Directory in un file che può essere spostato da un computer all’altro. La sincronizzazione locale non interferisce con la sincronizzazione cloud per i profili che la consentono.

## <a name="how-it-works"></a>Come funziona

Microsoft Edge consente l'associazione dei profili agli account di Active Directory (AD), che non possono essere usati con la sincronizzazione cloud. Una volta abilitata la sincronizzazione locale, i dati del profilo AD vengono salvati in un file denominato profile.pb. Per impostazione predefinita, il file viene archiviato in *%APPDATA%/Microsoft/Edge*. Una volta scritto, il file potrà essere spostato tra diversi computer e i dati utente verranno letti e scritti in ogni computer. Microsoft Edge legge e scrive solo da questo file; è responsabilità dell'amministratore assicurarsi che il file sia stato spostato in base alle esigenze.

## <a name="use-on-premises-sync"></a>Utilizzare la sincronizzazione locale

Per utilizzare la sincronizzazione locale è necessario abilitarla, associare un profilo a un account di Active Directory e, facoltativamente, cambiare il percorso dei dati utente.

### <a name="enable-on-premises-sync"></a>Abilitare la sincronizzazione locale

Per abilitare la sincronizzazione locale in Microsoft Edge, configurare il criterio [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled).

### <a name="ensure-that-a-profile-is-associated-with-an-active-directory-account"></a>Verificare che un profilo sia associato a un account di Active Directory

La sincronizzazione locale funziona solo se il profilo è associato a un account di Active Directory (AD). Se non esistono profili di questo tipo, la sincronizzazione locale non funzionerà. Per assicurarsi che gli utenti accedano con un account di Active Directory, configurare il criterio [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin). Per la sincronizzazione locale, Microsoft Edge si basa solo su AD per stabilire un'identità per i dati utente e non esiste alcuna relazione diretta tra il modo in cui Microsoft Edge legge e scrive i dati locali in modo che l'amministratore abbia configurato il roaming per un utente AD.

### <a name="change-the-location-of-the-user-data-optional"></a>Cambiare il percorso dei dati utente (facoltativo)

Per impostazione predefinita, i dati utente vengono archiviati in un file denominato **profile.pb** in *%APPDATA%/Microsoft/Edge*. Per modificare il percorso del file, configurare il criterio [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation).

## <a name="changes-in-the-user-experience-when-on-premises-sync-is-enabled"></a>Modifiche dell'esperienza utente quando è abilitata la sincronizzazione locale

Quando la sincronizzazione locale è abilitata, agli utenti non viene richiesto di abilitare la sincronizzazione. Inoltre, gli utenti non possono disattivare la sincronizzazione nelle impostazioni di sincronizzazione e non possono attivare tipi di sincronizzazione non supportati dalla sincronizzazione locale.

## <a name="on-premises-sync-usage-notes"></a>Note sull'utilizzo della sincronizzazione locale

### <a name="running-cloud-sync-and-on-premises-sync-on-the-same-computer"></a>Eseguire la sincronizzazione cloud e la sincronizzazione locale nello stesso computer

La sincronizzazione locale non interferisce con la sincronizzazione cloud. Se Microsoft Edge include più account Microsoft o profili Azure Active Directory che eseguono la sincronizzazione con il cloud, questi profili continueranno a farlo anche mentre la sincronizzazione locale è abilitata.

### <a name="running-microsoft-edge-on-more-than-one-computer-at-a-time-isnt-recommended"></a>Non è consigliabile eseguire Microsoft Edge in più computer alla volta

Poiché la sincronizzazione locale funziona spostando un file di dati utente da un computer all’altro, la sincronizzazione locale non sincronizza le modifiche tra sessioni simultanee. Per questo motivo, la sincronizzazione locale funziona al meglio in un computer alla volta. Se sono in esecuzione sessioni locali simultanee, i dati di uno o più computer potrebbero essere sovrascritti in modo imprevisto con quelli di un altro computer all'avvio successivo di una sessione del browser.

> [!NOTE]
> Microsoft Edge blocca il file **profile.pb** quando la sincronizzazione locale è abilitata. Se il reindirizzamento delle cartelle viene usato per condividere un singolo file **profile.pb** tra diversi computer, è possibile avviare una sola istanza di Microsoft Edge con quel file.

### <a name="using-other-sync-policies-with-on-premises-sync"></a>Utilizzare altri criteri di sincronizzazione con la sincronizzazione locale

È possibile utilizzare il criterio [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) per disabilitare in modo selettivo i preferiti o le impostazioni di sincronizzazione, se necessario. Il [criterio SyncDisabled](./microsoft-edge-policies.md#syncdisabled) non ha alcun impatto sulla sincronizzazione locale.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ed Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Sincronizzazione di Microsoft Edge in modalità Enterprise](microsoft-edge-enterprise-sync.md)