---
title: Configurare Microsoft Edge in macOS con Jamf
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 6/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge nei dispositivi Mac con Jamf
ms.openlocfilehash: 8556a5b1d0fc01feb67fc86cb016a9ed47061b55
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979745"
---
# <a name="configure-microsoft-edge-policy-settings-on-macos-with-jamf"></a>Configurare le impostazioni dei criteri di Microsoft Edge in macOS con Jamf

Questo articolo descrive come configurare le impostazioni dei criteri in macOS usando un file manifesto dei criteri Microsoft Edge in Jamf Pro 10.19.

È possibile anche configurare le impostazioni dei criteri di Microsoft Edge su macOS usando un file di elenco delle proprietà (.plist). Per altre informazioni, consultare [Configurare macOS con un file plist](configure-microsoft-edge-on-mac.md)


## <a name="prerequisites"></a>Prerequisiti

È necessario il software seguente:

- Canale Stable di Microsoft Edge 81
- File dei modelli di criteri, versione 81.0.416.3
- Jamf Pro, versione 10.19

## <a name="about-the-jamf-pro-application--custom-settings-menu"></a>Informazioni sul menu Impostazioni dell'applicazione e personalizzate di Jamf Pro

Prima di Jamf Pro 10,18, era necessario creare manualmente un file plist per la gestione di Office 365. Si trattava di un flusso di lavoro che richiedeva molto tempo e una solida preparazione tecnica. Jamf Pro 10.18 ha superato tali ostacoli semplificando il processo di configurazione. Tuttavia, gli amministratori IT possono usare questa nuova interfaccia utente solo per determinate applicazioni e domini di preferenza specificati da Jamf.

In Jamf Pro 10.19 l'utente può caricare un manifesto JSON come "schema personalizzato" scegliendo qualsiasi dominio di preferenza come destinazione, l'interfaccia utente grafica verrà generata da tale manifesto. Lo schema personalizzato creato segue la specifica dello Schema JSON.

Per altre informazioni, consultare [Profili di configurazione del computer](https://jamf.it/computer-configuration-profiles) nel manuale dell'amministratore di Jamf Pro.

## <a name="get-the-policy-manifest-for-a-specific-version-of-microsoft-edge"></a>Ottenere il manifesto dei criteri per una versione specifica di Microsoft Edge

Per ottenere il manifesto del criterio:

- Passare alla [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).
- Nell'elenco a discesa Canale/Versione, selezionare **qualsiasi canale con la versione 81 o successiva.***.
- Nell'elenco a discesa Build selezionare qualsiasi **Build 81 o versione successiva.***.
- Fare clic su OTTIENI FILE DEI CRITERI per scaricare il pacchetto dei modelli di criteri.

  > [!NOTE]
  > Attualmente il pacchetto dei modelli di criteri è firmato come file CAB. È necessario usare uno strumento di terze parti, ad esempio The Unarchiver per aprire il file in macOS.

Decomprimere prima il file CAB poi il file ZIP e passare alla directory "Mac" di primo livello. Il manifesto, denominato "policy_manifest.json, si trova in questa directory.

Questo manifesto verrà pubblicato in ogni pacchetto di criteri a partire dalla build 81.0.416.3. Se si vogliono testare i criteri nel canale Dev, è possibile usare il manifesto associato a ogni rilascio di Dev e testarlo in Jamf Pro.  

## <a name="use-the-policy-manifest-in-jamf-pro"></a>Usare il manifesto dei criteri in Jamf Pro

Seguire la procedura seguente per caricare il manifesto dei criteri in Jamf Pro e poi creare un profilo dei criteri per macOS.

1. Accedere a Jamf.
2. Selezionare la scheda **Computer**.
3. In **Gestione dei contenuti** selezionare **Profili di configurazione**.
4. Nella pagina **Profili di configurazione** fare clic su **+ Nuovo**.

   ![Aggiungere un nuovo profilo in Jamf](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. In **Nuovo profilo di configurazione di macOS**>**Opzioni** selezionare ** Impostazioni dell'applicazione e personalizzate**.
6. Nella finestra popup **Impostazioni dell'applicazione e personalizzate** fare clic su **Configura**.

   ![Configurare le impostazioni dell'applicazione e le impostazioni personalizzate](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. Nella sezione **Impostazioni dell'applicazione e personalizzate** impostare i valori visualizzati nella schermata seguente.

   ![Origine profilo e schema personalizzato](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - Per **Metodo di creazione** selezionare **Configura le impostazioni**.
   - Per **Origine** selezionare **Schema personalizzato**.
   - Per **Dominio di preferenza** specificare il nome del proprio dominio. Questo esempio usa *com.microsoft.Edge* come dominio.
   - Per **Schema personalizzato** incollare il contenuto del file manifesto "policy_manifest.json".
   - Fare clic su **Save**.

8. Dopo aver salvato il profilo, Jamf visualizza la sezione **Generale** mostrata nella schermata successiva.

   ![Configurare la Sezione generale](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - Fornire un **Nome** visualizzato per il profilo e una **Descrizione**.
   - Mantenere l'impostazione predefinita per la **Categoria** ovvero **Nessuna**.
   - Per **Metodo di distribuzione** le opzioni sono **Installa automaticamente** oppure **Rendi disponibile in modalità self-service**.
   - Per **Livello** le opzioni sono **Livello utente** o **Livello computer**.
   - Fare clic su **Save**.

9. Dopo aver salvato la Sezione generale, Jamf visualizza il profilo di configurazione del canale Microsoft Edge Beta impostato per l'esempio. Nella schermata successiva, tenere presente che è possibile continuare a usare il profilo facendo clic **Modifica** oppure, se si è terminato, fare clic su **Fine**.

   ![Nuovo profilo di configurazione con opzioni](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > È possibile modificare il profilo dopo che è stato salvato e in un'altra sessione di Jamf. Ad esempio, si può decidere di modificare il metodo di distribuzione per renderla disponibile in modalità self-service.

   Per eseguire una successiva modifica al canale Stable di Microsoft Edge o per eliminarlo, selezionare il nome del profilo visualizzato nella schermata Profili di configurazione seguente.

   ![Elenco profili di configurazione](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

Dopo aver creato il nuovo profilo di configurazione, è necessario configurare l'**Ambito** per il profilo.

### <a name="to-configure-the-scope"></a>Per configurare l'ambito

1. Per **Destinazioni** specificare le impostazioni minime seguenti:

   - COMPUTER DI DESTINAZIONE. Le opzioni disponibili sono: computer specifici o tutti i computer.
   - UTENTI DI DESTINAZIONE. Le opzioni disponibili sono: utenti specifici o tutti gli utenti.
   - Fare clic su **Save**.
2. Per **Limitazioni** mantenere l'impostazione predefinita: Nessuna. Fare clic su **Annulla**.
3. Per **Esclusioni** mantenere l'impostazione predefinita: Nessuna. Fare clic su **Annulla**.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Configurare per macOS con Intune](configure-microsoft-edge-on-mac.md)
- [Configurare per Windows](configure-microsoft-edge.md)
- [Configurare per Windows con Intune](configure-edge-with-intune.md)
