---
title: Edge per Virtualization Desktop Infrastructure (VDI)
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge per Virtualized Desktop Infrastructure.
ms.openlocfilehash: eaad1b72934b336ce86d14dd8da92a6984d21914
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618150"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a>Microsoft Edge per Virtualized Desktop Infrastructure

In questo articolo vengono descritti i requisiti e le limitazioni per Microsoft Edge in un ambiente virtualizzato.

## <a name="what-is-vdi"></a>Che cos'è VDI?

Virtual Desktop Infrastructure (VDI) è una tecnologia di virtualizzazione che ospita un sistema operativo desktop e applicazioni su un server centralizzato in un data center. Ciò consente di offrire agli utenti un'esperienza desktop completamente personalizzata con un'origine centralizzata completamente protetta e conforme.

Microsoft Edge può essere usato in un ambiente virtualizzato allo stesso modo che su un dispositivo locale, mentre è in esecuzione da un ambiente server sicuro e controllato. A seconda della soluzione VDI scelta, è inoltre possibile consentire agli utenti di accedere facilmente alle applicazioni e ai siti Intranet.

La maggior parte delle funzionalità di Edge è supportata in ambienti VDI senza alcuna configurazione particolare. Tuttavia, per garantire un'esperienza ottimale, è consigliabile seguire le indicazioni riportate di seguito.

## <a name="platforms-certified-for-edge"></a>Piattaforme certificate per Edge

- Desktop virtuale Azure
- App e desktop virtuali Citrix (in precedenza noti come XenApp e XenDesktop)

Sebbene altre soluzioni VDI non siano ancora state verificate dal team Edge, si ritene che i flussi di lavoro più comuni in Edge siano supportati. Le indicazioni fornite di seguito potrebbero o meno essere applicabili alla soluzione scelta.

## <a name="edge-on-vdi-performance-considerations"></a>Considerazioni sulle prestazioni di VDI su Edge

Nel progettare l'ambiente VDI, è consigliabile considerare attentamente i flussi di lavoro e le esigenze degli utenti in modo da ottenere prestazioni ottimali, nonché limiti alla configurazione del server.

Edge consiglia i seguenti requisiti minimi per la distribuzione di Edge in ambienti VDI:

- vCPU: 2-4 Core per utente
- RAM: 1 GB per utente

Tenere presente che le estensioni e le applicazioni Web complesse di grandi dimensioni richiedono maggiore memoria e devono essere gestite durante la configurazione dell'ambiente.

## <a name="edge-on-non-persisted-vdi-environments"></a>Edge in ambienti VDI non persistenti

Molte soluzioni VDI consentono l'accesso agli ambienti persistenti. All’interno di questi ultimi, agli utenti viene assegnato un ambiente virtuale che persiste tra una sessione e l’altra e ambienti non persistenti, in cui gli utenti vengono assegnati a uno dei computer disponibili, probabilmente a un computer diverso per ogni sessione. È possibile sincronizzare o meno i dati degli utenti tra una sessione e l’altra.

Quando si utilizza un ambiente non persistente, in genere viene creata un’"immagine di riferimento" che viene usata per ogni dispositivo che include le app e le configurazioni necessarie. Di seguito sono riportati i suggerimenti per la preparazione di Edge per un'immagine di questo tipo.

### <a name="deploy-edge"></a>Distribuire Edge

Se si utilizza Windows 10, versione 1803 e successive, è necessario aver installato Microsoft Edge sul sistema. Tuttavia, se si utilizza una versione precedente di Windows o si desidera distribuire un canale diverso di Edge, è consigliabile seguire i passaggi seguenti.

