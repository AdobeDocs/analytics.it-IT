---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento in cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 1%

---

# Dominio di riferimento originale

Il &quot;dominio di riferimento originale&quot; [dimensione](overview.md) segnala il primo dominio di riferimento in cui un visitatore ha fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore. Questa dimensione è utile per capire quali siti di terze parti originariamente indirizzano il traffico verso il sito.

>[!IMPORTANT]
>
>Devi configurare i [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Popola questa dimensione con i dati

Questa dimensione richiede la configurazione sia nell’interfaccia di Analytics che nell’implementazione.

* All&#39;interno dell&#39;implementazione, questa dimensione recupera i dati da [`r` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati che non rientra in AppMeasurement (ad esempio tramite l’API), accertati di includere i `r` parametro della stringa di query nelle richieste di immagini.
* Nell’interfaccia di Analytics, devi configurare i [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

L’Adobe mantiene il dominio di riferimento originale per tutta la vita di un visitatore. Se un visitatore abbandona e fa clic su un collegamento in un dominio diverso in qualsiasi momento, il nuovo valore non viene registrato. Se desideri visualizzare nuovi valori, consulta [Dominio di riferimento](referring-domain.md).

## Elementi dimensionali

Gli elementi del Dimension includono i domini su cui i visitatori fanno clic per accedere al sito. Se un hit non ha dati di riferimento (impostati o persistenti), viene raggruppato sotto l’elemento dimensione `"None"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro.

## Confronta dominio di riferimento con dominio di riferimento originale

Il dominio di riferimento può cambiare tra le visite. Ad esempio, un visitatore arriva al tuo sito tramite `google.com`, quindi una settimana dopo, arriva al tuo sito tramite `twitter.com`. Alla fine effettuano un acquisto sul tuo sito. Se utilizzi Dominio di riferimento come dimensione con attribuzione ultimo contatto, `twitter.com` ottiene il merito per l’acquisto. Se utilizzi il dominio di riferimento Originale come dimensione, `google.com` ottiene il merito per l’acquisto indipendentemente dal modello di attribuzione.

Il dominio di riferimento originale non cambia mai per l’intera durata di un determinato ID visitatore.
