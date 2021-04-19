---
description: Elenca alcune valutazioni di cui tenere conto prima di eliminare i segmenti.
title: Eliminare segmenti
feature: Segmentazione
uuid: cb6db6ad-f400-4633-900a-8a02dcfccf2c
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 100%

---

# Eliminare segmenti

Elenca alcune valutazioni di cui tenere conto prima di eliminare i segmenti.

Quando elimini un segmento,

* I rapporti e le dashboard programmati con questo segmento applicato continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.
* I rapporti programmati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Ad esempio, supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

   ![](assets/duplicate_seg_names.png)

   È presente un segnalibro che fa riferimento al segmento per la suite di rapporti principale. Quel segmento viene quindi eliminato in quanto si tratta di un duplicato. Il segnalibro continuerà a essere eseguito e farà riferimento alla definizione del segmento eliminato. Se modifichi la definizione del segmento per il segmento rimanente in modo da includere Isola di Catalina e Tijuana Messico, il segmento applicato al segnalibro non subirà modifiche e utilizzerà la vecchia definizione. Per risolvere il problema, aggiorna il segnalibro in modo che faccia riferimento alla nuova definizione. Se hai dubbi sul fatto che un segnalibro, una dashboard o un rapporto programmato utilizzino un segmento eliminato, modifica il nome del segmento rimanente in modo che risulti più chiaro se il segnalibro lo sta utilizzando.
