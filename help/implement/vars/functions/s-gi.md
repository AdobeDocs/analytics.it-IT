---
title: s_gi()
description: Crea e tieni traccia delle istanze di AppMeasurement.
feature: Appmeasurement Implementation
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
role: Admin, Developer
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 10%

---

# s_gi

La funzione `s_gi()` crea un&#39;istanza di AppMeasurement o la trova in base all&#39;ID suite di rapporti. AppMeasurement tiene traccia di ogni istanza creata e `s_gi()` restituisce l&#39;istanza esistente per una suite di rapporti, se ne esiste una. Se non esiste alcuna istanza, viene creata una nuova istanza.

## Creare un&#39;istanza di un oggetto di tracciamento utilizzando l&#39;estensione Web SDK

L&#39;estensione Web SDK crea e gestisce automaticamente l&#39;oggetto di tracciamento. Tuttavia, puoi personalizzare il nome dell’oggetto di tracciamento nelle impostazioni dell’estensione:

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passare alla scheda [!UICONTROL Extensions], quindi fare clic sul pulsante **[!UICONTROL Configure]** in Adobe Experience Platform Web SDK.
1. Modificare il campo [!UICONTROL Name] nel valore desiderato. Il valore predefinito è `alloy`.

## Creare un&#39;istanza di un oggetto di tracciamento implementando manualmente il Web SDK

Il codice seguente carica il Web SDK e crea un&#39;istanza di un oggetto di tracciamento. È possibile personalizzare il nome dell&#39;oggetto di tracciamento modificando la stringa `"alloy"` alla fine dello script in linea con il valore desiderato.

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

Per ulteriori informazioni, vedere [Installare SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=it) nella documentazione di Web SDK.

## Creare un’istanza di un oggetto di tracciamento utilizzando l’estensione Adobe Analytics

L&#39;estensione Analytics crea e gestisce automaticamente l&#39;oggetto di tracciamento. Tuttavia, è anche possibile impostare un oggetto di tracciamento globale nel pannello a soffietto [!UICONTROL Library Management] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Library Management] e selezionare un pulsante di opzione diverso da [!UICONTROL Manage the library for me].

Il campo di testo variabile globale consente di impostare un oggetto di tracciamento personalizzato. Il valore predefinito è `s`.

## s_gi() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare la funzione `s_gi()` per creare un&#39;istanza di un oggetto di tracciamento. Il suo unico argomento contiene una stringa delimitata da virgole di ID suite di rapporti. L’argomento ID suite di rapporti è obbligatorio.

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
>Le sezioni e gli esempi seguenti contengono argomenti di implementazione complessi. Verifica accuratamente l&#39;implementazione e tieni traccia delle personalizzazioni importanti nel [documento di progettazione della soluzione](../../prepare/solution-design.md) della tua organizzazione.

## Gestire più implementazioni utilizzando diversi oggetti di tracciamento

Se crei un&#39;istanza di più oggetti di tracciamento, puoi inviare dati diversi a suite di rapporti diverse. Questi due oggetti di tracciamento operano in modo indipendente l&#39;uno dall&#39;altro.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name";
z.pageName = "An alternate page name";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Ripristina le variabili di AppMeasurement dopo la sovrascrittura dell’oggetto s

Alcuni strumenti di terze parti potrebbero inoltre utilizzare l&#39;oggetto JavaScript `s`. Se si sovrascrive accidentalmente l&#39;oggetto `s` sul sito, è possibile chiamare `s_gi` con lo stesso argomento stringa RSID per ripristinare tutte le variabili e i metodi sovrascritti.

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

## Fare riferimento allo stesso oggetto di tracciamento con più variabili

Se due variabili fanno riferimento alla stessa funzione `s_gi()` con la stessa suite di rapporti, è possibile utilizzare le variabili in modo intercambiabile.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
