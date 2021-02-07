---
title: Microsoft Edge nel tuo ambiente
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge nel tuo ambiente
ms.openlocfilehash: e1418d21ff9e541d83d5b86baf5ff25c50d2299d
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313942"
---
# Microsoft Edge nel tuo ambiente

Questo articolo descrive come prepararsi a implementare Microsoft Edge quandola versione legacy di Microsoft Edge raggiunge la fine del suo servizio.

Come da [post del blog](https://aka.ms/EdgeLegacyEOS) di Microsoft Edge Product Team, il supporto per l'applicazione desktop Microsoft Edge Legacy terminerà il 9 marzo 2021. Quando applichi la versione Update Tuesday (o "B") di aprile, si rimuoverà la versione legacy di Microsoft Edge dai dispositivi con Windows 10 RS4 attraverso 20H1 e lo sostituirà con Microsoft Edge.

## Come prepararsi

Per preparare l'installazione di Microsoft Edge nei dispositivi Windows 10 RS4-20H1 con la versione Update Tuesday di aprile, consigliamo leggere [Pianificare l’implementazione di Microsoft Edge](deploy-edge-plan-deployment.md).

Dopo aver pianificato la tua distribuzione, usa uno dei seguenti approcci per prepararti a distribuire Microsoft Edge.

- **Installare i criteri di gruppo per personalizzare l'approccio di aggiornamento di Microsoft Edge**. Per ulteriori informazioni, consulta [Configurare le impostazioni dei criteri di Microsoft Edge su Windows](configure-microsoft-edge.md), e presta particolare attenzione al materiale di [riferimento di Update Policy](microsoft-edge-update-policies.md). Se installi i criteri di gruppo per gestire gli aggiornamenti prima di installare la versione Update Tuesday di aprile, Microsoft Edge inizierà immediatamente a rispettare i tuoi criteri. Se non c'è alcun criterio di gruppo installato, Microsoft Edge si aggiornerà automaticamente.

- **Rimuovere l'applicazione desktop della versione legacy di Microsoft Edge prima della sua data di fine servizio del 9 marzo 2021 e distribuire Microsoft Edge**. Per Windows 10 RS4 fino a 20H1, potete farlo usando Windows Updates. Per altre informazioni, consulta [Distribuire Microsoft Edge con gli aggiornamenti di Windows 10](deploy-edge-with-windows-10-updates.md).

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Pianificare la distribuzione di Microsoft Edge](deploy-edge-plan-deployment.md)