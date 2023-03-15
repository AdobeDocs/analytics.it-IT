---
description: Il pannello di impostazione Activity Map consente di modificare le impostazioni e le proprietà per tutti i tipi di visualizzazioni di sovrapposizione.
title: Configurare le impostazioni di Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 5%

---

# Configurare le impostazioni di Activity Map

Il pannello di impostazione Activity Map consente di modificare le impostazioni e le proprietà per tutti i tipi di visualizzazioni di sovrapposizione.

Per accedere al pannello Impostazioni Activity Map, fai clic sull’icona a forma di ingranaggio nella barra degli strumenti Activity Map.

## Impostazioni generali {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Companies]** | Seleziona la società di accesso applicabile. |
| **[!UICONTROL Report Suite]** | L’elenco delle suite di rapporti a cui puoi accedere non è più limitato alle suite di rapporti definite nel tag della pagina web. Ora puoi sostituire la suite di rapporti selezionata (corrispondente a uno dei tag nella pagina) con un’altra suite di rapporti. La nuova suite di rapporti non deve necessariamente essere collegata a un tag sulla pagina. Se modifichi la suite di rapporti selezionata nelle Impostazioni Activity Map, il processo di salvataggio aggiorna tutti i rapporti Analytics interessati.<br>**Importante**: [!UICONTROL Virtual Report Suites] non sono compatibili con [!UICONTROL Live Mode], solo con [!UICONTROL Standard Mode]. Se ti trovi in [!UICONTROL Live Mode] per una suite di rapporti standard, ma seleziona una [!UICONTROL Virtual Report Suite] in questa finestra di dialogo, dopo aver fatto clic su **[!UICONTROL OK]** in questo caso viene visualizzata la modalità Standard. Inoltre, il controllo Calendar viene reinizializzato per corrispondere al tipo di calendario della suite di rapporti (gregoriano, al dettaglio, personalizzato...). |
| **[!UICONTROL Page Name]** | Pagina a cui si applicano queste impostazioni. |
| **[!UICONTROL Language]** | La selezione corrisponde alle lingue offerte per Adobe Analytics. |
| **[!UICONTROL Label Overlays With]** | <ul><li>**[!UICONTROL No Label]**: applicabile solo per la sovrapposizione sfumatura. In questo caso, il colore della sovrapposizione trasmette un senso per la classificazione del collegamento</li><li>**[!UICONTROL Value]**: totale delle metriche non elaborate per il collegamento</li><li>**[!UICONTROL Percent]**: percentuale della metrica per questo collegamento sulla metrica totale della pagina.</li><li>**[!UICONTROL Rank]**: classificazione di questo collegamento tra tutti i collegamenti presenti nella pagina sottoposta a rendering</li></ul> |
| **[!UICONTROL Label Font Size]** | Consente di aumentare/diminuire la dimensione del font dell’etichetta di sovrapposizione utilizzando un cursore, per una migliore leggibilità. |
| **[!UICONTROL Gradient/Bubble Color]** | Per visualizzare le classificazioni dei collegamenti di sovrapposizione per le visualizzazioni Sovrapposizione sfumatura o bolla, seleziona una gamma di colori. |
| **[!UICONTROL Color Gradient Based On]** | <ul><li>**[!UICONTROL Top 30 Rankings]**: l’intensità del colore è normalizzata per i primi 30 valori.</li><li>**[!UICONTROL Absolute Metric Value]**: l’intensità del colore è una funzione del valore metrico assoluto.</li></ul> |
| **[!UICONTROL Gradient Transparency]** | Selezionare il livello di trasparenza per le sovrapposizioni sfumatura. Questa impostazione non influisce sul [!UICONTROL Bubble] sovrapposizioni. |

## Impostazioni standard {#section_24DB95376E1A448494ECF3F57743FC19}

Queste impostazioni si applicano alla sovrapposizione in modalità standard.

![](assets/settings_standard.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Dynamic Data Filtering]** | Questo menu a discesa consente di visualizzare le sovrapposizioni per<ul><li>(impostazione predefinita) Tutti i collegamenti nella pagina</li><li>Il primo (più alto) o il primo (più basso) numero di collegamenti classificati nella pagina, dove # può essere un numero di 1, 10, 50 o 100.</li></ul> |
| **[!UICONTROL Hide overlays for links that received no hits]**. | Casella di controllo che attiva la visibilità delle sovrapposizioni per i collegamenti privi di dati.<ul><li>(impostazione predefinita) Se la casella di controllo è selezionata, non viene visualizzata alcuna sovrapposizione quando un collegamento non contiene dati di collegamento ActivityMap.</li><li>Se la casella di controllo è deselezionata, allora se un collegamento non ha dati di collegamento ActivityMap, viene visualizzata una sovrapposizione e ha un’etichetta &quot;-&quot;, che significa N/A (non applicabile). |

## Impostazioni Live {#section_D30F6E62FB5D404090B588F396A460AF}

Queste impostazioni si applicano alla sovrapposizione della modalità live.

![](assets/settings_live.png)

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Display Top]** | Per visualizzare **[!UICONTROL Gainers]** o **[!UICONTROL Losers]** (o entrambi) come sovrapposizioni, seleziona il numero di collegamenti. |
| **[!UICONTROL Exclude bottom (%)]** | Seleziona questa opzione per eliminare i collegamenti Gainers-Losers con dati sparsi. Escludi la percentuale inferiore di modifiche collegamento per visualizzare solo i collegamenti con un numero di dati sufficiente per mostrare guadagni o perdite rilevanti. La percentuale viene calcolata in base al numero di collegamenti presenti nella pagina. Ad esempio, se si esclude il 10% inferiore di un elenco di 200 collegamenti, i 20 collegamenti inferiori verranno filtrati. |
| **[!UICONTROL Auto Update Data]** | Consente di decidere se i dati di Analytics mostrati nell’interfaccia devono essere aggiornati automaticamente quando viene calcolato un nuovo periodo. |
| **[!UICONTROL Auto Update Period]** | Se questa opzione è selezionata, aggiorna la pagina web con ogni nuovo recupero di dati, in modo che i collegamenti nella pagina possano essere sincronizzati più strettamente con i dati raccolti. |
