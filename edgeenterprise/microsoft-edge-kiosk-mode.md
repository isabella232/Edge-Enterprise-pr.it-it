---
title: Modalità tutto schermo di Microsoft Edge
ms.author: brianalt
author: brianalt
manager: seanlynd
ms.date: 01/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Modalità tutto schermo di Microsoft Edge
ms.openlocfilehash: 7a690820752b5361349bf394055a737bd8175215
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980290"
---
# Modalità tutto schermo di Microsoft Edge

In questo articolo viene fornita una panoramica delle opzioni della modalità tutto schermo di Microsoft Edge (versione 77 o successiva). Vengono inoltre illustrate le informazioni necessarie per continuare a utilizzare la modalità tutto schermo di Microsoft Edge Legacy (versione 45 e versioni precedenti).

Per informazioni sulla modalità tutto schermo di Microsoft Edge Legacy (versione 45 e versioni precedenti), vedi [Distribuire la modalità tutto schermo di Microsoft Edge](https://aka.ms/edgekioskmode).

## Microsoft Edge con accesso assegnato

Microsoft Edge può essere eseguito con [accesso assegnato con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) su Windows 10, che è l'equivalente del tipo di modalità tutto schermo per l'esplorazione normale di Microsoft Edge Legacy. Per configurare Microsoft Edge con l'accesso assegnato con più app, segui le istruzioni su come [configurare un chiosco multimediale con più app](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps). L'AUMID per il canale Microsoft Edge Stable è **MSEdge.**

Quando usi Microsoft Edge con accesso assegnato con più app, puoi utilizzare i [criteri del browser Microsoft Edge](microsoft-edge-policies.md) per configurare l'esperienza di esplorazione per soddisfare i tuoi requisiti univoci.

Oggi Microsoft Edge non supporta gli stessi tipi di modalità tutto schermo di Microsoft Edge Legacy per l'accesso assegnato con una singola app e il tipo di modalità tutto schermo "Esplorazione pubblica" nell'accesso assegnato con più app. Se hai bisogno di un browser per il tuo dispositivo in modalità tutto schermo ad accesso singolo assegnato con singola app, ti consigliamo di usare la [modalità tutto schermo di Microsoft Edge Legacy](https://aka.ms/edgekioskmode) o l'[app del browser in modalità tutto schermo di Microsoft](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab). 

## Il parametro della riga di comando "--kiosk" di Microsoft Edge

Puoi avviare Microsoft Edge in modalità tutto schermo utilizzando il parametro della riga di comando "`--kiosk`". Verrà aperto il browser a schermo intero con la combinazione di tasti di scelta rapida a schermo intero disabilitata (F11). A questo scopo, crea un collegamento con la destinazione impostata su:<br>
*`"<local path>\msedge.exe" --kiosk http://bing.com`*

> [!NOTE]
> Il parametro "`--kiosk`" non impedirà all'utente di accedere ai tasti di scelta rapida di Windows né l'esecuzione di altre applicazioni. Per eseguire questo tipo di controllo, puoi usare [AppLocker per creare un chiosco multimediale Windows 10](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker) e un [filtro della tastiera](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter).

Per uscire dalla modalità tutto schermo e chiudere il browser, usa ALT + F4.

## Supporto per la modalità tutto schermo di Microsoft Edge Legacy

Quando viene installata la nuova versione del canale Microsoft Edge Stable, Microsoft Edge Legacy è nascosto e tutti i tentativi di avviarlo vengono reindirizzati alla nuova versione. Per informazioni su:

- Requisiti per l'aggiornamento di Windows, vedi [Aggiornamenti di Windows per supportare la prossima versione di Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md). 
- Accesso a Microsoft Edge Legacy dopo l'installazione di Microsoft Edge, vedi [Accedere a Microsoft Edge Legacy dopo l'installazione della nuova versione di Microsoft Edge](microsoft-edge-sysupdate-access-old-edge.md)
 
Per continuare a usare la modalità tutto schermo di Microsoft Edge Legacy nei dispositivi in modalità tutto schermo, effettua una delle azioni seguenti: 

- Se prevedi di installare il canale Microsoft Edge Stable, desideri autorizzare l'installazione o se è già installato nel tuo dispositivo a modalità tutto schermo, distribuisci il criterio Microsoft Edge [Consenti esperienza browser Microsoft Edge affiancata](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs).
- Per impedire l'installazione del canale Microsoft Edge Stable nei dispositivi in modalità tutto schermo, distribuisci il criterio Microsoft Edge [Consenti installazione predefinita](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) per il canale Stable o prendi in esame l'uso di [Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge](microsoft-edge-blocker-toolkit.md). 

## Vedi anche

- [Configurare chioschi multimediali e firme digitali nelle edizioni desktop di Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Distribuire la modalità tutto schermo di Microsoft Edge Legacy](https://aka.ms/edgekioskmode) 
- [Pianificare la distribuzione di Microsoft Edge](deploy-edge-plan-deployment.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
