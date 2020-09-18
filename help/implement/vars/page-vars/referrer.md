---
title: referrer
description: Ignora il referente raccolto automaticamente per un hit.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 2%

---


# referrer

La `referrer` variabile sostituisce il referente raccolto automaticamente nei report. Questa variabile è utile nelle situazioni in cui il referente potrebbe andare perso, ad esempio durante i reindirizzamenti o l&#39;inoltro temporaneo del visitatore a un elaboratore di pagamenti. Questa variabile consente di compilare le dimensioni &#39;Referente&#39; e &#39;Dominio di riferimento&#39;.

## Referente in  Adobe Experience Platform Launch

Puoi impostare il referente sia durante la configurazione dell&#39;estensione di Analytics (variabili globali), sia in base a regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su  Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Referrer] sezione.

È possibile impostare il referente su qualsiasi valore di stringa, compresi gli elementi di dati.

## s.referrer nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.referrer` variabile è una stringa contenente l’URL della pagina precedente. Questa variabile può contenere un massimo di 255 byte; vengono troncati valori superiori a 255 byte. AppMeasurement imposta automaticamente questa variabile su `document.referrer`; non è necessario impostare questa variabile a meno che non si desideri ignorare il valore raccolto automaticamente.

```js
s.referrer = "https://example.com";
```

Se si utilizza il livello `digitalData` [](../../prepare/data-layer.md)dati:

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Evitate di impostare questa variabile su valori non URL. Non rimuovere il protocollo dell&#39;URL.

## Esempio

Molte organizzazioni si occupano di implementazioni relative ai reindirizzamenti. Potete utilizzare l&#39; [`Util.getQueryParam()`](../functions/util-getqueryparam.md) utility per ottenere il referente dall&#39;URL se il sito lo contiene. Accertatevi di codificare URL eventuali valori inclusi nella stringa di query.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
