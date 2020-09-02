---
title: Configurare le impostazioni dei criteri di Microsoft Edge per Windows usando Microsoft Intune
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare le impostazioni dei criteri di Microsoft Edge per Windows usando Microsoft Intune.
ms.openlocfilehash: 6200b52e9061f37f85fe0bfe7cf59a2172db97df
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980158"
---
# Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.

Questo articolo descrive come configurare le impostazioni dei criteri di Microsoft Edge per Windows 10 usando Microsoft Intune.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

Puoi configurare i criteri e le impostazioni di Microsoft Edge aggiungendo un profilo di configurazione del dispositivo a Microsoft Intune. L'uso di Intune per la gestione e l'applicazione dei criteri è equivalente all'uso di Criteri di gruppo di Active Directory o alla configurazione delle impostazioni di un oggetto Criteri di gruppo locale nei dispositivi utente.

Per altre informazioni sulla gestione dei criteri di Microsoft Edge con Microsoft Intune, puoi leggere l'articolo [Gestire l'accesso Web usando Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge), ma tieni presente che tale articolo è specifico per Microsoft Edge versione 45 e versioni precedenti e pertanto può contenere informazioni e riferimenti che non si applicano a Microsoft Edge in modalità Enterprise versione 77 e successive.

> [!TIP]
> Per informazioni su come configurare Microsoft Edge su macOS usando Microsoft Intune, vedi [Configurare per macOS](configure-microsoft-edge-on-mac.md).

## Creare un profilo per gestire le impostazioni in Microsoft Edge per Windows 10

Con i modelli amministrativi in Microsoft Intune, puoi gestire criteri di gruppo di Microsoft Edge nei dispositivi Windows 10 usando il cloud. Questa sezione consente di creare un modello per configurare le impostazioni dell'applicazione specifiche per Microsoft Edge. Quando crei il modello, viene creato un profilo di configurazione del dispositivo. Puoi quindi assegnare o distribuire questo profilo ai dispositivi Windows 10 nell'organizzazione.

### Prerequisiti

- Windows 10, con i requisiti minimi di sistema seguenti:
  - Windows 10, versione 1909
  - Windows 10, versione 1903 con [KB4512941](https://support.microsoft.com/kb/4512941) installato
  - Windows 10, versione 1809 con [KB4512534](https://support.microsoft.com/kb/4512534) installato
  - Windows 10, versione 1803 con [KB4512509](https://support.microsoft.com/kb/4512509) installato
  - Windows 10, versione 1709 con [KB4516071](https://support.microsoft.com/kb/4516071) installato

### Usare i modelli amministrativi per creare un criterio per Microsoft Edge

Questa procedura consente di usare i modelli amministrativi (con cui si potrebbe avere familiarità grazie ai criteri di gruppo), integrati in Intune. È possibile usare questi modelli per creare un criterio per Microsoft Edge selezionando le impostazioni da un elenco già configurato.

1. Accedere al portale [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).
2. Selezionare **Dispositivi** nel riquadro di spostamento sinistro.
3. Da **Panoramica** | **dispositivi**, selezionare **Profili di configurazione** (sotto l'intestazione del criterio).
4. Sulla barra dei comandi superiore seleziona **Crea profilo**.
5. Nell'elenco a discesa **Piattaforma**, selezionare **Windows 10 e versioni successive**.
6. Nell'elenco a discesa sotto **Profilo**, selezionare **Modelli amministrativi**, quindi fare clic sul pulsante **Crea**. Lo screenshot seguente mostra gli elenchi a discesa per selezionare la piattaforma e il tipo di profilo.

    ![Selezionare la piattaforma e il tipo di profilo](./media/configure-edge-with-intune/create-profile-platform.png)

7. Nella scheda **Dati principali**, immettere Nome descrittivo, ad esempio criteri di Microsoft Edge. È facoltativo inserire una **Descrizione** del criterio.
Lo screenshot seguente mostra il modulo della scheda **Dati principali** e la barra dei menu indica i passaggi successivi (come schede disabilitate) per creare il profilo.

   ![Immettere Nome e Descrizione](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. Seleziona **Avanti**.
9. Nella scheda **Impostazioni di configurazione** selezionare la cartella Microsoft Edge in una delle posizioni seguenti:

   - cartella Configurazione computer
   - cartella Configurazione utente.

   Le impostazioni disponibili per Microsoft Edge verranno visualizzate nel riquadro a destra. Ad esempio, *Configurazione computer/Microsoft Edge/Consenti restrizioni download* come è mostrato nello screenshot seguente.

   ![Scheda Impostazioni di configurazione](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > Vedi [Microsoft Edge-Policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) e [Microsoft Edge-Update policy](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies) per l'elenco più completo e aggiornato di tutte le impostazioni disponibili per Microsoft Edge.

10. Usare il campo di ricerca ("Cerca per filtrare gli elementi...") per trovare un'opzione specifica da configurare. In questo esempio la stringa di ricerca è "home page". Lo screenshot seguente mostra i risultati della ricerca.

    ![Risultati ricerca](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. Dopo aver individuato l'impostazione che si intende configurare, selezionarla per esporre i valori che è possibile impostare. Nello screenshot seguente è stato selezionato "Configura l'URL della home page" come esempio.

    ![Configurare il criterio dell'URL della home page](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. Abilitare il criterio e immettere un valore per l'URL della home page, come illustrato nello screenshot precedente.

13. Fai clic su **OK**. La colonna "Stato" delle impostazioni dovrebbe essere visualizzata come "Enabled", come mostrato nello screenshot seguente.

    ![Lo stato dell'impostazione è abilitato](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. Fare clic sul pulsante **Avanti**.

15. Nella scheda **Tag di ambito**, aggiungere un tag di ambito, se del caso, altrimenti fare clic sul pulsante **Avanti**.

16. Nella scheda **Assegnazioni**, fare clic su + Seleziona gruppi da includere per assegnare il criterio al gruppo di Azure Active Directory (Azure AD) che contiene i dispositivi o gli utenti che si desidera ricevano questa impostazione dei criteri. Vedere [Assegnare profili utente e profili di dispositivo in Microsoft Intune](https://docs.microsoft.com/intune/device-profile-assign) per informazioni su come assegnare il profilo ai gruppi di utenti o di dispositivi di Azure AD.

    ![Selezionare i gruppi da includere](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. Fare clic sul pulsante **Avanti**.

18. Nella scheda **Controlla e crea**, rivedere il riepilogo delle modifiche per assicurarsi che sia corretto e quindi fare clic sul pulsante **Crea**.

19. Il criterio appena creato (criterio Microsoft Edge) viene mostrato nello screenshot seguente.

    ![Selezionare i gruppi da includere](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

Per altre informazioni sui profili di Windows 10, vedi [Usare i modelli di Windows 10 per configurare le impostazioni di Criteri di gruppo in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows).

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Gestire l'accesso Web usando Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge)
- [Usare i modelli di Windows 10 per configurare le impostazioni di Criteri di gruppo in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows)
- [Distribuire Microsoft Edge usando Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
