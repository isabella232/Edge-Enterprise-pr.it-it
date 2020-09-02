---
title: Configurare i criteri della modalità IE
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 03/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare i criteri della modalità IE
ms.openlocfilehash: 2d2ded3a3fb338bdf2d815d681b52249007945ac
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980170"
---
# Configurare i criteri della modalità IE

Questo articolo spiega come configurare i criteri della modalità IE.

> [!NOTE]
> Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.

La configurazione della modalità IE richiede tre passaggi:

1. [Configurare l'integrazione Internet Explorer](#configure-internet-explorer-integration)
2. [Reindirizzare i siti da Microsoft Edge alla modalità IE](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. [Reindirizzare i siti da IE a Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge) (facoltativo)

> [!NOTE]
> I criteri per abilitare la modalità Internet Explorer possono essere configurati con Intune. Per altre informazioni, vedere [Aggiungere Microsoft Edge a Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) e [Configurare i criteri Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/DeployEdge/configure-edge-with-intune).

## Configurare l'integrazione Internet Explorer

È possibile configurare Internet Explorer in modo che venga aperto direttamente all'interno di Microsoft Edge (modalità IE). È anche possibile configurare Internet Explorer in modo che venga aperto con una finestra autonoma di Internet Explorer 11. La maggior parte degli utenti preferisce l'opzione che consente di aprire i siti direttamente all'interno di Microsoft Edge in modalità IE.

### Abilitare l'integrazione Internet Explorer con Criteri di gruppo

1. Scarica e usa il [modello di criteri di Microsoft Edge](https://www.microsoft.com/en-us/edge/business/download) più recente.
2. Apri Editor Criteri di gruppo.
3. Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
4. Fai doppio clic su **Configura integrazione Internet Explorer**.
5. Seleziona **Attivata**.
6. In **Opzioni** impostare il valore del menu a discesa su 
   -  **Modalità Internet Explorer** se si vuole che i siti vengano aperti in modalità IE su Microsoft Edge
   -  **Internet Explorer 11** se si vuole che i siti vengano aperti in una finestra di Internet Explorer 11 autonoma
   -  **Nessuno** se si desidera impedire agli utenti di configurare la modalità Internet Explorer tramite edge://flags o la riga di comando

   > [!NOTE]
   > Se si impostano i criteri su **Disabilitato** la modalità Internet Explorer è disabilitata in base ai criteri, ma può essere impostata tramite edge://flags o le opzioni della riga di comando.
7. Fai clic su **OK** o su **Applica** per salvare questa impostazione.

## Reindirizzare i siti da Microsoft Edge alla modalità IE

Sono disponibili due opzioni per identificare i siti che devono essere aperti in modalità IE:

- (Consigliato) [Configurare i siti nell'elenco di siti in modalità Enterprise](#configure-sites-on-the-enterprise-site-list)
- [Configurare tutti i siti Intranet](#configure-all-intranet-sites)

### Configurare i siti nell'elenco di siti in modalità Enterprise

Puoi usare i seguenti criteri di gruppo per configurare siti specifici da aprire in modalità Internet Explorer:

- [Usa elenco siti Web di Internet Explorer modalità Enterprise](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)
- [Configura elenco siti modalità Enterprise](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, versione 78 o successiva)<br/>Questi criteri consentono di creare un elenco di siti in modalità Enterprise separati per Microsoft Edge. L'abilitazione di questo criterio sovrascrive le impostazioni nel criterio "Usa elenco siti Web di Internet Explorer modalità Enterprise", purché "Configura integrazione Internet Explorer" sia abilitato. La disabilitazione o la configurazione di questo criterio non influisce sul comportamento predefinito del criterio "Configura integrazione Internet Explorer".
    > [!NOTE]
    > Non è obbligatorio configurare il criterio di Microsoft Edge. Molte organizzazioni usano questo criterio come override per indirizzare l'elenco di siti corrente a tutti gli utenti con il criterio di IE e per inoltrare più facilmente una versione aggiornata agli utenti pilota con il criterio di Microsoft Edge.

Per altre informazioni sull'elenco di siti per la modalità Enterprise, vedi:

- [Usare Enterprise Mode Site List Manager](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- [Aggiungere più siti all'elenco dei siti per la modalità Enterprise tramite un file ed Enterprise Mode Site List Manager (schema v.2)](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).

### Configurare tramite il criterio Usa elenco siti Web di Internet Explorer modalità Enterprise

La modalità IE può usare il criterio esistente configurando l'elenco di siti in modalità Enterprise per Internet Explorer, che consente di creare e gestire un unico elenco.

1. Creare o usare nuovamente un file XML dell'elenco di siti
    1. Tutti i siti che contengono l'elemento _\<open-in\>IE11\</open-in\>_ ora si apriranno in modalità di Internet Explorer.
2. Apri Editor Criteri di gruppo.
3. Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Componenti di Windows** > **Internet Explorer**.
4. Fai doppio clic su **Usa elenco siti Web di Internet Explorer modalità Enterprise**.
5. Seleziona **Attivata**.
6. In **Opzioni**, digita il percorso dell'elenco di siti Web. Puoi usare uno dei percorsi seguenti:
    - Percorso HTTPS: **https**:**//iemode/sites.xml** (scelta consigliata)
    - File di rete locale: **\\\network\shares\sites.xml**
    - File locale: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.

### Configurare tramite il criterio Configura elenco siti modalità Enterprise

È anche possibile configurare la modalità IE con un criterio separato per Microsoft Edge. Questo criterio aggiuntivo consente di eseguire l'override dell'elenco di siti IE. Ad esempio, alcune organizzazioni indirizzano l'elenco di siti di produzione a tutti gli utenti. È quindi possibile distribuire l'elenco di siti pilota a un piccolo gruppo di utenti con questo criterio.

1. Creare o usare nuovamente un file XML dell'elenco di siti
    1. Tutti i siti che contengono l'elemento _\<open-in\>IE11\</open-in\>_ ora si apriranno in modalità di Internet Explorer.
2. Apri Editor Criteri di gruppo.
3. Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
4. Fai doppio clic su **Configura elenco siti modalità Enterprise**.
5. Seleziona **Attivata**.
6. In **Opzioni**, digita il percorso dell'elenco di siti Web. Puoi usare uno dei percorsi seguenti:
    - Percorso HTTPS: **https**:**//iemode/sites.xml** (scelta consigliata) <!--Trying to keep this from being an active link in MD -->
    - File di rete locale: **\\\network\shares\sites.xml**
    - File locale: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.

### Configurare tutti i siti Intranet

La modalità IE può essere configurata come tutti i siti nella zona dell'area Intranet locale. È possibile rimuovere singoli siti dalla modalità IE con un elenco di siti in modalità Enterprise.

>[!NOTE]
>
> L'area Intranet locale contiene siti aggiunti esplicitamente, ma è anche possibile assegnare i siti a questa area usando l'euristica. Possono essere inclusi nomi host senza punto (ad esempio, **https**:**//payroll**) e i siti che lo script di configurazione del proxy configura per ignorare il proxy. Se una parte esterna controlla il DNS o il proxy, potrebbe forzare i siti Web in modalità IE.

1. Aprire l'Editor Criteri di gruppo locali.
2. Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.
3. Fai doppio clic su **Invia tutti i siti Intranet a Internet Explorer**.
4. Seleziona **Abilitato** e quindi fai clic su **OK** o su **Applica** per salvare le impostazioni.

## Reindirizzare i siti da IE a Microsoft Edge

È possibile impedire agli utenti di usare Internet Explorer per i siti che non lo richiedono. Internet Explorer può reindirizzare automaticamente i siti a Microsoft Edge se non si trovano nell'elenco di siti.

1. Apri Editor Criteri di gruppo.
2. Fare clic su **Configurazione computer** > **Strumenti di amministrazione** > **Componenti di Windows** > **Internet Explorer**.
3. Fare doppio clic su **Invia a Microsoft Edge tutti i siti non inclusi nell'elenco siti modalità Enterprise**.
4. Selezionare **Attivato**.
5. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.
6. Fare doppio clic su **Configura quale canale di Microsoft Edge usare per aprire i siti reindirizzati**.
7. Seleziona **Attivata**.
8. In **Opzioni**, selezionare le prime tre scelte per il canale da usare: Internet Explorer reindirizzerà alla scelta con la classificazione più alta che l'utente ha installato sul dispositivo:
   - Canale stabile Microsoft Edge
   - Canale Microsoft Edge Beta versione 77 o successiva
   - Canale Microsoft Edge Dev versione 77 o successiva
   - Canale Microsoft Edge Canary versione 77 o successiva
   - Microsoft Edge versione 45 o precedente
9. Fai clic su **OK** o su **Applica** per salvare queste impostazioni.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni sulla modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [Informazioni aggiuntive sulla modalità Enterprise](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)