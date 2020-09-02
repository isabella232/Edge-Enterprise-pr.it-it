---
title: Automatizzare la distribuzione di Microsoft Edge per macOS con Jamf
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Come automatizzare la distribuzione di Microsoft Edge per macOS con Jamf.
ms.openlocfilehash: 3065e4f02dbfed70b887a60b1cf076335dbff19a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980109"
---
# Distribuire in macOS con Jamf

Questo articolo descrive come distribuire Microsoft Edge per macOS con Jamf.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## Prerequisiti

Prima di iniziare a distribuire Microsoft Edge, verifica che siano soddisfatti i seguenti prerequisiti:

- Il file di installazione di Microsoft Edge, **MicrosoftEdgeDev-\<version\>pkg**, si trova in un percorso di rete accessibile. Puoi scaricare i file di installazione per Microsoft Edge in modalità Enterprise nella [pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise).
- Devi disporre di un account Jamf Cloud con il livello di accesso e i privilegi necessari per creare e distribuire file di installazione nei computer.

## Per distribuire Microsoft Edge tramite Jamf:

1. Accedi a Jamf e vai a **Tutte le impostazioni**.

    ![Aprire Tutte le impostazioni](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. In **Tutte le impostazioni** fai clic su **Gestione computer**.

    ![Selezionare Gestione computer](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. In **Gestione computer** fai clic su **Pacchetti**.

    ![Selezionare Pacchetti.](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. Nella pagina **Pacchetti** fai clic su **+ Nuovo** per aggiungere un nuovo pacchetto.

    ![Selezionare Nuovo per aggiungere un nuovo pacchetto](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. Nella pagina **Nuovo pacchetto** immetti i dettagli relativi al pacchetto e quindi fai clic su **Salva**. (Ad esempio NOME VISUALIZZATO, INFO o NOTE.)

    ![Seleziona Salva per salvare le informazioni sul pacchetto](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. Seleziona **Computer** sulla barra dei menu e quindi seleziona **Criteri** sulla barra di spostamento.

7. Seleziona **+ Nuovo** per visualizzare il riquadro **Nuovo criterio**.

    ![Selezionare Nuovo per creare un nuovo criterio](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. Nella scheda **Opzioni** scegliere **Generale**.

    - In **NOME VISUALIZZATO** immetti il nome visualizzato per il criterio.
    - In **Attivazione** seleziona l'evento che attiverà il criterio. Nell'esempio seguente l'evento è l'avvio.

    ![Immettere le informazioni sulla distribuzione](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. Nella scheda **Opzioni** fai clic su **Pacchetti**.

10. Nella finestra popup **Configura pacchetti** fai clic su **Configura**.

    ![Configurare un pacchetto](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. Il pacchetto aggiunto viene visualizzato nel riquadro **Pacchetti**. Fai clic su **Aggiungi**. Per questo esempio, il pacchetto è "MicrosoftEdgeBeta" nella schermata seguente.

    ![Aggiungere un pacchetto](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. Nella pagina **Nuovo criterio** usa gli elenchi a discesa per selezionare il **PUNTO DI DISTRIBUZIONE** e l'**AZIONE** da eseguire per il criterio. Fai clic su **Salva**. Nella schermata seguente vengono usati "Punto di distribuzione predefinito di ogni computer" e "Installa" come esempio.

    ![Selezionare il punto di distribuzione e l'azione](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. Nella pagina **Nuovo criterio** selezionare la scheda **Ambito**. Puoi gestire l'ambito della distribuzione in base a computer oppure a utenti. Per questo esempio, seleziona **Tutti i computer** nell'elenco a discesa **COMPUTER DI DESTINAZIONE** e quindi fai clic su **Salva**.

    ![Selezionare l'ambito della distribuzione](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. A questo punto puoi esaminare i criteri di distribuzione di Microsoft Edge. Se le opzioni di distribuzione soddisfano i requisiti, fai clic su **Fine**.

    ![Fare clic su Fine.](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > Puoi tornare a un criterio di distribuzione in qualsiasi momento per modificare le impostazioni.

Complimenti. Hai appena finito di configurare Jamf per distribuire Microsoft Edge per macOS. Quando la condizione di trigger definita è true, il pacchetto verrà distribuito ai computer specificati.

## Vedi anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Jamf.com](https://www.jamf.com/)
- [Integrare Jamf con Microsoft Intune](https://docs.microsoft.com/intune/conditional-access-integrate-jamf)
