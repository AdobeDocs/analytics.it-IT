---
title: Pagine non trovate (dimensioni)
description: URL che hanno restituito un errore sul sito.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 2%

---

# Pagine non trovate

*Questa pagina della guida descrive come funziona &quot;Pagine non trovate&quot; come dimensione. Consulta la [Pagine non trovate](../metrics/pages-not-found.md) per ulteriori informazioni.*

La dimensione &quot;Pagine non trovate&quot; mostra gli URL che contenevano un errore. Questa dimensione è utile quando vuoi ridurre il numero di errori che il visitatore riceve sul tuo sito.

* Puoi utilizzare questa dimensione in una [Visualizzazione del flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per vedere quali pagine i visitatori fanno clic per raggiungere l’errore. Puoi quindi lavorare con i team di sviluppo della tua organizzazione per correggere il collegamento su ogni pagina.
* Puoi utilizzare questa dimensione con [&#39;Referrer&#39;](referrer.md) per vedere dove i visitatori arrivano al sito da collegamenti esterni. Puoi quindi implementare i reindirizzamenti alla posizione desiderata o collaborare con terze parti per correggere il collegamento.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`pageType` e `g` stringhe di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Se il `pageType` stringa di query uguale a `errorPage`, il `g` stringa di query (URL della pagina) registrata. AppMeasurement raccoglie questi dati utilizzando [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabile. Se il `pageType` la variabile non è definita o impostata su un valore diverso da `errorPage`, non vengono raccolti dati per questa dimensione.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito in cui si è verificato un errore.
