---
title: Effettuare il provisioning dei preferiti per Microsoft Edge
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 09/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Effettuare il provisioning dei preferiti per Microsoft Edge
ms.openlocfilehash: 94bd42573bdbc0fd1b971ded1c82e5fe152acc54
ms.sourcegitcommit: 854dd73eb168960c0eb4b483f81a8efe88806a64
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088704"
---
# Effettuare il provisioning dei preferiti per Microsoft Edge

Sulla base del feedback dei clienti, sono stati apportati miglioramenti al provisioning dei preferiti. A partire da Microsoft Edge versione 85, gli amministratori non devono più creare manualmente un file per eseguire il provisioning dei preferiti. Possono aggiungere preferiti e cartelle mediante l'interfaccia utente di Microsoft Edge per generare un file che può essere esportato in un criterio di gruppo.

Questo articolo descrive come eseguire il provisioning di un set di preferiti e di cartelle per l'organizzazione. È possibile usare il criterio [Configura i Preferiti](https://docs.microsoft.com//DeployEdge/microsoft-edge-policies#configure-favorites) per effettuare il provisioning di preferiti e cartelle.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 85 o successiva.

## Prerequisiti e consigli

- Microsoft Edge versione 85 con il modello amministrativo appropriato installato per i criteri di gruppo.
- È consigliabile usare un nuovo profilo in Microsoft Edge per effettuare il provisioning di questi preferiti. Tutti i preferiti salvati con il profilo verranno inclusi nell'esportazione.  

## Provisioning di preferiti e cartelle

Seguire questa procedura per eseguire il provisioning di preferiti e cartelle per gli utenti.

1. Passare alla barra degli indirizzi di Microsoft Edge e digitare questo URL: *edge://flags/#edge-favorites-admin-export*.
2. In **Esportazione configurazione dei preferiti per gli amministratori** scegliere **Abilitato** nell'elenco a discesa e quindi fare clic su **Riavvia**.

3. Passare alla pagina **Preferiti** in *edge://favorites* per aggiungere i preferiti e le cartelle di cui effettuate il provisioning.

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. Dopo aver aggiunto i preferiti e le cartelle si procederà ad esportarli, in modo che possano essere usati dal criterio **Configura i Preferiti**. Andare alla barra degli indirizzi, passare a *edge://favorites*, fare clic sui puntini di sospensione "**…**" e scegliere **Esporta configurazione dei preferiti**. Il prossimo screenshot mostra le opzioni disponibili durante il provisioning dei preferiti.

   ![Opzioni di menu per l'uso dei preferiti.](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. In **Esporta configurazione dei preferiti** specificare un nome per la cartella che gli utenti vedranno. Digitare il nome della cartella e selezionare il formato della piattaforma da usare. Fare clic su **Copia negli Appunti**. Lo screenshot seguente mostra il nome "Preferiti gestiti" per la cartella e la piattaforma scelta è Windows.

   ![Finestra di dialogo per l'esportazione dei preferiti in una cartella di Windows.](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. Aprire l'Editor Criteri di gruppo, passare a *Configurazione computer/Modelli amministrativi/* e scegliere **Configura i Preferiti**. Abilitare il criterio "Configura i Preferiti". In **Opzioni:** incollare il contenuto esportato nell'area di testo Configura i Preferiti e quindi fare clic su **Applica**. Lo screenshot seguente mostra un esempio della cartella "Preferiti gestiti" del passaggio 5.

   ![Utilizzare gpedit per abilitare e configurare il criterio "Configura i Preferiti".](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. Fare clic su **OK** o su **Applica** per salvare queste impostazioni dei criteri.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)