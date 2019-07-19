---
description: Elenca alcune considerazioni da considerare prima di eliminare i segmenti.
seo-description: Elenca alcune considerazioni da considerare prima di eliminare i segmenti.
seo-title: Eliminare i segmenti
solution: Analytics
title: Eliminare i segmenti
topic: Segmenti
uuid: cb 6 db 6 ad-f 400-4633-900 a -8 a 02 dcfccf 2 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Eliminare i segmenti

Elenca alcune considerazioni da considerare prima di eliminare i segmenti.

Quando eliminate un segmento,

* I report pianificati e le dashboard in cui questo segmento è applicato continuano a funzionare normalmente, ovvero il segmento o il dashboard continua a utilizzare il segmento eliminato.
* I rapporti pianificati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Esempio: Supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

   ![](assets/duplicate_seg_names.png)

   Hai un segnalibro che fa riferimento al segmento per la suite di rapporti principale. Quindi, eliminate il segmento perché si tratta di un duplicato. Il segnalibro continua a essere eseguito facendo riferimento alla definizione del segmento eliminato. Se modifichi la definizione del segmento per il segmento rimanente in modo che includa Catalina Island e Tijuana Mexico, il segmento applicato al segnalibro non cambierà. Verrà utilizzata la vecchia definizione. Per risolvere questo problema, aggiornare il segnalibro per fare riferimento alla nuova definizione. Se non sei sicuro se un segnalibro, un dashboard o un rapporto pianificato utilizzi un segmento eliminato, potresti modificare il nome del segmento rimanente in modo da chiarire se il segnalibro utilizza il segmento rimanente.

## Edit Embedded Deleted Segments in Ad Hoc Analysis {#section_976D601DBD2244E38B0A0222E31D2610}

Ad Hoc Analysis now lets you edit embedded deleted segments within the [Calculated Metric Builder](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) and lets you perform a "Save As" operation on that segment.

Tuttavia, tutti gli altri segmenti eliminati che fanno riferimento al segmento eliminato rimarranno invariati.
