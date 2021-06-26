---
title: Supporto della piattaforma per le funzionalità di Microsoft Edge
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/25/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Riepilogo del supporto della piattaforma per le funzionalità di Microsoft Edge
ms.openlocfilehash: 3fb4fc0bc2671bdee5055fa650f191c5d3821963
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617726"
---
# <a name="platform-support-for-microsoft-edge-features"></a>Supporto della piattaforma per le funzionalità di Microsoft Edge

In questo articolo viene riepilogato il supporto della piattaforma per le funzionalità di Microsoft Edge.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

## <a name="feature-matrix-for-platforms"></a>Matrice di funzionalità per le piattaforme

Le tabelle seguenti riepilogano il supporto delle funzionalità per le piattaforme Windows e macOS.

> [!NOTE]
> Android e iOS non sono attualmente rappresentati nelle tabelle di supporto, ma stiamo continuando a lavorare su queste informazioni e le piattaforme relative verranno aggiornate di conseguenza.

| Funzionalità di sicurezza |Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|Accesso condizionale ad Azure Active Directory (Azure AD)|Sì|Sì|Sì|Sì|[Accesso condizionale di Azure AD](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)|
|Microsoft Defender Application Guard|Sì (1890+)|No|No|No|[Microsoft Defender Application Guard](/deployedge/microsoft-edge-security-windows-defender-application-guard) |
|Microsoft Defender SmartScreen|Sì|Sì|Sì|Sì|[Microsoft Defender SmartScreen](/deployedge/microsoft-edge-security-smartscreen) |
|Microsoft Endpoint DLP|Sì|No|No|No|[Microsoft Endpoint DLP](/deployedge/microsoft-edge-security-dlp#microsoft-endpoint-data-loss-prevention-endpoint-dlp)|
|Monitoraggio password|Sì|Sì|Sì|Sì|[Monitoraggio password](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|Generatore di password|Sì|Sì|Sì|Sì|[Generatore di password](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|Windows Information Protection (WIP)|Sì (1607+)|No|No|No|[WiP](/deployedge/microsoft-edge-security-windows-information-protection#system-requirements)|

|Funzionalità di identità| Win 10 | Win 8.1 | Win 7 | macOS | URL |
|--|--|--|--|--|--|
|Accesso automatico (ibrido/AAD-J)|Sì|Sì|Sì|No|[ibrido/AAD-J](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|Accesso automatico (aggiunto a un dominio)|Sì|Sì|Sì|No|[dominio aggiunto](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|Accesso automatico (l'account predefinito del sistema operativo è MSA)|Sì (1709+)|No|No|No|[MSA](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|Single Sign-On da browser a Web (SSO)|Sì|Sì|Sì|Sì|[Browser-Web SSO](https://www.microsoft.com/microsoft-365/roadmap?featureid=66332)|
|Commutatore guidato/"Cambio automatico del profilo"|Sì|Sì|Sì|Sì|[Utilizzo di più profili sul lavoro e a casa](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|Più profili|Sì|Sì|Sì|Sì|[Utilizzo di più profili sul lavoro e a casa](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|Sincronizzazione locale per Active Directory (AD)|Sì|Sì|Sì|No|[Sincronizzazione locale per gli utenti di Active Directory (AD)](/deployedge/microsoft-edge-on-premises-sync) |
|Accesso SSO facile|Sì (1709+)|Sì|Sì|Sì|[Accesso SSO facile](/deployedge/microsoft-edge-security-identity#seamless-sso)|
|SSO con token di aggiornamento primario|Sì (1709+)|Sì|Sì|No|[SSO con PRT](/deployedge/microsoft-edge-security-identity#sso-with-primary-refresh-token-prt)|
|Autenticazione integrata di Windows|Sì|Sì|Sì|Sì* (Criterio obbligatorio)|[WIA](/deployedge/microsoft-edge-security-identity#windows-integrated-authentication-wia)|

|Funzionalità aggiuntive|Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|Raccolte|Sì|Sì|Sì|Sì|[Raccolte](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/) |
|Pagina Nuova scheda per utenti Enterprise|Sì|Sì|Sì|Sì|[Pagina Nuova scheda](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/) |
|Modalità IE|Sì|Sì|Sì|No|[Modalità IE](/deployedge/edge-ie-mode#prerequisites)|
|Modalità tutto schermo|Sì|No|No|No|[Modalità tutto schermo](/deployedge/microsoft-edge-configure-kiosk-mode)|
|Microsoft Search in Bing|Sì|Sì|Sì|Sì|[Ricerca intelligente in Bing](https://www.microsoft.com/edge/business/intelligent-search-with-bing) |
|Lettore PDF|Sì|Sì|Sì|Sì|[Lettore PDF](/deployedge/microsoft-edge-pdf) |
|Shopping|Sì|Sì|Sì|Sì|[Shopping](https://techcommunity.microsoft.com/t5/articles/introducing-shopping-with-microsoft-edge/m-p/1870080) |
|Schede in sospensione|Sì|Sì|Sì|Sì|[Panoramica delle funzionalità](/deployedge/microsoft-edge-relnote-stable-channel)<br>[Post di blog più recente](https://blogs.windows.com/msedgedev/2021/03/04/edge-89-performance/)<br>[Criteri di gruppo](/deployedge/microsoft-edge-policies#sleeping-tabs-settings)|
|Sincronizzazione|Sì|Sì|Sì|Sì| [Sincronizzazione in Enterprise](/deployedge/microsoft-edge-enterprise-sync) |
|Rollback versione|Sì|Sì|Sì|No|[Rollback versione](/deployedge/edge-learnmore-rollback) |
|Schede verticali|Sì|Sì|Sì|Sì| |

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)