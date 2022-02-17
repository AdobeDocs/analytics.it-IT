---
description: Mostra come creare una semplice metrica "Visualizzazioni pagina per visita".
title: Creare una semplice metrica "Visualizzazioni pagina in base alle visite"
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 6%

---

# Creare una semplice metrica &quot;Visualizzazioni pagina in base alle visite&quot;

Mostra come creare una semplice metrica &quot;Visualizzazioni pagina per visita&quot;.

Per una descrizione dettagliata dei componenti dell’interfaccia utente, vedi [Creazione di metriche](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

Ecco come creare una semplice metrica &quot;Visualizzazioni pagina per visita&quot;.

1. Passa al Generatore di metrica calcolata.
1. Denomina la metrica &quot;Visualizzazioni pagina per visita&quot; o qualcosa di simile.
1. Dagli un facile utilizzo **[!UICONTROL Description]** per mostrare a cosa serve.
1. Seleziona a destra **[!UICONTROL Format]**, in questo caso Decimal.
1. Decidere quante posizioni decimali visualizzare nel rapporto.
1. Imposta la polarità della metrica. Per questa metrica, una tendenza al rialzo sarebbe una buona cosa (verde).
1. Aggiungi un **[!UICONTROL Tag]** per organizzare le metriche.
1. Per questa metrica, trascina innanzitutto Visualizzazioni di pagina nell’area di lavoro, quindi trascina Visite sotto (aspetta che appaia la linea blu per rilasciarla).
1. Selezionare l’operatore Dividi. (Dividi è l’operatore predefinito.)
1. Ora è possibile visualizzare un **[!UICONTROL Preview]** di quella metrica mentre la stai costruendo, in alto a destra.
1. La compatibilità del prodotto mostra se la metrica è compatibile con [Dati correnti](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) o solo con dati completamente elaborati.
1. Fai clic su **[!UICONTROL Save]**.
1. Tieni presente che **[!UICONTROL Summary]** La formula viene aggiornata ogni volta che apporti una modifica alla definizione della metrica.
1. Ora viene automaticamente portato al [Gestore della metrica calcolata](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), simile al Gestore segmenti. Ti consente di condividere, approvare, (ri)assegnare tag, rinominare o eliminare metriche.
