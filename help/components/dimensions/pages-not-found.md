---
title: Pagine non trovate (dimensioni)
description: URL che hanno restituito un errore sul sito.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 4%

---

# Pagine non trovate

*Questa pagina della Guida descrive il funzionamento di &quot;Pagine non trovate&quot; come [dimensione](overview.md). Consulta la pagina delle metriche [Pagine non trovate](../metrics/pages-not-found.md) per informazioni sul funzionamento come metrica.*

La dimensione &quot;Pagine non trovate&quot; mostra gli URL che contenevano un errore. Questa dimensione è utile quando desideri ridurre il numero di errori che i visitatori ricevono sul sito.

* Puoi utilizzare questa dimensione in una [Visualizzazione del flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per vedere quali pagine i visitatori fanno clic per raggiungere l&#39;errore. Puoi quindi lavorare con i team di sviluppo della tua organizzazione per correggere il collegamento su ogni pagina.
* Puoi utilizzare questa dimensione con la dimensione [&#39;Referrer&#39;](referrer.md) per vedere dove i visitatori arrivano al tuo sito da collegamenti esterni. Puoi quindi implementare i reindirizzamenti alla posizione desiderata o collaborare con terze parti per correggere il collegamento.

>[!NOTE]
>
>In Data Warehouse questa dimensione è denominata &#39;[!UICONTROL Page Type Error]&#39;.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalle stringhe di query [`pageType` e `g`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Se la stringa di query `pageType` è uguale a `errorPage`, viene registrata la stringa di query `g` (URL pagina). AppMeasurement raccoglie questi dati utilizzando la variabile [`pageType`](/help/implement/vars/page-vars/pagetype.md). Se la variabile `pageType` non è definita o impostata su un valore diverso da `errorPage`, non verranno raccolti dati per questa dimensione.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito in cui si è verificato un errore.
