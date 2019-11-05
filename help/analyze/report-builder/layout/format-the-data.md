---
description: Oltre alle opzioni di formattazione standard disponibili tramite la funzione Formato > Celle di Excel (Ctrl+1), con il generatore di report puoi applicare una formattazione limitata agli intervalli di celle. Queste scelte di formattazione dipendono dalla metrica scelta.
seo-description: Oltre alle opzioni di formattazione standard disponibili tramite la funzione Formato > Celle di Excel (Ctrl+1), con il generatore di report puoi applicare una formattazione limitata agli intervalli di celle. Queste scelte di formattazione dipendono dalla metrica scelta.
seo-title: Formattare la data
solution: Analytics
title: Formattare la data
topic: Generatore di report
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# Formattare la data

Oltre alle opzioni di formattazione standard disponibili tramite la funzione Formato &gt; Celle di Excel (Ctrl+1), con il generatore di report puoi applicare una formattazione limitata agli intervalli di celle. Queste scelte di formattazione dipendono dalla metrica scelta.

Dopo aver [aggiunto le dimensioni](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) alla griglia Etichette righe, fare clic su **[!UICONTROL Format]**.

Nel **[!UICONTROL Format]** menu, fate clic su **[!UICONTROL Custom Format]** per applicare formati personalizzati per date simili alla funzione di inoltro e postpend. Ad esempio, è possibile immettere testo che si verifica sempre dopo la data (ad esempio A.D. B.C.E. A.H. ecc.). Potete aggiungere del testo prima della data, ad esempio [!UICONTROL Start Date] e [!UICONTROL Start and End Date]. È inoltre possibile creare un'espressione data personalizzata a partire da abbreviazioni di giorno, mese e anno, e utilizzare un separatore personalizzato tra parti della data. Tutti i formati di data devono essere composti da tre abbreviazioni racchiuse tra parentesi.

La tabella seguente descrive come utilizzare le abbreviazioni di data nel [!UICONTROL Custom Format] campo:

| Abbreviazione | Significato | Esempio con mercoledì 14 marzo 2012 |
|--- |--- |--- |
| MM/gg/aaaa | Data intera numerica | 03/14/2012 |
| M | Numero di mesi | 3 |
| MM | Numero di mesi con 0 riempimento per mesi &lt; 10 | 03 |
| MMM | Nome breve del mese | Mar |
| MMMM | Nome lungo del mese | marzo |
| D | Nome lungo della data | mercoledì 14 marzo 2012 |
| d | Numero di giorni | 14 |
| dd | Numero di giorni con 0 spazi per giorni &lt; 10 | 01 - 09 |
| ddd | Nome abbreviato del giorno | Wed |
| dddd | Nome completo del giorno | mercoledì |
| yy | anno di 2 cifre | 10 |
| yyyy | Anno completo a 4 cifre | 2012 |
