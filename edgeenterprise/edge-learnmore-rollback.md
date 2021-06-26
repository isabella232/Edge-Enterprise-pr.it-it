---
title: Rollback di Microsoft Edge per le aziende
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 02/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Come eseguire il rollback di Microsoft Edge a una versione precedente
ms.openlocfilehash: 38954f4b293470758b5484591779a3af52c6992c
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617376"
---
# <a name="how-to-roll-back-microsoft-edge-to-a-previous-version"></a>Come eseguire il rollback di Microsoft Edge a una versione precedente

Questo articolo descrive come eseguire il rollback a una versione precedente di Microsoft Edge usando la funzionalità di rollback. Per altre informazioni su questa funzionalità, vedere il [video: rollback della versione Microsoft Edge](microsoft-edge-video-version-rollback.md).

>[!NOTE]
>Questo articolo si applica a Microsoft Edge versione 86 o successiva.

## <a name="introduction-to-rollback"></a>Introduzione al rollback

Il rollback consente di sostituire la versione corrente del browser Microsoft Edge con una versione precedente. Questa funzionalità è stata sviluppata per fungere da rete di protezione per le aziende che distribuiscono Microsoft Edge. Consente di risolvere problemi relativi a Microsoft Edge. Uno dei vantaggi del rollback è la possibilità di tornare alla versione precedente del browser in modo semplice e rapido. Il rollback riduce l’impatto potenziale di un problema di Microsoft Edge sulle operazioni aziendali.

## <a name="before-you-begin"></a>Prima di iniziare

È importante comprendere come avviene l’installazione della funzionalità di rollback in un ambiente Microsoft Edge. È possibile distribuire il rollback in due modi diversi: manualmente con un MSI o usando Microsoft Edge Update e Criteri di gruppo. È anche consigliabile usare determinati Criteri di gruppo per una distribuzione più fluida.

### <a name="recommendations"></a>Consigli

La funzionalità di rollback è pensata come correzione temporanea per i problemi che potrebbe causare un aggiornamento del browser Microsoft Edge. È consigliabile installare l’ultima versione del browser Microsoft Edge per sfruttare la protezione fornita dagli aggiornamenti della sicurezza più recenti. Il ripristino di una versione precedente può comportare rischi di esposizione a problemi di sicurezza noti.

Prima di ripristinare temporaneamente la versione precedente del browser, è inoltre consigliabile abilitare la sincronizzazione per tutti gli utenti dell'organizzazione. Se la sincronizzazione non viene abilitata, si rischia la perdita permanente dei dati di navigazione. Per altre informazioni sulla sincronizzazione, vedere [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md).

> [!CAUTION]
> Usare il rollback solo se necessario, in quanto comporta sempre un rischio di perdita di dati.

## <a name="enable-rollback-manually-with-an-msi"></a>Abilitare manualmente il rollback con un MSI

Seguire la procedura seguente per eseguire il rollback manualmente con un MSI.

