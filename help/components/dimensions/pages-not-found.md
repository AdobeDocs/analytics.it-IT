---
title: Pagine non trovate
description: URL che hanno restituito un errore sul sito.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---


# Pagine non trovate

*Questa pagina della guida descrive il funzionamento di &quot;Pagine non trovate&quot; come una dimensione. Per ulteriori informazioni, vedere la metrica[Pagine non trovate](../metrics/pages-not-found.md).*

La dimensione &quot;Pagine non trovate&quot; mostra gli URL che contenevano un errore. Questa dimensione è utile per ridurre il numero di errori che il visitatore riceve sul sito.

* Puoi usare questa dimensione in una visualizzazione [](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) Flusso per vedere quali pagine i visitatori passano attraverso per raggiungere l’errore. Potete quindi lavorare con i team di sviluppo della vostra organizzazione per correggere il collegamento su ogni pagina.
* Puoi utilizzare questa dimensione con la dimensione [&quot;Referente&quot;](referrer.md) per vedere dove arrivano i visitatori sul tuo sito dai collegamenti esterni. Potete quindi implementare i reindirizzamenti alla posizione desiderata oppure collaborare con la terza parte per risolvere il collegamento.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalle [`pageType` stringhe `g`](/help/implement/validate/query-parameters.md) di query e query nelle richieste di immagini. Se la stringa di `pageType` query è uguale a `errorPage`, viene registrata la stringa di `g` query (URL pagina). AppMeasurement raccoglie questi dati utilizzando la [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabile. Se la `pageType` variabile non è definita o impostata su un valore diverso da `errorPage`, non viene raccolto alcun dato per questa dimensione.

## Valori dimensione

I valori delle dimensioni includono gli URL delle pagine del sito in cui si è verificato un errore.
