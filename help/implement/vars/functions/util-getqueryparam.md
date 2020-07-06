---
title: Util.getQueryParam
description: Restituisce il valore di un parametro di stringa di query.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---


# Util.getQueryParam

I parametri della stringa di query in un URL del browser contengono spesso dati importanti per  Analytics. Utilizzare il `Util.getQueryParam()` metodo per recuperare i dati dalla stringa di query.

## Ottenere i dati dei parametri della stringa di query nel lancio  Adobe Experience Platform

È possibile ottenere i dati dei parametri delle stringhe di query impostando i valori negli elementi di dati.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Data Elements] scheda, quindi fai clic sull&#39;elemento dati desiderato (o crea un elemento dati).
4. Impostate il [!UICONTROL Extension] menu a discesa su [!UICONTROL Core], quindi [!UICONTROL Data Element Type] su [!UICONTROL Query String Parameter].
5. Immettere il parametro della stringa di query nel campo di testo.

Il valore del parametro della stringa di query è memorizzato nell&#39;elemento dati. Potete quindi fare riferimento all&#39;elemento dati nelle regole per assegnare  variabili Analytics.

## s.Util.getQueryParam() in AppMeasurement e Avvia editor di codice personalizzato

Chiamate il `s.Util.getQueryParam()` metodo per recuperare un valore di stringa di query dall’URL del browser. L&#39;argomento stringa contenente un parametro di stringa di query è obbligatorio. Questo metodo restituisce una stringa che potete assegnare  variabili Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un secondo argomento facoltativo consente di specificare la stringa da verificare per i parametri della stringa di query. Per impostazione predefinita, l&#39;utilità cerca l&#39;URL del browser.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un terzo argomento opzionale consente di personalizzare il delimitatore della stringa di query. Its default value is `&`. È possibile modificare questo valore se la stringa di query utilizza un delimitatore diverso.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>È disponibile un plug-in simile denominato [`s.getQueryParam`](../plugins/getqueryparam.md) . Questo plug-in contiene funzioni più avanzate, ma è anche più complesso e non è incluso in AppMeasurement per impostazione predefinita.
