---
description: Elenca alcune valutazioni di cui tenere conto prima di eliminare i segmenti.
title: Eliminare segmenti
topic: Segments
uuid: cb6db6ad-f400-4633-900a-8a02dcfccf2c
translation-type: ht
source-git-commit: 9e70cd51f8828cdcb698175a2b4c0150610d14d0
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---


# Eliminare segmenti

Elenca alcune valutazioni di cui tenere conto prima di eliminare i segmenti.

Quando elimini un segmento,

* I rapporti e le dashboard programmati con questo segmento applicato continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.
* I rapporti programmati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Ad esempio, supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

   ![](assets/duplicate_seg_names.png)

   È presente un segnalibro che fa riferimento al segmento per la suite di rapporti principale. Quel segmento viene quindi eliminato in quanto si tratta di un duplicato. Il segnalibro continuerà a essere eseguito e farà riferimento alla definizione del segmento eliminato. Se modifichi la definizione del segmento per il segmento rimanente in modo da includere Isola di Catalina e Tijuana Messico, il segmento applicato al segnalibro non subirà modifiche e utilizzerà la vecchia definizione. Per risolvere il problema, aggiorna il segnalibro in modo che faccia riferimento alla nuova definizione. Se hai dubbi sul fatto che un segnalibro, una dashboard o un rapporto programmato utilizzino un segmento eliminato, modifica il nome del segmento rimanente in modo che risulti più chiaro se il segnalibro lo sta utilizzando.

## Modificare i segmenti eliminati incorporati in Ad Hoc Analysis {#section_976D601DBD2244E38B0A0222E31D2610}

Ad Hoc Analysis ora consente di modificare i segmenti integrati eliminati nel [generatore di metriche calcolate](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/cm-overview.html) e di eseguire un’operazione “Salva con nome” sul segmento.

Tuttavia, tutti gli altri segmenti eliminati che fanno riferimento al segmento eliminato rimarranno invariati.
