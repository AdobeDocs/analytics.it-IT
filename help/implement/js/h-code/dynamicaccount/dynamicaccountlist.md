---
title: dynamicAccountList
description: Stabilisci la logica su come l’implementazione determina la suite di rapporti.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti o nella raccolta dati di Adobe Experience Platform.

La `s.dynamicAccountList` determina dinamicamente il valore di `s_account`. Se `dynamicAccountSelection` è impostato su `true`, `dynamicAccountMatch` viene confrontata con `dynamicAccountList`. Se viene trovata una corrispondenza, viene utilizzato l&#39;ID suite di rapporti corrispondente.

## Sintassi

Questa variabile è una stringa che viene analizzata automaticamente dal file JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

L&#39;input valido è un elenco separato da punto e virgola di coppie di valori e rsid. Ogni elenco contiene i seguenti elementi:

* Uno o più ID suite di rapporti (separati da virgole)
* Un segno uguale a
* Una o più stringhe da abbinare (separate da virgole)

Nella stringa devono essere utilizzati solo caratteri ASCII standard. Non includere spazi.

## Esempi

Per tutti gli esempi seguenti, l’URL della pagina è `https://example.com/path2/?prod_id=12345`, `dynamicAccountSelection` è impostata su `true`e `s_account` è impostata su `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Insidie, domande e suggerimenti

* Le regole elencate in questa variabile vengono applicate in ordine da sinistra a destra. Se la `dynamicAccountMatch` corrisponde a più di una regola; la regola più a sinistra viene utilizzata per determinare la suite di rapporti. Di conseguenza, posiziona regole più generiche a destra dell’elenco.
* Se non corrispondono regole, la suite di rapporti predefinita in `s_account` viene utilizzato.
* Se la pagina viene salvata sul disco rigido di un utente o tradotta tramite un motore di traduzione basato sul web (come le pagine tradotte di Google), la selezione dell’account dinamico probabilmente non funzionerà.
* La `dynamicAccountSelection` le regole si applicano solo alla sezione dell’URL specificato in `dynamicAccountMatch`.
* Utilizza la [!DNL Adobe Experience Cloud Debugger] per testare la suite di rapporti di destinazione.
