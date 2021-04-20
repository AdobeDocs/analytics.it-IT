---
description: Oltre alle opzioni di formattazione standard disponibili tramite la funzione Formato > Celle di Excel (Ctrl+1), è possibile applicare una formattazione limitata agli intervalli di celle con Report Builder. Queste scelte di formattazione dipendono dalla metrica scelta.
title: Formattare la data
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 7%

---


# Formattare la data

Oltre alle opzioni di formattazione standard disponibili tramite la funzione Formato > Celle di Excel (Ctrl+1), è possibile applicare una formattazione limitata agli intervalli di celle con Report Builder. Queste scelte di formattazione dipendono dalla metrica scelta.

Dopo aver [aggiunto dimensioni](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) alla griglia delle etichette delle righe, fare clic su **[!UICONTROL Format]**.

Nel menu **[!UICONTROL Format]** , fai clic su **[!UICONTROL Custom Format]** per applicare formati personalizzati per date simili alla funzione di inoltro e di inoltro. Ad esempio, puoi immettere testo che si verifica sempre dopo la data (ad esempio A.D. B.C.E. A.H. e così via). È possibile aggiungere testo prima della data, ad esempio [!UICONTROL Start Date] e [!UICONTROL Start and End Date]. Inoltre, puoi creare un’espressione data personalizzata a partire da abbreviazioni giorno, mese e anno e utilizzare un separatore personalizzato tra parti della data. Tutti i formati di data devono essere costituiti da tre abbreviazioni racchiuse solo tra parentesi.

La tabella seguente descrive come utilizzare le abbreviazioni di data nel campo [!UICONTROL Custom Format] :

| Abbreviazione | Significato | Esempio   con mercoledì 14 marzo 2012 |
|--- |--- |--- |
| gg/MM/aaaa | Data numerica completa | 14/03/2012 |
| M | Numero di mesi | 3 |
| MM | Numero di mesi con 0 spaziatura per mesi &lt; 10 | 03 |
| MMM | Nome breve del mese | mar |
| MMMM | Nome lungo del mese | Marzo |
| D | Nome lungo della data | Mercoledì 14 marzo 2012 |
| d | Numero di giorni | 14 |
| gg | Numero di giorni con spaziatura 0 per giorni &lt; 10 | 01 - 09 |
| ddd | Nome breve del giorno | Erba |
| dddd | Nome lungo del giorno | Mercoledì |
| yy | Anno a due cifre | 10 |
| aaaa | Anno completo a 4 cifre | 2012 |
