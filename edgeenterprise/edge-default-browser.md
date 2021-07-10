---
title: Impostare Microsoft Edge come browser predefinito in Windows e macOS
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Scopri come impostare Microsoft Edge come browser predefinito
ms.openlocfilehash: 191d7835a0c4aacfc2fde409c57622ff5a351926
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641542"
---
# <a name="set-microsoft-edge-as-the-default-browser"></a>Impostare Microsoft Edge come browser predefinito

Questo articolo spiega come impostare Microsoft Edge come browser predefinito in Windows e macOS.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge, versione 77 in Windows 8 e Windows 10. Per Windows 7 e macOS, vedi il criterio [Impostare Microsoft Edge come browser predefinito](./microsoft-edge-policies.md#defaultbrowsersettingenabled).

## <a name="introduction"></a>Introduzione

Puoi usare l'impostazione di Criteri di gruppo **Imposta file di configurazione delle associazioni predefinite** o l'impostazione di gestione dei dispositivi mobili [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) per configurare Microsoft Edge come browser predefinito per l'organizzazione.

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

## <a name="set-microsoft-edge-as-the-default-browser-on-domain-joined-devices"></a>Impostare Microsoft Edge come browser predefinito in dispositivi aggiunti al dominio

Puoi impostare Microsoft Edge come browser predefinito in dispositivi aggiunti al dominio configurando l'impostazione di Criteri di gruppo **Imposta file di configurazione delle associazioni predefinite**. Per attivare questa impostazione devi inoltre creare e archiviare un file di configurazione di associazioni predefinite. Questo file viene archiviato localmente o in una condivisione di rete. Per altre informazioni sulla creazione di questo file, vedi [Esportare o importare associazioni di applicazioni predefinite](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)

### <a name="to-configure-the-group-policy-for-a-default-file-type-and-protocol-associations-configuration-file"></a>Per configurare i criteri di gruppo per un tipo di file e un file di configurazione di associazioni di protocollo predefiniti:

1. Apri Editor Criteri di gruppo e vai a **Configurazione computer\Modelli amministrativi\Componenti Windows\Esplora file**.
2. Seleziona **Imposta file di configurazione delle associazioni predefinite**.
3. Fai clic su **Impostazione criterio** e quindi fai clic su **Abilitato**.
4. Nell'area **Opzioni** digita il percorso del file di configurazione delle associazioni predefinite.
5. Fai clic su **OK** per salvare le impostazioni dei criteri.

L'esempio nella schermata successiva mostra un file di associazioni denominato *appassoc.xml* in una condivisione di rete accessibile dal dispositivo di destinazione.

   ![Abilitare l'associazione di file in Criteri di gruppo](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > Se questa impostazione è abilitata e il dispositivo dell'utente è aggiunto a un dominio, il file di configurazione delle associazioni viene elaborato al successivo accesso dell'utente.

## <a name="set-microsoft-edge-as-the-default-browser-on-azure-active-directory-joined-devices"></a>Configurare Microsoft Edge come browser predefinito in dispositivi aggiunti ad Azure Active Directory

Per configurare Microsoft Edge come browser predefinito in dispositivi aggiunti ad Azure Active Directory, attieniti ai passaggi descritti nell'impostazione di gestione dei dispositivi mobili [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) usando come esempio il file di associazione dell'applicazione che segue.

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

## <a name="set-microsoft-edge-as-the-default-browser-on-macos"></a>Impostare Microsoft Edge come browser predefinito in Windows e macOS

Se tenti di impostare il browser predefinito a livello di codice su macOS viene visualizzata una richiesta per l'utente finale. Questa richiesta è una funzionalità di sicurezza di macOS che può essere automatizzata solo tramite AppleScript.

A causa di questa limitazione, esistono due metodi principali per impostare Microsoft Edge come browser predefinito in un macOS. La prima opzione consiste nell'eseguire il flash del dispositivo con un'immagine di macOS, in cui Microsoft Edge è già stato impostato come browser predefinito. L'altra opzione consiste nell'usare i criteri [Impostare Microsoft Edge come browser predefinito](./microsoft-edge-policies.md#defaultbrowsersettingenabled) , che ti richiede di impostare Microsoft Edge come browser predefinito.

Quando usi uno di questi metodi, puoi comunque modificare il browser predefinito. Questo perché la preferenza del browser predefinito non può essere bloccata a livello di codice per motivi di sicurezza. Per questo motivo, ti consigliamo di distribuire i criteri **Impostare Microsoft Edge come browser predefinito** anche se crei un'immagine con Microsoft Edge come browser predefinito. Se i criteri sono impostati e un utente cambia il browser predefinito in un browser diverso da Microsoft Edge, la prossima volta che avvii Microsoft Edge ti verrà richiesto di impostarlo come browser predefinito.

## <a name="see-also"></a>Vedi anche

- [Pianificare la distribuzione di Microsoft Edge](./deploy-edge-plan-deployment.md)
- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Impostare Microsoft Edge come browser predefinito (Windows 7 e macOS)](./microsoft-edge-policies.md#defaultbrowsersettingenabled)
- [Windows 10: come configurare le associazioni di file per i professionisti IT?](/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [Esportare o importare associazioni di applicazioni predefinite](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [Panoramica di DISM](/windows-hardware/manufacture/desktop/what-is-dism)
  - [DISM - Gestione e manutenzione immagini distribuzione](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)