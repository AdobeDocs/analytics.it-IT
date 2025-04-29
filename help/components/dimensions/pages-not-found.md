---
title: Pagine non trovate (dimensioni)
description: URL che hanno restituito un errore sul sito.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 828f41bf45c1954c3b68ad71a7746e24626b9eed
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Pagine non trovate

*Questa pagina della Guida descrive il funzionamento di &quot;Pagine non trovate&quot; come [dimensione](overview.md). Consulta la pagina delle metriche [Pagine non trovate](../metrics/pages-not-found.md) per informazioni sul funzionamento come metrica.*

La dimensione &quot;Pagine non trovate&quot; mostra gli URL che contenevano un errore. Questa dimensione è utile quando desideri ridurre il numero di errori che i visitatori ricevono sul sito.

* Puoi utilizzare questa dimensione in una [Visualizzazione del flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per vedere quali pagine i visitatori fanno clic per raggiungere l&#39;errore. Puoi quindi lavorare con i team di sviluppo della tua organizzazione per correggere il collegamento su ogni pagina.
* Puoi utilizzare questa dimensione con la dimensione [&#39;Referrer&#39;](referrer.md) per vedere dove i visitatori arrivano al tuo sito da collegamenti esterni. Puoi quindi implementare i reindirizzamenti alla posizione desiderata o collaborare con terze parti per correggere il collegamento.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalle stringhe di query [`pageType` e `g`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Se la stringa di query `pageType` è uguale a `errorPage`, viene registrata la stringa di query `g` (URL pagina). AppMeasurement raccoglie questi dati utilizzando la variabile [`pageType`](/help/implement/vars/page-vars/pagetype.md). Se la variabile `pageType` non è definita o impostata su un valore diverso da `errorPage`, non verranno raccolti dati per questa dimensione.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito in cui si è verificato un errore.
