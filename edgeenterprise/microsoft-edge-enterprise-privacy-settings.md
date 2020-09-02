---
title: Impostazioni della privacy di Microsoft Edge Enterprise
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni della privacy di Microsoft Edge Enterprise
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980278"
---
# Configurare i criteri di Microsoft Edge per sostenere la privacy dell'organizzazione.

Microsoft si impegna a fornire alle aziende le informazioni e i controlli necessari per scegliere le opzioni relative alla raccolta dei dati in Microsoft Edge.

## Panoramica

Per impostazione predefinita, Microsoft Edge distribuito in piattaforme diverse da Windows non invia dati di diagnostica o informazioni sul sito a Microsoft. Quando si distribuisce Microsoft Edge in Windows 10, per impostazione predefinita vengono inviati dati di diagnostica basati sull'[impostazione dati di diagnostica di Windows](https://go.microsoft.com/fwlink/?linkid=2099569) dell’utente.

È anche possibile configurare il modo in cui Microsoft Edge gestisce la raccolta dei dati per l'organizzazione con i criteri di gruppo seguenti:

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali.
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Invia informazioni sul sito per migliorare i servizi Microsoft.

## Configurare le impostazioni dei criteri

Prima di iniziare, scarica e usa il modello di criteri di Microsoft Edge più recente (per altre informazioni, vedi [Configurare Microsoft Edge](configure-microsoft-edge.md)).

### Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali

Questi criteri abilitano l'invio di report a Microsoft sui dati sull'uso e sull'arresto anomalo di Microsoft Edge.

Microsoft Edge raccoglie una serie di dati necessari per mantenere il prodotto sicuro, aggiornato e correttamente funzionante. Questi dati includono informazioni di configurazione e connettività di base del dispositivo ottenute da Microsoft Edge sul consenso corrente alla raccolta dei dati, sulla versione dell'app e sullo stato di installazione per mantenere Microsoft Edge.La raccolta dei dati può essere disattivata disabilitando i criteri.

Abilita questo criterio per inviare a Microsoft report di dati sull'uso e sull'arresto anomalo. Disabilita questi criteri se non vuoi inviare questi dati a Microsoft. In entrambi i casi, gli utenti non possono modificare né sovrascrivere l'impostazione.

Se Microsoft Edge è in esecuzione in Windows 10:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per i dati di diagnostica Windows.
- Se questi criteri sono abilitati, Microsoft Edge invierà solo i dati sull'utilizzo se l'impostazione dati di diagnostica Windows è impostata su **Avanzato** o **Completo**.
- Se questi criteri sono disabilitati, Microsoft Edge non invierà i dati sull'utilizzo. I dati relativi agli arresti anomali vengono inviati in base all'impostazione dei dati di diagnostica Windows. [Altre informazioni sulle impostazioni dei dati di diagnostica di Windows](https://go.microsoft.com/fwlink/?linkid=2099569).

Se Microsoft Edge è in esecuzione in Windows 7, 8 e macOS:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.

### Invia informazioni sul sito per migliorare i servizi Microsoft

Questi criteri consentono di inviare informazioni sui siti Web visitati in Microsoft Edge a Microsoft per migliorare i prodotti e i servizi Microsoft, ad esempio la ricerca.

Abilita questi criteri per inviare a Microsoft le informazioni sui siti Web visitati in Microsoft Edge. Disabilita questi criteri per non inviare a Microsoft le informazioni sui siti Web visitati in Microsoft Edge. In entrambi i casi, gli utenti non possono modificare né sovrascrivere l'impostazione.

Se Microsoft Edge è in esecuzione in Windows 10:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per i dati di diagnostica Windows.
- Se questi criteri sono abilitati, Microsoft Edge invierà solo le informazioni sui siti Web visitati se l'impostazione dei dati di diagnostica Windows è impostata su **Completo**.
- Se questi criteri sono disabilitati, Microsoft Edge non invierà le informazioni sui siti Web visitati. Per [ulteriori informazioni sulle impostazioni dei dati di diagnostica Windows](https://go.microsoft.com/fwlink/?linkid=2099569).

Se Microsoft Edge è in esecuzione in Windows 7, 8 e macOS:

- Se questi criteri non sono configurati, Microsoft Edge applicherà l'impostazione predefinita per le preferenze degli utenti.

## Dettagli sull'implementazione

Per Windows 10, per comprendere la nostra implementazione con la dipendenza dall'impostazione dei dati di diagnostica Windows, nella tabella seguente viene descritta la configurazione se **Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali** e **Invia informazioni sul sito per migliorare i servizi Microsoft** non sono state configurate.

| Impostazione dati di diagnostica Windows | Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali | Invia informazioni sul sito per migliorare i servizi Microsoft |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| Sicurezza                        | Non inviato                                      | Non inviato                                            |
| Di base                           | Non inviato                                      | Non inviato                                            |
| Avanzato                        | Inviato                                          | Non inviato                                            |
| Completo                            | Inviato                                          | Inviato                                                |

Se le configurazioni per Windows 10 sono state configurate in modo non conforme alla tabella precedente, verrà eseguito il fallback all'impostazione di raccolta dei dati minore.

Ad esempio:

- Imposti i criteri “Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali” su **Abilitato** ma la configurazione dei dati di diagnostica Windows è impostata su **Base**. Non invieremo i dati correlati all'uso e agli arresti anomali.
- Imposti i criteri “Invia informazioni sul sito per migliorare i servizi Microsoft” su **Disabilitato** ma la configurazione dei dati di diagnostica Windows è impostata su **Completo**. Non invieremo informazioni sui siti di visitati.

La corretta implementazione per le configurazioni precedenti sarebbe l'impostazione dei criteri “Abilita la segnalazione dei dati correlati all'uso e agli arresti anomali” su **Abilitato** e l’impostazione dei dati di diagnostica Windows su **Avanzato** o **Completo**.

## Opzioni aggiuntive per l'informativa sulla privacy

Puoi prendere in esame i criteri di gruppo seguenti relativi alla privacy dei dati:

- Blocca i cookie in siti specifici
- Blocca i cookie di terze parti
- Configura Do Not Track
- Disabilita la modalità InPrivate

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Criteri di Microsoft Edge](microsoft-edge-policies.md)
- [Whitepaper sulla privacy di Microsoft Edge](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
