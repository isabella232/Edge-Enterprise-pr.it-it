---
title: Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge all’interno della grande impresa
ms.openlocfilehash: dad239a448ec1f0ebef60c7072bfaad5c3baed57
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641372"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a><span data-ttu-id="f14f3-103">Usare i criteri di gruppo per gestire le impostazioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f14f3-103">Use group policies to manage Microsoft Edge extensions</span></span>

<span data-ttu-id="f14f3-104">In questo articolo vengono descritte le opzioni e i passaggi per la gestione delle estensioni tramite criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f14f3-104">This article describes the options and steps for managing extensions by using group policies.</span></span> <span data-ttu-id="f14f3-105">Queste opzioni presuppongono che si abbia già gestito Microsoft Edge per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f14f3-105">These options  assume that you already have Microsoft Edge managed for your users.</span></span> <span data-ttu-id="f14f3-106">Se Microsoft Edge non è statp già gestito per gli utenti, seguire il collegamento seguente.</span><span class="sxs-lookup"><span data-stu-id="f14f3-106">If you have not already set up Microsoft Edge to be managed for your users please follow the below link to do so now.</span></span>

- [<span data-ttu-id="f14f3-107">Gestire le estensioni di Microsoft Edge nella grande impresa</span><span class="sxs-lookup"><span data-stu-id="f14f3-107">Manage Microsoft Edge extensions in the enterprise</span></span>](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> <span data-ttu-id="f14f3-108">L’articolo riguarda Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="f14f3-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="block-extensions-based-on-their-permissions"></a><span data-ttu-id="f14f3-109">Bloccare le estensioni a seconda delle relative autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f14f3-109">Block extensions based on their permissions</span></span>

<span data-ttu-id="f14f3-110">È possibile controllare le estensioni che gli utenti possono installare a seconda delle autorizzazioni tramite il criterio [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings).</span><span class="sxs-lookup"><span data-stu-id="f14f3-110">You can control what extensions your users can install based on permissions using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span> <span data-ttu-id="f14f3-111">Un'estensione installata non verrà eseguita se necessita di un'autorizzazione bloccata.</span><span class="sxs-lookup"><span data-stu-id="f14f3-111">If an installed extension needs a permission that’s blocked, it just won't run.</span></span> <span data-ttu-id="f14f3-112">L'estensione non viene rimossa, ma solo disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f14f3-112">The extension isn't removed, just disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="f14f3-113">Le impostazioni relative alle autorizzazioni bloccate possono essere configurate solo tramite il criterio Impostazioni estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-113">The blocked permissions setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="f14f3-114">Utilizzare i passaggi seguenti come riferimento per bloccare un’estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-114">Use the following steps as a guide for blocking an extension.</span></span>

1. <span data-ttu-id="f14f3-115">Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**,  quindi selezionare **Configura impostazioni di gestione delle estensioni**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-115">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**  and then select **Configure extension management settings**.</span></span>
2. <span data-ttu-id="f14f3-116">Abilitare il criterio, quindi specificare le autorizzazioni che si desidera consentire o bloccare utilizzando una stringa JSON che andrà compressa.</span><span class="sxs-lookup"><span data-stu-id="f14f3-116">Enable the policy, then enter the permissions that you want allowed or blocked, by using a JSON string that gets compressed.</span></span> <span data-ttu-id="f14f3-117">La schermata successiva mostra come bloccare un'estensione che utilizza l'autorizzazione "USB".</span><span class="sxs-lookup"><span data-stu-id="f14f3-117">The next screenshot shows how to block an extension that uses the permission "usb".</span></span>

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="Configurare i criteri di gruppo per bloccare un'estensione.":::

<span data-ttu-id="f14f3-119">L'esempio seguente mostra l’utilizzo di JSON per bloccare qualsiasi estensione che richiede l'uso dell'autorizzazione "USB" e della relativa stringa compressa.</span><span class="sxs-lookup"><span data-stu-id="f14f3-119">The following example shows the JSON to block any extension that needs the use of permission "usb" and its compressed string.</span></span>

### <a name="json-example"></a><span data-ttu-id="f14f3-120">Esempio di JSON</span><span class="sxs-lookup"><span data-stu-id="f14f3-120">JSON example</span></span>

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > <span data-ttu-id="f14f3-121">Per bloccare tutte le estensioni che utilizzano l'autorizzazione, utilizzare un asterisco per l'ID di estensione, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="f14f3-121">To block all extensions that use the permission, use an asterisk for the extension ID, as shown in the previous example.</span></span> <span data-ttu-id="f14f3-122">Se si specifica un ID di estensione, il criterio verrà applicato solo a tale estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-122">If you specify one extension ID, the policy will only apply to that extension.</span></span> <span data-ttu-id="f14f3-123">È possibile bloccare più di un’estensione, ma queste devono essere voci separate.</span><span class="sxs-lookup"><span data-stu-id="f14f3-123">You can block more than one, but they need to be separate entries.</span></span>

## <a name="prevent-extensions-from-altering-web-pages"></a><span data-ttu-id="f14f3-124">Impedire alle estensioni di modificare le pagine Web</span><span class="sxs-lookup"><span data-stu-id="f14f3-124">Prevent extensions from altering web pages</span></span>

<span data-ttu-id="f14f3-125">Questa impostazione impedisce alle estensioni di leggere e modificare i dati sensibili di siti Web e domini.</span><span class="sxs-lookup"><span data-stu-id="f14f3-125">This setting prevents extensions from reading and changing  data from sensitive websites and domains.</span></span> <span data-ttu-id="f14f3-126">Il blocco delle azioni indesiderate viene eseguito bloccando azioni quali l'inserimento di script nei siti Web, la lettura dei cookie o la modifica delle richieste Web.</span><span class="sxs-lookup"><span data-stu-id="f14f3-126">Blocking unwanted actions is done by blocking actions such as script injection into your websites, reading the cookies, or making web-request modifications.</span></span> <span data-ttu-id="f14f3-127">Questa impostazione non impedisce agli utenti di installare o rimuovere estensioni, ma impedisce alle estensioni di modificare i siti Web specificati.</span><span class="sxs-lookup"><span data-stu-id="f14f3-127">This setting doesn’t prevent your users from installing or removing extensions, it only prevents extensions from altering the specified websites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f14f3-128">Le impostazioni agli host di runtime consenti/bloccati bloccate possono essere configurate solo tramite il criterio Impostazioni estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-128">The Runtime allowed/blocked hosts setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="f14f3-129">È possibile configurare le impostazioni seguenti tramite il criterio ExtensionSettings per impedire (o consentire) di apportare modifiche a siti Web o domini:</span><span class="sxs-lookup"><span data-stu-id="f14f3-129">You can configure the following settings in the ExtensionSettings policy to prevent (or allow) alterations of websites or domains:</span></span>

- <span data-ttu-id="f14f3-130">**Runtime_blocked_hosts**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-130">**Runtime_blocked_hosts**.</span></span> <span data-ttu-id="f14f3-131">Questa impostazione impedisce alle estensioni di apportare modifiche o leggere i dati dei siti Web specificati.</span><span class="sxs-lookup"><span data-stu-id="f14f3-131">This setting blocks extensions from making changes or reading data from the websites you specify.</span></span>
- <span data-ttu-id="f14f3-132">**Runtime_allowed_hosts**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-132">**Runtime_allowed_hosts**.</span></span> <span data-ttu-id="f14f3-133">Questa impostazione consente alle estensioni di apportare modifiche o leggere i dati dei siti Web specificati.</span><span class="sxs-lookup"><span data-stu-id="f14f3-133">This setting allows extensions to make changes or read data from the websites you specify.</span></span> <span data-ttu-id="f14f3-134">Il formato seguente viene usato per specificare i siti nella stringa JSON all’interno del criterio:</span><span class="sxs-lookup"><span data-stu-id="f14f3-134">The following format is used for specifying your site(s) in the JSON string in the policy:</span></span>

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` <span data-ttu-id="f14f3-135">le sezioni sono obbligatorie, ma la sezione `[subdomain|*]` è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f14f3-135">sections are required, but `[subdomain|*]` section is optional.</span></span>

<span data-ttu-id="f14f3-136">La tabella seguente mostra esempi di modelli host e di corrispondenza validi.</span><span class="sxs-lookup"><span data-stu-id="f14f3-136">The following table shows examples of valid host patterns and matching patterns.</span></span>

|<span data-ttu-id="f14f3-137">Modelli host validi</span><span class="sxs-lookup"><span data-stu-id="f14f3-137">Valid host patterns</span></span>|<span data-ttu-id="f14f3-138">Corrisponde</span><span class="sxs-lookup"><span data-stu-id="f14f3-138">Matches</span></span>|<span data-ttu-id="f14f3-139">Non corrisponde</span><span class="sxs-lookup"><span data-stu-id="f14f3-139">Doesn't match</span></span>|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | <span data-ttu-id="f14f3-140">Tutti gli URL</span><span class="sxs-lookup"><span data-stu-id="f14f3-140">All URLs</span></span>  |   |

<span data-ttu-id="f14f3-141">Utilizzare i passaggi seguenti come riferimento per bloccare o consentire alle estensioni di accedere a un sito Web o a un dominio.</span><span class="sxs-lookup"><span data-stu-id="f14f3-141">Use the following steps as a guide to block or allow extensions to access a website or domain.</span></span>

1. <span data-ttu-id="f14f3-142">Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Configura impostazioni di gestione delle estensioni**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-142">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**, and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="f14f3-143">Abilitare il criterio, quindi specificare le autorizzazioni che si desidera consentire o bloccare comprimendole a una singola stringa JSON.</span><span class="sxs-lookup"><span data-stu-id="f14f3-143">Enable the policy, then enter the permissions that you want allowed or blocked, compressing the permissions to a single JSON string.</span></span>

<span data-ttu-id="f14f3-144">Gli esempi seguenti mostrano come bloccare le estensioni su un nome host e uno stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="f14f3-144">The following examples show how to block extensions on a hostname and how to block extensions on the same domain.</span></span>

### <a name="json-example-to-block-hostname"></a><span data-ttu-id="f14f3-145">Esempio di JSON per bloccare il nome host</span><span class="sxs-lookup"><span data-stu-id="f14f3-145">JSON example to block hostname</span></span>

<span data-ttu-id="f14f3-146">Questo esempio mostra la stringa JSON e quella JSON compressa per impedire a qualsiasi estensione di accedere al `www.microsoft.com` nome host.</span><span class="sxs-lookup"><span data-stu-id="f14f3-146">This example shows the JSON and compressed JSON string to block any extension from accessing the `www.microsoft.com` hostname.</span></span>

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> <span data-ttu-id="f14f3-147">Per impedire a tutte le estensioni di accedere alla pagina Web, utilizzare un asterisco per l'ID di estensione, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="f14f3-147">To block all extensions from accessing a webpage, use an asterisk for the extension ID, as shown in the previous example.</span></span>  <span data-ttu-id="f14f3-148">Se si specifica un ID di estensione invece che un asterisco, il criterio verrà applicato solo a tale estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-148">If you specify one extension ID instead of an asterisk, the policy will only apply to that extension.</span></span> <span data-ttu-id="f14f3-149">È possibile bloccare più di un’estensione, ma queste devono essere voci separate.</span><span class="sxs-lookup"><span data-stu-id="f14f3-149">You can block more than one extension, but they need to be separate entries.</span></span>

### <a name="json-example-to-block-extensions-on-same-domain"></a><span data-ttu-id="f14f3-150">Esempio di JSON per bloccare le estensioni per lo stesso dominio</span><span class="sxs-lookup"><span data-stu-id="f14f3-150">JSON example to block extensions on same domain</span></span>

<span data-ttu-id="f14f3-151">Questo esempio mostra la stringa JSON e quella JSON compressa per bloccare l'esecuzione di estensioni specifiche nello stesso dominio, "importantwebsite".</span><span class="sxs-lookup"><span data-stu-id="f14f3-151">This example shows the JSON and compressed JSON string to block specific extensions from running on the same domain, "importantwebsite".</span></span>

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a><span data-ttu-id="f14f3-152">Consentire o bloccare le estensioni nei criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="f14f3-152">Allow or block extensions in group policy</span></span>

<span data-ttu-id="f14f3-153">È possibile usare i criteri [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) e [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) per controllare le estensioni bloccate o consentite.</span><span class="sxs-lookup"><span data-stu-id="f14f3-153">You can use the [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) and [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) policies to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="f14f3-154">Utilizzare i passaggi seguenti come riferimento per consentire tutte le estensioni ad eccezione di quelle che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="f14f3-154">Use the following steps as a guide to allow all extensions except those you want to block.</span></span>

1. <span data-ttu-id="f14f3-155">Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Controlla quali estensioni non è possibile installare**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-155">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Control which extensions cannot be installed**.</span></span>
2. <span data-ttu-id="f14f3-156">Seleziona **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-156">Select **Enabled**.</span></span>
3. <span data-ttu-id="f14f3-157">Fai clic su **Mostra**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-157">Click **Show**.</span></span>
4. <span data-ttu-id="f14f3-158">Immettere l'ID app delle estensioni che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="f14f3-158">Enter the app ID of the extensions that you want to block.</span></span> <span data-ttu-id="f14f3-159">Per aggiungere più ID app, utilizzare una riga separata per ogni ID.</span><span class="sxs-lookup"><span data-stu-id="f14f3-159">When adding multiple app ID’s use a separate row for each ID.</span></span>
5. <span data-ttu-id="f14f3-160">Per bloccare tutte le estensioni, digitare \* _ nel criterio per impedire *\** l'installazione di eventuali estensioni.</span><span class="sxs-lookup"><span data-stu-id="f14f3-160">To block all extensions, type \**\**_ into the policy to prevent any extensions from being installed.</span></span> <span data-ttu-id="f14f3-161">È possibile utilizzare quest’ultimo insieme al criterio "Consenti l'installazione di estensioni specifiche" per consentire solo l'installazione di determinate estensioni.</span><span class="sxs-lookup"><span data-stu-id="f14f3-161">You can use this in conjunction with the "Allow specific extensions to be installed" policy to only allow certain extensions to be installed.</span></span> <span data-ttu-id="f14f3-162">La schermata successiva mostra un'estensione che verrà bloccata in base all'ID app fornito.</span><span class="sxs-lookup"><span data-stu-id="f14f3-162">The next screenshot shows an extension that will be blocked based on the app ID that's provided.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="Usare l'ID app per bloccare un'estensione.":::

   > [!TIP]
   > <span data-ttu-id="f14f3-164">Se non è possibile trovare l'ID app di un'estensione, cercare l'estensione nel sito Web Componenti aggiuntivi di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f14f3-164">If you can’t find the app ID of an extension, look at the extension in the Microsoft Edge Add-ons website.</span></span> <span data-ttu-id="f14f3-165">Trovare l'estensione specifica. L'ID app verrà visualizzato nella parte finale dell'URL nell'omnibox.</span><span class="sxs-lookup"><span data-stu-id="f14f3-165">Find the specific extension and you will see the app ID at the end of the URL in the omnibox.</span></span>

> [!NOTE]
> <span data-ttu-id="f14f3-166">È possibile aggiungere un'estensione già installata sul computer di un utente all'elenco di estensioni bloccate.</span><span class="sxs-lookup"><span data-stu-id="f14f3-166">You can add an extension to the blocklist that’s already installed on a user’s computer.</span></span> <span data-ttu-id="f14f3-167">Ciò disabiliterà l'estensione e impedirà all'utente di riattivarla.</span><span class="sxs-lookup"><span data-stu-id="f14f3-167">This will disable the extension and prevent the user from re-enabling it.</span></span> <span data-ttu-id="f14f3-168">Questa non verrà disinstallata, ma soltanto disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f14f3-168">It won't be uninstalled, just disabled.</span></span>

## <a name="force-install-an-extension"></a><span data-ttu-id="f14f3-169">Forzare l'installazione di un'estensione</span><span class="sxs-lookup"><span data-stu-id="f14f3-169">Force-install an extension</span></span>

<span data-ttu-id="f14f3-170">Usare il criterio [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) per controllare le estensioni bloccate o consentite.</span><span class="sxs-lookup"><span data-stu-id="f14f3-170">Use the [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) policy to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="f14f3-171">Utilizzare i passaggi seguenti come riferimento per forzare l’installazione di un’estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-171">Use the following steps as a guide to force-install an extension.</span></span>

1. <span data-ttu-id="f14f3-172">Nell'Editor Criteri di gruppo, andare a _ Modelli amministrativi *> Microsoft Edge > estensioni >*\* e quindi selezionare Controlla quali estensioni vengono installate in modo **invisibile all'utente.**</span><span class="sxs-lookup"><span data-stu-id="f14f3-172">In the Group Policy Editor, go to _*Administrative Templates> Microsoft Edge >  Extensions >*\* and then select **Control which extensions are installed silently**.</span></span>
2. <span data-ttu-id="f14f3-173">Seleziona **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-173">Select **Enabled**.</span></span>  
3. <span data-ttu-id="f14f3-174">Fai clic su **Mostra**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-174">Click **Show**.</span></span>
4. <span data-ttu-id="f14f3-175">Immettere l'app ID o gli ID dell’estensione o delle estensioni per cui forzare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-175">Enter the app ID or IDs of the extension or extensions you want to force-install.</span></span>  

<span data-ttu-id="f14f3-176">L'estensione verrà installata automaticamente senza necessità di interazione da parte dell’utente.</span><span class="sxs-lookup"><span data-stu-id="f14f3-176">The extension will be installed silently with no need for user interaction.</span></span> <span data-ttu-id="f14f3-177">L'utente non potrà inoltre disinstallare o disabilitare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="f14f3-177">The user also won’t be able to uninstall or disable the extension.</span></span> <span data-ttu-id="f14f3-178">Questa impostazione sovrascriverà i criteri dell'elenco abilitato di estensioni bloccate.</span><span class="sxs-lookup"><span data-stu-id="f14f3-178">This setting will overwrite over any blocklist policy that’s enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="f14f3-179">Per le estensioni ospitate nel Chrome Web Store utilizzare una stringa, come ad esempio: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`.</span><span class="sxs-lookup"><span data-stu-id="f14f3-179">For extensions hosted in the Chrome web store use a string such as: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`.</span></span>

## <a name="block-extensions-from-a-specific-store-or-update-url"></a><span data-ttu-id="f14f3-180">Bloccare le estensioni da uno Store o un URL di aggiornamento specifico</span><span class="sxs-lookup"><span data-stu-id="f14f3-180">Block extensions from a specific store or update URL</span></span>

<span data-ttu-id="f14f3-181">Per bloccare le estensioni di un determinato Store o URL, è sufficiente bloccare *update_url* per tale store utilizzando il criterio [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings).</span><span class="sxs-lookup"><span data-stu-id="f14f3-181">To block extensions from a particular store or URL, you only need to block the *update_url* for that store using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span>

<span data-ttu-id="f14f3-182">Utilizzare i passaggi seguenti come riferimento per bloccare le estensioni da un determinato Store o URL.</span><span class="sxs-lookup"><span data-stu-id="f14f3-182">Use the following steps as a guide to block extensions from an particular store or URL.</span></span>

1. <span data-ttu-id="f14f3-183">Aprire l'editor Gestione criteri di gruppo e passare a **Modelli amministrativi > Microsoft Edge > Estensioni**, quindi selezionare **Configura impostazioni di gestione delle estensioni**.</span><span class="sxs-lookup"><span data-stu-id="f14f3-183">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="f14f3-184">Abilitare il criterio, quindi specificare le autorizzazioni che si desidera consentire o bloccare comprimendole a una singola stringa JSON.</span><span class="sxs-lookup"><span data-stu-id="f14f3-184">Enable the policy, then enter the permissions that you want allowed or blocked, compressing it to a single JSON string.</span></span>

<span data-ttu-id="f14f3-185">L'esempio seguente mostra la stringa JSON e quella JSON compressa per il blocco delle estensioni dal Chrome Web Store tramite il relativo URL di aggiornamento (`https://clients2.google.com/service/update2/crx`).</span><span class="sxs-lookup"><span data-stu-id="f14f3-185">The next example shows the JSON and compressed JSON string to block from the Chrome Web Store using its update URL (`https://clients2.google.com/service/update2/crx`).</span></span>

### <a name="json-example-for-blocking-on-update-url"></a><span data-ttu-id="f14f3-186">Esempio di JSON per il blocco dell'URL di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f14f3-186">JSON example for blocking on update URL</span></span>

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> <span data-ttu-id="f14f3-187">È ancora possibile usare \*\* ExtensionInstallForceList\*\* e **ExtensionInstallAllowList** per consentire/forzare l'installazione di estensioni specifiche tramite JSON nell'esempio precedente, anche se lo Store è bloccato.</span><span class="sxs-lookup"><span data-stu-id="f14f3-187">You can still use **ExtensionInstallForceList** and **ExtensionInstallAllowList** to allow/force install specific extensions even if the store is blocked using the JSON in the previous example.</span></span>

## <a name="see-also"></a><span data-ttu-id="f14f3-188">Consultare anche</span><span class="sxs-lookup"><span data-stu-id="f14f3-188">See also</span></span>

- [<span data-ttu-id="f14f3-189">Gestire le estensioni di Microsoft Edge nella grande impresa</span><span class="sxs-lookup"><span data-stu-id="f14f3-189">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="f14f3-190">Creare un archivio Web per ospitare le estensioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f14f3-190">Create a web store to host Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-webstore.md)
- [<span data-ttu-id="f14f3-191">Guida di riferimento per i criteri ExtensionSettings</span><span class="sxs-lookup"><span data-stu-id="f14f3-191">Reference guide for the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="f14f3-192">Domande frequenti sulle estensioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f14f3-192">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="f14f3-193">Pagina di destinazione di Microsoft Edge per le aziende</span><span class="sxs-lookup"><span data-stu-id="f14f3-193">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
