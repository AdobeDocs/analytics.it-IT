---
title: t
description: Inviare una chiamata di tracciamento della visualizzazione della pagina ad Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---


# t()

Il `t()` metodo è un componente di base importante per Adobe  Analytics. Prende tutte  variabili Analytics definite nella pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati Adobe.

Ad esempio, prendere in considerazione il seguente codice JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

L&#39;esecuzione del `t()` metodo prende tutte  variabili Analytics definite e formula un URL basato su tali variabili. Alcune variabili Analytics  determinano l’URL dell’immagine, mentre altre determinano i valori dei parametri delle stringhe di query.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe riceve la richiesta di immagine, quindi analizza i parametri dell’intestazione della richiesta, dell’URL e della stringa di query. I server di raccolta dati restituiscono quindi un’immagine trasparente da 1 x 1 pixel, visualizzata in modo invisibile sul sito.

## Chiamata di tracciamento visualizzazione pagina in  lancio Adobe Experience Platform

Launch ha una posizione dedicata impostata come chiamata di tracciamento della visualizzazione della pagina.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic sull&#39;icona &quot;+&quot;
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e su [!UICONTROL Action Type] Invia beacon.
6. Click the `s.t()` radio button.

## s.t() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiama il `s.t()` metodo per inviare una chiamata di tracciamento ad Adobe.

```js
s.t();
```

Facoltativamente, è possibile utilizzare un oggetto come argomento per ignorare i valori delle variabili. Per ulteriori informazioni, vedi [sostituzioni](../../js/overrides.md) variabili.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement utilizzavano diverse righe di codice per chiamare questa funzione. Il codice aggiuntivo, che comprendeva soluzioni storicamente adattate per diversi browser. La standardizzazione e le best practice nei browser più recenti non richiedono più questo blocco di codice. È necessaria solo la chiamata del metodo `s.t()` ora.
