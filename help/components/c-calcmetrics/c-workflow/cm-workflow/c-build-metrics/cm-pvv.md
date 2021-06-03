---
description: Mostra come creare una semplice metrica "Visualizzazioni pagina per visita".
title: Creare una semplice metrica "Visualizzazioni pagina in base alle visite"
uuid: 0730e51c-1f8f-473b-8825-d72911f2944c
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 6%

---

# Creare una semplice metrica &quot;Visualizzazioni pagina in base alle visite&quot;

Mostra come creare una semplice metrica &quot;Visualizzazioni pagina per visita&quot;.

Per una descrizione dettagliata dei componenti dell&#39;interfaccia utente, consulta [Creazione di metriche](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

Ecco come creare una semplice metrica &quot;Visualizzazioni pagina per visita&quot;.

1. Passa al Generatore di metrica calcolata.
1. Denomina la metrica &quot;Visualizzazioni pagina per visita&quot; o qualcosa di simile.
1. Fornisci un **[!UICONTROL Description]** intuitivo per mostrare a cosa serve.
1. Seleziona il **[!UICONTROL Format]** a destra, in questo caso Decimal.
1. Decidere quante posizioni decimali visualizzare nel rapporto.
1. Imposta la polarità della metrica. Per questa metrica, una tendenza al rialzo sarebbe una buona cosa (verde).
1. Aggiungi un **[!UICONTROL Tag]** per organizzare le metriche.
1. Per questa metrica, trascina innanzitutto Visualizzazioni di pagina nell’area di lavoro, quindi trascina Visite sotto (aspetta che appaia la linea blu per rilasciarla).
1. Selezionare l’operatore Dividi. (Dividi è l’operatore predefinito.)
1. Ora puoi vedere una **[!UICONTROL Preview]** di quella metrica mentre la stai creando, in alto a destra.
1. La compatibilità del prodotto indica se la metrica è compatibile con [Dati correnti](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) o solo con dati completamente elaborati.
1. Fai clic su **[!UICONTROL Save]**.
1. La formula **[!UICONTROL Summary]** viene aggiornata ogni volta che apporti una modifica alla definizione della metrica.
1. Ora viene automaticamente visualizzato il [Gestore della metrica calcolata](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), simile al Gestore segmenti. Ti consente di condividere, approvare, (ri)assegnare tag, rinominare o eliminare metriche.
