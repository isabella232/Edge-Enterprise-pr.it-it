---
title: Configurare Microsoft Edge per macOS con un file plist
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge in macOS con un file di elenco delle proprietà (con estensione plist)
ms.openlocfilehash: 84469a4f84deeee0e47b6d8899426fa36cf345aa
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980122"
---
# Configurare le impostazioni dei criteri di Microsoft Edge per macOS con un file di elenco delle proprietà (con estensione plist)

Questo articolo descrive come configurare Microsoft Edge su macOS usando un file di elenco delle proprietà (con estensione plist). Informazioni su come creare il file e poi distribuirlo in Microsoft Intune.

Per altre informazioni, vedi [Informazioni sui file di elenco delle proprietà di informazione](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (sito Web di Apple) e [Impostazioni di payload personalizzate](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Configurare i criteri di Microsoft Edge in macOS

Il primo passaggio consiste nel creare un file plist. Puoi creare il file plist con qualsiasi editor di testo oppure puoi usare [Terminal per creare il profilo di configurazione](#create-a-configuration-profile-using-terminal). Tuttavia, è più semplice creare e modificare un file plist usando uno strumento che formatti automaticamente il codice XML. *Xcode* è un ambiente di sviluppo integrato gratuito che puoi ottenere da una delle seguenti risorse:

- [Sito Web per sviluppatori Apple](https://developer.apple.com/xcode/)
- [App Store Mac](https://apps.apple.com/app/xcode/id497799835?mt=12)

Per un elenco dei criteri supportati e dei relativi nomi chiave di preferenza, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md). Nel file dei modelli di criteri, che può essere scaricato dalla [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise), è disponibile un file plist di esempio (*itadminexample.plist*) nella cartella **esempi**. Il file di esempio contiene tutti i tipi di dati supportati che puoi personalizzare per definire le impostazioni dei criteri. 

Il passaggio successivo dopo aver creato il contenuto del file plist è quello di nominarlo usando il dominio di preferenza di Microsoft Edge, ovvero *com.mcrosoft.Edge*. Il nome fa distinzione tra maiuscole e minuscole e non deve includere il canale di destinazione, perché si applica a tutti i canali Microsoft Edge. Il nome del file plist deve essere **_com.microsoft.Edge.plist_**. 

> [!IMPORTANT]
> A partire dalla build 78.0.249.2, tutti i canali Microsoft Edge in macOS leggono dal dominio delle preferenze **com.microsoft.Edge**. Tutte le versioni precedenti vengono lette da un dominio specifico, ad esempio **com.microsoft.Edge.Dev** per il canale Dev.

L'ultimo passaggio consiste nel distribuire il file plist nei dispositivi Mac degli utenti usando il provider MDM preferito, ad esempio Microsoft Intune. Per istruzioni, vedi [Distribuire il file plist](#deploy-your-plist).

### Creare un profilo di configurazione con Terminal

1. In Terminal usa il comando seguente per creare un file plist per Microsoft Edge sul desktop con le impostazioni preferite:

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. Converti il file plist dal formato binario al testo normale:

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```
Dopo la conversione del file, verifica che i dati dei criteri siano corretti e che il file contenga le impostazioni desiderate per il profilo di configurazione.

> [!NOTE]
> Solo le coppie chiave-valore devono essere nel contenuto del file plist o XML. Prima di caricare il file in Intune, rimuovi tutti i valori \<plist> e \<dict> e le intestazioni XML dal file. Il file deve contenere solo coppie chiave-valore.

## Distribuire il file plist

Per Microsoft Intune crea un nuovo profilo di configurazione del dispositivo destinato alla piattaforma macOS e seleziona il tipo di profilo *File delle preferenze*. Definisci **com.microsoft.Edge** come nome di dominio di preferenze e carica il file plist. Per altre informazioni, vedi [Aggiungere un file di elenco delle proprietà ai dispositivi macOS usando Microsoft Intune](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos).

Per Jamf carica il file plist come un payload *Impostazioni personalizzate*.

## Domande frequenti

### Microsoft Edge può essere configurato per l'uso delle preferenze master?

Sì, Microsoft Edge può essere configurato per l'uso di un file delle preferenze master.

Un file delle preferenze master consente di configurare le impostazioni predefinite per un profilo utente del browser quando Microsoft Edge viene distribuito. Puoi anche usare un file delle preferenze master per applicare le impostazioni nei computer che non sono gestiti da un sistema di gestione dei dispositivi. Queste impostazioni vengono applicate al profilo dell'utente la prima volta che l'utente usa il browser. Dopo che l'utente ha usato il browser, le modifiche apportate al file delle preferenze master non vengono applicate. Un utente può modificare le impostazioni delle preferenze master nel browser. Se desideri impostare un valore obbligatorio o modificare un'impostazione dopo la prima esecuzione del browser, devi usare un criterio.

Un file delle preferenze master ti permette di personalizzare molte impostazioni e preferenze diverse per il browser, incluse quelle condivise con altri browser basati su Chromium e specifici per Microsoft Edge.  Le preferenze relative ai criteri possono essere configurate usando il file delle preferenze master. Nei casi in cui è stato impostato un criterio ed è presente un set di preferenze master corrispondente, l'impostazione dei criteri ha la precedenza.

> [!IMPORTANT]
> Tutte le preferenze disponibili potrebbero non essere coerenti con la terminologia e le convenzioni di denominazione di Microsoft Edge.  Non c'è alcuna garanzia che queste preferenze continueranno a funzionare come previsto nelle versioni future. Le preferenze potrebbero essere modificate o ignorate nelle versioni successive.

Un file delle preferenze master è un file di testo formattato con il markup JSON. Questo file deve essere aggiunto alla stessa directory dell'eseguibile msedge.exe. Per distribuzioni aziendali a livello di sistema in macOS si tratta in genere di "*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*" o "*/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*".

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Configurare per macOS con Jamf](configure-microsoft-edge-on-mac-jamf.md)
- [Configurare per Windows](configure-microsoft-edge.md)
- [Configurare per Windows con Intune](configure-edge-with-intune.md)
