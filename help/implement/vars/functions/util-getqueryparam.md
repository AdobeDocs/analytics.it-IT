---
title: Util.getQueryParam
description: Restituisce il valore di un parametro stringa query.
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 7%

---

# Util.getQueryParam

I parametri delle stringhe di query in un URL del browser contengono spesso dati importanti per Analytics. Utilizza il `Util.getQueryParam()` per recuperare dati dalla stringa query.

## Ottenere i dati dei parametri della stringa di query tramite l’estensione Adobe Analytics e l’estensione Web SDK

Puoi ottenere i dati dei parametri della stringa di query impostando i valori negli elementi dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai a [!UICONTROL Data Elements] , quindi fai clic sull’elemento dati desiderato (o crea un elemento dati).
4. Imposta il [!UICONTROL Extension] elenco a discesa per **[!UICONTROL Core]** e [!UICONTROL Data Element Type] a **[!UICONTROL Query String Parameter]**.
5. Immetti il parametro della stringa di query nel campo di testo.

Il valore del parametro della stringa di query viene memorizzato nell&#39;elemento dati. Puoi quindi fare riferimento all’elemento dati nelle regole per assegnare le variabili desiderate.

## s.Util.getQueryParam() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.Util.getQueryParam()` per recuperare un valore stringa query dall&#39;URL del browser. L&#39;argomento stringa contenente un parametro stringa query è obbligatorio. Questo metodo restituisce una stringa che puoi assegnare alle variabili di Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un secondo argomento facoltativo consente di specificare la stringa da controllare per i parametri della stringa di query. Per impostazione predefinita, l’utility esamina l’URL del browser.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un terzo argomento facoltativo consente di personalizzare il delimitatore della stringa di query. Il valore predefinito è `&`. È possibile modificare questo valore se la stringa di query utilizza un delimitatore diverso.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>Un plug-in simile denominato [`s.getQueryParam`](../plugins/getqueryparam.md) è disponibile. Questo plug-in contiene funzioni più avanzate, ma è anche più complesso e non è incluso in AppMeasurement per impostazione predefinita.