1. Disabilitare Microsoft Edge Update.

   > [!NOTE]
   > È consigliabile installare i Modelli amministrativi più recenti. Per ulteriori informazioni, vedere [Scaricare e installare il modello amministrativo di Microsoft Edge](./configure-microsoft-edge.md#1-download-and-install-the-microsoft-edge-administrative-template).

   - Aprire l'Editor Criteri di gruppo locali e passare a *Configurazione computer>Modelli amministrativi>Microsoft Edge Update>Applicazioni>Microsoft Edge>*.
   - Selezionare **Sostituzione dei criteri di aggiornamento** e quindi selezionare **Abilitato**.
   - In **Opzioni** scegliere **Aggiornamento disabilitato** nell'elenco a discesa Criteri.

2. Ottenere il file MSI.

   - Scaricare [da qui](https://www.microsoft.com/edge/business/download) il file MSI per la versione di cui si vuole eseguire il rollback.
   - Salvare il file MSI nel desktop.

3. Eseguire il comando di rollback.

   - Aprire il prompt dei comandi di Windows con **Esegui come amministratore**.
   - Digitare il comando seguente, dove: *C:\Users\username\Desktop\test* rappresenta il percorso del file MSI scaricato e FileName è il nome del file MSI:<br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > Per altre informazioni su msiexec, vedere [msiexec](/windows-server/administration/windows-commands/msiexec).
   - Chiudere e riaprire Microsoft Edge per verificare che il rollback sia andato a buon fine. In **Impostazioni e altro** (ALT + F), passare a **Impostazioni** e selezionare **Informazioni su Microsoft Edge**.

## <a name="enable-rollback-with-microsoft-edge-update-and-group-policy"></a>Abilitare il rollback con Microsoft Edge Update e Criteri di gruppo

Seguire la procedura seguente per abilitare il rollback con Microsoft Edge Update e Criteri di gruppo.

1. Aprire l'Editor Criteri di gruppo locali e passare a *Configurazione computer>Modelli amministrativi>Microsoft Edge Update>Applicazioni>Microsoft Edge>*.
2. Selezionare **Ripristina versione di destinazione** e quindi selezionare **Abilitato**.
3. Selezionare **Sostituzione della versione di destinazione** e scegliere la versione del browser di cui si vuole eseguire il rollback.
4. Selezionare **Sostituzione dei criteri di aggiornamento** e quindi selezionare **Abilitato**. In **Opzioni**, selezionare una delle opzioni seguenti nell'elenco a discesa Criteri (tranne **Aggiornamento disabilitato**):

   - Consenti sempre gli aggiornamenti
   - Solo aggiornamenti automatici

     > [!NOTE]
     > Per forzare un aggiornamento dei criteri di gruppo, digitare `gpupdate /force` nel prompt dei comandi di Windows (Esegui come amministratore).

5. Fai clic su **OK** per salvare le impostazioni dei criteri. Il rollback verrà eseguito la volta successiva in cui Microsoft Edge Update verificherà la presenza di un aggiornamento. Se si vuole eseguire prima l'aggiornamento, è necessario modificare l'intervallo di polling di Microsoft Edge Update o abilitare il rollback con un MSI.

### <a name="common-rollback-errors"></a>Errori comuni di rollback

Gli errori seguenti impediscono l’esecuzione del rollback:

- L’input è una versione di destinazione non supportata
- L’input è una versione di destinazione inesistente
- L’input è formattato in modo errato

### <a name="recommended-group-policies"></a>Criteri di gruppo consigliati

Le impostazioni e i criteri di gruppo seguenti sono altamente consigliati per eseguire il rollback.

#### <a name="sync-group-policies"></a>Criteri di gruppo per la sincronizzazione

- ForceSync. Impostare ForceSync su Abilitato. Questo criterio impone l'abilitazione della sincronizzazione per tutti gli utenti di Azure Active Directory (Azure AD). Questo criterio è valido solo per la versione 86 di Microsoft Edge e le versioni successive.
- *Configura l'elenco dei tipi esclusi dai criteri di sincronizzazione* consente agli amministratori di controllare i dati che possono essere sincronizzati dagli utenti.

#### <a name="browser-restart-group-policies"></a>Criteri di gruppo di riavvio del browser

È consigliabile imporre agli utenti il riavvio dopo l'abilitazione del rollback.

- Abilitare *Invia una notifica a un utente in merito al riavvio del browser consigliato o necessario per gli aggiornamenti in sospeso*. In Opzioni selezionare **Obbligatorio**.
- Abilitare *Imposta il periodo di tempo per le notifiche sugli aggiornamenti* e quindi impostare l'ora desiderata in millisecondi.

## <a name="snapshot"></a>Snapshot

Una snapshot è una copia con versione stampata della cartella dei dati dell'utente. Durante un aggiornamento della versione, una snapshot della versione precedente viene creata e salvata nella cartella della snapshot. Al termine del rollback, una snapshot con versione corrispondente sarà copiata nella nuova cartella di dati dell'utente e cancellata dalla cartella della snapshot. Se nessuna snapshot con versione corrispondente è disponibile dopo il downgrade, il rollback utilizzerà Sync per immettere i dati dell'utente nella nuova versione di Microsoft Edge.

I criteri di gruppo di [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) consentono di impostare un limite per il numero di snapshot che possono essere conservati in un determinato momento. Per impostazione predefinita, vengono conservate tre snapshot. Il criterio può essere configurato per conservare da 0 a 5 snapshot.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="manual-msi-rollback"></a>Rollback manuale con MSI

#### <a name="what-generic-msi-failures-that-can-happen"></a>Quali errori generici di MSI possono verificarsi?

1. Se il criterio di gruppo Installa aggiornamento è disabilitato, non verrà eseguito il rollback.

   - Per eseguire il rollback, assicurarsi che l'opzione Installa sia impostata su **Abilitato**. Se questo criterio è disabilitato, i canali di Microsoft Edge non possono essere installati. Per ulteriori informazioni, vedere [Installa](./microsoft-edge-update-policies.md#install).

2. Se gli aggiornamenti di riconoscimento dei dati aziendali non sono presenti, le installazioni di Microsoft Edge verranno bloccate, a meno che non sia abilitato *Consenti esperienza browser Microsoft Edge affiancata*.

   - Per Windows versioni 1903 e 1909: se l'ultimo aggiornamento è precedente a ottobre 2019, potrebbe verificarsi questo problema.
   - Per Windows versioni 1709, 1803 e 1809: se l'ultimo aggiornamento è precedente a novembre 2019, potrebbe verificarsi questo problema.<br>
Per altre informazioni, vedere [Aggiornamenti di Windows per supportare la prossima versione di Microsoft Edge](./microsoft-edge-sysupdate-windows-updates.md)

#### <a name="the-following-error-message-was-shown-after-using-the-command-prompt-and-rollback-didnt-occur-whats-wrong"></a>È apparso il messaggio di errore seguente dopo che ho usato il prompt dei comandi e il rollback non si è verificato. Qual è il problema?

![Messaggio di stato del rollback](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

*ALLOWDOWNGRADE=1* non è stato eseguito.

### <a name="microsoft-edge-update-and-group-policy-rollback"></a>Rollback con Microsoft Edge Update e Criteri di gruppo

#### <a name="i-set-rollback-to-target-version-enabled-update-policy-override-input-my-desired-browser-version-for-target-version-override-but-the-browser-version-wasnt-what-i-expected-whats-wrong"></a>Ho impostato *Ripristina versione di destinazione*, abilitato *Sostituzione dei criteri di aggiornamento*, immesso la versione del browser desiderata per *Sostituzione della versione di destinazione*, ma la versione del browser non era quella prevista. Qual è il problema?

Alcuni errori comuni che impediscono l’esecuzione del rollback sono:

- Se Ripristina versione di destinazione non è impostato, il rollback non verrà eseguito.
- L'impostazione di sostituzione della versione di destinazione presenta uno dei problemi seguenti:

  - La sostituzione della versione di destinazione è impostata su una versione di destinazione non supportata.
  - La sostituzione della versione di destinazione è impostata su una versione di destinazione inesistente.
  - L'input della sostituzione della versione di destinazione è formattato in modo errato.

- Se Sostituzione dei criteri di aggiornamento è impostato su "Aggiornamenti disabilitati", Microsoft Edge Update non accetterà alcun aggiornamento e il rollback non sarà eseguito.

### <a name="i-set-all-the-group-policies-correctly-but-rollback-didnt-execute-what-happened"></a>Ho impostato correttamente tutti i criteri di gruppo, ma il rollback non è stato eseguito. Cosa è successo?

Microsoft Edge Update non ha ancora verificato la disponibilità di aggiornamenti. Per impostazione predefinita, l'aggiornamento automatico verifica la disponibilità degli aggiornamenti ogni 10 ore. Per risolvere il problema, è possibile modificare l'intervallo di polling di Microsoft Edge Update con il criterio di gruppo Sostituzione del periodo di controllo dell'aggiornamento automatico. Per altre informazioni, vedere il criterio [AutoUpdateCheckPeriodMinutes](./microsoft-edge-update-policies.md#autoupdatecheckperiodminutes).

### <a name="as-an-it-admin-i-followed-all-the-steps-for-rollback-correctly-only-a-portion-of-my-user-group-was-rolled-back-why-havent-the-other-users-been-rolled-back-yet"></a>In quanto amministratore IT, ho eseguito correttamente i passaggi per il rollback. Il rollback è stato eseguito solo per una parte del mio gruppo di utenti. Perché per gli altri utenti non è ancora avvenuto?

L'impostazione dei criteri di gruppo non è ancora stata sincronizzata con tutti i client. Quando gli amministratori configurano un criterio di gruppo, i client non ricevono le nuove impostazioni immediatamente. È possibile [Forzare un aggiornamento remoto di Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11)).

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: Ripristino della versione precedente di Microsoft Edge](microsoft-edge-video-version-rollback.md)