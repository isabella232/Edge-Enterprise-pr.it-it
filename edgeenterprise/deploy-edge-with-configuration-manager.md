---
title: Distribuire Microsoft Edge tramite System Center Configuration Manager
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come distribuire Microsoft Edge con System Center Configuration Manager (SCCM)
ms.openlocfilehash: be14f2db3b28b7585bfad1706b9f82209235df0a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980187"
---
# Distribuire Microsoft Edge tramite System Center Configuration Manager

In questo articolo viene illustrato come automatizzare una distribuzione di Microsoft Edge tramite System Center Configuration Manager (SCCM).

>[!NOTE]
>Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Prima di iniziare

Leggere le informazioni in [Introduzione alla gestione delle applicazioni in Configuration Manager](https://docs.microsoft.com/sccm/apps/understand/introduction-to-application-management). Questo articolo sulla gestione delle applicazioni consente di comprendere la terminologia usata ed è una guida alla preparazione del sito per l'installazione delle applicazioni.

Scarica il file di installazione di Microsoft Edge in modalità Enterprise (**MicrosoftEdgeDevEnterpriseX64.msi** e/o **MicrosoftEdgeDevEnterpriseX86.msi**) nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).

Assicurati di archiviare i file di installazione di Microsoft Edge in un percorso di rete accessibile.

## Creare l'applicazione

Creerai l'applicazione usando una procedura guidata di Gestione configurazione.

### Avviare la Creazione guidata applicazione e creare l'applicazione  

1. Nella console di Gestione configurazione fai clic su **Raccolta software** > **Gestione applicazioni** > **Applicazioni**.  

