---
title: s_gi()
description: Crea e tieni traccia delle istanze di AppMeasurement.
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# s_gi

La funzione `s_gi()` crea o trova un&#39;istanza di AppMeasurement per ID suite di rapporti. AppMeasurement tiene traccia di ogni istanza creata e `s_gi()` restituisce l&#39;istanza esistente per una suite di rapporti, se presente. Se un&#39;istanza non esiste, viene creata una nuova istanza.

## s_gi() utilizzando i tag in Adobe Experience Platform

L&#39;estensione Analytics crea un&#39;istanza e gestisce l&#39;oggetto di tracciamento per te. Tuttavia, puoi anche impostare un oggetto di tracciamento globale nel pannello a soffietto [!UICONTROL Library Management] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Library Management] pannello a soffietto e seleziona un pulsante di scelta diverso da [!UICONTROL Manage the library for me].

Il campo di testo della variabile globale consente di impostare un oggetto di tracciamento personalizzato. Il valore predefinito è `s`.

## s_gi() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama la funzione `s_gi()` per creare un&#39;istanza di un oggetto di tracciamento. L&#39;unico argomento contiene una stringa delimitata da virgole degli ID suite di rapporti. L’argomento ID suite di rapporti è obbligatorio.

>[!TIP]
>
>Adobe consiglia di utilizzare la variabile `s` come oggetto di tracciamento. Adobe utilizza `s` nella documentazione, negli esempi di implementazione e nei plug-in. Tuttavia, puoi utilizzare qualsiasi variabile purché sia coerente all’interno del sito.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>Le sezioni e gli esempi seguenti contengono argomenti di implementazione complessi. Verifica accuratamente l&#39;implementazione e monitora importanti personalizzazioni nel [documento di progettazione della soluzione](../../prepare/solution-design.md) della tua organizzazione.

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

Alcuni strumenti di terze parti potrebbero inoltre utilizzare l&#39;oggetto JavaScript `s` . Se sovrascrivi accidentalmente l&#39;oggetto `s` sul sito, puoi chiamare `s_gi` con lo stesso argomento della stringa RSID per ripristinare tutte le variabili e i metodi sovrascritti.

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

Se due variabili fanno riferimento alla stessa funzione `s_gi()` con la stessa suite di rapporti, puoi utilizzare le variabili in modo intercambiabile.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