1. Scaricare il pacchetto MSI di Edge corrispondente al sistema operativo della macchina virtuale di VDI da:

    - [Scaricare Microsoft Edge for Business - Microsoft](https://www.microsoft.com/edge/business/download)

2. Installare il file MSI nella macchina virtuale di VDI eseguendo il comando seguente:

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a>Disabilitare gli aggiornamenti automatici

Per gli ambienti non persistenti è consigliabile disabilitare gli aggiornamenti automatici e aggiornare Edge eseguendo l’aggiornamento dell’“immagine di riferimento” per assicurarsi che non vi siano versioni non corrispondenti tra il pool di computer.

Per disabilitare gli aggiornamenti automatici, vedere i criteri seguenti:

- [Sostituzione dei criteri di aggiornamento predefinita](/deployedge/microsoft-edge-update-policies#updatedefault)

- [Sostituzione dei criteri di aggiornamento](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a>Gestione del profilo

Nelle configurazioni non persistenti è importante considerare che le macchine virtuali potrebbero non mantenere lo stato utente tra le sessioni o che gli utenti potrebbero essere assegnati a una macchina virtuale che non hanno mai usato prima e, di conseguenza, non disporre dei relativi dati utente.

Edge supporta diversi metodi per la sincronizzazione dei dati utente in modo che questi siano disponibili indipendentemente dalla modalità di accesso a Edge.

### <a name="azure-ad-sync"></a>Azure AD Sync

Se il piano di Azure AD lo supporta, la sincronizzazione aziendale è il metodo più rapido e semplice per garantire che i dati degli utenti Edge siano sincronizzati su tutti i dispositivi utente.  

Per ulteriori informazioni sui requisiti e sulla configurazione, vedere quanto segue.  

- [Configurare la sincronizzazione aziendale di Microsoft Edge | Microsoft Docs](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a>Sincronizzazione locale per gli utenti di Active Directory

Con la sincronizzazione locale, Microsoft Edge salva i preferiti e le impostazioni di un utente di Active Directory in un file che può essere facilmente spostato da un computer all’altro.  

Per ulteriori informazioni sui requisiti e sulla configurazione, vedere quanto segue.  

- [Sincronizzazione locale per gli utenti di Active Directory (AD) | Microsoft Docs](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a>Reindirizzamento profilo utente  

Esistono diverse soluzioni per la migrazione e il reindirizzamento dell'intera cartella utente in modo da garantire il mantenimento del contesto utente in tali ambienti non persistenti. Contattare il provider VDI per determinare la soluzione consigliata.

Alcune tra soluzioni più popolari includono:

- [Panoramica di FSLogix - FSLogix | Microsoft Docs](/fslogix/overview)
- [Come configurare la gestione del profilo Citrix](https://support.citrix.com/article/CTX222893)

Quando si utilizza questo metodo, è inoltre consigliabile escludere dalla cartella utente di cui è stato eseguito il backup cartelle non necessarie, in modo da ridurre i tempi di caricamento iniziali durante l’accesso degli utenti a tale computer e la migrazione del profilo. In tal caso, è consigliabile escludere dal backup le cartelle seguenti per ridurne le dimensioni.

- %LocalAppData%\Microsoft\Edge\User Data\Default\Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed

## <a name="known-issues"></a>Problemi noti

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a>Microsoft Edge si arresta in modo anomalo nelle versioni precedenti di XenApp e XenDesktop

È necessario risolvere tale problema nelle versioni più recenti. Tuttavia, se si verifica questo problema all’interno dell'ambiente, è possibile risolvere il problema disabilitando gli hook dell’API Citrix per Edge. Vedere [ Come disabilitare gli hook dell’API Citrix in base alle singole applicazioni.](https://support.citrix.com/article/CTX107825)

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a>Prestazioni ridotte durante il rendering delle pagine contenenti tabelle HTML eccezionalmente grandi

I criteri Citrix seguenti sono noti per rallentare il rendering delle pagine HTML contenenti tabelle di grandi dimensioni (oltre 30.000 righe).

- Visualizzazione automatica della tastiera
- Eseguire in remoto la casella combinata

Per ulteriori informazioni, vedere [Impostazioni dei criteri per l'esperienza su dispositivo mobile (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html). La disabilitazione di questi criteri dovrebbe risolvere il problema.

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a>Scenari di autorizzazione di Windows Account manager (ad esempio, sincronizzazione di Azure) hanno esito negativo in Edge quando questo viene eseguito come un’applicazione seamless Citrix

Si tratta di un problema noto in Edge e in altre applicazioni che utilizzano WAM (ad esempio Office) a causa dei componenti Windows necessari a tali scenari non inizializzati durante l'esecuzione in modalità "seamless". Per risolvere il problema:

- Usare Edge tramite desktop remoto per l'host Citrix anziché come applicazione seamless remota.
- Usare invece le app remote del Desktop virtuale Azure, che dispongono di una prevenzione per questo problema.
