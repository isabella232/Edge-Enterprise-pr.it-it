---
title: Che cos'è la modalità Internet Explorer?
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 08/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Ulteriori informazioni su come la modalità Internet Explorer di Microsoft Edge consente di accedere ai siti che necessitano di Internet Explorer 11, oltre all'accesso ai siti moderni.
ms.openlocfilehash: a426d9bd9d2ac3d81682e9fc2304e9e90d3461f8
ms.sourcegitcommit: 4442aa94d4ff2fef8dd6f389ec0c6823b150d04f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2021
ms.locfileid: "12053325"
---
# <a name="what-is-internet-explorer-ie-mode"></a>Che cos'è la modalità Internet Explorer (IE)?

>[!Note]
> L'applicazione desktop Internet Explorer 11 verrà ritirata e non sarà più disponibile per il supporto il 15 giugno 2022 (per un elenco degli elementi nell'ambito, [vedere le domande frequenti](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)). Le stesse app e gli stessi siti di Internet Explorer 11 in uso oggi potranno essere aperti in Microsoft Edge in modalità Internet Explorer. 
            [Per altre informazioni, vedere](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

Abbiamo creato la modalità Internet Explorer (IE) in Microsoft Edge per le organizzazioni che necessitano ancora di Internet Explorer 11 per garantire la compatibilità con i siti Web esistenti, ma a cui occorre anche un browser moderno. Questa funzionalità rende più semplice per le organizzazioni l'utilizzo di un browser per il Web e le app legacy o per il Web e le app moderni. Questo articolo fornisce un'introduzione all'uso di Microsoft Edge con la modalità IE.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="what-is-ie-mode"></a>Che cos'è la modalità IE?

La modalità IE su Microsoft Edge semplifica l'utilizzo di tutti i siti necessari all'organizzazione in un singolo browser. Utilizza il motore Chromium integrato per i siti moderni e utilizza il motore Trident MSHTML di Internet Explorer 11 (IE11) per i siti legacy.

Quando un sito viene caricato in modalità Internet Explorer, l'indicatore del logo IE viene visualizzato sul lato sinistro della barra di spostamento. Fare clic sull'indicatore del logo IE per visualizzare informazioni aggiuntive, come mostrato di seguito:

  ![Indicatore del logo IE](./media/ie-mode/ie-logo-indicator1.png)

Solo i siti configurati specificatamente (tramite criteri) utilizzeranno la modalità IE, tutti gli altri siti verranno visualizzati come siti Web moderni. Per utilizzare la modalità IE per un sito, è necessario:

- elencare il sito nell'XML dell'elenco dei siti in modalità Enterprise definito in uno di questi criteri:
  - Microsoft Edge 78 o versione successiva, "Configura elenco siti modalità Enterprise"
  - Internet Explorer, "Usa elenco siti Web di Internet Explorer modalità Enterprise"
  > [!NOTE]
  > Viene elaborato solo un elenco di siti in modalità Enterprise. I criteri dell'elenco dei siti di Microsoft Edge hanno la precedenza su criteri dell'elenco dei siti di Internet Explorer.
- Configura i Criteri di gruppo **Invia tutti i siti Intranet a Internet Explorer** e impostali su **Abilitati** (Microsoft Edge 77 o versione successiva)

### <a name="ie-mode-supports-the-following-internet-explorer-functionality"></a>La modalità Internet Explorer supporta le funzionalità di Internet Explorer seguenti

- Tutte le modalità documento e le modalità Enterprise.
- Controlli ActiveX (ad esempio Java o Silverlight). 
            **Nota:** Silverlight raggiungerà [la fine del supporto](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788) il 12 ottobre 2021. 
- Oggetti browser helper 
- Impostazioni di Internet Explorer e criteri di gruppo che influiscono sulle impostazioni dell'area di sicurezza e sulla modalità protetta
- Strumenti di sviluppo F12 per IE, quando vengono avviati con [IEChooser](/deployedge/edge-ie-mode-faq#how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge-)
- Le estensioni Microsoft Edge che interagiscono direttamente con i contenuti della pagina di Internet Explorer non sono supportate.

### <a name="ie-mode-doesnt-support-the-following-internet-explorer-functionality"></a>La modalità Internet Explorer non supporta le funzionalità di Internet Explorer seguenti

- Barre degli strumenti di Internet Explorer
- Impostazioni e criteri di gruppo di Internet Explorer che controllano il menu di spostamento.
- Strumenti di sviluppo di IE11 o Microsoft Edge F12

## <a name="prerequisites"></a>Prerequisiti

I prerequisiti seguenti si applicano all'uso di Microsoft Edge con la modalità Internet Explorer.

> [!IMPORTANT]
> Per un'esperienza ottimale, installare gli aggiornamenti più recenti per Windows e Microsoft Edge. In caso contrario, è probabile che la modalità IE non funzioni.

1. Gli aggiornamenti minimi del sistema per i sistemi operativi sono elencati nella tabella seguente.

 | Sistema operativo | Versione       | Aggiornamenti |
 |------------------|---------------|---------|
 | Windows 10       | 1909 o versione successiva |         |
 | Windows 10       | 1903          | 
            [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) o versione successiva |
 | Windows Server   | 1903          | 
            [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) o versione successiva |
 | Windows 10       | 1809          | 
            [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) o versione successiva |
 | Windows Server   | 1809          | 
            [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) o versione successiva |
 | Windows Server   | 2019          | 
            [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) o versione successiva |
 | Windows 10       | 1803          | 
            [KB4512509](https://support.microsoft.com/help/4512509/windows-10-update-kb4512509) o versione successiva |
 | Windows 10       | 1709          | 
            [KB4512494](https://support.microsoft.com/help/4512494/windows-10-update-kb4512494) o versione successiva |
 | Windows 10       | 1607          | 
            [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) o versione successiva |
 | Windows Server   | 2016          | 
            [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) o versione successiva |
 | Windows 10       | versione iniziale, luglio 2015 | 
            [KB4520011](https://support.microsoft.com/help/4520011/windows-10-update-kb4520011) o versione successiva |
 | Windows 8       | 8.1              | 
            [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows Server   | 2012 R2       | 
            [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows 8  | Incorporato            | Installare [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) per eseguire l'aggiornamento a Internet Explorer 11, quindi installare [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows Server   | 2012           | Installare [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) per eseguire l'aggiornamento a Internet Explorer 11, quindi installare [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows 7        |  SP1**        | 
            [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows Server   |  2008 R2**    | 
            [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
  > [!IMPORTANT]
  > * * Windows 7 and Windows Server 2008 R2 saranno supportati da Microsoft Edge anche dopo la fine del supporto per tali sistemi operativi. Per consentire il supporto della modalità Internet Explorer in questi sistemi operativi, i dispositivi dovranno disporre degli [aggiornamenti della sicurezza estesa per Windows 7](https://support.microsoft.com/help/4527878/faq-about-extended-security-updates-for-windows-7). È consigliabile eseguire l'aggiornamento a un sistema operativo supportato appena possibile per mantenere la protezione. Il supporto di Microsoft Edge con gli aggiornamenti della sicurezza estesa deve essere considerato un bridge temporaneo per passare a uno stato supportato del sistema operativo.

2. Il modello amministrativo di Microsoft Edge. Per altre informazioni, vedi [Configurare Microsoft Edge](./configure-microsoft-edge.md).
3. Internet Explorer 11 abilitato nelle funzionalità di Windows.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
