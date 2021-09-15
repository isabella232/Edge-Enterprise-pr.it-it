---
title: Sicurezza Microsoft Edge per la tua azienda
ms.author: collw
author: seanongit
manager: chuckf
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Sicurezza Microsoft Edge per la tua azienda
ms.openlocfilehash: d16b22b63212e3f5319b0bb7df1e457e45cd6208
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980335"
---
# <a name="microsoft-edge-security-for-your-business"></a>Sicurezza Microsoft Edge per la tua azienda

Microsoft Edge si basa sul progetto open source Chromium, lo stesso progetto da cui nasce Google Chrome, il che significa che alla base condivide l’architettura e il design di sicurezza ben progettati e collaudati. La storia della sicurezza di Microsoft Edge non finisce qui. **Microsoft Edge, infatti, è più sicuro di Google Chrome per le tua azienda su Windows 10**. Ha potenti difese integrate contro phishing e malware e supporta in modo nativo l'isolamento dell'hardware su Windows 10: non è richiesto alcun software aggiuntivo per raggiungere questo standard di sicurezza. Inoltre, se abbinato al supporto nativo per i servizi di sicurezza e conformità di Microsoft 365, Microsoft Edge offre funzionalità e caratteristiche di sicurezza aggiuntive e potenti che aiutano a proteggere dalla perdita di dati cosi da ottenere ulteriori vantaggi. Per altre informazioni, vedere il [video: sicurezza, compatibilità e gestibilità di Microsoft Edge](microsoft-edge-video-security-compatibility-manageability.md).

Entriamo nei dettagli, iniziando con le **minacce esterne** e poi esaminiamo i **rischi interni e la protezione delle informazioni**.

## <a name="external-threat-protection"></a>Protezione dalle minacce esterne

### <a name="highest-rated-protection-against-phishing-and-malware"></a>Massima protezione contro phishing e malware

