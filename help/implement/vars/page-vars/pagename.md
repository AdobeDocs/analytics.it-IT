---
title: pageName
description: Il nome della pagina sul sito.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 1%

---


# pageName

In genere, la `pageName` variabile memorizza il nome di una determinata pagina. È utile determinare quali singole pagine sono più popolari. Questa variabile popola la dimensione &#39;Nome pagina&#39;.

>[!NOTE]
>
>Questa dimensione viene sempre esclusa dalle chiamate di tracciamento dei collegamenti. Per visualizzare il nome della pagina in cui è stato tracciato un collegamento, considera la possibilità di copiare la variabile in una eVar.

Se questa variabile non è definita in una determinata chiamata di tracciamento della pagina, viene utilizzata la [`pageURL`](pageurl.md) variabile.

## Nome pagina nel lancio  Adobe Experience Platform

Potete impostare il nome della pagina sia durante la configurazione dell’estensione Analytics  (variabili globali), sia in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Page name] sezione.

È possibile impostare il nome della pagina su qualsiasi valore di stringa, compresi gli elementi di dati.

## s.pageName nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.pageName` variabile è una stringa che in genere contiene il nome della pagina. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati. Questo troncamento include le istanze in cui rientra `pageURL` se questa variabile è vuota.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
