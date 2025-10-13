---
title: dynamicAccountList
description: Stabilisci la logica su come l’implementazione determina la suite di rapporti.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando le implementazioni legacy di JavaScript (codice H). Queste variabili non sono supportate nelle librerie AppMeasurement o nella raccolta dati di Adobe Experience Platform correnti.

La variabile `s.dynamicAccountList` determina dinamicamente il valore di `s_account`. Se `dynamicAccountSelection` è impostato su `true`, la variabile `dynamicAccountMatch` viene confrontata con `dynamicAccountList`. Se viene trovata una corrispondenza, viene utilizzato l’ID suite di rapporti corrispondente.

## Sintassi

Questa variabile è una stringa che viene analizzata automaticamente dal file JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

L&#39;input valido è un elenco separato da punto e virgola di coppie rsid e valore. Ogni elenco contiene i seguenti elementi:

* Uno o più ID suite di rapporti (separati da virgole)
* Un segno di uguale
* Una o più stringhe da associare (separate da virgole)

Nella stringa devono essere utilizzati solo i caratteri ASCII standard. Non includere spazi.

## Esempi

Per tutti gli esempi seguenti, l&#39;URL della pagina è `https://example.com/path2/?prod_id=12345`, la variabile `dynamicAccountSelection` è impostata su `true` e la variabile `s_account` è impostata su `examplersid`.

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

* Le regole elencate in questa variabile vengono applicate da sinistra a destra. Se la variabile `dynamicAccountMatch` corrisponde a più di una regola, per determinare la suite di rapporti viene utilizzata la regola all&#39;estrema sinistra. Di conseguenza, posiziona le regole più generiche a destra dell’elenco.
* Se nessuna regola corrisponde, viene utilizzata la suite di rapporti predefinita in `s_account`.
* Se la pagina viene salvata sul disco rigido di un utente o tradotta tramite un motore di traduzione basato su Web (ad esempio le pagine tradotte di Google), la selezione dinamica dell’account probabilmente non funzionerà.
* Le regole `dynamicAccountSelection` si applicano solo alla sezione dell&#39;URL specificato in `dynamicAccountMatch`.
* Utilizza [!DNL Adobe Experience Cloud Debugger] per testare la suite di rapporti di destinazione.
