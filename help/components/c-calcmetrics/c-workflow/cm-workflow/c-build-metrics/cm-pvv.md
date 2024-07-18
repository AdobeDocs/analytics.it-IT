---
description: Mostra come creare una semplice metrica "Visualizzazioni pagina in base alle visite".
title: Creare una semplice metrica “Visualizzazioni pagina in base alle visite”
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 7%

---

# Creare una metrica “Visualizzazioni pagina in base alle visite”

Le informazioni seguenti spiegano come creare una semplice metrica &quot;Visualizzazioni pagina in base alle visite&quot;.

Per creare una semplice metrica &quot;Visualizzazioni pagina in base alle visite&quot;:

1. Inizia a creare una metrica, come descritto in [Metriche di compilazione](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. Denomina la metrica &quot;Visualizzazioni pagina in base alle visite&quot; o qualcosa di simile.
1. Assegnagli un **[!UICONTROL Description]** intuitivo per mostrare a cosa serve.
1. Seleziona **[!UICONTROL Format]** a destra. Per questo esempio, scegli [!UICONTROL **Decimal**].
1. Decidi quante cifre decimali visualizzare nel rapporto.
1. Nel menu a discesa [!UICONTROL **Mostra tendenza verso l&#39;alto come**], seleziona [!UICONTROL **Buono (verde)**].
1. Aggiungi **[!UICONTROL Tag]** per organizzare le metriche.
1. Per questa metrica, trascina Visualizzazioni pagina nella sezione [!UICONTROL **Definizione**] dell&#39;area di lavoro, quindi trascina Visite sotto di essa (attendi che la linea blu venga visualizzata prima di rilasciarla).
1. Selezionare l&#39;operatore Dividi. (Dividi è l&#39;operatore predefinito).
1. È ora possibile visualizzare **[!UICONTROL Preview]** di tale metrica mentre la si sta creando, in alto a destra.
1. La compatibilità del prodotto indica se la metrica è compatibile con [Dati correnti](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) o solo con Dati completamente elaborati.
1. Seleziona **[!UICONTROL Save]**.

   La formula **[!UICONTROL Summary]** viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica.

1. (Facoltativo) Per condividere, approvare, (ri)assegnare tag, rinominare o eliminare una metrica, passare alla [pagina Metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).
