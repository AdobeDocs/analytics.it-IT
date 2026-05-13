---
title: Collegamento di uscita
description: Nome del collegamento di uscita.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 225
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
