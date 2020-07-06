---
title: s_gi()
description: Crea e monitora le istanze di AppMeasurement.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 1%

---


# s_gi

La `s_gi()` funzione crea o trova un&#39;istanza di AppMeasurement per ID suite di rapporti. AppMeasurement tiene traccia di ogni istanza creata e `s_gi()` restituisce l&#39;istanza esistente per una suite di rapporti, se esistente. Se un&#39;istanza non esiste, viene creata una nuova istanza.

## s_gi() in  lancio Adobe Experience Platform

L&#39;estensione Analytics  crea un&#39;istanza e gestisce automaticamente l&#39;oggetto di tracciamento. Tuttavia, potete anche impostare un oggetto di tracciamento globale nel [!UICONTROL Library Management] pannello a soffietto quando configurate l&#39;estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandete la [!UICONTROL Library Management] fisarmonica e selezionate un pulsante di scelta diverso da [!UICONTROL Manage the library for me].

Il campo di testo della variabile globale consente di impostare un oggetto di tracciamento personalizzato. Its default value is `s`.

## s_gi() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiamare la `s_gi()` funzione per creare un&#39;istanza di un oggetto di tracciamento. L&#39;unico argomento contiene una stringa delimitata da virgole di ID suite di rapporti. L&#39;argomento ID suite di rapporti è obbligatorio.

>[!TIP]
>
>Adobe consiglia di utilizzare la `s` variabile come oggetto di tracciamento. Adobe utilizza `s` nella documentazione, negli esempi di implementazione e nei plug-in. Tuttavia, potete utilizzare qualsiasi variabile purché sia coerente sul sito.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>Le sezioni e gli esempi seguenti contengono argomenti di implementazione complessi. Verifica accuratamente l&#39;implementazione e monitora importanti personalizzazioni nel documento [di progettazione della](../../prepare/solution-design.md)soluzione aziendale.

## Gestire più implementazioni utilizzando diversi oggetti di tracciamento

Se create un&#39;istanza di più oggetti di tracciamento, potete inviare dati diversi a suite di rapporti diverse. Questi due oggetti di tracciamento operano indipendentemente l&#39;uno dall&#39;altro.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Ripristina variabili AppMeasurement dopo la sovrascrittura dell&#39;oggetto s

Alcuni strumenti di terze parti potrebbero inoltre utilizzare l&#39;oggetto JavaScript `s` . Se si sovrascrive accidentalmente l’ `s` oggetto sul sito, è possibile chiamare `s_gi` con lo stesso argomento della stringa RSID per ripristinare tutte le variabili e i metodi sovrascritti.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Riferimento allo stesso oggetto di tracciamento con più variabili

Se due variabili fanno riferimento alla stessa `s_gi()` funzione della stessa suite di rapporti, è possibile utilizzare le variabili in modo intercambiabile.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
