---
title: pageURL
description: Ignorate l’URL di pagina raccolto automaticamente sul sito.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---


# pageURL

AppMeasurement raccoglie automaticamente l’URL della pagina in ogni hit. Se desiderate ignorare l’URL della pagina raccolto automaticamente da AppMeasurement, potete usare questa variabile. Nella maggior parte dei casi non è necessario impostare questa variabile.

>[!NOTE]
>
>Questa variabile non è una dimensione disponibile in  Analysis Workspace. È disponibile solo in Data Warehouse e feed di dati. Inoltre,  server di raccolta dati di Adobe eliminano questa dimensione da tutte le richieste di immagini per il tracciamento dei [collegamenti](/help/implement/vars/functions/tl-method.md) . Se desideri usare l’URL della pagina come dimensione in  Analysis Workspace o vuoi che questa dimensione sia negli hit di tracciamento dei collegamenti, puoi considerare la possibilità di passare la `pageURL` variabile in un eVar [](evar.md) per ogni hit.

## URL pagina in  Adobe Experience Platform Launch

Launch compila automaticamente l’URL della pagina. Tuttavia, puoi impostare l’URL della pagina come override sia durante la configurazione dell’estensione Analytics (variabili globali), sia in base a regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla **[!UICONTROL Rules]** scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In **[!UICONTROL Actions]**, fare clic su un&#39;azione esistente **[!UICONTROL Adobe Analytics - Set Variables]** o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il **[!UICONTROL Extension]** menu a discesa su  Adobe Analytics e **[!UICONTROL Action Type]** su **[!UICONTROL Set Variables]**.
6. Individuare la **[!UICONTROL Page URL]** sezione.

Potete impostare l’URL della pagina su qualsiasi valore di stringa.

## s.pageURL nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.pageURL` variabile è una stringa che contiene l’URL della pagina. AppMeasurement raccoglie automaticamente questa variabile, ma se necessario puoi ignorarne il valore.

```js
s.pageURL = "https://example.com";
```

Se desiderate utilizzare l&#39;URL di pagina come dimensione nei rapporti, prendete in considerazione l&#39;idea di utilizzare quanto segue nella vostra implementazione:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Se si utilizza il livello `digitalData` [](../../prepare/data-layer.md)dati:

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
