---
title: t
description: Invia ad Adobe una chiamata di tracciamento della visualizzazione della pagina.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# t()

La `t()` è un componente di base importante per Adobe Analytics. Prende tutte le variabili Analytics definite nella pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe.

Ad esempio, considera il seguente codice JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

Esecuzione del `t()` prende tutte le variabili di Analytics definite e formula un URL basato su tali variabili. Alcune variabili di Analytics determinano l’URL dell’immagine, mentre altre variabili determinano i valori dei parametri della stringa di query.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe riceve la richiesta di immagine, quindi analizza l’intestazione della richiesta, l’URL e i parametri della stringa di query. I server di raccolta dati restituiscono quindi un’immagine trasparente da 1 pixel x 1, visualizzata in modo invisibile sul sito.

## Chiamata di tracciamento della visualizzazione pagina tramite tag in Adobe Experience Platform

L’interfaccia utente di raccolta dati dispone di una posizione dedicata impostata per una chiamata di tracciamento della visualizzazione della pagina.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic sull&#39;icona &quot;+&quot;
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a Invia beacon.
6. Fai clic sul pulsante `s.t()` pulsante di scelta.

## s.t() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama il `s.t()` quando desideri inviare una chiamata di tracciamento ad Adobe.

```js
s.t();
```

Facoltativamente, è possibile utilizzare un oggetto come argomento per sostituire i valori delle variabili. Vedi [sostituzioni delle variabili](../../js/overrides.md) per ulteriori informazioni.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement utilizzavano diverse righe di codice per chiamare questa funzione. Il codice aggiuntivo sistemato storicamente soluzioni alternative per diversi browser. La standardizzazione e le best practice nei browser moderni non richiedono più questo blocco di codice. Solo la chiamata del metodo `s.t()` È necessario ora.
