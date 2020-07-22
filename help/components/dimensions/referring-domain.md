---
title: Dominio di riferimento
description: Il dominio di primo livello su cui era collocato un visitatore prima di passare al sito.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Dominio di riferimento

La dimensione &#39;Dominio di riferimento&#39; indica quali domini i visitatori selezionano per raggiungere il tuo sito. Questa dimensione è utile per capire quali siti di terze parti generano il maggior traffico verso i vostri. Un collegamento deve esistere sul sito esterno e un visitatore deve fare clic su di esso per visualizzare l’elemento dimensione.

>[!IMPORTANT]
>
>Devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Compilare questa dimensione con i dati

Questa dimensione richiede la configurazione nell&#39;interfaccia  Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla stringa [`r` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio del Adobe Experience Platform), questa dimensione non è disponibile. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `r` query nelle richieste di immagine.
* Nell&#39;interfaccia Analytics  devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Adobe continua a fare riferimento al dominio per una visita. Se un visitatore lascia e fa clic su un collegamento su un dominio diverso all’interno di una singola visita, il nuovo valore si aggiorna e persiste per il resto della visita. Se si desidera visualizzare solo il valore originale, vedere Dominio [di riferimento](original-referring-domain.md)originale.

## Elementi dimensione

Gli elementi dimensione includono i domini che i visitatori fanno clic sul sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione indica che non era presente alcun valore di referente, ad esempio se il visitatore digitava manualmente l&#39;indirizzo del browser nella barra degli indirizzi o faceva clic su un segnalibro.
