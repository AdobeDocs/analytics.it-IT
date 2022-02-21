---
title: s_gi()
description: Crea e tieni traccia delle istanze di AppMeasurement.
feature: Variables
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# s_gi

La `s_gi()` crea un&#39;istanza di AppMeasurement per l&#39;ID suite di rapporti. AppMeasurement tiene traccia di ogni istanza creata, e `s_gi()` restituisce l&#39;istanza esistente per una suite di rapporti, se esistente. Se un&#39;istanza non esiste, viene creata una nuova istanza.

## s_gi() utilizzando i tag in Adobe Experience Platform

L&#39;estensione Analytics crea un&#39;istanza e gestisce l&#39;oggetto di tracciamento per te. Tuttavia, puoi anche impostare un oggetto di tracciamento globale nel [!UICONTROL Library Management] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Library Management] e selezionare un pulsante di scelta diverso da [!UICONTROL Manage the library for me].

Il campo di testo della variabile globale consente di impostare un oggetto di tracciamento personalizzato. Il valore predefinito è `s`.

## s_gi() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama il `s_gi()` per creare un&#39;istanza di un oggetto di tracciamento. L&#39;unico argomento contiene una stringa delimitata da virgole degli ID suite di rapporti. L’argomento ID suite di rapporti è obbligatorio.

>[!TIP]
>
>L&#39;Adobe consiglia di utilizzare `s` come oggetto di tracciamento. Adobe di utilizzo `s` nella documentazione, esempi di implementazione e plug-in. Tuttavia, puoi utilizzare qualsiasi variabile purché sia coerente all’interno del sito.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>Le sezioni e gli esempi seguenti contengono argomenti di implementazione complessi. Verifica accuratamente l’implementazione e monitora importanti personalizzazioni nelle [documento di progettazione della soluzione](../../prepare/solution-design.md).

## Gestire più implementazioni utilizzando diversi oggetti di tracciamento

Se crei un&#39;istanza di più oggetti di tracciamento, puoi inviare dati diversi a suite di rapporti diverse. Questi due oggetti di tracciamento operano indipendentemente l’uno dall’altro.

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

## Ripristinare le variabili AppMeasurement dopo la sovrascrittura dell&#39;oggetto s

Alcuni strumenti di terze parti potrebbero inoltre utilizzare JavaScript `s` oggetto. Se sovrascrivi accidentalmente il `s` sul sito, puoi chiamare `s_gi` con lo stesso argomento della stringa RSID per ripristinare tutte le variabili e i metodi sovrascritti.

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

## Fai riferimento allo stesso oggetto di tracciamento con più variabili

Se due variabili fanno riferimento allo stesso `s_gi()` con la stessa suite di rapporti, puoi utilizzare le variabili in modo intercambiabile.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
