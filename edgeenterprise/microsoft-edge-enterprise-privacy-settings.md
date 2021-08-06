---
title: Impostazioni della privacy di Microsoft Edge Enterprise
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Configurare le impostazioni della privacy di Microsoft Edge Enterprise
ms.openlocfilehash: fe2a6e57d70a6a37297e28854291b913af1fd08e826df845fc3572fecb09f07a
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726189"
---
# <a name="configure-microsoft-edge-policies-to-support-enterprise-privacy"></a>Configurare i criteri di Microsoft Edge per sostenere la privacy dell'organizzazione.

Microsoft si impegna a fornire alle aziende le informazioni e i controlli necessari per scegliere le opzioni relative alla raccolta dei dati in Microsoft Edge.

## <a name="overview"></a>Panoramica

Quando si distribuisce Microsoft Edge in Windows 10, per impostazione predefinita vengono inviati dati di diagnostica basati sull'[impostazione dati di diagnostica di Windows](/windows/privacy/configure-windows-diagnostic-data-in-your-organization) dell’utente.

Quando Microsoft Edge è distribuito su piattaforme non Windows, i dati diagnostici sono raccolti in base ai seguenti criteri di gruppo:

- (DEPRECATO) [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali. Questo criterio diventerà obsoleto nella versione 89 di Microsoft Edge.
- (DEPRECATO) [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Invia informazioni sul sito per migliorare i servizi Microsoft. Questo criterio diventerà obsoleto nella versione 89 di Microsoft Edge.

I criteri deprecati di cui sopra sono sostituiti da [Consenti telemetria](/windows/privacy/configure-windows-diagnostic-data-in-your-organization) su Windows 10, e dal criterio [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) per tutte le altre piattaforme.  

## <a name="configure-policy-settings"></a>Configurare le impostazioni dei criteri

Prima di iniziare, scarica e usa il modello di criteri di Microsoft Edge più recente (per altre informazioni, vedi [Configurare Microsoft Edge](configure-microsoft-edge.md)).

### <a name="send-required-and-optional-diagnostic-data-about-browser-usage"></a>Invia dati di diagnostica necessari e facoltativi sull'uso del browser

Se il criterio [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) è configurato, avrà la precedenza su [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) e [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices).

#### <a name="required-and-optional-diagnostic-data"></a>Dati di diagnostica necessari e facoltativi

I dati di diagnostica necessari raccolti assicurano che Microsoft Edge resti sicuro e aggiornato, e funzioni come previsto.

I dati di diagnostica facoltativi includono i dati sull'uso del browser, sui siti internet visitati e sugli arresti anomali, per garantire che Microsoft Edge sia sicuro e aggiornato e funzioni come previsto, oltre che per migliorare Microsoft e altri prodotti e servizi Microsoft per tutti gli utenti.

> [!NOTE]
> Questo criterio non è supportato nei dispositivi Windows 10. Per controllare la raccolta di dati in Windows 10, gli amministratori IT devono usare i criteri di gruppo dei dati di diagnostica Windows. Questo criterio può essere sia **Consenti telemetria** o **Consenti dati di diagnostica**, a seconda della versione di Windows in uso. Altre informazioni sulla [raccolta dei dati di diagnostica di Windows 10](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).

Usare una delle impostazioni seguenti per configurare **DiagnosticData**:

- Disattivato (Non raccomandato) (0) disattiva la raccolta dei dati diagnostici obbligatori e facoltativi. 
- Dati necessari (1) invia i dati di diagnostica necessari, ma disattiva la raccolta dei dati di diagnostica facoltativi. Microsoft Edge invia i dati di diagnostica necessari per assicurare che Microsoft Edge rimanga sicuro, aggiornato e funzioni come previsto. 
- Dati facoltativi (2) invia a Microsoft i dati di diagnostica facoltativi, inclusi i dati sull'uso del browser, i siti internet visitati e le segnalazioni degli arresti anomali, per garantire che Microsoft Edge sia sicuro e aggiornato, e funzioni come previsto, oltre che per migliorare Microsoft e altri prodotti e servizi Microsoft per tutti gli utenti.

In Windows 7, Windows 8/8.1 e macOS, questo criterio controlla l'invio di dati obbligatori e facoltativi a Microsoft.

Se non configuri o disattivi questo criterio, Microsoft Edge lo applicherà come impostazione predefinita per le preferenze degli utenti.

### <a name="deprecated-enable-usage-and-crash-related-data-reporting"></a>(DEPRECATO) Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali

Il criterio **MetricsReportingEnabled** abilita l'invio di report a Microsoft per i dati sull'uso e gli arresti anomali di Microsoft Edge.

Microsoft Edge raccoglie una serie di dati necessari per assicurare che il prodotto sia aggiornato, sicuro e funzioni come previsto. Questi dati includono informazioni di configurazione e connettività di base del dispositivo ottenute da Microsoft Edge sul consenso corrente alla raccolta dei dati, sulla versione dell'app e sullo stato di installazione per mantenere Microsoft Edge.La raccolta dei dati può essere disattivata disabilitando i criteri.

Abilita questo criterio per inviare a Microsoft report di dati sull'uso e sull'arresto anomalo. Disabilita questi criteri se non vuoi inviare questi dati a Microsoft. In entrambi i casi, gli utenti non possono modificare né sovrascrivere l'impostazione.

Se Microsoft Edge è in esecuzione in Windows 10:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per i dati di diagnostica Windows.
- Se questi criteri sono abilitati, Microsoft Edge invierà solo i dati sull'utilizzo se l'impostazione dati di diagnostica Windows è impostata su **Avanzato** o **Completo**.
  - Se questo criterio è abilitato, Microsoft Edge invia i dati di utilizzo solo se anche [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) è abilitato.
- Se questi criteri sono disabilitati, Microsoft Edge non invierà i dati sull'utilizzo. I dati relativi agli arresti anomali vengono inviati in base all'impostazione dei dati di diagnostica Windows. [Altre informazioni sulle impostazioni dei dati di diagnostica di Windows](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).

Se Microsoft Edge è in esecuzione in Windows 7, 8 e macOS:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.
-  Se questo criterio è abilitato, Microsoft Edge invia i dati di utilizzo solo se anche [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) è abilitato.

### <a name="deprecated-send-site-information-to-improve-microsoft-services"></a>(DEPRECATO) Invia informazioni sul sito per migliorare i servizi Microsoft

Il criterio **SendSiteInformationToImproveServices** abilita l'invio a Microsoft di informazioni sui siti web visitati con Microsoft Edge, per migliorare i prodotti e i servizi Microsoft, come la ricerca.

Abilita questi criteri per inviare a Microsoft le informazioni sui siti Web visitati in Microsoft Edge. Disabilita questi criteri per non inviare a Microsoft le informazioni sui siti Web visitati in Microsoft Edge. In entrambi i casi, gli utenti non possono modificare né sovrascrivere l'impostazione.

Se Microsoft Edge è in esecuzione in Windows 10:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per i dati di diagnostica Windows.
- Se questi criteri sono abilitati, Microsoft Edge invierà solo le informazioni sui siti Web visitati se l'impostazione dei dati di diagnostica Windows è impostata su **Completo**.
  - Se questo criterio è abilitato, Microsoft Edge invia i dati di utilizzo solo se anche [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) è abilitato. 
- Se questi criteri sono disabilitati, Microsoft Edge non invierà le informazioni sui siti Web visitati. Per [ulteriori informazioni sulle impostazioni dei dati di diagnostica Windows](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).

Se Microsoft Edge è in esecuzione in Windows 7, 8 e macOS:

- Se questo criterio è abilitato, Microsoft Edge invia i dati di utilizzo solo se anche [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) è abilitato.
- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.

## <a name="implementation-details"></a>Dettagli sull'implementazione

Per dispositivi non Windows 10: 
- Se il criterio [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) è configurato, avrà la precedenza su [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) e [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices). 
- Se il criterio [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) non è configurato, Microsoft Edge ascolta [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) e [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices).  

Affinché Windows 10 possa comprendere la nostra implementazione con la dipendenza dall'impostazione dei dati di diagnostica di Windows, la tabella seguente identifica se i dati di diagnostica  **Necessari** e **Facoltativi** sono inviati a Microsoft.

| Impostazione dati di diagnostica Windows | Dati di diagnostica necessari  | Dati di diagnostica facoltativi |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| Sicurezza                        | Non inviato                                      | Non inviato                                            |
| Di base                           | Inviato                                      | Non inviato                                            |
| Avanzato                        | Inviato                                          | Non inviato                                            |
| Completo                            | Inviato                                          | Inviato                                                |

> [!IMPORTANT]
> Microsoft Edge supporterà **MetricsReportingEnabled** e **SendSiteInfoToImproveServices** per le versioni 86-88 di Microsoft Edge. Nella versione 89 di Microsoft Edge, **MetricsReportingEnabled** e **SendSiteInfoToImproveServices** non saranno più supportati, e saranno sostituiti per impostazione predefinita da **DiagnosticData** sulle piattaforme non Windows 10 o dal criterio **Consenti telemetria** per Windows 10.

## <a name="additional-privacy-policy-options"></a>Opzioni aggiuntive per l'informativa sulla privacy

Puoi prendere in esame i criteri di gruppo seguenti relativi alla privacy dei dati:

- Blocca i cookie in siti specifici
- Blocca i cookie di terze parti
- Configura Do Not Track
- Disabilita la modalità InPrivate

## <a name="see-also"></a>Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Criteri di Microsoft Edge](microsoft-edge-policies.md)
- [Whitepaper sulla privacy di Microsoft Edge](/microsoft-edge/privacy-whitepaper)