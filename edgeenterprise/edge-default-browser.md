---
title: Impostare Microsoft Edge come browser predefinito in Windows e macOS
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come impostare Microsoft Edge come browser predefinito
ms.openlocfilehash: c8cc45e0fe42dcbbd828dd81ae568f141cda2985
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980172"
---
# Impostare Microsoft Edge come browser predefinito

Questo articolo spiega come impostare Microsoft Edge come browser predefinito in Windows e macOS.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge, versione 77 in Windows 8 e Windows 10. Per Windows 7 e macOS, vedi il criterio [Impostare Microsoft Edge come browser predefinito](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled).

## Introduzione

Puoi usare l'impostazione di Criteri di gruppo **Imposta file di configurazione delle associazioni predefinite** o l'impostazione di gestione dei dispositivi mobili [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) per configurare Microsoft Edge come browser predefinito per l'organizzazione.

Per configurare Microsoft Edge Stable come browser predefinito per i file html, i collegamenti http/https e i file PDF, usa il seguente file di associazione dell'applicazione nell'esempio:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> Per configurare Microsoft Edge Beta come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Beta" e **ProgId** su "MSEdgeBHTML". Per configurare Microsoft Edge Dev come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Dev" e **ProgId** su "MSEdgeDHTML".


> [!NOTE]
> Le associazioni di file predefinite non vengono applicate se Microsoft Edge non è installato nel dispositivo di destinazione. In questo scenario, agli utenti viene richiesto di selezionare l'applicazione predefinita quando aprono un collegamento o un file htm/html.

## Impostare Microsoft Edge come browser predefinito in dispositivi aggiunti al dominio

Puoi impostare Microsoft Edge come browser predefinito in dispositivi aggiunti al dominio configurando l'impostazione di Criteri di gruppo **Imposta file di configurazione delle associazioni predefinite**. Per attivare questa impostazione devi inoltre creare e archiviare un file di configurazione di associazioni predefinite. Questo file viene archiviato localmente o in una condivisione di rete. Per altre informazioni sulla creazione di questo file, vedi [Esportare o importare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)

### Per configurare i criteri di gruppo per un tipo di file e un file di configurazione di associazioni di protocollo predefiniti:

1. Apri Editor Criteri di gruppo e vai a **Configurazione computer\Modelli amministrativi\Componenti Windows\Esplora file**.
2. Seleziona **Imposta file di configurazione delle associazioni predefinite**.
3. Fai clic su **Impostazione criterio** e quindi fai clic su **Abilitato**.
4. Nell'area **Opzioni** digita il percorso del file di configurazione delle associazioni predefinite.
5. Fai clic su **OK** per salvare le impostazioni dei criteri.

L'esempio nella schermata successiva mostra un file di associazioni denominato *appassoc.xml* in una condivisione di rete accessibile dal dispositivo di destinazione.

   ![Abilitare l'associazione di file in Criteri di gruppo](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > Se questa impostazione è abilitata e il dispositivo dell'utente è aggiunto a un dominio, il file di configurazione delle associazioni viene elaborato al successivo accesso dell'utente.

## Configurare Microsoft Edge come browser predefinito in dispositivi aggiunti ad Azure Active Directory

Per configurare Microsoft Edge come browser predefinito in dispositivi aggiunti ad Azure Active Directory, attieniti ai passaggi descritti nell'impostazione di gestione dei dispositivi mobili [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) usando come esempio il file di associazione dell'applicazione che segue.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> Per configurare Microsoft Edge Beta come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Beta" e **ProgId** su "MSEdgeBHTML". Per configurare Microsoft Edge Dev come browser predefinito, imposta **ApplicationName** su "Microsoft Edge Dev" e **ProgId** su "MSEdgeDHTML".

## Impostare Microsoft Edge come browser predefinito in Windows e macOS

Se tenti di impostare il browser predefinito a livello di codice su macOS viene visualizzata una richiesta per l'utente finale. Questa richiesta è una funzionalità di sicurezza di macOS che può essere automatizzata solo tramite AppleScript.

A causa di questa limitazione, esistono due metodi principali per impostare Microsoft Edge come browser predefinito in un macOS. La prima opzione consiste nell'eseguire il flash del dispositivo con un'immagine di macOS, in cui Microsoft Edge è già stato impostato come browser predefinito. L'altra opzione consiste nell'usare i criteri [Impostare Microsoft Edge come browser predefinito](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) , che ti richiede di impostare Microsoft Edge come browser predefinito.

Quando usi uno di questi metodi, puoi comunque modificare il browser predefinito. Questo perché la preferenza del browser predefinito non può essere bloccata a livello di codice per motivi di sicurezza. Per questo motivo, ti consigliamo di distribuire i criteri **Impostare Microsoft Edge come browser predefinito** anche se crei un'immagine con Microsoft Edge come browser predefinito. Se i criteri sono impostati e un utente cambia il browser predefinito in un browser diverso da Microsoft Edge, la prossima volta che avvii Microsoft Edge ti verrà richiesto di impostarlo come browser predefinito.

## Vedi anche

- [Pianificare la distribuzione di Microsoft Edge](https://docs.microsoft.com/DeployEdge/deploy-edge-plan-deployment)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Impostare Microsoft Edge come browser predefinito (Windows 7 e macOS)](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled)
- [Windows 10: come configurare le associazioni di file per i professionisti IT?](https://docs.microsoft.com/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [Esportare o importare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [Panoramica di DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism)
  - [DISM - Gestione e manutenzione immagini distribuzione](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)
