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
# <span data-ttu-id="03c37-103">Microsoft Edge nel tuo ambiente</span><span class="sxs-lookup"><span data-stu-id="03c37-103">Microsoft Edge in your environment</span></span>

<span data-ttu-id="03c37-104">Questo articolo descrive come prepararsi a implementare Microsoft Edge quandola versione legacy di Microsoft Edge raggiunge la fine del suo servizio.</span><span class="sxs-lookup"><span data-stu-id="03c37-104">This article describes how to prepare to deploy Microsoft Edge when Microsoft Edge Legacy reaches its end of service.</span></span>

<span data-ttu-id="03c37-105">Come da [post del blog](https://aka.ms/EdgeLegacyEOS) di Microsoft Edge Product Team, il supporto per l'applicazione desktop Microsoft Edge Legacy terminerà il 9 marzo 2021.</span><span class="sxs-lookup"><span data-stu-id="03c37-105">As per the Microsoft Edge Product Team’s [blog post](https://aka.ms/EdgeLegacyEOS), support for the Microsoft Edge Legacy desktop application will end on March 9, 2021.</span></span> <span data-ttu-id="03c37-106">Quando applichi la versione Update Tuesday (o "B") di aprile, si rimuoverà la versione legacy di Microsoft Edge dai dispositivi con Windows 10 RS4 attraverso 20H1 e lo sostituirà con Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="03c37-106">When you apply the Update Tuesday (or "B") release in April, it will remove Microsoft Edge Legacy from devices running Windows 10 RS4 through 20H1 and replace it with Microsoft Edge.</span></span>

## <span data-ttu-id="03c37-107">Come prepararsi</span><span class="sxs-lookup"><span data-stu-id="03c37-107">How to Prepare</span></span>

<span data-ttu-id="03c37-108">Per preparare l'installazione di Microsoft Edge nei dispositivi Windows 10 RS4-20H1 con la versione Update Tuesday di aprile, consigliamo leggere [Pianificare l’implementazione di Microsoft Edge](deploy-edge-plan-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="03c37-108">To prepare for Microsoft Edge being installed on Windows 10 RS4 through 20H1 devices with the Update Tuesday release in April, we recommend reading [Plan your deployment of Microsoft Edge](deploy-edge-plan-deployment.md).</span></span>

<span data-ttu-id="03c37-109">Dopo aver pianificato la tua distribuzione, usa uno dei seguenti approcci per prepararti a distribuire Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="03c37-109">After you plan your deployment, use one of the following approaches to prepare to deploy Microsoft Edge.</span></span>

- <span data-ttu-id="03c37-110">**Installare i criteri di gruppo per personalizzare l'approccio di aggiornamento di Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="03c37-110">**Install group policies to customize your Microsoft Edge update approach**.</span></span> <span data-ttu-id="03c37-111">Per ulteriori informazioni, consulta [Configurare le impostazioni dei criteri di Microsoft Edge su Windows](configure-microsoft-edge.md), e presta particolare attenzione al materiale di [riferimento di Update Policy](microsoft-edge-update-policies.md).</span><span class="sxs-lookup"><span data-stu-id="03c37-111">For more information, see [Configure Microsoft Edge policy settings on Windows](configure-microsoft-edge.md), and pay special attention to the [Update Policy reference](microsoft-edge-update-policies.md) material.</span></span> <span data-ttu-id="03c37-112">Se installi i criteri di gruppo per gestire gli aggiornamenti prima di installare la versione Update Tuesday di aprile, Microsoft Edge inizierà immediatamente a rispettare i tuoi criteri.</span><span class="sxs-lookup"><span data-stu-id="03c37-112">If you install group policies to manage your updates before installing April’s Update Tuesday release, Microsoft Edge will immediately start respecting your policy.</span></span> <span data-ttu-id="03c37-113">Se non c'è alcun criterio di gruppo installato, Microsoft Edge si aggiornerà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="03c37-113">If there isn't any installed group policy, Microsoft Edge will automatically update itself.</span></span>

- <span data-ttu-id="03c37-114">**Rimuovere l'applicazione desktop della versione legacy di Microsoft Edge prima della sua data di fine servizio del 9 marzo 2021 e distribuire Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="03c37-114">**Remove the Microsoft Edge Legacy desktop application before its end of service date of March 9, 2021 and deploy Microsoft Edge**.</span></span> <span data-ttu-id="03c37-115">Per Windows 10 RS4 fino a 20H1, potete farlo usando Windows Updates.</span><span class="sxs-lookup"><span data-stu-id="03c37-115">For Windows 10 RS4 through 20H1, you can do this by using Windows Updates.</span></span> <span data-ttu-id="03c37-116">Per altre informazioni, consulta [Distribuire Microsoft Edge con gli aggiornamenti di Windows 10](deploy-edge-with-windows-10-updates.md).</span><span class="sxs-lookup"><span data-stu-id="03c37-116">For more information, see [Deploy Microsoft Edge with Windows 10 updates](deploy-edge-with-windows-10-updates.md).</span></span>

## <span data-ttu-id="03c37-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03c37-117">See also</span></span>

- [<span data-ttu-id="03c37-118">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="03c37-118">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="03c37-119">Pianificare la distribuzione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="03c37-119">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)