2. Nella scheda **Home**, nel gruppo **Crea** fai clic su **Crea applicazione**. In alternativa, fai clic con il pulsante destro del mouse su **Applicazioni** sulla barra di spostamento e quindi fai clic su **Crea applicazione**.

    ![Creare l'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. Nella pagina **Generale** della **Creazione guidata applicazione** seleziona la casella di controllo **Rileva automaticamente le informazioni sull'applicazione dai file di installazione**. In questo esempio vengono pre-popolate alcune informazioni della procedura guidata con le informazioni estratte dal file di installazione msi. Specifica le informazioni seguenti:  

   - **Tipo**: scegli **Windows Installer (file \*.msi)**.  

   - **Percorso**: digita il percorso (o fai clic su **Sfoglia** per selezionare il percorso) del file di installazione **MicrosoftEdgeDevEnterpriseX64.msi** o **MicrosoftEdgeDevEnterpriseX86.msi**. Nota che il percorso deve essere specificato nella forma *\\\Server\Condivisione\File* affinché Gestione configurazione individui i file di installazione.  

   La pagina **Specifica le impostazioni per l'applicazione** avrà un aspetto simile al seguente:  

    ![Specifica le impostazioni per l'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. Fai clic su **Avanti**. In **Dettagli** nella pagina **Informazioni importate** vengono visualizzate le informazioni sull'applicazione e su tutti i file associati importati. Fai clic su **Avanti** per continuare con la procedura guidata.  

    ![Visualizzare le informazioni importate](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. Nella pagina **Informazioni generali** puoi aggiungere altre informazioni sull'applicazione. Ad esempio, la versione del software, i commenti dell'amministratore e l'autore. Puoi usare queste informazioni per facilitare l'ordinamento e trovare l'applicazione nella console di Gestione configurazione.

   Puoi anche usare il campo **Programma di installazione** per specificare la riga di comando completa da usare per installare l'applicazione sui PC. Puoi modificare questa operazione per aggiungere proprietà personalizzate, ad esempio **/q** per un'installazione automatica.

   Nella schermata seguente viene illustrato un esempio in cui vengono usati i campi **Specifica le informazioni sull'applicazione**.

   ![Specificare i metadati dell'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. Fai clic su **Avanti**.
7. Nella pagina **Riepilogo** puoi verificare le impostazioni dell'applicazione in **Dettagli** e quindi uscire dalla procedura guidata. Fai clic su **Avanti**.  

    ![Dettagli delle impostazioni dell'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. Nella pagina **Completamento** fai clic su **Chiudi**.

    ![Finestra di dialogo per l'operazione riuscita](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

Hai completato la creazione dell'applicazione. Per visualizzarla in Gestione configurazione, segui questi passaggi:

- seleziona l'area di lavoro **Raccolta software**
- espandi **Gestione applicazioni**
- fai clic su **Applicazioni**.

Nella schermata seguente viene illustrato l'esempio usato per questo articolo.  

![Applicazioni](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## Modificare le proprietà dell'applicazione e le impostazioni di distribuzione

Dopo aver creato un'applicazione, puoi ottimizzare le impostazioni dell'applicazione, se necessario. Per visualizzare le proprietà dell'applicazione:

- seleziona l'applicazione
- in **Home**>**Proprietà**, fai clic su **Proprietà**.  

   ![Configurare le proprietà dell'applicazione](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 Nella finestra di dialogo **<nome applicazione\> Proprietà applicazione** viene visualizzata una vista a schede degli elementi che puoi configurare per modificare il comportamento dell'applicazione. Per altre informazioni sulle impostazioni che puoi configurare, vedi [Creare applicazioni](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications).

Per questo esempio, modificherai alcune proprietà del tipo di distribuzione dell'applicazione. Per modificare le proprietà di distribuzione:

1. Fai clic sulla scheda **Tipi di distribuzione**.
2. In **Tipi di distribuzione** seleziona il **Nome** dell'applicazione.
3. Fai clic su **Modifica**.

   ![Modificare il tipo di distribuzione](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### Aggiungere un requisito al tipo di distribuzione

 I requisiti specificano le condizioni che devono essere soddisfatte prima che un'applicazione possa essere installata in un dispositivo. Puoi scegliere tra requisiti predefiniti oppure puoi creare requisiti personalizzati. Puoi ad esempio aggiungere un requisito in base al quale l'applicazione verrà installata solo in PC che eseguono Windows 10 **x86** o **x64**, a seconda dell'architettura del processore di destinazione del file di installazione. In questo esempio, devi specificare Windows 10 **x86**.

1. Nella pagina delle proprietà del tipo di distribuzione aperta, fai clic sulla scheda **Requisiti**.

2. Fai clic su **Aggiungi** per aprire la finestra di dialogo **Crea requisito**.

    ![Creare il requisito](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. Nella finestra di dialogo **Crea requisito** specifica le seguenti informazioni:

    - **Categoria**: **Dispositivo**  

    - **Condizione**: **Sistema operativo**  

    - **Tipo di regola**: **Valore**  

    - **Operatore**: **Uno di**  

    - Nell'elenco di sistemi operativi seleziona **Windows 10** > **Tutte le piattaforme Windows 10 (32-bit)**.  

    Al termine, la finestra di dialogo sarà simile alla schermata di esempio seguente:

    ![Aggiungere un requisito](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. Fai clic su **OK** per chiudere la pagina delle proprietà aperta e tornare all'elenco **Applicazioni** nella console di Gestione configurazione.  

## Aggiungere il contenuto dell'applicazione a un punto di distribuzione  

Per distribuire l'applicazione aggiornata ai PC, assicurati che il contenuto dell'applicazione venga copiato in un punto di distribuzione. I PC accedono al punto di distribuzione per installare l'applicazione.  

>[!TIP]
>Per altre informazioni sui punti di distribuzione e la gestione dei contenuti in Gestione configurazione, vedi [Distribuire e gestire il contenuto per System Center Configuration Manager](https://docs.microsoft.com/sccm/core/servers/deploy/configure/deploy-and-manage-content).  

1. Nella console di Gestione configurazione fai clic su **Raccolta software**.  

2. Nell'area di lavoro **Raccolta software** espandi **Applicazioni**. Seleziona l'applicazione creata nell'elenco delle applicazioni.

3. Nella scheda **Home**, nel gruppo **Distribuzione** fai clic su **Distribuisci contenuto**.  

4. Nella pagina **Generale** della **Distribuzione guidata contenuto** verifica che il nome dell'applicazione sia corretto e quindi fai clic su **Avanti**.  

5. Nella pagina **Contenuto** esamina le informazioni che verranno copiate nel punto di distribuzione e quindi fai clic su **Avanti**.  

6. Nella pagina **Destinazione contenuto** fai clic su **Aggiungi** per selezionare una o più raccolte oppure uno o più punti di distribuzione o gruppi di punti di distribuzione in cui installare il contenuto dell'applicazione.

7. Completa la procedura guidata.

Puoi verificare che il contenuto dell'applicazione si stato copiato in modo corretto al punto di distribuzione nell'area di lavoro **Monitoraggio**, in **Stato distribuzione** > **Stato contenuto**.  

## Distribuire l'applicazione  

Distribuisci quindi l'applicazione in una raccolta dispositivi nella gerarchia. In questo esempio, l'applicazione viene distribuita nella raccolta di dispositivi **Tutti i sistemi**.  

>[!TIP]
>Tieni presente che solo i computer Windows 10 con l'architettura del processore specificata installeranno l'applicazione a causa dei requisiti selezionati in precedenza.  

1. Nella console di Gestione configurazione fai clic su **Raccolta software** > **Gestione applicazioni** > **Applicazioni**.

2. Nell'elenco di applicazioni, seleziona l'applicazione creata in precedenza. Nella scheda **Home**, nel gruppo **Distribuzione** fai clic su **Distribuisci** o fai clic con il pulsante destro del mouse sull'applicazione e seleziona **Distribuisci**.

    ![Distribuire l'applicazione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. Nella pagina **Generale** della **Distribuzione guidata software** fai clic su **su Sfoglia** per selezionare la raccolta di dispositivi in cui desideri distribuire l'applicazione.

    ![Accedere al file di installazione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. Nella pagina **Contenuto** verifica che il punto di distribuzione da cui desideri installare sia selezionato.

    ![Specificare il punto di distribuzione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. Nella pagina **Impostazioni di distribuzione** verifica che l'azione di distribuzione sia impostata su **Installa** e che lo scopo della distribuzione sia impostato su **Obbligatorio**.

    ![Configurare le impostazioni di distribuzione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    >Impostando lo scopo della distribuzione su **Obbligatorio**, assicuri che l'applicazione sia installata nei PC che soddisfano i requisiti impostati. Se imposti questo valore su **Disponibile**, gli utenti possono installare l'applicazione su richiesta da Software Center.  

6. Nella pagina **Pianificazione** puoi configurare il momento in cui installare l'applicazione. Per questo esempio, seleziona **Appena possibile dopo il tempo disponibile**.

    ![Pianificare la distribuzione](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. Nella pagina **Esperienza utente** seleziona in valori desiderati e quindi fai clic su **Avanti**.

    ![Specificare l'esperienza utente](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. Specifica le opzioni di avviso desiderate e fai clic su **Avanti**.

    ![Specificare le impostazioni di avviso](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. Completa la procedura guidata.

Usa le informazioni riportate nella sezione **Monitorare l'applicazione** seguente per visualizzare lo stato della distribuzione dell'applicazione.  

## Monitorare l'applicazione

 In questa sezione puoi esaminare rapidamente lo stato dell'applicazione distribuita.  

### Per esaminare lo stato di distribuzione  

1. Nella console di Gestione configurazione fai clic su **Monitoraggio** > **Distribuzioni**.  

2. Nell'elenco delle distribuzioni seleziona l'applicazione.

    ![Monitorare la distribuzione](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. Nella scheda **Home** fai clic su **Visualizza stato** nel gruppo **Distribuzione**.  

4. Seleziona una delle seguenti schede per visualizzare ulteriori aggiornamenti sullo stato della distribuzione delle applicazioni:  

    - **Operazione riuscita**: l'applicazione è stata installata nei PC indicati.  

    - **In corso**: l'installazione dell'applicazione non è ancora stata completata.  

    - **Errore**: si è verificato un errore durante l'installazione dell'applicazione nei PC indicati. Vengono inoltre visualizzate altre informazioni sull'errore.  

    - **Requisiti non soddisfatti**: non è stato effettuato alcun tentativo di installazione sui dispositivi indicati perché non soddisfano i requisiti configurati (in questo esempio perché non vengono eseguiti in Windows 10).

    - **Sconosciuto**: Gestione configurazione non è riuscito a segnalare lo stato della distribuzione. Ricontrolla in seguito.  

    >[!TIP]
    >Esistono diversi modi per monitorare le distribuzioni delle applicazioni. Per altre informazioni, vedi [Monitorare le applicazioni dalla console di System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/monitor-applications-from-the-console).  

## Esperienza dell'utente finale  

Gli utenti che dispongono di PC gestiti da Gestione configurazione e che eseguono Windows 10 con l'architettura del processore specificata, ricevono un messaggio che indica la necessità di installare l'applicazione Microsoft Edge Dev. Quando accettano questa opzione di installazione, l'applicazione viene installata.  

## Vedi

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Per altre informazioni su come distribuire i pacchetti MSI, vedi Creare e distribuire un'applicazione con System Center Configuration Manager.](https://docs.microsoft.com/sccm/apps/get-started/create-and-deploy-an-application)