Integrato in Microsoft Edge, SmartScreen blocca più tentativi di [phishing](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWASN1) e [malware](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWANMW) rispetto alla navigazione sicura di Google Chrome, in base a uno studio indipendente di NSS Labs. SmartScreen fornisce controlli della reputazione di siti e download in tempo reale, mentre gli utenti lavorano online e fa parte di [Microsoft Intelligent Security Graph](https://www.microsoft.com/microsoft-365/windows/intelligent-security), che trae segnali e approfondimenti generati dalla vasta rete di risorse globali, ricercatori e partner di Microsoft. Eseguendo controlli sugli elenchi dinamici basati nel cloud contenenti siti e download pericolosi, Microsoft Edge aiuta a rilevare e bloccare anche le minacce effimere che scompaiono rapidamente.  

[Microsoft Edge SmartScreen](//DeployEdge/microsoft-edge-security-smartscreen) ha bloccato il 95,5% dei tentativi di phishing durante il test di [protezione anti phishing di NSS Labs](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWASN1) e il 98,5% dei tentativi di malware durante il test di [protezione anti malware di NSS Labs](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWANMW) rispetto all’86,9% e all'86,0% dell’esplorazione sicura di Chrome.

### <a name="the-only-browser-on-windows-10-that-natively-supports-hardware-isolation"></a>L'unico browser su Windows 10 che supporta in modo nativo le funzionalità di isolamento hardware

Microsoft Edge è l'unico browser su Windows 10 che supporta in modo nativo le funzionalità di isolamento hardware. Microsoft Defender Application Guard (Application Guard), facente parte di Windows 10 Pro o Enterprise, esegue i siti non attendibili in un kernel isolato dal dispositivo locale e dalle reti interne. I siti non attendibili vengono eseguiti in un "contenitore", pertanto quando si verifica un attacco, viene eseguito il sandboxing dal resto della rete aziendale. Per ulteriori informazioni, vedi [Supporto di Microsoft Edge per Application Guard](./microsoft-edge-security-windows-defender-application-guard.md).

Per Chrome, è disponibile un'estensione per sfruttare l'isolamento hardware di Windows 10: l'estensione MDAG. Questa estensione avvia quindi Microsoft Edge per sfruttare l'isolamento a livello di kernel di Application Guard. Inoltre, per ottenere un isolamento a livello di kernel simile solo per Chrome, è necessario un software di isolamento di terze parti.

> [!NOTE]
> Application Guard è disponibile su Windows 10, 1809 e versioni successive. Application Guard non è disponibile nelle edizioni di Windows 10 Home.

## <a name="internal-risks-and-information-protection"></a>Rischi interni e protezione delle informazioni

### <a name="native-support-for-microsoft-365-security-without-additional-software"></a>Supporto nativo per la sicurezza di Microsoft 365 senza software aggiuntivo

Oltre a proteggere dalle minacce esterne, gli amministratori IT devono anche proteggere dai rischi interni. La protezione dei dati aziendali sensibili, in modo vigoroso e su larga scala, è una priorità assoluta per gli amministratori IT, soprattutto perché la forza lavoro si è decentralizzata. Microsoft Edge è l'unico browser con supporto nativo per l’Accesso Condizionale di Azure AD, Windows Information Protection e la nuova prevenzione della perdita di dati degli endpoint di Microsoft (DLP) senza software aggiuntivo richiesto.

**Microsoft Edge è l'unico browser a supportare in modo nativo l'Accesso Condizionale**. [Il supporto di Microsoft Edge per l'accesso condizionale](ms-edge-security-conditional-access.md) semplifica l’utilizzo da parte delle organizzazioni dei segnali di identità come parte delle loro decisioni di controllo degli accessi. L'[Accesso Condizionale](/azure/active-directory/conditional-access/overview) è lo strumento utilizzato da Azure Active Directory per riunire i segnali, prendere decisioni e applicare i criteri dell'organizzazione. L'accesso condizionale è al centro del nuovo piano di controllo basato sull'identità. Per ottenere il supporto per l'Accesso Condizionale su Chrome, è necessario un plug-in aggiuntivo.

> [!NOTE]
> È richiesto un abbonamento a Microsoft 365 E3 o versione successiva per l'Accesso Condizionale di Azure AD.

**Microsoft Edge è l'unico browser a supportare in modo nativo Windows Information Protection (WIP)**, che fornisce protezione ai dati aziendali in modo da aiutare a prevenire perdite accidentali da parte degli utenti sui dispositivi Windows 10. [Il supporto di Microsoft Edge per WIP](./microsoft-edge-security-windows-information-protection.md) può essere configurato per consentire solo alle app con mandato IT di accedere ai dati aziendali. Fornisce inoltre controlli sulle perdite, come la protezione degli appunti, la crittografia dei file durante il download e la prevenzione del caricamento dei file in condivisioni di rete non autorizzate o posizioni nel cloud, per un'esperienza utente uniforme. WIP funziona su una configurazione basata sul perimetro, in cui gli amministratori IT definiscono il confine aziendale e tutti i dati all'interno di tale confine sono considerati aziendali. Google Chrome non è ottimizzato per l'utilizzo di WIP con controlli di perdita dei dati.

> [!NOTE]
> La configurazione di Windows Information Protection (WIP) richiede una licenza di Microsoft Intune o Microsoft Endpoint Configuration Manager o l'utilizzo di una soluzione di gestione dei dispositivi mobili (MDM) di terze parti, che potrebbe avere requisiti di licenza aggiuntivi.

**La prevenzione delle perdita dei dati di Microsoft Endpoint (Endpoint DLP) è supportata solo in modo nativo in Microsoft Edge**. Endpoint DLP si integra con Microsoft Security Center ed estende la protezione delle informazioni a Microsoft Edge per avvisare gli utenti di attività non conformi e prevenire la perdita di dati mentre gli utenti lavorano online. Rileva ed etichetta i dati sensibili all'interno dell'azienda che corrispondono ai criteri definiti dall'amministratore, come file contenenti numeri di carta di credito o ID governativi (ad esempio, numeri di previdenza sociale), informazioni finanziarie, ecc. È possibile distribuire i criteri di Microsoft Information Protection su Microsoft Endpoint DLP senza riconfigurazione aggiuntiva, includendo identificatori di contenuti sensibili e criteri che gli amministratori IT hanno già personalizzato. Si tratta di una distribuzione senza interruzioni della protezione delle informazioni per gli amministratori IT.

Per altre informazioni sui prerequisiti di Endpoint DLP e su come configurarlo, vai a [Introduzione a la prevenzione della perdita di dati di Endpoint](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide).

> [!NOTE]
> È richiesto un abbonamento a Microsoft 365 E5 o Microsoft 365 E5 Compliance per la prevenzione della perdita di dati di Microsoft Endpoint.

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: sicurezza, compatibilità e gestibilità di Microsoft Edge](microsoft-edge-video-security-compatibility-manageability.md)