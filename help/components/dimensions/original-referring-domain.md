---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento su cui un visitatore si trovava prima di fare clic per passare al sito.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Dominio di riferimento originale

La dimensione &quot;Dominio di provenienza originale&quot; indica il primo dominio di provenienza su cui un visitatore ha fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata dell’ID visitatore. Questa dimensione è utile per comprendere quali siti di terze parti originariamente indirizzano il traffico al sito.

>[!IMPORTANT]
>
>Devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Compilare questa dimensione con i dati

Questa dimensione richiede la configurazione sia nell&#39;interfaccia Analytics  che nella sua implementazione.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla stringa [`r` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite  Adobe Experience Platform Launch), questa dimensione non è inclusa nella casella. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `r` query nelle richieste di immagine.
* Nell&#39;interfaccia Analytics  devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

 Adobe persiste il dominio di riferimento originale per la durata di un visitatore. Se un visitatore lascia e fa clic su un collegamento in un altro dominio in qualsiasi momento, il nuovo valore non viene registrato. Per visualizzare nuovi valori, vedere Dominio [di](referring-domain.md)riferimento.

## Elementi Dimension

Gli elementi di Dimension includono domini che i visitatori fanno clic sul sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l’elemento dimensione `"None"`. Questo elemento dimensione indica che non era presente alcun valore di referente, ad esempio se il visitatore digitava manualmente l&#39;indirizzo del browser nella barra degli indirizzi o faceva clic su un segnalibro.

## Confronta dominio di riferimento con dominio di riferimento originale

Il dominio di riferimento può cambiare tra le visite. Ad esempio, un visitatore arriva sul sito attraverso `google.com`, quindi una settimana dopo, arriva sul sito attraverso `twitter.com`. Alla fine effettuano un acquisto sul sito. Se si utilizza il dominio di riferimento come dimensione con l&#39;ultima attribuzione di tocco, `twitter.com` l&#39;acquisto viene accreditato. Se si utilizza il dominio di riferimento Originale come dimensione, `google.com` si ottiene credito per l&#39;acquisto indipendentemente dal modello di attribuzione.

Il dominio di riferimento originale non cambia mai per l’intera durata di un determinato ID visitatore.
