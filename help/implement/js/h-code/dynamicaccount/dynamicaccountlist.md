---
title: dynamicAccountList
description: Stabilite la logica su come l'implementazione determina la suite di rapporti.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# s.dynamicAccountList

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript precedenti (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti né  lancio del Adobe Experience Platform.

La `s.dynamicAccountList` variabile determina in modo dinamico il valore di `s_account`. Se `dynamicAccountSelection` è impostata su `true`, la `dynamicAccountMatch` variabile viene confrontata con `dynamicAccountList`. Se viene trovata una corrispondenza, viene utilizzato l&#39;ID suite di rapporti corrispondente.

## Sintassi

Questa variabile è una stringa che viene analizzata automaticamente dal file JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

Un input valido è un elenco separato da punto e virgola di coppie rsid e valore. Ogni elenco contiene i seguenti elementi:

* Uno o più ID suite di rapporti (separati da virgole)
* Simbolo uguale a
* Una o più stringhe alle quali conformarsi (separate da virgole)

Nella stringa devono essere utilizzati solo i caratteri ASCII standard. Non includete spazi.

## Esempi

Per tutti gli esempi seguenti, l’URL della pagina è `https://example.com/path2/?prod_id=12345`, la `dynamicAccountSelection` variabile è impostata su `true`e la `s_account` variabile è impostata su `examplersid`.

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

* Le regole elencate in questa variabile vengono applicate in ordine da sinistra a destra. Se la `dynamicAccountMatch` variabile corrisponde a più regole, per determinare la suite di rapporti viene utilizzata la regola più a sinistra. Di conseguenza, collocate a destra dell&#39;elenco regole più generiche.
* Se nessuna regola corrisponde, `s_account` viene utilizzata la suite di rapporti predefinita in.
* Se la pagina viene salvata sul disco rigido di un utente o tradotta tramite un motore di traduzione basato sul Web (come le pagine tradotte di Google), la selezione dell&#39;account dinamico probabilmente non funzionerà.
* Le `dynamicAccountSelection` regole si applicano solo alla sezione dell&#39;URL specificato in `dynamicAccountMatch`.
* Utilizzate l&#39;icona [!DNL Adobe Experience Cloud Debugger] per testare la suite di rapporti di destinazione.
