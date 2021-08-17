---
title: Microsoft Edge e Accesso condizionale
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge e Accesso condizionale
ms.openlocfilehash: 56d593809d9c14a6ecfe58ef67745de78eeba452
ms.sourcegitcommit: a1d30ff66c448db4fd9fdb59ea439c0b0908b1c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "11894129"
---
# <a name="microsoft-edge-and-conditional-access"></a>Microsoft Edge e Accesso condizionale
  
Questo articolo descrive in che modo Microsoft Edge supporta l'accesso condizionale e come accedere alle risorse protette dall'accesso condizionale.

> [!NOTE]
> Questo articolo si applica a Microsoft Edge versione 77 o successiva.

Un aspetto fondamentale della sicurezza del cloud è il controllo delle identità e dell'accesso in relazione alla gestione delle risorse cloud. In un ambiente orientato alla mobilità e al cloud, gli utenti possono accedere alle risorse dell'organizzazione usando un'ampia gamma di dispositivi e app praticamente ovunque. Di conseguenza, concentrarsi solo su chi può accedere a una risorsa non è sufficiente. Devi anche esaminare la modalità di accesso a una risorsa. L'accesso condizionale di Azure Active Directory (Azure AD) consente di bilanciare la sicurezza e la produttività.

## <a name="accessing-conditional-access-protected-resources-in-microsoft-edge"></a>Accesso alle risorse protette con accesso condizionale in Microsoft Edge

Microsoft Edge supporta in modo nativo l'accesso condizionale di Azure AD. Non è necessario installare un'estensione separata. Quando si accede a un profilo Microsoft Edge con le credenziali Azure AD aziendali, Microsoft Edge consente di accedere in modo semplice alle risorse cloud aziendali protette con l'accesso condizionale.

In un dispositivo conforme, l'identità che accede alla risorsa deve corrispondere all'identità del profilo.  In caso contrario, viene visualizzato un messaggio come quello nella schermata successiva. Nella schermata di esempio, "testadmin@evostsoneboxtest.com" è l'account di accesso necessario per accedere alla risorsa.

![Messaggio di accesso condizionale nel browser](./media/edge-security/microsoft-edge-security-conditional-access.png)

Per continuare, devi passare al profilo richiesto (se ne hai uno) o creare un profilo con identità corrispondente.

Per accedere e usare il tuo profilo, fai clic sull'immagine dell'account nell'angolo superiore destro del browser. Puoi usare il menu a discesa per:

- Selezionare un altro profilo Fare clic sul nome del profilo.
- Creare un profilo. Fai clic su **Aggiungi un profilo**.
- Gestire i tuoi profili. Fai clic su **Gestisci impostazioni del profilo**.

Questo supporto è disponibile in tutte le piattaforme, incluse tutte le versioni supportate di Windows e macOS.

### <a name="how-to-deploy-conditional-access-in-azure-active-directory"></a>Come distribuire l'accesso condizionale in Azure Active Directory

L'articolo [Distribuire l'accesso condizionale](/azure/active-directory/conditional-access/plan-conditional-access) fornisce una guida dettagliata per distribuire l'accesso condizionale in Azure Active Directory.

## <a name="see-also"></a>Vedere anche

- [Pagina di destinazione di Microsoft Edge in modalità Enterprise](https://aka.ms/EdgeEnterprise)
- [Video: sicurezza, compatibilità e gestibilità](/deployedge/microsoft-edge-video-security-compatibility-manageability)