---
title: Domande frequenti su Microsoft Edge nell'azienda
ms.author: jwhit
author: jwhit-MSFT
manager: laurawi
ms.date: 11/04/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Domande frequenti sulla distribuzione di Microsoft Edge nell'azienda
ms.openlocfilehash: e689967cbad950e2969535bad0dd63d5d7081798
ms.sourcegitcommit: 12827458f6217f443128e826c1d18d36d401d03b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154321"
---
# Domande frequenti su Microsoft Edge nell'azienda

> [!NOTE]
> Questo articolo si applica a Microsoft Edge, versione 77 o successiva.

## Come posso sapere qual è la versione di Microsoft Edge in uso?

Nell'angolo superiore destro di Microsoft Edge fai clic sull'icona con i puntini di sospensione (**…**) e seleziona **Impostazioni**. Seleziona **informazioni su Microsoft Edge** per visualizzare la versione di Microsoft Edge in uso.

## Internet Explorer 11 continuerà a ricevere gli aggiornamenti?

Ci impegniamo a mantenere Internet Explorer un browser supportato, affidabile e sicuro. Internet Explorer è ancora un componente di Windows e segue il ciclo di vita del supporto del sistema operativo in cui è installato. Per altre informazioni, vedi [Domande frequenti sul ciclo di vita - Internet Explorer](https://support.microsoft.com/help/17454/). Mentre Microsoft continua a supportare e ad aggiornare Internet Explorer, gli aggiornamenti delle funzionalità e della piattaforma più recenti saranno disponibili solo in Microsoft Edge.

## Posso eseguire la versione corrente di Microsoft Edge (Microsoft Edge Legacy) in modalità affiancata quando provo la nuova versione?

Sì. Dopo il 15 gennaio 2020 la nuova versione di Microsoft Edge (basata su Chromium) verrà distribuita nei dispositivi con edizioni Home e Pro in cui è in esecuzione Windows 10, versione 1803 o successiva. I dispositivi aggiunti al dominio sono esclusi da questo aggiornamento. Per altre informazioni, vedi [Panoramica degli aggiornamenti di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-blocker-toolkit#overview). Puoi eseguire un'installazione affiancata di Microsoft Edge Legacy man mano che valuti la versione successiva di Microsoft Edge. Per altre informazioni, vedi [Come accedere alla versione precedente di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge). Inoltre, tutti i nuovi canali di Microsoft Edge supportano anche installazioni affiancate. Per altre informazioni, vedi [Panoramica dei canali di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-channels).

## Microsoft Edge (basato su Chromium) supporta i controlli ActiveX o gli oggetti browser helper come Silverlight o Java?

No. Microsoft Edge non supporta i controlli ActiveX e gli oggetti browser helper come Silverlight o Java. Tuttavia, se si eseguono app Web che usano i controlli ActiveX, oggetti browser helper o le modalità documento legacy in Internet Explorer 11, è possibile configurarle in modo che vengano eseguite in modalità Internet Explorer nel nuovo Microsoft Edge. Per altre informazioni, consultare[Configurare la modalità Internet Explorer in Microsoft Edge](https://docs.microsoft.com/DeployEdge/edge-ie-mode).

## I preferiti verranno trasferiti dalla versione corrente di Microsoft Edge o dovrò aggiungerli di nuovo?

Attualmente, Microsoft Edge supporta l'importazione da installazioni esistenti di Microsoft Edge, Chrome, Internet Explorer e Firefox (in Windows 10). Le impostazioni seguenti sono supportate per l'importazione di segnalibri, cronologia, password e riempimento automatico (pagamenti, indirizzi e moduli generici). Puoi scegliere di eseguire l'importazione alla prima esperienza d'uso o dalle impostazioni del browser.  

## Qual è la differenza tra i canali/le build Stable, Beta e Dev?

Il canale Stable della versione successiva di Microsoft Edge è il canale di anteprima più stabile che offriamo, con le funzionalità orientate alle aziende pronte per essere [usate in una fase pilota e valutate](https://aka.ms/EdgeEnterprise) in tutta la tua organizzazione. Il canale Beta consente di convalidare la successiva versione Stable con un set di utenti rappresentativo. I canali Stable e Beta verranno aggiornati approssimativamente ogni sei settimane. I canali Dev e Canary continueranno a essere aggiornati rispettivamente ogni settimana e ogni giorno. I programmi di installazione offline (file MSI e PKG) sono disponibili solo per i canali Stable, Beta e Dev. Per altre informazioni, vedi [Panoramica dei canali di Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-channels).

## Quale tipo di supporto per le estensioni ho con la nuova versione di Microsoft Edge?

Microsoft Edge supporta le estensioni da [Componenti aggiuntivi di Microsoft Edge Insider](https://go.microsoft.com/fwlink/?linkid=2081222) e [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2072338).

## La funzionalità di gestione di dispositivi mobili (MDM) e Microsoft Intune è supportata?

Sì. È ora supportata la configurazione di Microsoft Edge in Windows 10 tramite Microsoft Intune e la gestione di dispositivi mobili (MDM). Per altre informazioni, vedi [Configurare Microsoft Edge con Microsoft Intune](configure-edge-with-intune.md) e [Configurare Microsoft Edge con la gestione di dispositivi mobili](configure-edge-with-mdm.md).

## WSUS supporta la distribuzione iniziale del nuovo Microsoft Edge?

Sì. Sono disponibili pacchetti nel [Catalogo di Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=the%20new%20microsoft%20edge%20for%20windows), che possono essere usati per la distribuzione iniziale del nuovo Microsoft Edge tramite WSUS. Dopo la distribuzione iniziale, gli aggiornamenti automatici sono configurati per impostazione predefinita. Per altre informazioni, vedere [Aggiornamento in WSUS per il nuovo Microsoft Edge per Windows 10, versione 1809, 1903, 1909 e 2004: 29 ottobre 2020](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge).

Gli aggiornamenti manuali possono essere eseguiti tramite uno strumento di gestione della configurazione, ad esempio [ConfigMgr](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json).

## Vedere anche

- [Pagina di destinazione della documentazione di Microsoft Edge](https://docs.microsoft.com/DeployEdge/)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
