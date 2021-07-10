---
title: Microsoft Edge nel tuo ambiente
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge nel tuo ambiente
ms.openlocfilehash: 2381380cb399f6a1fbb5efa9378ffeba20fa774f
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641602"
---
# <a name="microsoft-edge-in-your-environment"></a>Microsoft Edge nel tuo ambiente

Questo articolo descrive come prepararsi a implementare Microsoft Edge quandola versione legacy di Microsoft Edge raggiunge la fine del suo servizio.

Come da [post del blog](https://aka.ms/EdgeLegacyEOS) di Microsoft Edge Product Team, il supporto per l'applicazione desktop Microsoft Edge Legacy terminerà il 9 marzo 2021. Quando applichi la versione Update Tuesday (o "B") di aprile, si rimuoverà la versione legacy di Microsoft Edge dai dispositivi con Windows 10 RS4 attraverso 20H1 e lo sostituirà con Microsoft Edge.

## <a name="how-to-prepare"></a>Come prepararsi

Per preparare l'installazione di Microsoft Edge nei dispositivi Windows 10 RS4-20H1 con la versione Update Tuesday di aprile, consigliamo leggere [Pianificare l’implementazione di Microsoft Edge](deploy-edge-plan-deployment.md).

Dopo aver pianificato la tua distribuzione, usa uno dei seguenti approcci per prepararti a distribuire Microsoft Edge.

- **Installare i criteri di gruppo per personalizzare l'approccio di aggiornamento di Microsoft Edge**. Per ulteriori informazioni, consulta [Configurare le impostazioni dei criteri di Microsoft Edge su Windows](configure-microsoft-edge.md), e presta particolare attenzione al materiale di [riferimento di Update Policy](microsoft-edge-update-policies.md). Se installi i criteri di gruppo per gestire gli aggiornamenti prima di installare la versione Update Tuesday di aprile, Microsoft Edge inizierà immediatamente a rispettare i tuoi criteri. Se non c'è alcun criterio di gruppo installato, Microsoft Edge si aggiornerà automaticamente.

- **Rimuovere l'applicazione desktop della versione legacy di Microsoft Edge prima della sua data di fine servizio del 9 marzo 2021 e distribuire Microsoft Edge**. Per Windows 10 RS4 fino a 20H1, potete farlo usando Windows Updates. Per altre informazioni, consulta [Distribuire Microsoft Edge con gli aggiornamenti di Windows 10](deploy-edge-with-windows-10-updates.md).

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Pianificare la distribuzione di Microsoft Edge](deploy-edge-plan-deployment.md)