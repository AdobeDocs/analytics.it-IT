---
description: Elenca alcune valutazioni di cui tenere conto prima di eliminare i segmenti.
title: Eliminare segmenti
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 38%

---

# Eliminare segmenti

In questo articolo sono elencate alcune considerazioni di cui tenere conto prima di eliminare i segmenti.

Quando elimini un segmento:

* I rapporti e le dashboard pianificati a cui è applicato questo segmento continuano a funzionare normalmente. Ad esempio, il segmento o il dashboard continua a utilizzare il segmento eliminato.
* I rapporti programmati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Esempio: supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

  | Nome segmento | Suite di rapporti |
  |---|---|
  | Visite dalla California | mainprod |
  | Visite dalla California | maindev |

  È presente un segnalibro che fa riferimento al segmento per la suite di rapporti [!UICONTROL mainprod]. Quindi elimini quel segmento perché è un duplicato. Il segnalibro continuerà a essere eseguito e farà riferimento alla definizione del segmento eliminato. Se modifichi la definizione del segmento per il segmento rimanente in modo da includere Isola di Catalina e Tijuana Messico, il segmento applicato al segnalibro non subirà modifiche e Il segmento utilizzerà la vecchia definizione. Per risolvere il problema, aggiorna il segnalibro in modo che faccia riferimento alla nuova definizione. Se non sei sicuro se un segnalibro, una dashboard o un rapporto programmato utilizzino un segmento eliminato, puoi modificare il nome del segmento rimanente per indicare se il segnalibro lo sta utilizzando.
