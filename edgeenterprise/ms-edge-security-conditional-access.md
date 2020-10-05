---
title: Microsoft Edge e Accesso condizionale
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 10/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge e Accesso condizionale
ms.openlocfilehash: a81d39c15f418dab6565ee7acc45de17f66e3828
ms.sourcegitcommit: 3478cfcf2b03944213a7c7c61f05490bc37aa7c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "11094775"
---
# Microsoft Edge e Accesso condizionale
  
Questo articolo descrive in che modo Microsoft Edge supporta l'accesso condizionale e come accedere alle risorse protette dall'accesso condizionale.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

Un aspetto fondamentale della sicurezza del cloud è il controllo delle identità e dell'accesso in relazione alla gestione delle risorse cloud. In un ambiente orientato alla mobilità e al cloud, gli utenti possono accedere alle risorse dell'organizzazione usando un'ampia gamma di dispositivi e app praticamente ovunque. Di conseguenza, concentrarsi solo su chi può accedere a una risorsa non è sufficiente. Devi anche esaminare la modalità di accesso a una risorsa. L'accesso condizionale di Azure Active Directory (Azure AD) consente di bilanciare la sicurezza e la produttività.

## Accesso alle risorse protette con accesso condizionale in Microsoft Edge

Microsoft Edge supporta in modo nativo l'accesso condizionale di Azure AD. Non è necessario installare un'estensione separata. Quando si accede a un profilo Microsoft Edge con le credenziali Azure AD aziendali, Microsoft Edge consente di accedere in modo semplice alle risorse cloud aziendali protette con l'accesso condizionale.

In un dispositivo conforme, l'identità che accede alla risorsa deve corrispondere all'identità del profilo.  In caso contrario, viene visualizzato un messaggio come quello nella schermata successiva. Nella schermata di esempio, "testadmin@evostsoneboxtest.com" è l'account di accesso necessario per accedere alla risorsa.

![Messaggio di accesso condizionale nel browser](./media/edge-security/microsoft-edge-security-conditional-access.png)

Per continuare, devi passare al profilo richiesto (se ne hai uno) o creare un profilo con identità corrispondente.

Per accedere e usare il tuo profilo, fai clic sull'immagine dell'account nell'angolo superiore destro del browser. Puoi usare il menu a discesa per:

- Selezionare un altro profilo Fare clic sul nome del profilo.
- Creare un profilo. Fai clic su **Aggiungi un profilo**.
- Gestire i tuoi profili. Fai clic su **Gestisci impostazioni del profilo**.

Questo supporto è disponibile in tutte le piattaforme, incluse tutte le versioni supportate di Windows e macOS.

### Come distribuire l'accesso condizionale in Azure Active Directory

L'articolo [Distribuire l'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) fornisce una guida dettagliata per distribuire l'accesso condizionale in Azure Active Directory.

## Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: sicurezza, compatibilità e gestibilità](/microsoft-edge-video-security-compatibility-manageability.md)
