---
description: Elenca alcune considerazioni di cui tenere conto prima di eliminare i segmenti.
solution: Analytics
title: Eliminare segmenti
topic: Segments
uuid: cb6db6ad-f400-4633-900a-8a02dcfccf2c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Eliminare segmenti

Elenca alcune considerazioni di cui tenere conto prima di eliminare i segmenti.

Quando si elimina un segmento,

* I rapporti e le dashboard pianificati con questo segmento continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.
* I rapporti pianificati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Esempio: Supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

   ![](assets/duplicate_seg_names.png)

   È presente un segnalibro che fa riferimento al segmento della suite di rapporti principale. Quindi si elimina quel segmento perché è un duplicato. Il segnalibro continuerà a essere eseguito, facendo riferimento alla definizione del segmento eliminato. Se modificate la definizione del segmento per il segmento rimanente in modo da includere Catalina Island e Tijuana Mexico, il segmento applicato al segnalibro non subirà modifiche. Utilizzerà la vecchia definizione. Per risolvere il problema, aggiornare il segnalibro in modo che faccia riferimento alla nuova definizione. Se non sei sicuro se un segnalibro, una dashboard o un rapporto pianificato utilizza un segmento eliminato, puoi modificare il nome del segmento rimanente in modo che sia più chiaro se il segnalibro utilizza il segmento rimanente.

## Modifica di segmenti eliminati incorporati in Analisi ad hoc {#section_976D601DBD2244E38B0A0222E31D2610}

Ad Hoc Analysis now lets you edit embedded deleted segments within the [Calculated Metric Builder](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) and lets you perform a "Save As" operation on that segment.

Tuttavia, tutti gli altri segmenti eliminati che fanno riferimento al segmento eliminato rimarranno invariati.
