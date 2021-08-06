---
title: Reimpostare i dati Microsoft Edge
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Come reimpostare i dati Microsoft Edge nel cloud
ms.openlocfilehash: 7b1b54bd3e59190d6ff3bdfeb71b8f97080538c224b7dbddb73b9d11708706ac
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "11725989"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a>Reimpostare i dati Microsoft Edge nel cloud

In questo articolo vengono illustrati i passaggi per reimpostare i dati Microsoft Edge nel cloud.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 88 o successiva, se non diversamente specificato.

> [!NOTE]
> Se il tenant si trova in un ambiente GCC Mod, l'amministratore del tenant dovrà determinare una richiesta di supporto a Microsoft per reimpostare i dati.

## <a name="overview"></a>Panoramica

Ci sono situazioni in cui vuoi reimpostare i dati Microsoft Edge nel cloud. Ad esempio vuoi sincronizzare i dati, ma Microsoft Edge segnala che non riesce a sincronizzarli. In alternativa, è possibile verificare che i dati vengano rimossi dal cloud di Microsoft. In entrambi i casi, Microsoft Edge consente di eseguire un ripristino dei dati cloud.

## <a name="back-up-your-favorites"></a>Eseguire il backup dei Preferiti

Prima di eseguire un ripristino, è consigliabile eseguire il backup dei preferiti. Usare la procedura seguente per eseguire il backup dei preferiti.

1. In Microsoft Edge, selezionare **premere CTRL+MAIUSC+O > scegliere tre punti > fare clic su Esporta preferiti**.
2. Scegliere il file in cui salvare i preferiti. È possibile digitare un nome per il file o usare quello predefinito di Microsoft Edge, "favorites_month_day_year.html". Ad esempio, "favorites_07_05_21.html". Se è necessario ripristinare i preferiti in un secondo momento, è possibile farlo da tale file.
3. Fai clic su **Salva**.

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a>Esegui un ripristino per risolvere un problema di sincronizzazione

Se Microsoft Edge segnala che non riesce a sincronizzare i dati e suggerisce di reimpostare i dati, esegui un reset per risolvere il problema.

Usa la procedura seguente per eseguire un ripristino.

1. Prima di tutto, assicurati di aver eseguito l'accesso a Microsoft Edge in tutti i tuoi dispositivi, inclusi i tuoi dispositivi mobili, eccetto il dispositivo in cui stai eseguendo il ripristino. Per disconnettersi da Microsoft Edge, selezionare **Impostazioni > Profili > Disconnetti**. Al momento della disconnessione, non selezionare l'opzione per cancellare preferiti, impostazioni e così via dal dispositivo locale.
2. Dopo aver eseguito l'accesso a tutti gli altri dispositivi, aprire Microsoft Edge sul desktop. Selezionare **Impostazioni > Profili > Reimposta sincronizzazione**. Nella finestra di dialogo risultante scegliere di riprendere la sincronizzazione dopo la reimpostazione dei dati e quindi selezionare **Reimposta ora.**

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a>Eseguire un ripristino per rimuovere i dati dal cloud Microsoft

Se vuoi rimuovere i dati dal cloud Microsoft, esegui la procedura seguente per effettuare il ripristino.

1. Interrompere la sincronizzazione nei dispositivi, tranne per il dispositivo di cui si sta eseguendo il ripristino.  In Microsoft Edge, selezionare **Impostazioni > Profili > Disattiva sincronizzazione**.  
2. Dopo aver interrotto la sincronizzazione, **selezionare Impostazioni > Profili > Reimposta sincronizzazione**. Nella finestra di dialogo risultante **non** scegliere di riprendere la sincronizzazione sul dispositivo dopo la reimpostazione della sincronizzazione. Selezionare **Reimposta**.

## <a name="what-to-expect-during-and-after-a-data-reset"></a>Cosa aspettarsi durante e dopo la reimpostazione dei dati

Un reset dei dati può richiedere da pochi secondi a pochi minuti, a seconda della quantità di dati archiviati nel cloud di Microsoft. In alcuni casi potrebbe essere visualizzato un messaggio che indica che non è stato possibile completare un ripristino e che è stato suggerito di reimpostarlo. In questo caso, attendi qualche ora e riprova a reimpostare i dati. Se non si riesce ancora a reimpostare i dati, contatta il supporto Microsoft Edge.

Dopo che un ripristino dei dati è stato completato correttamente, i dati verranno di nuovo sincronizzati dal dispositivo se si è scelto di riprendere la sincronizzazione dopo il ripristino. Se si vuole eseguire la sincronizzazione da questi dispositivi, è necessario eseguire di nuovo l'accesso in altri dispositivi. Tuttavia, se non hai scelto di riprendere la sincronizzazione, i dati Microsoft Edge vengono rimossi dal cloud e i dati non verranno più sincronizzati.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Sincronizzazione di Microsoft Edge in modalità Enterprise](microsoft-edge-enterprise-sync.md)
