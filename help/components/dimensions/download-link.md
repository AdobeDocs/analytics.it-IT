---
title: Collegamento di download
description: Nome del collegamento per il download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---

# Collegamento di download

La [dimensione](overview.md) del collegamento di download riporta i nomi dei collegamenti di download implementati nel sito. Questa dimensione è utile quando desideri ulteriori informazioni sul comportamento dei visitatori in merito ai collegamenti di download, ad esempio:

* Quali file vengono scaricati più frequentemente dal sito.
* Indica se alcuni file vengono scaricati più spesso in determinati periodi di tempo.
* Se i visitatori scaricano diversi tipi di file quando vengono offerti.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`pev2`](/help/implement/validate/query-parameters.md) nelle richieste di immagini, a seconda del valore nella stringa di query `pe`. La stringa di query `pe` determina la dimensione di collegamento che riceve il valore `pev2`:

* **[Collegamento personalizzato](custom-link.md)**: `lnk_o`
* **Collegamento di download** (questa pagina): `lnk_d`
* **[Collegamento di uscita](exit-link.md)**: `lnk_e`

Se `pev2` non viene fornito, verrà utilizzato come valore della dimensione l&#39;URL del collegamento (`pev1`). Quando il nome di un collegamento viene specificato in modo esplicito, la lunghezza massima è di 100 byte. I valori derivati dall’URL del collegamento non sono soggetti a questo limite.

Per popolare questa dimensione utilizzando AppMeasurement, invia una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento tipo collegamento di `"d"`. Impostare l&#39;argomento del nome del collegamento sul valore desiderato:

```js
s.tl(true,"d","Example download link");
```

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting. Se non viene fornito alcun nome di collegamento, gli elementi dimensione vengono visualizzati come URL non elaborati. Questi URL non elaborati sono più difficili da interpretare nei rapporti, quindi fornisci un nome di collegamento descrittivo laddove possibile.
