---
title: Configurare Microsoft Edge per macOS con un file plist
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge in macOS con un file di elenco delle proprietà (con estensione plist)
ms.openlocfilehash: df8a51869665416ae7babe24fb7419ccaf723af6b8ca0381065d97b3728a4d87
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11725279"
---
# <a name="configure-microsoft-edge-policy-settings-for-macos-using-a-plist"></a>Configurare le impostazioni dei criteri di Microsoft Edge per macOS con un file di elenco delle proprietà (con estensione plist)

Questo articolo descrive come configurare Microsoft Edge su macOS usando un file di elenco delle proprietà (con estensione plist). Informazioni su come creare il file e poi distribuirlo in Microsoft Intune.

Per altre informazioni, vedi [Informazioni sui file di elenco delle proprietà di informazione](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (sito Web di Apple) e [Impostazioni di payload personalizzate](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="configure-microsoft-edge-policies-on-macos"></a>Configurare i criteri di Microsoft Edge in macOS

Il primo passaggio consiste nel creare un file plist. Puoi creare il file plist con qualsiasi editor di testo oppure puoi usare [Terminal per creare il profilo di configurazione](#create-a-configuration-profile-using-terminal). Tuttavia, è più semplice creare e modificare un file plist usando uno strumento che formatti automaticamente il codice XML. *Xcode* è un ambiente di sviluppo integrato gratuito che puoi ottenere da una delle seguenti risorse:

- [Sito Web per sviluppatori Apple](https://developer.apple.com/xcode/)
- [App Store Mac](https://apps.apple.com/app/xcode/id497799835?mt=12)

Per un elenco dei criteri supportati e dei relativi nomi chiave di preferenza, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md). Nel file dei modelli di criteri, che può essere scaricato dalla [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise), è disponibile un file plist di esempio (*itadminexample.plist*) nella cartella **esempi**. Il file di esempio contiene tutti i tipi di dati supportati che puoi personalizzare per definire le impostazioni dei criteri. 

Il passaggio successivo dopo aver creato il contenuto del file plist è quello di nominarlo usando il dominio di preferenza di Microsoft Edge, ovvero *com.mcrosoft.Edge*. Il nome fa distinzione tra maiuscole e minuscole e non deve includere il canale di destinazione, perché si applica a tutti i canali Microsoft Edge. Il nome del file plist deve essere **_com.microsoft.Edge.plist_**.

> [!IMPORTANT]
> A partire dalla build 78.0.249.2, tutti i canali Microsoft Edge in macOS leggono dal dominio delle preferenze **com.microsoft.Edge**. Tutte le versioni precedenti vengono lette da un dominio specifico, ad esempio **com.microsoft.Edge.Dev** per il canale Dev.

L'ultimo passaggio consiste nel distribuire il file plist nei dispositivi Mac degli utenti usando il provider MDM preferito, ad esempio Microsoft Intune. Per istruzioni, vedi [Distribuire il file plist](#deploy-your-plist).

### <a name="create-a-configuration-profile-using-terminal"></a>Creare un profilo di configurazione con Terminal

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

## <a name="deploy-your-plist"></a>Distribuire il file plist

Per Microsoft Intune crea un nuovo profilo di configurazione del dispositivo destinato alla piattaforma macOS e seleziona il tipo di profilo *File delle preferenze*. Definisci **com.microsoft.Edge** come nome di dominio di preferenze e carica il file plist. Per altre informazioni, vedi [Aggiungere un file di elenco delle proprietà ai dispositivi macOS usando Microsoft Intune](/intune/configuration/preference-file-settings-macos).

Per Jamf carica il file plist come un payload *Impostazioni personalizzate*.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Configurare per macOS con Jamf](configure-microsoft-edge-on-mac-jamf.md)
- [Configurare per Windows](configure-microsoft-edge.md)
- [Configurare per Windows con Intune](configure-edge-with-intune.md)