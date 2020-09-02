---
title: Microsoft Edge ed Enterprise State Roaming
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge ed Enterprise State Roaming
ms.openlocfilehash: a759b1d9d4be8dced7bfcc2ef8d0f23b514f4be0
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980288"
---
# Microsoft Edge ed Enterprise State Roaming

Questo articolo spiega come cambia la partecipazione di Microsoft Edge all'offerta Enterprise State Roaming (ESR) per supportare meglio la sincronizzazione su piattaforme e dispositivi.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Introduzione

Con Windows 10, gli utenti di [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) hanno la possibilità di sincronizzare in modo sicuro nel cloud le impostazioni dell'utente e i dati delle impostazioni dell'applicazione. [Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) offre agli utenti un'esperienza unificata su tutti i loro dispositivi Windows e riduce il tempo necessario per la configurazione di un nuovo dispositivo.

Come parte di Microsoft Edge che adotta la piattaforma Chromium, la soluzione di sincronizzazione è ora disconnessa dal framework di sincronizzazione di Windows. Ciò influisce sulla relazione di Microsoft Edge rispetto all'offerta di ESR.

> [!IMPORTANT]
> Il nuovo Microsoft Edge non partecipa all'offerta di ESR.

## Cosa cambia con Microsoft Edge?

Con il nuovo Microsoft Edge, la soluzione di sincronizzazione non è legata all'ecosistema di sincronizzazione di Windows. Questo ci consente di offrire Microsoft Edge in tutte le piattaforme, ad esempio Windows 7, Windows 8.1, iOS, Android e macOS. Ci consente inoltre di offrire la sincronizzazione per gli account non primari su Windows. Inoltre, possiamo distribuire Microsoft Edge a una cadenza di rilascio più frequente e flessibile rispetto a Windows. Per altre informazioni, vedi [Aggiornamenti di Windows per supportare la prossima versione di Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md). Tutti questi fattori hanno evidenziato la necessità di rivalutare la partecipazione di Microsoft Edge all'offerta ESR.

ESR è inquadrato come un'offerta di prodotti Windows con la promessa di gestione dei dati dai dispositivi Windows, ma la sincronizzazione di Microsoft Edge si estende oltre i dispositivi Windows. Inoltre, poiché i dati vengono trasferiti su questi dispositivi, risulta difficile definire l'offerta di sincronizzazione di Microsoft Edge nel contesto di ESR. Per semplificare il funzionamento e la gestione della sincronizzazione e per soddisfare le modifiche evidenziate, è stata presa la decisione di eliminare Microsoft Edge dall'offerta ESR.

## Questo significa che le imprese perderanno le capacità che avevano come parte dell'ESR?

No. Microsoft Edge continuerà a supportare la maggior parte delle funzionalità fornite nell'offerta ESR.

### Esperienza unificata tra dispositivi e nuovo tempo di configurazione dei dispositivi

Quando un utente è connesso al dispositivo Windows con Azure Active Directory (account Azure AD), Microsoft Edge eredita l'identità in modo implicito al primo avvio del nuovo browser.

Dopo che un utente ha acconsentito esplicitamente ad attivare la sincronizzazione nel nuovo Microsoft Edge, il browser sincronizza tutti i dati del browser, ad esempio i preferiti, le password e la cronologia. Questo garantisce un'esperienza unificata tra i dispositivi e riduce il tempo necessario per personalizzare il browser.

### Separazione dei dati aziendali e consumer

Le organizzazioni hanno il controllo dei propri dati e non vi è alcuna combinazione di dati aziendali di un account cloud consumer o un account cloud aziendale.

### Sicurezza avanzata

I dati vengono crittografati automaticamente prima di lasciare il dispositivo Windows 10 dell'utente tramite Azure Information Protection e rimangono crittografati nel cloud. Tutti i contenuti rimangono crittografati nel cloud, fatta eccezione per gli spazi dei nomi, come i nomi delle impostazioni.

### Monitoraggio

Viene fornito il controllo e la visibilità per l'utente che sincronizza le impostazioni dell'organizzazione e i dispositivi utilizzati, tramite l'integrazione con il portale di Azure AD. Questa capacità verrà abilitata in una versione futura.

### Gestione

Gli amministratori sono in grado di controllare quali membri dell'organizzazione possono abilitare la sincronizzazione. Per informazioni, vedi [Opzioni di configurazione per la sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md#configuration-options-for-microsoft-edge-sync) e [Criteri di gruppo per la sincronizzazione](microsoft-edge-enterprise-sync.md#sync-group-policies). Inoltre, gli utenti possono attivare o disattivare la sincronizzazione per ogni dispositivo, nonché attivare o disattivare singolarmente ogni attributo di dati per la sincronizzazione.

### Gestione delle chiavi

La funzionalità di sincronizzazione utilizza Azure Information Protection (AIP) per proteggere i dati sincronizzati solo per l'utente e gli amministratori dell'organizzazione. AIP supporta sia la chiave gestita da Microsoft (impostazione predefinita) che la tua chiave per la gestione delle chiavi del cloud. La strategia di gestione delle chiavi del cloud utilizzata dall'organizzazione è trasparente per Microsoft Edge e non ha alcun impatto sulla funzionalità di sincronizzazione.

> [!IMPORTANT]
> [Hold your own key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) e il servizio Active Directory Rights Management Services non sono supportati.

## Riepilogo degli attributi di sincronizzazione

I seguenti attributi di dati verranno sincronizzati nella nuova versione di Microsoft Edge al primo avvio:

- Preferiti
- Password
- Riempimento di moduli
- Cronologia
- Schede aperte (sessioni)
- Impostazioni (preferenze)
- Estensioni

L'elenco degli attributi precedente è diverso dagli attributi che possono essere sincronizzati in Microsoft Edge Legacy. Per informazioni dettagliate sulle impostazioni di Microsoft Edge Legacy, vedi [Impostazioni di roaming di Windows 10](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference). Gli utenti possono abilitare o disabilitare selettivamente questi attributi usando le impostazioni di Microsoft Edge. Data la differenza negli attributi tra le due versioni (ad esempio, la cronologia), agli utenti potrebbe essere richiesto di concedere nuovamente il consenso per la sincronizzazione.

> [!NOTE]
> A differenza di Microsoft Edge Legacy, il nuovo Microsoft Edge non usa Gestione credenziali di Windows per le password e di conseguenza non sincronizza le password con Internet Explorer o altre app che usano Gestione credenziali di Windows.

## Condizioni per l'utilizzo del servizio

Le condizioni per l'utilizzo del servizio di sincronizzazione Microsoft Edge rientrano nella licenza software Microsoft visualizzabile in Microsoft Edge all'indirizzo *edge://terms*.

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md)