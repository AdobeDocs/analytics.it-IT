---
description: Oltre alle opzioni di formattazione delle celle standard disponibili tramite la funzione Formato > Celle (Ctrl +1) di Excel, è possibile applicare una formattazione limitata agli intervalli di celle con generatore di report. Queste scelte di formattazione dipendono dalla metrica scelta.
seo-description: Oltre alle opzioni di formattazione delle celle standard disponibili tramite la funzione Formato > Celle (Ctrl +1) di Excel, è possibile applicare una formattazione limitata agli intervalli di celle con generatore di report. Queste scelte di formattazione dipendono dalla metrica scelta.
seo-title: Formattare la data
solution: Analytics
title: Formattare la data
topic: Generatore di report
uuid: 5211 db 30-07 b 3-4413-97 c 3-e 40 e 6 ff 223 cd
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Formattare la data

Oltre alle opzioni di formattazione delle celle standard disponibili tramite la funzione Formato &gt; Celle (Ctrl +1) di Excel, è possibile applicare una formattazione limitata agli intervalli di celle con generatore di report. Queste scelte di formattazione dipendono dalla metrica scelta.

After you [add dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) to the Row Labels grid, click **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. Ad esempio, potete inserire un testo che si verifica sempre dopo la data (ad esempio, A.D.B.C.E.A.H.). You can add text before the date, such as [!UICONTROL Start Date] and [!UICONTROL Start and End Date]. Inoltre, è possibile creare un'espressione data personalizzata dalle abbreviazioni giorno, mese e anno e utilizzare un separatore personalizzato tra parti della data. Tutti i formati di data devono essere composti da tre abbreviazioni solo racchiuse tra parentesi.

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field:

| Abbreviazione | Significato | Esempio di utilizzo di mercoledì 14 marzo 2012 |
|--- |--- |--- |
| MM/gg/yyy | Data numerica completa | 03/14/2012 |
| M | Numero di mesi | 3 |
| MM | Numero di mesi con riempimento 0 per mesi &lt; 10 | 03 |
| MMM | Nome breve del mese | Mar |
| MMMM | Nome esteso del mese | Marzo |
| D | Nome esteso della data | Mercoledì 14 marzo 2012 |
| d | Numero di giorni | 14 |
| dd | Numero di giorni con riempimento 0 per giorni &lt; 10 | 01 - 09 |
| ddd | Nome breve del giorno | Wed |
| dddd | Nome esteso del giorno | Mercoledì |
| yy | Anno di 2 cifre | 10 |
| yyyy | Anno completo di 4 cifre | 2012 |