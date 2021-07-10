---
title: Guida dettagliata alla funzionalità di individuazione siti aziendale
ms.author: collw
author: appcompatguy
manager: saudm
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Usare la funzionalità di individuazione siti aziendale per prepararsi alla modalità IE
ms.openlocfilehash: bbcf829e8c2504286ea68df673dabd9b296887c9
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641822"
---
# <a name="enterprise-site-discovery-step-by-step-guide"></a>Guida dettagliata alla funzionalità di individuazione siti aziendale

>[!Note]
> L'applicazione desktop di Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi interessati, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. [Altre informazioni qui](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Questo articolo contiene una guida dettagliata sull'uso della funzionalità di individuazione dei siti aziendali con Microsoft Endpoint Configuration Manager.

La funzionalità di individuazione siti aziendale può aiutarti a configurare l'elenco dei siti in modalità Enterprise. La funzionalità di individuazione siti aziendale ti aiuterà a:

- Scoprire i siti che usano le modalità documento legacy. A meno che questi siti non rilevino i browser moderni e offrano diversi linguaggi HTML, potrebbe essere necessario usare la modalità IE.
- Scoprire i siti che usano i controlli ActiveX. Microsoft Edge non supporta i controlli ActiveX. A meno che questi siti non rilevino i browser moderni e offrano diversi linguaggi HTML, potrebbe essere necessario usare la modalità IE.

> [!NOTE]
> Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.

## <a name="prerequisites"></a>Prerequisiti

Questa guida presuppone un'esperienza nell'uso di Microsoft Endpoint Configuration Manager e che siano installati i servizi e i ruoli seguenti:

1. Microsoft Endpoint Configuration Manager
2. Microsoft SQL Server Reporting Services
3. (Facoltativo) Ruolo del punto di Reporting Services di Configuration Manager configurato.

## <a name="download-enterprise-site-discovery-tools"></a>Scaricare gli strumenti della funzionalità di individuazione siti aziendale

Scarica gli strumenti seguenti:

