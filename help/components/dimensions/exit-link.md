---
title: Esci dal collegamento
description: Nome del collegamento di uscita.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# Esci dal collegamento

La dimensione &#39;Exit link&#39; segnala i nomi dei collegamenti di uscita implementati sul sito. Questa dimensione è preziosa quando si desidera capire quali collegamenti sono più popolari che puntano a domini esterni al sito.

## Compilare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla stringa [`pev2` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini per gli hit che dispongono anche della stringa di `pe` query con il valore di `lnk_e`. Se la stringa di `pe` query ha un valore diverso nell’hit, questa dimensione non raccoglie dati.

Se vuoi inviare dati a questa dimensione utilizzando AppMeasurement:

* Compilare la [`linkName`](/help/implement/vars/config-vars/linkname.md) variabile con il valore desiderato.
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"e"`.
* Invia una richiesta di [`tl()`](/help/implement/vars/functions/tl-method.md) immagine.

## Valori dimensione

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina i valori della dimensione. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
