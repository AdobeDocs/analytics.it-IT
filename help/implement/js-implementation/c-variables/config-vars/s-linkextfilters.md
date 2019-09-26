---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

Se il sito contiene molti collegamenti a siti esterni e non si desidera tenere traccia di tutti i collegamenti di uscita, utilizzare per creare rapporti su un sottoinsieme specifico di collegamenti di uscita.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Percorsi &gt; Voci ed uscite &gt; Esci dai collegamenti | "" |

La *`linkExternalFilters`* variabile è una variabile opzionale utilizzata insieme *`linkInternalFilters`* per determinare se un collegamento è un collegamento di uscita. Un collegamento di uscita è definito come qualsiasi collegamento che allontani un visitatore dal sito. A prescindere dal fatto che la finestra di destinazione di un collegamento di uscita sia una finestra a comparsa o una finestra esistente, il collegamento non influisce sulla sua visualizzazione nel rapporto dei collegamenti di uscita. I collegamenti di uscita vengono tracciati solo se *`trackExternalLinks`* è impostato su 'true'. I filtri in *`linkExternalFilters`* e *`linkInternalFilters`* non fanno distinzione tra maiuscole e minuscole.

>[!NOTE]
>
>Se non si desidera utilizzare *`linkExternalFilters`*, cancellarlo o impostarlo su "".

L'elenco dei filtri *`linkExternalFilters`* e *`linkInternalFilters`* si applica al dominio e al percorso di qualsiasi collegamento per impostazione predefinita. Se *`linkLeaveQueryString`* è impostato su 'true', i filtri si applicano all'intero URL (dominio, percorso e stringa di query). Questi filtri vengono sempre applicati al percorso assoluto dell'URL, anche se come valore href viene utilizzato un percorso relativo.

La maggior parte delle aziende ritiene che *`linkInternalFilters`* gli dia un controllo sufficiente sui collegamenti di uscita di cui non hanno bisogno *`linkExternalFilters`*. Utilizzando *`linkExternalFilters`* semplicemente diminuisce la probabilità che un collegamento di uscita venga considerato esterno. Se *`linkExternalFilters`* ha un valore, un collegamento viene considerato esterno solo se non corrisponde *`linkInternalFilters`* e non corrisponde *`linkExternalFilters`*.

L’esempio seguente illustra come viene utilizzata questa variabile. In questo esempio, l’URL della pagina è `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## Sintassi e valori possibili

La *`linkExternalFilters`* variabile è un elenco separato da virgole di caratteri ASCII. Non sono consentiti spazi.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Qualsiasi parte di un URL può essere inclusa in *`linkExternalFilters`*, separata da virgole.

## Esempi

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Impostazioni di configurazione

Nessuno

## Pitfalls, Questions, and Tips

* L'utilizzo *`linkExternalFilters`* può ridurre i collegamenti del sito. Non utilizzare questa variabile invece di *`linkInternalFilters`* forzare i collegamenti interni a diventare collegamenti di uscita.

* Se *`linkExternalFilters`* si desidera applicare alla stringa di query di un collegamento, assicurarsi che *`linkLeaveQueryString`* sia impostata su 'true'. See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set  to .*`trackExternalLinks`*`"false"`
