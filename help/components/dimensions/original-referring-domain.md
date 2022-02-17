---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento su cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 1%

---

# Dominio di riferimento originale

La dimensione &quot;Dominio di riferimento originale&quot; riporta il primo dominio di riferimento che un visitatore ha fatto clic per raggiungere il tuo sito. Una volta impostato, contiene lo stesso valore per l&#39;intera durata dell&#39;ID visitatore. Questa dimensione è utile per capire quali siti di terze parti originariamente indirizzano il traffico al sito.

>[!IMPORTANT]
>
>Devi configurare i [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md) per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione sia nell’interfaccia di Analytics che nell’implementazione.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla [`r` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il `r` parametro della stringa query nelle richieste di immagini.
* All’interno dell’interfaccia di Analytics, devi configurare i [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

L&#39;Adobe persiste nel dominio di riferimento originale per tutta la durata di un visitatore. Se un visitatore lascia e fa clic su un collegamento su un dominio diverso in qualsiasi momento, il nuovo valore non viene registrato. Per visualizzare i nuovi valori, consulta [Dominio di riferimento](referring-domain.md).

## Elementi Dimension

Gli elementi di Dimension includono domini che i visitatori cliccano sul tuo sito. Se un hit non ha dati di riferimento (impostati o persistenti), si raggruppa sotto l’elemento dimensione `"None"`. Questo elemento dimensione significa che non vi era alcun valore referente, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro.

## Confronta dominio di riferimento con dominio di riferimento originale

Il dominio di riferimento può cambiare tra le visite. Ad esempio, un visitatore arriva al tuo sito tramite `google.com`, poi una settimana dopo, arriva al tuo sito attraverso `twitter.com`. Alla fine fanno un acquisto sul tuo sito. Se utilizzi il dominio di riferimento come dimensione con attribuzione ultimo contatto, `twitter.com` ottiene credito per l&#39;acquisto. Se utilizzi come dimensione il dominio di riferimento originale, `google.com` ottiene credito per l’acquisto indipendentemente dal modello di attribuzione.

Il dominio di riferimento originale non cambia mai per l&#39;intera durata di un determinato ID visitatore.
