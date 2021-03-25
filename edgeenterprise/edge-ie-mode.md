---
title: Informazioni sulla modalità IE
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 03/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Scopri come usare Microsoft Edge in modalità Internet Explorer.
ms.openlocfilehash: ecb4bffc5afdde3a8891d1eaa6e28508205ab097
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447340"
---
# <a name="about-ie-mode"></a>Informazioni sulla modalità IE

Questo articolo include una panoramica e i prerequisiti per l'uso di Microsoft Edge con la modalità IE.

> [!NOTE]
> Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.

## <a name="what-is-ie-mode"></a>Che cos'è la modalità Internet Explorer?

La modalità IE su Microsoft Edge semplifica l'utilizzo di tutti i siti necessari all'organizzazione in un singolo browser. Utilizza il motore Chromium integrato per i siti moderni e utilizza il motore Trident MSHTML di Internet Explorer 11 (IE11) per i siti legacy.

Quando un sito viene caricato in modalità Internet Explorer, l'indicatore del logo IE viene visualizzato sul lato sinistro della barra di spostamento. Fare clic sull'indicatore del logo IE per visualizzare informazioni aggiuntive, come mostrato di seguito:

  ![Indicatore del logo IE](./media/ie-mode/ie-logo-indicator1.png)

Solo i siti configurati specificatamente (tramite criteri) utilizzeranno la modalità IE, tutti gli altri siti verranno visualizzati come siti Web moderni. Per utilizzare la modalità IE per un sito, è necessario:

- Elencare il sito nell'XML dell'elenco dei siti in modalità Enterprise definito in uno di questi criteri:
  - Microsoft Edge 78 o versione successiva, "Configura elenco siti modalità Enterprise"
  - Internet Explorer, "Usa elenco siti Web di Internet Explorer modalità Enterprise"
  > [!NOTE]
  > Viene elaborato solo un elenco di siti in modalità Enterprise. I criteri dell'elenco dei siti di Microsoft Edge hanno la precedenza su criteri dell'elenco dei siti di Internet Explorer.
- Tutti i siti Intranet quando i criteri di gruppo **Invia tutti i siti Intranet a Internet Explorer** sono abilitati (Microsoft Edge 77 o versione successiva).

### <a name="ie-mode-supports-the-following-internet-explorer-functionality"></a>La modalità Internet Explorer supporta le funzionalità di Internet Explorer seguenti

- Tutte le modalità documento e le modalità Enterprise.
- Controlli ActiveX, come Java o Silverlight
- Oggetti browser helper 
- Impostazioni e Criteri di gruppo di Internet Explorer che influiscono sulle impostazioni dell'area di sicurezza e sulla modalità protetta
- Gli strumenti di sviluppo F12 per IE, all'avvio con [IEChooser](/office/dev/add-ins/testing/debug-add-ins-using-f12-developer-tools-on-windows-10)
- Le estensioni Microsoft Edge che interagiscono con i contenuti della pagina di Internet Explorer direttamente non sono supportate.

### <a name="ie-mode-doesnt-support-the-following-internet-explorer-functionality"></a>La modalità Internet Explorer non supporta le funzionalità di Internet Explorer seguenti

- Barre degli strumenti di Internet Explorer
- Impostazioni e Criteri di gruppo di Internet Explorer che interessano il menu di spostamento (ad esempio motori di ricerca e home page)
- Strumenti di sviluppo di IE11 o Microsoft Edge F12

## <a name="prerequisites"></a>Prerequisiti

I prerequisiti seguenti si applicano all'uso di Microsoft Edge con la modalità Internet Explorer.

> [!IMPORTANT]
> Per un'esperienza ottimale, installare gli aggiornamenti più recenti per Windows e Microsoft Edge. In caso contrario, è probabile che la modalità IE non funzioni.

1. Gli aggiornamenti minimi del sistema per i sistemi operativi sono elencati nella tabella seguente.

 | Sistema operativo | Versione       | Aggiornamenti |
 |------------------|---------------|---------|
 | Windows10       | 1909 o versione successiva |         |
 | Windows10       | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) o versione successiva |
 | Windows Server   | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) o versione successiva |
 | Windows10       | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) o versione successiva |
 | Windows Server   | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) o versione successiva |
 | Windows Server   | 2019          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) o versione successiva |
 | Windows10       | 1803          | [KB4512509](https://support.microsoft.com/help/4512509/windows-10-update-kb4512509) o versione successiva |
 | Windows10       | 1709          | [KB4512494](https://support.microsoft.com/help/4512494/windows-10-update-kb4512494) o versione successiva |
 | Windows10       | 1607          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) o versione successiva |
 | Windows Server   | 2016          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) o versione successiva |
 | Windows10       | versione iniziale, luglio 2015 | [KB4520011](https://support.microsoft.com/help/4520011/windows-10-update-kb4520011) o versione successiva |
 | Windows 8       | 8.1              | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows Server   | 2012 R2       | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows 8  | Incorporato            | Installare [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) per eseguire l'aggiornamento a Internet Explorer 11, quindi installare [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows Server   | 2012           | Installare [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) per eseguire l'aggiornamento a Internet Explorer 11, quindi installare [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows 7        |  SP1**        | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
 | Windows Server   |  2008 R2**    | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) o versione successiva oppure [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) o versione successiva |
  > [!IMPORTANT]
  > * * Windows 7 and Windows Server 2008 R2 saranno supportati da Microsoft Edge anche dopo la fine del supporto per tali sistemi operativi. Per consentire il supporto della modalità Internet Explorer in questi sistemi operativi, i dispositivi dovranno disporre degli [aggiornamenti della sicurezza estesa per Windows 7](https://support.microsoft.com/help/4527878/faq-about-extended-security-updates-for-windows-7). È consigliabile eseguire l'aggiornamento a un sistema operativo supportato appena possibile per mantenere la protezione. Il supporto di Microsoft Edge con gli aggiornamenti della sicurezza estesa deve essere considerato un bridge temporaneo per passare a uno stato supportato del sistema operativo.

2. Il modello amministrativo di Microsoft Edge. Per altre informazioni, vedi [Configurare Microsoft Edge](./configure-microsoft-edge.md).
3. Internet Explorer 11 abilitato nelle funzionalità di Windows.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Informazioni aggiuntive sulla modalità Enterprise](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)