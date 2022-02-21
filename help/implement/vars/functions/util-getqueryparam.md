---
title: Util.getQueryParam
description: Restituisce il valore di un parametro di stringa query.
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Util.getQueryParam

I parametri della stringa di query in un URL del browser contengono frequentemente dati importanti per Analytics. Utilizza la `Util.getQueryParam()` per recuperare i dati dalla stringa di query.

## Ottenere i dati dei parametri della stringa di query utilizzando i tag in Adobe Experience Platform

È possibile ottenere i dati dei parametri della stringa di query impostando i valori negli elementi dati.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Data Elements] , quindi fai clic sull’elemento dati desiderato (o crea un elemento dati).
4. Imposta la [!UICONTROL Extension] a discesa [!UICONTROL Core]e [!UICONTROL Data Element Type] a [!UICONTROL Query String Parameter].
5. Immettere il parametro della stringa query nel campo di testo.

Il valore del parametro della stringa di query viene memorizzato nell&#39;elemento dati. Puoi quindi fare riferimento all’elemento dati nelle regole per assegnare le variabili di Analytics.

## s.Util.getQueryParam() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama il `s.Util.getQueryParam()` per recuperare un valore della stringa di query dall&#39;URL del browser. L&#39;argomento stringa contenente un parametro della stringa di query è obbligatorio. Questo metodo restituisce una stringa che puoi assegnare alle variabili di Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un secondo argomento facoltativo consente di specificare la stringa da verificare per i parametri della stringa di query. Per impostazione predefinita, l&#39;utilità controlla l&#39;URL del browser.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un terzo argomento facoltativo consente di personalizzare il delimitatore di stringa query. Il valore predefinito è `&`. È possibile modificare questo valore se la stringa di query utilizza un delimitatore diverso.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>Un plug-in simile denominato [`s.getQueryParam`](../plugins/getqueryparam.md) è disponibile. Questo plug-in contiene funzioni più avanzate, ma è anche più complesso e non è incluso in AppMeasurement per impostazione predefinita.