- [Pacchetto di installazione e configurazione della funzionalità di individuazione siti aziendale](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [Generatore report Microsoft](https://www.microsoft.com/download/details.aspx?id=53613)

## <a name="enable-enterprise-site-discovery"></a>Abilitare la funzionalità di individuazione siti aziendale

Per poterti connettere alla Strumentazione gestione Windows per recuperare i dati di individuazione del sito devi prima di tutto distribuire il provider della classe WMI nel dispositivo.

Estrai il contenuto del **pacchetto di installazione e configurazione della funzionalità di individuazione siti aziendale** in una cartella della condivisione file nella raccolta software definitiva. Esempio: **\\\\DSL\\EnterpriseSiteDiscovery**.

Quindi, crea un pacchetto in Microsoft Endpoint Configuration Manager, come descritto nella [documentazione](/configmgr/apps/deploy-use/packages-and-programs), selezionando le opzioni seguenti:

- Nella pagina **Pacchetto** seleziona **Nome** e specifica il nome **Abilita funzionalità di individuazione siti**
- Nella pagina **Pacchetto** seleziona **Questo pacchetto contiene file di origine**.
- Nella pagina **Pacchetto** specifica la cartella di origine in cui hai estratto i file, ad esempio **\\\\DSL\\EnterpriseSiteDiscovery**
- Nella pagina **Tipo di programma** scegli **Programma standard**
- Nella pagina **Programma standard** immetti la riga di comando per configurare la funzionalità di individuazione siti nel dispositivo come indicato di seguito:
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > Lo script supporta l'uso di opzioni per `-ZoneAllowList` e `-SiteAllowList`. Per questa procedura dettagliata, verranno configurate queste opzioni con criteri di gruppo (di seguito).
- Nella pagina **Programma standard** seleziona l'opzione per eseguire **Nascosto**.
- Nella pagina **Programma standard**, in **Requisiti per esecuzione programma**, seleziona l'opzione **Indipendentemente dalla connessione degli utenti**

Dopo avere creato il pacchetto, fai doppio clic sul nome del pacchetto **Abilita funzionalità di individuazione siti** per visualizzarne le proprietà. Nella proprietà **Dopo l'esecuzione** seleziona **Configuration Manager riavvia il computer**. La raccolta di dati WMI inizierà dopo il riavvio del dispositivo.

> [!NOTE]
> Puoi configurare la quantità di tempo per cui un utente deve riavviare il dispositivo, come descritto nella [documentazione relativa alle impostazioni del client](/configmgr/core/clients/deploy/about-client-settings#computer-restart).

## <a name="configure-enterprise-site-discovery-via-group-policy"></a>Configurare la funzionalità di individuazione siti aziendale usando Criteri di gruppo

Con la funzionalità di individuazione siti aziendale abilitata, puoi configurare i dati da raccogliere. Considera le leggi locali e i requisiti normativi come descritto [qui](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected).

1. Apri Editor Criteri di gruppo
2. Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Componenti di Windows** > **Internet Explorer** 
3. Fai doppio clic su **Attiva output WMI individuazione siti**
4. Selezionare **Attivato**.
5. Fai clic su **OK** o su **Applica** per salvare questa impostazione

Puoi limitare le aree in cui raccogliere i dati del sito:

1. Fai doppio clic su **Limita l'output di individuazione siti in base all'area**
2. Selezionare **Attivato**.
3. Immetti una maschera di bit che indichi le aree per cui abilitare l'individuazione siti:
    1. Area Siti con restrizioni
    2. Area Internet
    3. Area Siti attendibili
    4. Area Intranet locale
    5. Area Computer locale
    
    Esempio 1: **00010** raccoglierà solo i dati per l'area Intranet locale

    Esempio 2: **10111** raccoglierà i dati per tutte le aree tranne l'area Internet
4. Fai clic su **OK** o su **Applica** per salvare questa impostazione

Puoi limitare i domini per cui raccogliere i dati del sito:

1. Fai doppio clic su **Limita l'output di individuazione siti in base al dominio**
2. Selezionare **Attivato**.
3. Immetti i domini in cui vuoi raccogliere i dati, un dominio per riga
4. Fai clic su **OK** o su **Applica** per salvare questa impostazione

## <a name="collect-site-discovery-data-using-configuration-manager"></a>Raccogliere i dati di individuazione siti con Configuration Manager

Ora che i dispositivi stanno generando i dati, è il momento di raccoglierli in Configuration Manager.

1. Nella console di Configuration Manager scegli **Amministrazione** > **Impostazioni client** > **Impostazioni client predefinite**
2. Nella scheda **Home**, nel gruppo **Proprietà**, scegli **Proprietà**
3. Nella finestra di dialogo **Impostazioni client predefinite** scegli **Inventario hardware**
4. Nell'elenco **Impostazioni del dispositivo** scegli **Imposta classi**
5. Nella finestra di dialogo **Classi di inventario hardware** scegli **Aggiungi**
6. Nella finestra di dialogo **Aggiungi classe di inventario hardware** fai clic su **Connetti**
7. Nella finestra di dialogo **Connetti a Strumentazione gestione Windows (WMI)** immetti il nome del computer in cui è configurata la funzionalità di individuazione siti aziendale. Se ti connetti a un altro computer, ti serviranno le credenziali con autorizzazione per accedere a WMI.
8. Nella casella di testo **Spazio dei nomi WMI** immetti **root\cimv2\IETelemetry**
9. Scegli **Connetti**.
10. Nella finestra di dialogo **Aggiungi classe di inventario hardware**, nell'elenco **Classi di inventario**, seleziona le classi **iESystemINfo**, **iEUrlInfo** e **iECountInfo*.
11. Scegli **OK** per chiudere la finestra di dialogo **Qualificatori classe** e le altre finestre di dialogo aperte.

Dopo l'aggiornamento delle impostazioni del client dal punto di gestione, verrà generato il report relativo ai dati durante l'esecuzione del prossimo inventario hardware (per impostazione predefinita, ogni sette giorni).

## <a name="import-site-discovery-reports"></a>Importare report di individuazione siti

Il pacchetto della funzionalità di individuazione siti aziendale include due report di esempio. Un report mostra i siti che usano i controlli ActiveX e un altro mostra i siti che usano la modalità documento legacy.

### <a name="configure-the-site-discovery-sample-report"></a>Configurare il report di esempio della funzionalità di individuazione siti

Usa la procedura seguente per creare un report di esempio che usa tre origini dati: i siti visitati da un utente, le informazioni sul suo sistema e le modalità di documento usate dai siti. Questo report consente di identificare i siti che possono dipendere da modalità documento legacy.

1. Copia il report **SCCM_Report-Site_Discovery.rdl** nel server di Configuration Manager.
2. Installa [Generatore report Microsoft](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).
3. Fai doppio clic su **SCCM_Report-Site_Discovery.rdl** per aprire il report in Generatore report.
4. La prima volta che lo apri, il report proverà a contattare il server in cui è stato creato. Quando viene chiesto **Connetti al server di report**, fai clic su **No**.
5. Dopo l'apertura del report, espandi **Origini dati** e fai doppio clic su **DataSource1**.
6. Nella finestra **Proprietà origine dati** seleziona **Usa una connessione incorporata nel report** e quindi scegli il pulsante **Compila**.
7. Nella finestra di dialogo **Proprietà connessione** seleziona **Nome server** e immetti il nome del server di Configuration Manager. Quindi, in **Selezionare o immettere un nome di database** seleziona il nome del database di Configuration Manager dall'elenco a discesa.
8. Fai clic su **OK** per chiudere la finestra **Proprietà connessione**.
9. Fai clic su **Verifica connessione** per verificare la connessione. Se la connessione è riuscita, fai clic su **OK** per chiudere la finestra **Proprietà origine dati**.
10. Ripeti i passaggi da 5 a 9 per **Origine dati 2**.
11. Espandi **Set di dati** e fai doppio clic su **DataSet1**.
12. Nella finestra **Proprietà set di dati** fai clic nella casella di testo **Query:** e sostituisci **USE CM_A1B** con il nome del database selezionato nel passaggio 7.
13. Ripeti i passaggi da 11 a 12 per **DataSet2**, **DataSet3** e **DataSet4**.
14. Nella scheda **Home** sulla barra multifunzione fai clic sul pulsante **Esegui** per testare il report.
15. Salva il report.
16. Chiudi il Generatore report Microsoft.
17. Rinomina il file in **Individuazione siti.rdl**

### <a name="configure-the-activex-sample-report"></a>Configura il report di esempio ActiveX

Usa la procedura seguente per creare un report di esempio che usa un'unica origine dati: i siti che usano i controlli ActiveX. Dal momento che Internet Explorer è l'unico browser che supporta i controlli ActiveX, questi siti potrebbero richiedere la modalità IE.

1. Copia il report **SCCM Report Sample - ActiveX.rdl** nel server di Configuration Manager.
2. Installa [Generatore report Microsoft](/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).
3. Fai doppio clic su **SCCM Report Sample - ActiveX.rdl** per aprire il report in Generatore report.
4. La prima volta che lo apri, il report proverà a contattare il server in cui è stato creato. Quando viene chiesto **Connetti al server di report**, fai clic su **No**.
5. Dopo l'apertura del report, espandi **Origini dati** e fai doppio clic su **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.
6. Nella finestra **Proprietà origine dati** seleziona **Usa una connessione incorporata nel report** e quindi scegli il pulsante **Compila**.
7. Nella finestra di dialogo **Proprietà connessione** seleziona **Nome server** e immetti il nome del server di Configuration Manager. Quindi, in **Selezionare o immettere un nome di database** seleziona il nome del database di Configuration Manager dall'elenco a discesa.
8. Fai clic su **OK** per chiudere la finestra **Proprietà connessione**.
9. Fai clic su **Verifica connessione** per verificare la connessione. Se la connessione è riuscita, fai clic su **OK** per chiudere la finestra **Proprietà origine dati**.
10. Espandi **Set di dati** e fai doppio clic su **DataSet1**.
11. Nella finestra **Proprietà set di dati** fai clic nella casella di testo **Query:** e sostituisci **USE CM_A1B** con il nome del database selezionato nel passaggio 7.
12. Nella scheda **Home** sulla barra multifunzione fai clic sul pulsante **Esegui** per testare il report.
13. Salva il report.
14. Chiudi il Generatore report Microsoft.
15. Rinomina il file in **ActiveX**

### <a name="upload-configured-reports-to-microsoft-sql-server-reporting-services"></a>Caricare i report configurati in Microsoft SQL Server Reporting Services

Dopo aver configurato i report per l'ambiente, caricali nel server dei report.

1. Avvia l'applicazione **Gestione configurazione Reporting Services**.
2. Nella finestra **Connessione del server di report** fai clic su **Connetti** e quindi sull'URL elencato in **Identificazione del sito del portale Web**
3. Nella finestra del browser che si apre dovrebbe essere visualizzata la pagina **SQL Server Reporting Services**: fai clic sulla cartella **ConfigMgr_SCCMSiteCode** per il codice del sito di SCCM.
4. Sulla barra multifunzione, passa il puntatore del mouse su **+Nuovo** e quindi fai clic sulla voce di menu **Cartella**.
5. Immetti un nome per la cartella, ad esempio **Individuazione siti aziendale**, e quindi fai clic sul pulsante **Crea**.
6. Fai clic sulla cartella **Individuazione siti aziendale**.
7. Nella barra multifunzione, fai clic sul pulsante **Carica**.
8. Seleziona il report **Individuazione siti** e fai clic su **OK**.
9. Ripeti i passaggi 7 e 8 per il report **ActiveX**.

### <a name="view-reports-in-configuration-manager"></a>Visualizzare i report in Configuration Manager

Dopo aver personalizzato e caricato i report, puoi visualizzarli in Configuration Manager.

1. Nella console di Configuration Manager scegli **Monitoraggio** > **Report** > **Report** > **Individuazione siti aziendale**
2. Fai doppio clic su un report per visualizzarlo.

## <a name="disable-enterprise-site-discovery"></a>Disabilitare la funzionalità di individuazione siti aziendale

Una volta completata la raccolta dei dati, è consigliabile disabilitare l'individuazione siti aziendale. Crea un secondo pacchetto per disabilitare la funzionalità di individuazione siti aziendale in Microsoft Endpoint Configuration Manager, come descritto nella [documentazione](/configmgr/apps/deploy-use/packages-and-programs), selezionando le opzioni seguenti:

- Nella pagina **Pacchetto** seleziona **Nome** e specifica il nome **Disabilita funzionalità di individuazione siti**
- Nella pagina **Pacchetto** seleziona **Questo pacchetto contiene file di origine**.
- Nella pagina **Pacchetto** specifica la cartella di origine in cui hai estratto i file, ad esempio **\\\\DSL\\EnterpriseSiteDiscovery**
- Nella pagina **Tipo di programma** scegli **Programma standard**
- Nella pagina **Programma standard** immetti la riga di comando per disabilitare la funzionalità di individuazione siti nel dispositivo come indicato di seguito:
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- Nella pagina **Programma standard** seleziona l'opzione per eseguire **Nascosto**
- Nella pagina **Programma standard**, in **Requisiti per esecuzione programma**, seleziona l'opzione **Indipendentemente dalla connessione degli utenti**

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](./edge-ie-mode.md)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Informazioni aggiuntive sulla funzionalità di individuazione siti aziendale](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)