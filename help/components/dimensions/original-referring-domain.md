---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento su cui un visitatore si trovava prima di fare clic per passare al sito.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---


# Dominio di riferimento originale

La dimensione &quot;Dominio di provenienza originale&quot; indica il primo dominio di provenienza su cui un visitatore ha fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata dell’ID visitatore. Questa dimensione è utile per comprendere quali siti di terze parti originariamente indirizzano il traffico al sito.

## Compilare questa dimensione con i dati

Questa dimensione richiede la configurazione sia nell&#39;interfaccia di Analytics che nell&#39;implementazione.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla stringa [`r` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite Adobe Experience Platform Launch), questa dimensione non è disponibile. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `r` query nelle richieste di immagine.
* Nell&#39;interfaccia di Analytics devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Adobe persiste nel dominio di riferimento originale per tutta la durata di un visitatore. Se un visitatore lascia e fa clic su un collegamento in un altro dominio in qualsiasi momento, il nuovo valore non viene registrato. Per visualizzare nuovi valori, vedere Dominio [di](referring-domain.md)riferimento.

## Valori dimensione

I valori delle dimensioni includono domini che i visitatori possono selezionare nel sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto il valore della dimensione `"None"`. Questo valore di dimensione indica che non era presente alcun valore di riferimento, ad esempio se il visitatore digitava manualmente l&#39;indirizzo del browser nella barra degli indirizzi o faceva clic su un segnalibro.
