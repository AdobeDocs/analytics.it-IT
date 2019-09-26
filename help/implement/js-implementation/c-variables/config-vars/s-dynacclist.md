---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement] for JavaScript can dynamically select a report suite to which it sends data. The  variable contains the rules used to determine the destination report suite.

| Max Size | Debugger Parameter | Reports Populated | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

This variable is used in conjunction with the  and  variables. *`dynamicAccountSelection`**`dynamicAccountMatch`* The rules in  are applied if  is set to 'true,' and they apply to the section of the URL specified in .*`dynamicAccountList`**`dynamicAccountSelection`**`dynamicAccountMatch`*

Se nessuna delle regole in *`dynamicAccountList`* corrisponde all'URL della pagina, viene utilizzata la suite di rapporti identificata in `s_account` . The rules listed in this variable are applied in a left-to-right order. If the page URL matches more than one rule, the left-most rule is used to determine the report suite. As a result, your more generic rules should be moved to the right of the list.

Negli esempi seguenti, l’URL della pagina è `www.mycompany.com/path1/?prod_id=12345` e `dynamicAccountSelection` è impostato su *true* e `s_account` su `mysuitecom.`

| DynamicAccountList Value | Valore DynamicAccountMatch | Suite di rapporti per ricevere i dati |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuite ecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## Sintassi e valori possibili

La `dynamicAccountList` variabile è un elenco separato da punto e virgola di coppie nome=valore (regole). Ogni parte dell'elenco deve contenere i seguenti elementi:

* uno o più ID suite di rapporti (separati da virgole)
* un segno uguale
* uno o più filtri URL (separati da virgole)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Nella stringa devono essere utilizzati solo i caratteri ASCII standard (senza spazi).

## Esempi

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* La selezione di account dinamici non è supportata da [AppMeasurement per JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Se l’URL della pagina corrisponde a più regole, viene utilizzata la regola più a sinistra.
* Se nessuna regola corrisponde, viene utilizzata la suite di rapporti predefinita.
* Se la pagina viene salvata sul disco rigido di un utente o tradotta tramite un motore di traduzione basato sul Web (come le pagine tradotte di Google), la selezione dell'account dinamico probabilmente non funzionerà. Per un tracciamento più preciso, compila la `s_account` variabile lato server.
* Le `dynamicAccountSelection` regole si applicano solo alla sezione dell'URL specificato in `dynamicAccountMatch`.

* Quando utilizzate la selezione di account dinamici, accertatevi di eseguire l'aggiornamento *`dynamicAccountList`* ogni volta che ottenete un nuovo dominio.
* Use the  when trying to identify the destination report suite. [!DNL DigitalPulse Debugger] The  variable always overrides the value of .`dynamicAccountSelection``s_account`
