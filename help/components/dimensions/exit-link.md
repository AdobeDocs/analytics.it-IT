---
title: Collegamento di uscita
description: Nome del collegamento di uscita.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 4%

---

# Collegamento di uscita

La [dimensione](overview.md) del &#39;collegamento di uscita&#39; riporta i nomi dei collegamenti di uscita implementati nel sito. I collegamenti di uscita tengono traccia dei clic in uscita che allontanano i visitatori dal dominio corrente. Questa dimensione è utile quando desideri comprendere quali collegamenti in uscita vengono cliccati più frequentemente.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`pev2`](/help/implement/validate/query-parameters.md) nelle richieste di immagini, a seconda del valore nella stringa di query `pe`. La stringa di query `pe` determina la dimensione di collegamento che riceve il valore `pev2`:

* **[Collegamento personalizzato](custom-link.md)**: `lnk_o`
* **[Collegamento di download](download-link.md)**: `lnk_d`
* **Collegamento di uscita** (questa pagina): `lnk_e`

Se `pev2` non viene fornito, verrà utilizzato come valore della dimensione l&#39;URL del collegamento (`pev1`). Quando il nome di un collegamento viene specificato in modo esplicito, la lunghezza massima è di 100 byte. I valori derivati dall’URL del collegamento non sono soggetti a questo limite.

Per popolare questa dimensione utilizzando AppMeasurement, invia una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento tipo collegamento di `"e"`. Impostare l&#39;argomento del nome del collegamento sul valore desiderato:

```js
s.tl(true,"e","Example exit link");
```

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting. Se non viene fornito alcun nome di collegamento, gli elementi dimensione vengono visualizzati come URL non elaborati. Questi URL non elaborati sono più difficili da interpretare nei rapporti, quindi fornisci un nome di collegamento descrittivo laddove possibile.
