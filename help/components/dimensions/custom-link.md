---
title: Collegamento personalizzato
description: Nome del collegamento personalizzato.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 5c1d50fa09b0fad228f24018de2b062d09b0fe5f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---

# Collegamento personalizzato

La [dimensione](overview.md) del &#39;collegamento personalizzato&#39; riporta i nomi dei collegamenti personalizzati implementati nel sito. I collegamenti personalizzati sono un meccanismo di tracciamento flessibile per qualsiasi interazione che non sia il download di un file o la navigazione in uscita. Esempi comuni includono clic su pulsanti, navigazione interna o interazioni con moduli. Questa dimensione è utile quando desideri capire quale di queste interazioni coinvolge di più i visitatori.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`pev2`](/help/implement/validate/query-parameters.md) nelle richieste di immagini, a seconda del valore nella stringa di query `pe`. La stringa di query `pe` determina la dimensione di collegamento che riceve il valore `pev2`:

* **Collegamento personalizzato** (questa pagina): `lnk_o`
* **[Collegamento di download](download-link.md)**: `lnk_d`
* **[Collegamento di uscita](exit-link.md)**: `lnk_e`

Se `pev2` non viene fornito, verrà utilizzato come valore della dimensione l&#39;URL del collegamento (`pev1`). Quando il nome di un collegamento viene specificato in modo esplicito, la lunghezza massima è di 100 byte. I valori derivati dall’URL del collegamento non sono soggetti a questo limite.

Per popolare questa dimensione utilizzando AppMeasurement, invia una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento tipo collegamento di `"o"`. Impostare l&#39;argomento del nome del collegamento sul valore desiderato:

```js
s.tl(true,"o","Example custom link");
```

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting. Se non viene fornito alcun nome di collegamento, gli elementi dimensione vengono visualizzati come URL non elaborati. Questi URL non elaborati sono più difficili da interpretare nei rapporti, quindi fornisci un nome di collegamento descrittivo laddove possibile.
