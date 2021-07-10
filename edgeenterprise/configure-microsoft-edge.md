---
title: Configurare Microsoft Edge per Windows
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge nei dispositivi Windows
ms.openlocfilehash: a5db4352e723539843a5ad80a7b067e670bced5c
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642002"
---
# <a name="configure-microsoft-edge-policy-settings-on-windows"></a>Configurare le impostazioni dei criteri di Microsoft Edge in Windows

Usa le informazioni seguenti per configurare le impostazioni dei criteri di Microsoft Edge nei dispositivi Windows.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="configure-policy-settings-on-windows"></a>Configurare le impostazioni dei criteri in Windows

Puoi usare gli _oggetti Criteri di gruppo_ per configurare le impostazioni dei criteri per Microsoft Edge e per gli aggiornamenti gestiti di Microsoft Edge in tutte le versioni di Windows. Puoi anche effettuare il provisioning dei criteri tramite il Registro di sistema per i dispositivi Windows aggiunti a un dominio di Active Directory di Microsoft o alle istanze di Windows 10 Pro o Enterprise registrate per la gestione dei dispositivi in Microsoft Intune. Per configurare Microsoft Edge con gli oggetti Criteri di gruppo, puoi installare _modelli amministrativi_ che aggiungono regole e impostazioni per Microsoft Edge all'archivio centrale dei criteri di gruppo nel dominio di Active Directory o nella cartella dei modelli di definizione dei criteri nei singoli computer e quindi configurare i criteri specifici desiderati.

Puoi usare Criteri di gruppo di Active Directory per configurare le impostazioni dei criteri di Microsoft Edge se preferisci gestire i criteri a livello di dominio. In questo modo è possibile gestire le impostazioni dei criteri globalmente, scegliere impostazioni di criteri diverse per unità organizzative specifiche o usare filtri WMI per applicare le impostazioni solo agli utenti o ai computer restituiti da una particolare query. Se desideri configurare i criteri nei singoli computer, puoi applicare le impostazioni dei criteri che influiscono solo sul dispositivo locale usando Editor Criteri di gruppo locali nel computer di destinazione.

Microsoft Edge supporta sia i criteri _obbligatori_ sia quelli _consigliati_. I criteri obbligatori sostituiscono le preferenze dell'utente e impediscono all'utente di modificarle, mentre i criteri consigliati forniscono un'impostazione predefinita che potrebbe essere sostituita dall'utente. La maggior parte dei criteri è solo obbligatoria, mentre un sottoinsieme di criteri è obbligatorio e consigliato. Se entrambe le versioni di un criterio sono impostate, l'impostazione obbligatoria ha la precedenza. I criteri consigliati hanno effetto solo quando l'utente non ha modificato l'impostazione.

>[!TIP]
> Per configurare le impostazioni dei criteri di Microsoft Edge, puoi usare Microsoft Intune. Per altre informazioni, vedi [Configurare Microsoft Edge con Microsoft Intune](configure-edge-with-intune.md).

Esistono due modelli amministrativi per Microsoft Edge ed entrambi possono essere applicati a livello di computer o di dominio di Active Directory:

- *msedge.admx* per [configurare le impostazioni di Microsoft Edge](microsoft-edge-policies.md)
- *msedgeupdate.admx* per [gestire gli aggiornamenti di Microsoft Edge](microsoft-edge-update-policies.md).

Per iniziare, scarica e installa il modello amministrativo di Microsoft Edge.

### <a name="1-download-and-install-the-microsoft-edge-administrative-template"></a>1. Scaricare e installare il modello amministrativo di Microsoft Edge

Se desideri configurare le impostazioni dei criteri di Microsoft Edge in Active Directory, scarica i file in un percorso di rete a cui è possibile accedere da un controller di dominio o da una workstation con la funzionalità Strumenti di amministrazione remota del server installata. Per eseguire la configurazione in un singolo computer, è sufficiente scaricare i file in tale computer.

Quando aggiungi i file dei modelli amministrativi nel percorso appropriato, le impostazioni dei criteri di Microsoft Edge sono immediatamente disponibili in Editor Criteri di gruppo.

Vai alla [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise) per scaricare il file dei modelli dei criteri di Microsoft Edge (*MicrosoftEdgePolicyTemplates.cab*) ed estrai il contenuto.

#### <a name="add-the-administrative-template-to-active-directory"></a>Aggiungere il modello amministrativo ad Active Directory

