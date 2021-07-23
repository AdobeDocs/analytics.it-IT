---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento su cui si trovava un visitatore prima di fare clic sul sito.
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 1%

---

# Dominio di riferimento originale

La dimensione &quot;Dominio di riferimento originale&quot; riporta il primo dominio di riferimento che un visitatore ha fatto clic per raggiungere il tuo sito. Una volta impostato, contiene lo stesso valore per l&#39;intera durata dell&#39;ID visitatore. Questa dimensione è utile per capire quali siti di terze parti originariamente indirizzano il traffico al sito.

>[!IMPORTANT]
>
>Per utilizzare questa dimensione, devi configurare i [filtri URL interni](/help/admin/admin/internal-url-filter-admin.md) della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione sia nell’interfaccia di Analytics che nell’implementazione.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla [`r` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `r` nelle richieste di immagini.
* Nell&#39;interfaccia di Analytics devi configurare i [filtri URL interni della suite di rapporti](/help/admin/admin/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

L&#39;Adobe persiste nel dominio di riferimento originale per tutta la durata di un visitatore. Se un visitatore lascia e fa clic su un collegamento su un dominio diverso in qualsiasi momento, il nuovo valore non viene registrato. Per visualizzare i nuovi valori, consulta [Dominio di riferimento](referring-domain.md).

## Elementi Dimension

Gli elementi di Dimension includono domini che i visitatori cliccano sul tuo sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l’elemento dimensione `"None"`. Questo elemento dimensione significa che non vi era alcun valore referente, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro.

## Confronta dominio di riferimento con dominio di riferimento originale

Il dominio di riferimento può cambiare tra le visite. Ad esempio, un visitatore arriva al tuo sito attraverso `google.com`, quindi una settimana dopo arriva al tuo sito attraverso `twitter.com`. Alla fine fanno un acquisto sul tuo sito. Se utilizzi il dominio di riferimento come dimensione con attribuzione ultimo contatto, `twitter.com` ottiene credito per l’acquisto. Se utilizzi come dimensione il dominio di riferimento originale, `google.com` ottiene credito per l’acquisto indipendentemente dal modello di attribuzione.

Il dominio di riferimento originale non cambia mai per l&#39;intera durata di un determinato ID visitatore.
