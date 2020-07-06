---
title: Referrer
description: L’URL a cui si trovava un visitatore prima di passare al sito.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Referrer

La dimensione &quot;Referente&quot; indica gli URL che i visitatori accedevano quando facevano clic per raggiungere il sito. Questa dimensione è utile per comprendere quali URL specifici generano il maggior traffico verso il sito. Un collegamento deve esistere sull’URL esterno e un visitatore deve fare clic su di esso per visualizzare il valore della dimensione.

>[!IMPORTANT]
>
>Devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Compilare questa dimensione con i dati

Questa dimensione richiede la configurazione nell&#39;interfaccia  Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla stringa [`r` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio del Adobe Experience Platform), questa dimensione non è disponibile. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `r` query nelle richieste di immagine.
* Nell&#39;interfaccia Analytics  devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Valori dimensione

I valori delle dimensioni includono URL che i visitatori potranno visionare attraverso il sito. Se un hit non dispone di dati di riferimento, viene raggruppato sotto il valore della dimensione `"Typed/Bookmarked"`. Questo valore di dimensione indica che non era presente alcun valore di riferimento, ad esempio se il visitatore digitava manualmente l&#39;indirizzo del browser nella barra degli indirizzi o faceva clic su un segnalibro.