1. In un controller di dominio o in una workstation con Strumenti di amministrazione remota del server, vai alla cartella **PolicyDefinition** (nota anche come _archivio centrale_) in un qualsiasi controller di dominio del tuo dominio. Per le versioni precedenti di Windows Server, potrebbe essere necessario creare la cartella PolicyDefinition. Per altre informazioni, vedi [Come creare e gestire l'archivio centrale per i modelli amministrativi di Criteri di gruppo in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
2. Apri *MicrosoftEdgePolicyTemplates* e vai a **windows** > **admx**.
3. Copia il file *msedge.admx* nella cartella PolicyDefinition. (Esempio: %systemroot%\sysvol\domain\policies\PolicyDefinitions)
4. Nella cartella *admx* apri la cartella della lingua appropriata. Ad esempio, se sei in Italia, apri la cartella **it-it**.
5. Copia il file *msedge.adml* nella cartella della lingua corrispondente nella cartella PolicyDefinition. Crea la cartella se non esiste già. (Esempio: %systemroot%\sysvol\domain\policies\PolicyDefinitions\IT-IT)
6. Se il dominio dispone di più di un controller di dominio, i nuovi file ADMX verranno replicati al successivo intervallo di replica del dominio.
7. Per verificare che i file siano stati caricati in modo corretto, apri **Editor gestione Criteri di gruppo** in Strumenti di amministrazione Windows ed espandi **Configurazione computer** > **Criteri** > **Modelli amministrativi** > **Microsoft Edge**. Dovrebbero essere visualizzati uno o più nodi Microsoft Edge, come illustrato di seguito.

    ![Criteri di Microsoft Edge](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### <a name="add-the-administrative-template-to-an-individual-computer"></a>Aggiungere il modello amministrativo a un singolo computer

1. Nel computer di destinazione, apri *MicrosoftEdgePolicyTemplates* e vai a **windows** > **admx**.
2. Copia il file *msedge.admx* nella tua cartella dei modelli PolicyDefinition. (Esempio: C:\Windows\PolicyDefinitions)
3. Nella cartella *admx* apri la cartella della lingua appropriata. Ad esempio, se sei in Italia, apri la cartella **it-it**.
4. Copia il file *msedge.adml* nella cartella della lingua corrispondente nella tua cartella PolicyDefinition. (Esempio: C:\Windows\PolicyDefinitions\IT-IT)
5. Per verificare che i file siano stati caricati in modo corretto, apri direttamente Editor Criteri di gruppo locali (tasto Windows + R e immetti gpedit.msc) oppure apri MMC e carica Editor Criteri di gruppo locali. In genere, se si verifica un errore, i file si trovano in un percorso non corretto.

### <a name="2-set-mandatory-or-recommended-policies"></a>2. Impostare criteri obbligatori o consigliati

Puoi impostare criteri obbligatori o consigliati per configurare Microsoft Edge con Editor Criteri di gruppo sia per Active Directory sia per singoli computer. Puoi impostare l'ambito delle impostazioni dei criteri sia su **Configurazione computer** sia su **Configurazione utente** selezionando il nodo appropriato come descritto di seguito.

- Per configurare un criterio obbligatorio, apri Editor Criteri di gruppo e vai a (**Configurazione Computer** o **Configurazione utente**) > **Criteri** > **Modelli amministrativi** > **Microsoft Edge**.
- Per configurare un criterio consigliato, apri Editor Criteri di gruppo e vai a (**Configurazione Computer** o **Configurazione utente**) > **Criteri** > **Modelli amministrativi** > **Microsoft Edge - Impostazioni predefinite (sostituibili dagli utenti)**.

  ![Apri Editor Criteri di gruppo](./media/configure-microsoft-edge/edge-ad-policy.png)

### <a name="3-test-your-policies"></a>3. Testare i criteri

In un dispositivo client di destinazione, apri Microsoft Edge e passa a **edge://policy** per visualizzare tutti i criteri applicati. Se le impostazioni dei criteri sono state applicate nel computer locale, i criteri devono essere visualizzati immediatamente. Potrebbe essere necessario chiudere e riaprire Microsoft Edge se era aperto durante la configurazione delle impostazioni dei criteri.

![Visualizzare i criteri configurati nel browser](./media/configure-microsoft-edge/edge-gpEdit.png)

Per Criteri di gruppo di Active Directory, le impostazioni dei criteri vengono propagate ai computer di dominio a intervalli regolari definiti dall'amministratore di dominio e i computer di destinazione possono non ricevere gli aggiornamenti dei criteri immediatamente. Per aggiornare manualmente le impostazioni di Criteri di gruppo di Active Directory in un computer di destinazione, esegui questo comando da un prompt dei comandi o da una sessione PowerShell nel computer di destinazione:

``` powershell
gpupdate /force
```

Potrebbe essere necessario chiudere e riaprire Microsoft Edge prima che i nuovi criteri vengano visualizzati.

Puoi anche usare REGEDIT.exe in un computer di destinazione per visualizzare le impostazioni del Registro di sistema che archiviano le impostazioni dei criteri di gruppo. Tali impostazioni si trovano nel percorso del Registro di sistema **HKLM\SOFTWARE\Policies\Microsoft\Edge**.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Configurare per Windows con Intune](configure-edge-with-intune.md)
- [Configurare per macOS](configure-microsoft-edge-on-mac.md)
- [Esplorare i criteri aziendali di Microsoft Edge](microsoft-edge-policies.md)


