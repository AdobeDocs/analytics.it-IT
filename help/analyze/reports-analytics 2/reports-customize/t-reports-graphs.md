---
description: Passaggi che descrivono come personalizzare il grafico in modo che sia più utile per il pubblico a cui è destinato.
title: Modificare i grafici dei rapporti
uuid: c2e81c6c-bfe9-4457-8b5d-512255ca9711
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a098b38-0939-4dd2-9a05-1b6b678f2d50
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 96%

---

# Modificare i grafici dei rapporti

{{ra-eol}}

Puoi personalizzare il grafico in modo che sia più utile per il pubblico a cui è destinato.

Il tipo di grafico disponibile dipende dal tipo di rapporto eseguito. Ad esempio, i grafici a linee di tendenza sono utili per i rapporti con tendenze, ma è anche possibile utilizzare un grafico a barre verticali con linee di tendenza che illustrano chiaramente le tendenze per giorni, settimane, mesi e così via. In alternativa, è possibile scegliere un grafico a torta per illustrare le percentuali relative alle pagine visualizzate.

Per modificare un grafico del rapporto:

1. Esegui un rapporto.
1. Fai clic su **[!UICONTROL Configure Graph]**.
1. Seleziona un tipo di grafico.

   **[!UICONTROL Trend Line]**: le linee di tendenza mostrano le tendenze giornaliere per le metriche del rapporto e sono utili per la tendenza di una metrica nel tempo per linea.

   ![](assets/graph_trend_line.png)

   **[!UICONTROL Smooth Line]**: utilizza questo tipo di grafico con [!UICONTROL Video Detail Report]. Mostra i numeri o le percentuali di visualizzazioni per segmenti specifici di un video. Un aumento delle visualizzazioni per un segmento specifico del video indica che gli utenti hanno riavvolto e visualizzato più volte quella sezione del video. Se utilizzi percentuali, la percentuale visualizzata nel grafico è riferita a tutti i segmenti visualizzati, non è una percentuale degli utenti che hanno guardato quel segmento. Ad esempio, nel grafico la somma di tutti i segmenti del rapporto è 39. Il numero di visualizzazioni per il segmento da 0 a 10 secondi è 10. Pertanto, la percentuale di visualizzazioni per questo segmento è approssimativamente il 26%.

   ![](assets/graph_smooth_line.png)

   **[!UICONTROL Area]**: il grafico a superficie è simile al grafico a linee di tendenza ma viene riempita l’area sotto le linee. Per visualizzare il grafico a superficie, è necessario visualizzare un rapporto con tendenze.

   ![](assets/graph_area.png)

   **[!UICONTROL Stacked Area]**: i grafici a superfici sovrapposte sono utili per presentare un numero di prodotti o campagne nel tempo. Ad esempio, se presenti i primi cinque prodotti che mostrano ricavi, puoi vedere rapidamente quanti ricavi totali generano nel tempo tali prodotti. Puoi perfezionare la visualizzazione utilizzando un filtro di ricerca per includere o escludere prodotti specifici.

   ![](assets/graph_stacked_area.png)

   **[!UICONTROL Vertical Bar]**: il grafico a barre verticali mostra le percentuali relative alle metriche del rapporto.

   ![](assets/graph_vertical_bars.png)

   **[!UICONTROL Stacked Vertical Bar]**: impilando elementi simili è possibile ottenere una visualizzazione rapida dell’influenza totale di un elemento. Ad esempio, in un [!UICONTROL Campaign Report], puoi impilare metriche di successo simili e vedere quale campagna genera il maggior successo totale. L’impilamento consente di trovare più facilmente le campagne che non sono le più performanti in una metrica, ma che lo sono in una combinazione di metriche.

   ![](assets/graph_stacked_vertical.png)

   **[!UICONTROL Horizontal Bar]**: il grafico a barre orizzontali è simile al grafico a barre verticali, ma le colonne sono orizzontali.

   ![](assets/graph_horizontal_bar.png)

   **[!UICONTROL Stacked Horizontal Bar]**: il grafico a barre orizzontali sovrapposte è simile al grafico a barre verticali, ma le colonne sono orizzontali.

   ![](assets/graph_stacked_horizontal.png)

   **[!UICONTROL Pie]**: il grafico a torta mostra le percentuali dei valori della metrica principali in relazione tra loro e mostra la percentuale delle metriche selezionate in relazione all’intero. È possibile visualizzare il grafico a torta per i rapporti con classifica.

   ![](assets/graph_pie.png)

   **[!UICONTROL Scatter]**: il grafico a dispersione mostra una visualizzazione a dispersione delle metriche selezionate tra loro. I grafici a dispersione consentono di visualizzare i dati in due dimensioni, in modo da identificare quali elementi sono meno importanti.

   ![](assets/graph_scatter.png)

   **[!UICONTROL Bubble]**: il grafico a bolle mostra una visualizzazione a bolle delle metriche selezionate in relazione tra loro. La posizione delle bolle mostra le relazioni tra le metriche sull’asse orizzontale e verticale, mentre la dimensione della bolla mostra la metrica principale del rapporto. I grafici a bolle consentono di visualizzare i dati in due dimensioni, in modo da identificare quali elementi sono anomali.

   ![](assets/graph_bubble.png)
